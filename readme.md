# Cryptocurrency-predicting RNN Model
In this project, we will predict to buy the cryptocurrency or not after 3 minutes by analysing past 60 min cryptocurrencies price and volume using Recurrent Neural Network (RNN).
## Introduction
The [Dataset](https://drive.google.com/open?id=1YSFCm0QD0C2xOiOyUf7FnzPukZrFNo17)
of Bitcoin, Bitcoin Cash, Ethereum and Litecoin Cryptocurrencies is avalable in crypto_data folder which will be used for training the RNN Network and the networks highest accuracy checkpoints wil be stored in the model director.

### Network Architecture
```terminal
Layer (type)                 Output Shape              Param #
=================================================================
cu_dnnlstm (CuDNNLSTM)       (None, 60, 128)           70656
_________________________________________________________________
dropout (Dropout)            (None, 60, 128)           0
_________________________________________________________________
batch_normalization (BatchNo (None, 60, 128)           512
_________________________________________________________________
cu_dnnlstm_1 (CuDNNLSTM)     (None, 60, 128)           132096
_________________________________________________________________
dropout_1 (Dropout)          (None, 60, 128)           0
_________________________________________________________________
batch_normalization_1 (Batch (None, 60, 128)           512
_________________________________________________________________
cu_dnnlstm_2 (CuDNNLSTM)     (None, 128)               132096
_________________________________________________________________
dropout_2 (Dropout)          (None, 128)               0
_________________________________________________________________
batch_normalization_2 (Batch (None, 128)               512
_________________________________________________________________
dense (Dense)                (None, 32)                4128
_________________________________________________________________
dropout_3 (Dropout)          (None, 32)                0
_________________________________________________________________
dense_1 (Dense)              (None, 2)                 66
=================================================================
Total params: 340,578
Trainable params: 339,810
Non-trainable params: 768
```
CuDNNLSTM is LSTM layer with CUDA gpu support which makes it much more faster then normal LSTM layer

## Result
#### Train Accurecy after 20 epoch: 74.45%
#### Test Accurecy after 20 epoch: 54.32%

## Credits
Special thanks to Harrison Kinstey for [pythonprogramming.net](https://pythonprogramming.net/) lectures.