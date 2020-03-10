# Sentimental-analysis

With the increasing numbers of online stores, a lot of customers rely on reviews from other users when they are purchasing 
products online. Therefore, an automatic sentiment classification system can be very useful for online 
companies to analyse the satisfaction level for different products as well as aiding customers in their use of online services.


In this project, I adopted a convolution neural networks with long short-term memory model to analyse the satisfaction level 
(from 1 the least satisfied to 5 the most satisfied) from online product reviews.

Convolution neural networks is a deep machine learning method that allow information flow through the model. It can withdraw 
features from text and at the same time examine the relation in between. It helps to increase the accuracy in sentimental
analysis. For long short-term memory, a memory cell is made up off four components: an input gate, a self-recurrent connection
neuron, forget gate and output gate. This cell can remain the same from one timestep to the other. Each gate has different 
functionality, where input gate allow incoming signal to alter memory cell or block it; output gate allow memory cell to 
influence other neurons or prevent it and, the forget gate adjust memory cell’s self-recurrent connecting, which means 
letting it memorise or forget previous session.


![screenshot](/LSTM.png?raw=true "Optional Title")

For this model, I implemented Keras neural network sequential model which is a model that has a linear stack of layers. For 
the first layer, it needs to receive information about the input shape, therefore, I adopted an embedding layer as the 
first layer with a layer size of 32, vocabulary size 122427 and an input length of 12. The reason of using an embedding layer 
is that it will turn positive indexes into dense vector of fixed size, also, it will input a 2D tensor and output a 3D tensor. 
Then for the next layer I implemented Convolutional Neural Networks, and it will take the output from the previous layer to 
process and classify it to different categories. It has a filters size of 32 and kernel size of 3. Then a max pooling layer 
of 1D will be used as the third layer for the temporal data, with a pool size of 2. Then a time-series model- Long Short-Term 
Memory will be applied for the following layer which is defined by hidden state dims and number of layers, which will be 100. Lastly, a fully connected layer- Dense, following the LSTM layer will be used to output the prediction. 

This model has an accuracy of 0.4367.
