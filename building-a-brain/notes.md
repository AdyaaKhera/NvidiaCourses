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
- as the computer guesses more answers to the questions, it updates it slope and itercept to make the best fit of the data collected thus far
- neurons often receive multivariate data

### Architecture
- we will first build a neuron that takes a pixel value and assign weight to it. This weight would be equivalent to the slope of the linear regression function
- by assigning weights to every variable, we finally get the full equation containing the different variables as y = w0x0 + w1x1 + ... + b
- the total number of pixel = total number of independent variables = total number of weights required
- also, the output y would be a number be we are trying to categorize the images so we will make ten neurons, one for each output. The output for the correct corresponding neuron, would then be the highest value of y
- to check the expected structure of our model we can call the summary of the model by model.summary
- the summary helps us to check the output shape for each layer
- when we do multiply the image width with the imaeg height and the number of neurons + the ten neurons, we get the number of parameters as shown by the summary which is the total number of weights

### Initiate Training
- we need to give the model a function to grade its performance so it can get better
- this function is called a loss function
- in the example used we have a SparseCategoricalCrossentropy function which is specific to classifications
- *sparse* - refers to how our label is an integer index for the categories
- *categorical* - function for classification
- *cross-entropy* - the more confident the model is when it guesses incorrectly, the worse its score will be, e.g., being 100% wrong will make its score negative infinity
- *from_logits* - the linear output will be transformed into a probability which is the model's confidence towards classification
- this type of classification will work because this grades neurons simultaneously
- we can add additional metric to monitor how well the model is learning

### Evaluating the model
- the fit method will help our model learn and then it will evaluate it
- an *epoch* is one review of the training dataset - analogous to one reivsion made by the model
- after each epoch, the model is tested with validation data
- it keeps on improving after every epoch as the loss reduces and the accuracy increases significantly
- accuracies should be around 80%
- after training, we can use the predict method to see the output of our model on the testing dataset
- keras expects a batch to make a prediction
- raw results need formatting to be interpreted by humans
- the larger the value, the more confident the model is and the more negative it is, the more confident the model is that it is not the correct label
