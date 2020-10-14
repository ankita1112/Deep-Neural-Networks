  ## Classification of Images using Deep Neural Networks
  
  ### Dataset
  - The American Sign Language letter database of hand gestures represent a multi-class problem with 24 classes of letters 
   (excluding J and Z which require motion). The dataset format is patterned to match closely with the classic MNIST. 

  - Each training and test case represents a label (0-25) as a one-to-one map for each alphabetic letter A-Z 
   (and no cases for 9=J or 25=Z because of gesture motions).

  - The training data (27,455 cases) and test data (7172 cases) are approximately half the size of the standard MNIST but
   otherwise similar with a header row of label, pixel1,pixel2….pixel784 which represent a single 28x28 pixel image with 
   grayscale values between 0-255. 
   
### Implementation
- The following is the setting for the networks:
    - Batch size of 50
    - Maximum number of epochs of 100, but implement early stopping
    - Adam optimiser
    - ELU activation function for all hidden layers
    - He Uniform initialization for weights
    - Training/Validation/Testing set sizes are 2500/1000/1000 as described above (with the validation set derived from the original test dataset)
    - I will investigate both fully connected and CNN architectures.

-  Implemented fully connected and convolutional neural networks to classify images of hands in poses corresponding to letters 
  in American Sign Language with an accuracy of 92%

-  Optimised the architecture and parameters of the networks using individual parameter sweeps, grid search, dropout layers 
     and batch normalisation. Approach to optimisation:
    1. First i will explore the number of and size of hidden layers. I will see how my model performs for different layers. We know that MLP with just one hidden layer can theoretically model even the mostcomplex functions if it has enough neurons. Though for complex problems, deep networks have a much higher efficiency. My training and testing data sizes are 2500 and 1000 which is not too big, so 2 or three layers can give a good performance.
    2. Second i will explore the learning rate. The learning rate is one the most important hyperparameter. I will loop over the values 0.0001,0.001,0.01 and 0.1 to get a good performimg model. When plotting the loss as a function of the learning rate, it should drop at first but after sometime, the learning rate will become too large, so the loss will start to increase. Therefore using the Adam optimizer, the learning rate should lie around its default value.
Then i will use GridSearch to find the best epoch number for the model.I will use values between 20 to 100.Epoch value less than 20 may not be sufficient to train the network properly.Convolutional Neural Networks can be sensitive to the batch size. A disadvantage of using grid search is that it is very time consuming but it's result provide good parameters.
    3. Lastly i will explore the performance of the CNN network for different number of strides. A big stride in the pooling layer can lead to a high information loss.A stride of 2 or (2,2) is a fair choice
    
### Results
The best performance for my CNN model has an accuracy of 92.4% and loss of  0.29(with 3 hidden layers: 64,128,256 , number of epoch:80 ,strides:(2,2) & 2 & (2,2))

                precision    recall  f1-score   support

           A       0.96      1.00      0.98        44
           B       1.00      0.95      0.98        62
           C       0.97      0.97      0.97        40
           D       0.97      0.94      0.96        34
           E       0.95      1.00      0.97        71
           F       0.97      1.00      0.99        37
           G       0.85      0.83      0.84        54
           H       0.80      0.92      0.86        62
           I       0.78      0.91      0.84        43
           K       1.00      0.87      0.93        45
           L       0.77      1.00      0.87        23
           M       0.83      0.68      0.75        63
           N       0.71      0.75      0.73        32
           O       0.94      0.94      0.94        35
           P       1.00      1.00      1.00        58
           Q       0.94      0.94      0.94        18
           R       0.40      0.44      0.42        18
           S       0.76      0.87      0.81        30
           T       1.00      0.33      0.50        39
           U       0.61      0.66      0.63        29
           V       0.89      0.93      0.91        55
           W       0.74      0.88      0.81        26
           X       0.84      1.00      0.91        36
           Y       0.90      0.78      0.84        46
