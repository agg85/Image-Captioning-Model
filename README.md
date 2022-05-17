# Human Consensus-Oriented Image Captioning
***Proceedings of the Twenty-Ninth International Joint Conference on Artificial Intelligence (IJCAI-20)***

Authors - Ziwei Wang , Zi Huang and Yadan Luo
School of Information Technology and Electrical Engineering
The University of Queensland, Australia

## Brief Overview -
Image captioning aims to describe an image with a concise, accurate, and interesting sentence. In this project, an image captioning model is developed which explicitly identifies and tackles the annotation quality issues in image captioning, which allows the model to efficiently learn the higher quality annotations in priority.

[put image here]

## Prerequisities


## Dataset
We have implemented the model on the Flickr 8k dataset. It has 8,091 images that are each paired with five different captions which provide clear descriptions of the salient entities and events.

## Implementation

![image](https://user-images.githubusercontent.com/68149849/168824935-e26d87e8-df90-4c5c-8bf4-b82eec457bfd.png)

### Feature Extraction
We used Layer 4 (512 * 7 * 7) of the Resnet 18 model forfeature extraction from the images. ResNet-18 is a CNN that is 18 layers deep. We have loaded a pretrained version of the network trained on more than a million images from the ImageNet database.

### Caption Generation

#### LSTM

#### Transformer

### Loss function
In this work, we explicitly engage human consensus to measure the quality of ground truth captions in advance, and directly encourage the model to learn high quality captions with high priority. 

### Optimizer
The model is optimised using Adam with learning rate of 5e-4.


## Results

