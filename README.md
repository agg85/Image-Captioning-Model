# Human Consensus-Oriented Image Captioning
***Proceedings of the Twenty-Ninth International Joint Conference on Artificial Intelligence (IJCAI-20)***

Authors - Ziwei Wang , Zi Huang and Yadan Luo
School of Information Technology and Electrical Engineering
The University of Queensland, Australia

## Brief Overview -
Image captioning aims to describe an image with a concise, accurate, and interesting sentence. In this project, an image captioning model is developed which explicitly identifies and tackles the annotation quality issues in image captioning, which allows the model to efficiently learn the higher quality annotations in priority.

The next sections provide a brief outline of the structure we have followed
## Prerequisities
Mentioned in requirements.txt file

## Dataset
We have implemented the model on the Flickr 8k dataset. It has 8,091 images that are each paired with five different captions which provide clear descriptions of the salient entities and events.

## Implementation

![image](https://user-images.githubusercontent.com/68149849/168824935-e26d87e8-df90-4c5c-8bf4-b82eec457bfd.png)

### Feature Extraction
Each image is converted into a feature vector by using convolutional neural network. We used the pretrained version of ResNet-18, which is a standadrd CNN model available in PyTorch. The pretrained version of the network is trained on more than a million images from the ImageNet database. The pretrained network can classify images into 1000 object categories, such as keyboard, mouse, pencil, and many animals. From this, we extracted the output of layer 4 (512 * 7 * 7) to obtain the feature vector of the images.

### Word Embedding

#### LSTM
The Word Embedding layer of Pytorch was used, followed by a many-to-many LSTM layer that would help analyse the input sequence of words and give a 256-nodes layer output.

#### Transformer
The BERT model is used to understand the context of words as per all the surroundings of the word. A sequence of tokens in the form of integer IDs is passed to the BERT model to obtain the Word Embedding.
We have used the pretrained base-uncased BERT model.

### Caption Generation

### Loss function
In this work, we explicitly engage human consensus to measure the quality of ground truth captions in advance, and directly encourage the model to learn high quality captions with high priority. 
The standard cross-entropy (CE) loss measures the classification model performance based on the probability outputs from the model. The consensus loss was supposed to adjust the sentence-level loss, but we implemented consensus loss for a word predicted from a prefix of a sentence. This increases the loss of high quality captions, but reduces the loss of the low quality ones, by multiplying the calculated cross entropy loss with the cider score of the caption.

### Optimizer
The model is optimised using Adam with learning rate of 5e-4.

## Results

