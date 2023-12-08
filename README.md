# FAKE HANDWRITTEN SIGNATURE DETECTOR
This repo contains a google colab notebook that I used for a PoC to test a Neural Network able to compare two signature images and tell if the signature are of the same person.

## ARCHITECTURE
I used a Siamese NN to reach the goal.
This kind of architecture consist of two separate neural networks which create an embedding of the two images, the embeddings are then compared and evaluated, producing in output the probability of a signature to be fake. 

![Screenshot 2023-12-08 alle 18 56 14](https://github.com/poligenius/SiameseNN_HandwrittenRecognition/assets/48245313/b0ae256f-9970-4921-962d-f87af159421a)

## TRAINING DATA
We used as training and test data different images of handwritten signatures.
The dataset is structured as follows:

-- Train/Test Dataset

--- xxx  --> folder containing images of original signature of user number xxx

--- xxx_forg --> folder containing images of fake signature of user number xxx


To train the model I created pairs of images xxx - xxx_forg with label 1 (fake) and pairs of images xxx - xxx with label 0 (not fake)

## RESULTS
This was just a PoC for a client, the objective was only to show the client that a model like that could work fine and, up to now, it has not been brought to production yet. 
Anyway, at first try (with only 10 epochs and few pairs of images used for the training) we got an excellent **91%** of accuracy on the validation and test set. 
Of course this result could be optimized by performing fine tuning on the decision threshold and by increasing epochs and training dataset, or by modifying the model architecture.
