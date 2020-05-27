## Pets image classification  
The objective of this project is to create a image classification model which takes an image of a cat or a dog and predicts which of the 37 species do they belong to.
The dataset on which this model has been trained on is the [Oxford-IIIT pets dataset](https://www.robots.ox.ac.uk/~vgg/data/pets/)

### My approach  
I have used the ResNet34 architecture - a 34 layer deep Convolutional Neural Net pre-trained on 1 Million images of the ImageNet dataset to build this model.  
First, I used the learning rate finder method of the fastai library (which plots the learning rate vs the loss - which for this problem was chosen to be Negative Loss Likelihood) to find an optimal learning rate to train the last two layers of the model for the first two epochs.   The learner used a One-Cycle-Learning technique, which implements a special case of learning rate annealing where the learning rate is different for each mini-batch that is trained. The shape of the curve of learning-rate v/s the mini-batch trained is an 'inverted-U', where the maximum learning rate is chosen from the learning rate finder method.  
The model was then trained for another 4 epochs where all the layers were fine-tuned, though the learning rate for the initial layers was lower than that of the later layers  

### Performance  
The final model has a accuracy of 94.2%
