# SECM-Project--Masters-Project-

##Introduction

The objective of this project is to use machine learning to deconvolute topography and reactivity of catalytic substrates in Scanning Electrochemical Microscopy. Historically this has been done by solving partial differential equations which governs the science and theory behind the data acquired (One experiment provides one data point in the form a graph known as approach curve. See Figure 1 during Scanning Electrochemical Microscopy which is a microscopy technique that is used to study the structure-reactivity relationship of electrocatalysts. This project provides an alternative to solving the said partial differential equations.

![image](https://user-images.githubusercontent.com/55726382/172060837-777105f8-842f-44f7-b87c-5e45d81e3616.png)



Pandas, NumPy, Matplotlib and Sklearn-metrics were used to handle all data processing and visualization.} Two separate data sets were synthesized: one for the multilayer perceptrons (MLP) and the other for the convolutional neural network (CNN). The data for the MLP consisted of 2250 data points (approach curves). The data was synthesized using analytical expressions (Ideally one would want to use real experimental data to train the model. But carrying out one experiment to obtain one approach curve is very time consuming). See Figure 2.

![image](https://user-images.githubusercontent.com/55726382/172060889-78a0a45a-cac7-4737-aa5d-27a885de9fe0.png)

Two MLP models were built: MLP-C and MLP-S model. Each curve was designed to have 150 points. The MLP-C model used y-axis values at each point of the curve as features. The MLP-S model used slope values between two consecutive points as features. Figure 3 shows what the data looks like going into the model. 

![image](https://user-images.githubusercontent.com/55726382/172060931-aa65ed4d-2c4d-4722-84b6-d253d0effa04.png)

The data for the CNN consisted of 3800 images of approach curves (See Figure 4). These images were 100 pixel by 100 pixel gray-scale images that did not include the $x$ and $y$ axes or axis labels.

![image](https://user-images.githubusercontent.com/55726382/172060986-664066c5-ef34-44fd-a644-481829ecb966.png)

All machine learning algorithms were programmed in Python using Jupyter Notebooks. Keras library, a wrapper for the Tensorflow, was used as the machine learning library to implement the said algorithms. All source code for this study can be found in the Appendix.
Two MLP models were built; MLP-C and MLP-S. Both models only used ReLu activation function in all hidden layers. MLP-S consisted of 3 hidden layers each of which consisted of 10 nodes. MLP-S  consisted of 4 hidden layer where the first three layers consisted of 10 nodes each and the layer consisted of 5 nodes. The MLP models were used to approach the problem as a regression model and were trained over 1000 epochs.

The CNN model consisted of 2 feature extractors each of which consisted of a convolutional layer followed by a max pooling layer. The dimension of all max pooling layers was 2x2. The first convolutional layer used a 10x10 kernel to output a 32x32 lower-level feature map. The second convolutional layer used a 5x5 kernel which outputs a 10x10 higher-level feature map. Both feature extractors use ReLu as the activation function all through out and a dropout of 0.25.The first and only hidden layer of the MLP attached to the second extractor consisted of 256 nodes and uses the ReLu activation function as well. The final output layer of the said MLP consisted of 10 nodes to represent the 10 classes and it uses the softmax activation function.

Both datasets were split into training and testing sets, with and 80:20 split. Mean squared error and mean absolute error were used to determine the quality of the regression MLP model. Accuracy, precision, recall and f1 score were used to evaluate the multi-class classification CNN model.

Training results of all three models are shown in Figure 5. 

![image](https://user-images.githubusercontent.com/55726382/172061046-452592c1-4552-4eb5-9548-1d5eaa11fbc4.png)

All models were then tested 4 real world experimental approach curve data as well. The results are shown below in Figure 6.

![image](https://user-images.githubusercontent.com/55726382/172061085-f555033c-02f1-4d15-89a3-87e257271ff2.png)

During the experimental phase of this project I tried creating small data sets and tested on different models using Scikit-learn to get a general idea of how the model is responding to the data. Here I have experimented with using both x and y axis at each point of the approach curves as feature instead of using y-axis values alone or the slope values of the curves. The code can be found in https://github.com/DinuRajapakse/SECM-Project--Masters-Project-/blob/main/ML%20Code/Supporting%20code%20info.ipynb.

It was concluded that MLP models performed very well on ideal data (tested well on the test set but relatively poorly on ideal-data (real experimental data). CNN performed well on non-ideal data (tested well on the real experimental data as well).
