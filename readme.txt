Recurrent neural network

Requirements:

python: 3.6
Backend: Tensorflow latest version
Keras: latest version
a python interpreter/ editor/debuger

Original code:

github, \url{https://github.com/keras-team/keras/blob/master/examples/lstm_text_generation.py}. 

Included files: training and predicting model python files(.py), training text examples (.txt), weights (.hdf5) for predicting obtained with different ammounts of text data.

The chosen model was the simplest one, a recurrent neural network consisting of 1 LSTM layer as input layer consisting of 128 cells that match the input data fed into the network. 
This is followed by a dense layer and a final activation layer that uses softmax activation function to compute the probability of the next character predicted by the network. Number of epochs can be specified in the model fit function.

The training file will train the model on the text file assigned in the "filename" variable. The text file must be located in the same directory as the python file.
A function to reduce the Learning rate of the optimizer was added to the original code (ReduceLROnPlateau). if after an epoch there is not an improvement over the loss of the model added this function will multiply the current learning rate with the factor specified inside the function.
Furthermore a checkpoint was added to the code to after each epoch save the current weights of the model to an external file, so they can be loaded either for prediction or to resume training if the process has to be interrupted.

The training file will output the current state of the loss, and after each epoch, a prediction made by the model with the current configuration for 0.2 0.5 1.0 and 1.0 levels of "originality" given a random input from the training text file.

The predict file will predict text given the text stated in the variable "sentence", the text must be lowercase whatever values is in the variable "maxlen" characters long. A prediction will be made by the model with the loaded weights for 0.2 0.5 1.0 and 1.0 levels of "originality" given the input.

