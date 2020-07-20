  #The American Sign Language letter database of hand gestures represent a multi-class problem with 24 classes of letters 
   (excluding J and Z which require motion).

  #The dataset format is patterned to match closely with the classic MNIST. 

  #Each training and test case represents a label (0-25) as a one-to-one map for each alphabetic letter A-Z 
   (and no cases for 9=J or 25=Z because of gesture motions).

  #The training data (27,455 cases) and test data (7172 cases) are approximately half the size of the standard MNIST but
   otherwise similar with a header row of label, pixel1,pixel2….pixel784 which represent a single 28x28 pixel image with 
   grayscale values between 0-255. 
   
Below are the list of works that have been as a part fo this project: 

  1. Implemented two types of deep learning networks, fully connected and convolutional neural networks to classify images of 
     hands in poses corresponding to letters in American Sign Language and plot learning curves.

  2. Optimised the architecture and parameters of the networks using individual parameter sweeps, grid search, dropout layers 
     and batch normalisation.
