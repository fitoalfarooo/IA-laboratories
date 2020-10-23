# IA-laboratories
Laboratories evaluated from weeks 5-6-7-8 of the Artificial Intelligence course of the II Semester of 2020 at the Technological Institute of Costa Rica 

# Lab 1 (Week 5)

1. Try  to  build  a  classifier  for  the  MNIST  dataset  that  achieves  over 97%  accuracy on  the  test  set.  Hint:  the  KNeighborsClassifier  works  quite well  for  this  task;you  just  need  to  find  good  hyperparameter  values  (try a  grid  search  on  the weights and n_neighbors hyperparameters).
 
2.Write a function that can shift an MNIST image in any direction (left, right, up,or down) by one pixel.5 Then, for each image in the training set, create four shif‐ted copies (one per direction) and add them to the training set. Finally, train your best model on this expanded training set and measure its accuracy on the test set.You should observe that your model performs even better now! This technique of artificially  growing  the  training  set  is  called data  augmentation  or  training  set expansion.
 
Solucion: https://colab.research.google.com/drive/1qdfWozldUK2Mdn68hDVX4IbWeE45OHf_?usp=sharing

# Lab 2 (Week 6)

**1.Which  Linear  Regression  training  algorithm  can  you  use  if  you  have  a  training set with millions of features?**
 
You can use “Stochastic gradient descent” or “Mini-batch gradient descent”, in some cases “Batch gradient descent” is also recommended if the training dataset fits in memory. Also, it should be noted, that you can NOT use a normal equation because computational complexity grows very fast.
 
**3.Can  Gradient  Descent  get  stuck  in  a  local  minimum  when  training  a  Logistic Regression model?**
 
It cannot be done because the cost function is convex, this means that if a straight line is drawn between any two points on the curve, the line never crosses the curve.
 
**5.Suppose  you  use  Batch  Gradient  Descent  and  you  plot  the  validation  error  at every  epoch.  If  you  notice  that  the  validation  error  consistently  goes  up, what  is likely going on? How can you fix this?**
 
1. It means that the learning rate is too high and the algorithm diverges.
 
2. If the training error also increases, then this is the problem and to solve it the learning rate must be reduced, but if the training error does not increase, it is because the training data set is over-adjusted and in that case training must be stopped completely to fix it.
 
**7.Which  Gradient  Descent  algorithm  (among  those  we  discussed)  will  reach  the vicinity  of  the  optimal  solution  the  fastest?  Which  will  actually converge?  How Can you make the others converge as well?**
 
1. The “Stochastic”, because it considers only one instance of training at a time, so it is generally the first to reach the neighborhood of the global optimum.
 
2. Only “Batch Gradient Descent” will converge.
 
3. No other algorithm can converge normally, they only approach the global minimum, unless the learning rate is gradually reduced
 
**9.Suppose  you  are  using  Ridge  Regression  and  you  notice  that  the  training error and the validation error are almost equal and fairly high. Would you say that the model suffers from high bias or high variance? Should you increase the regularization hyperparameter α or reduce it?**
 
1. If the training error and the validation error are almost equal and quite high, it is likely that the model does NOT fit the training set, which means that it has a high bias.
 
2. You should reduce it. 

# Lab 3 (Week 7)

**Train  and  fine-tune  a  Decision  Tree  for  the  moons  dataset  by  following  these steps:**

a.Use make_moons(n_samples=10000, noise=0.4) to generate a moons dataset.

b.Use train_test_split() to split the dataset into a training set and a test set.

c.Use  grid  search  with  cross-validation  (with  the  help  of  the  GridSearchCVclass)  to  find  good  hyperparameter  values  for  a  DecisionTreeClassifier.Hint: try various values for max_leaf_nodes.

d.Train  it  on  the  full  training  set  using  these  hyperparameters,  and  measure your model’s performance on the test set. You should get roughly 85% to 87%accuracy.

Solucion: https://colab.research.google.com/drive/12-7Jvecku0U8nPUk1V47lcCzQOkyMyxp?usp=sharing

# Lab 4 (Week 8)

**1. The  TensorFlow  Playground  is  a  handy  neural  network  simulator  built  by  theTensorFlow team. In this exercise, you will train several binary classifiers in just a few  clicks,  and  tweak  the  model’s  architecture  and  its  hyperparameters  to  gain some  intuition  on  how  neural  networks  work  and  what  their  hyperparameters do. Take some time to explore the following:**

![inicio](<./images/Inicio.PNG>) 

a. The patterns learned by a neural net. Try training the default neural network by clicking the Run button (top left). Notice how it quickly finds a good solu‐tion  for  the  classification  task.  The  neurons  in  the  first  hidden  layer  have learned  simple  patterns,  while  the  neurons  in  the  second  hidden  layer  have learned  to  combine  the  simple  patterns  of  the  first  hidden  layer  into  more complex patterns. In general, the more layers there are, the more complex the patterns can be.

![a](<./images/a.PNG>) 

b. Activation  functions.  Try  replacing  the  tanh  activation  function  with  a  ReLU activation function, and train the network again. Notice that it finds a solution even faster, but this time the boundaries are linear. This is due to the shape of the ReLU function.

![b](<./images/b.PNG>) 

c. The  risk  of  local  minima.  Modify  the  network  architecture  to  have  just  one hidden layer with three neurons. Train it multiple times (to reset the network weights, click the Reset button next to the Play button). Notice that the train‐ing time varies a lot, and sometimes it even gets stuck in a local minimum.

![c](<./images/c.PNG>)

![c2](<./images/c2.PNG>) 

d. What  happens  when  neural  nets  are  too  small.  Remove  one  neuron  to  keep just  two.  Notice  that  the  neural  network  is  now  incapable  of  finding  a  good solution,  even  if  you  try  multiple  times.  The  model  has  too  few  parameters and systematically underfits the training set.

![d](<./images/d.PNG>) 

e. What happens when neural nets are large enough. Set the number of neurons to eight, and train the network several times. Notice that it is now consistently fast and never gets stuck. This highlights an important finding in neural net‐work  theory:  large  neural  networks  almost  never  get  stuck  in  local  minima,and  even  when  they  do  these  local  optima  are  almost  as  good  as  the  global optimum. However, they can still get stuck on long plateaus for a long time.
 
![e](<./images/e.PNG>) 

f. The risk of vanishing gradients in deep networks. Select the spiral dataset (the bottom-right dataset under “DATA”), and change the network architecture to have  four  hidden  layers  with  eight  neurons  each.  Notice  that  training  takes much  longer  and  often  gets  stuck  on  plateaus  for  long  periods  of  time.  Also notice  that  the  neurons  in  the  highest  layers  (on  the  right)  tend  to  evolve faster than the neurons in the lowest layers (on the left). This problem, called the “vanishing gradients” problem, can be alleviated with better weight initial‐ization  and  other  techniques,  better  optimizers  (such  as  AdaGrad  or  Adam),or Batch Normalization (discussed in Chapter 11).

![f](<./images/f.PNG>) 

**5. Name three popular activation functions. Can you draw them?**
 
1. Hyperbolic tangent function: tanh
2. Sigmoid
3. The Rectified Linear Unit function: ReLU

![func](<./images/Activation functions.png>)

**7. How many neurons do you need in the output layer if you want to classify email into spam or ham? What activation function should you use in the output layer? If instead you want to tackle MNIST, how many neurons do you need in the out‐put layer, and which activation function should you use? What about for getting your network to predict housing prices, as in Chapter 2?**

1. You only need 1 neuron in the output layer of a neural network, for example, the one that sets the probability that email is spam.
 
2. You could use the logistic activation function in the output layer.
 
3. You need 10 neurons in the output layer and you must use the “Softmax” activation function, because it can handle multiple classes, generating one probability per class.
 
4. You need an output neuron that does not use a trigger function.

**10. Train  a  deep  MLP  on  the  MNIST  dataset  (you  can  load  it  using  keras.datasets.mnist.load_data().  See  if  you  can  get  over  98%  precision.  Try  searchingfor the optimal learning rate by using the approach presented in this chapter (i.e.,by  growing  the  learning  rate  exponentially,  plotting  the  loss,  and  finding  thepoint  where  the  loss  shoots  up).  Try  adding  all  the  bells  and  whistles—savecheckpoints, use early stopping, and plot learning curves using TensorBoard.**

Solution:
