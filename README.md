# CNN Microscopy Image Classification

The goal of this project was to classify microscopy images of 9 different cell lines which are regularly misidentified. For this purpose, a total of 9632 training samples were provided, each sample consisted of three different images that showed different parts of the same cell (nucleus, microtubules, endoplasmic reticulum).

These three different images per sample were combined into a single 3-channel image for training using custom PyTorch Dataset and Dataloader objects. Furthermore various data augmentation techniques were applied during training time (random cropping, rotation, horizontal and vertical flipping) for better generalization of the model.

Regarding the model architecture, I wanted to use a pretrained model which could also be trained locally, on my rather weak Nvidia GTX 1650 GPU with just 4GB of CUDA memory. Hence, I decided to use the smallest version (b0) of the pretrained Convolutional Neural Network EfficientNet for feature extraction and placed a fully connected head on top of it to classify the images.

On the test set of 6869 samples, the final model showed a balanced accuracy of 87%.
