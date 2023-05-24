# Assignment - 3

## Sequence to Sequence model (transliteration)

In this assignment, I transliterated hindi words written in English script to Hindi script by implementing in both vanilla seq2seq transliteration and attention transliteration.
<br/>

### Libraries used:

1. torch: PyTorch
2. torch.nn: sub-module of PyTorch for building neural networks.
3. torch.optim: The sub-module of PyTorch for  optimization 
5.torch.autograd: A module in PyTorch for automatic differentiation.
5.torch.utils.data: A module in PyTorch for handling datasets and data loading utilities.
6. wandb:  used for experiment tracking and visualization.
7.random
<br/>
# Installations: 
1. pip package manager which i used to install libraries 
<br/>
# Dataset Used :
I downloaded hindi validation,test,train data and uploaded them to google drive and mounted the drive in my code and accessed by giving thier paths 

<br/>
# How to USE:
The entire project has been modularised using functions to make it as scalable as possible for future developments and extensions.

The main class for the model is `class Transliteration_EncoderDecoder(nn.Module):` is the function to train the model. The parameters for the constructor of this class are the following:
 cell_type='GRU', hidden_layer_size=32,num_encoder_layers=2, num_decoder_layers = 2, dropout=0.1, 
                 batch_size=32, n_batch,lr)

arg1 : cell_type  : To specify whether the RNN used is LSTM or GRU  <br/>
arg2 : hidden_layer_size  : Number of neurons in the hidden dense layer <br/>
arg3 : num_encoder_layers  : number of encoder layers used in model <br/>
arg4 : num_decoder_layers  : number of decoder layers used in model<br/>
arg5 : dropout  :  Dropout of the model <br/>
arg6 : batch_size  : Batch size used for training the model <br/>
arg7 : lr : learning rate used for training the model  <br/>
<br/>

## How to train the model? ##

train_batch(net, opt, criterion, batch_size, device = 'cpu', teacher_force = False):this method is used to train the model
```
This trains the model and logs the validation accuracy in wandb.this function is used for calculating the validation accuracy of the model
calc_accuracy(net_attn, device = 'cpu'):
train_setup(net=net, config=None, momentum=0.9, display_freq=5, device='cpu'):all the setups i used for training the model
<br/>
 
## How to inference the model? ##

Once the model is trained we call the method `infer(net_attn, eng_word,shape,device ='cpu'):` inference routine of sequence model.
```

<br/>
# Attention Mechanism #

Majority of the code remains the same in both vanilla seq2seq and attention models except for a few changes. In `forward method of transliteration class`, I added attention 

<br/>

