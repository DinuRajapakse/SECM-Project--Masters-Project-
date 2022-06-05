# SECM-Project--Masters-Project-

The objective of this project is to use machine learning to deconvolute topography and reactivity of catalytic substrates in Scanning Electrochemical Microscopy. Historically this has been done by solving partial differential equations which governs the science and theory behind the data acquired (One experiment provides one data point in the form a graph known as approach curve. See Figure 1 during Scanning Electrochemical Microscopy which is a microscopy technique that is used to study the structure-reactivity relationship of electrocatalysts. This project provides an alternative to solving the said partial differential equations.

![image](https://user-images.githubusercontent.com/55726382/172060837-777105f8-842f-44f7-b87c-5e45d81e3616.png)



Pandas, NumPy, Matplotlib and Sklearn-metrics were used to handle all data processing and visualization.} Two separate data sets were synthesized: one for the multilayer perceptrons (MLP) and the other for the convolutional neural network (CNN). The data for the MLP consisted of 2250 data points (approach curves). The data was synthesized using analytical expressions (Ideally one would want to use real experimental data to train the model. But carrying out one experiment to obtain one approach curve is very time consuming). See Figure 2

![image](https://user-images.githubusercontent.com/55726382/172060889-78a0a45a-cac7-4737-aa5d-27a885de9fe0.png)

Two MLP models were built: MLP-C and MLP-S model. Each curve was designed to have 150 points. The MLP-C model used y-axis values at each point of the curve as features. The MLP-S model used slope values between two consecutive points as features. Figure 3 shows what the data looks like going into the model. 

![image](https://user-images.githubusercontent.com/55726382/172060931-aa65ed4d-2c4d-4722-84b6-d253d0effa04.png)


