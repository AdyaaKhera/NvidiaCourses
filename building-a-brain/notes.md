# Building a Brain

## TensorFlow
- Recent versions of TensorFlow automatically detect if there is a GPU available for computation.
- GPUs were originally designed for the significant amount of matrix mathematics used when rendering computer graphics.
- Since Neural Networks also require a significant amount of matrix multiplications, GPUs are a good fit for building them.

## Neural Networks
- try to copy the human learning technique of trial and error
- split the data into train and test

## Procedure 
- we are using keras to load the dataset
- for training we have images and their respective labels, which means for every data_idx, we have a valid_label[data_idx] corresponding to the valid_images[data_idx]
- sequential API will allow us to stack layers
- in this model we will have two layers: flatten and dense
- flatten layer will convert multidimensional data into 1 dimensional data
- dense will create a row of neurons with each neuron having a weight corresponding to each input

### Building a Neuron
- neuron - fundamental building blocks of neural networks
- result in a numerical output with a given numerical input
- we first define the architecture, intiate the training and then evaluate the model
- biological neurons transmit information similar to a morse code like structure
- some of the first neurons attempted to mimic the biological ones were expressed by linear regression functions using y = mx + b
- x is like the informationa and y is the output through the temrinals
- as the computer guesses more answers tot he questions, it updates it slope and itercept to make the best fit of the data collected thus far
- neurons often receive multivariate data
- we will first build a neuron that takes a pixel value and assign weight to it. This weight would be equivalent to the slope of the linear regression function
- by assigning weights to every variable, we finally get the full equation containing the different variables as y = w0x0 + w1x1 + ... + b
- the total number of pixel = total number of independent variables = total number of weights required
- also, the output y would be a number be we are trying to categorize the images so we will make ten neurons, one for each output. The output for the correct corresponding neuron, would then be the highest value of y
- 
