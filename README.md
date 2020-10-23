# IA-laboratories
Laboratorios evaluados de las semanas 5-6-7-8 del curso de Inteligencia Artificial del II Semestre del 2020 en el Instituto Tecnologico de Costa Rica 

# Lab 1 (Week 5)

1. Try  to  build  a  classifier  for  the  MNIST  dataset  that  achieves  over 97%  accuracy on  the  test  set.  Hint:  the  KNeighborsClassifier  works  quite well  for  this  task;you  just  need  to  find  good  hyperparameter  values  (try a  grid  search  on  the weights and n_neighbors hyperparameters).
 
2.Write a function that can shift an MNIST image in any direction (left, right, up,or down) by one pixel.5 Then, for each image in the training set, create four shif‐ted copies (one per direction) and add them to the training set. Finally, train your best model on this expanded training set and measure its accuracy on the test set.You should observe that your model performs even better now! This technique of artificially  growing  the  training  set  is  called data  augmentation  or  training  set expansion.
 
Solucion: https://colab.research.google.com/drive/1qdfWozldUK2Mdn68hDVX4IbWeE45OHf_?usp=sharing

# Lab 2 (Week 6)

**1.Which  Linear  Regression  training  algorithm  can  you  use  if  you  have  a  training set with millions of features?**
 
Puede usar “Descenso de gradiente estocástico” o “Descenso de gradiente de mini-lote”, en algunos casos también se recomienda “Descenso de gradiente por lotes” si el conjunto de datos de entrenamiento cabe en la memoria. Además, cabe destacar, que NO puede usar una ecuación normal porque la complejidad computacional crece muy rápido.
 
**3.Can  Gradient  Descent  get  stuck  in  a  local  minimum  when  training  a  Logistic Regression model?**
 
No se puede porque la función de costo es convexa, esto quiere decir que si se dibuja una línea recta entre dos puntos cualesquiera de la curva, la línea nunca cruza la curva.
 
**5.Suppose  you  use  Batch  Gradient  Descent  and  you  plot  the  validation  error  at every  epoch.  If  you  notice  that  the  validation  error  consistently  goes  up, what  is likely going on? How can you fix this?**
 
1. Significa que la tasa de aprendizaje es demasiado alta y el algoritmo diverge. 
 
2. Si el error de entrenamiento también aumenta, entonces, este es el problema y para solucionarlo se debe reducir la tasa de aprendizaje, pero si el error de entrenamiento no aumenta, es porque el conjunto de datos de entrenamiento está sobreajustado y en ese caso se debe detener por completo el entrenamiento para solucionarlo.
 
**7.Which  Gradient  Descent  algorithm  (among  those  we  discussed)  will  reach  the vicinity  of  the  optimal  solution  the  fastest?  Which  will  actually converge?  How Can you make the others converge as well?**
 
1. El “Estocástico”, porque considera solo una instancia de entrenamiento a la vez, por lo que generalmente es el primero en alcanzar la vecindad del óptimo global. 
 
2. Únicamente el “Descenso de gradiente por lotes” va a converger.
 
3. Ningún otro algoritmo puede llegar a converger normalmente, solo se acercan al mínimo global, al menos de que se reduzca gradualmente la tasa de aprendizaje 
 
**9.Suppose  you  are  using  Ridge  Regression  and  you  notice  that  the  training error and the validation error are almost equal and fairly high. Would you say that the model suffers from high bias or high variance? Should you increase the regularization hyperparameter α or reduce it?**
 
1. Si el error de entrenamiento y el error de validación son casi iguales y bastante altos, es probable que el modelo NO se ajuste al conjunto de entrenamiento, lo que significa que tiene un alto sesgo. 
 
2. Debería reducirlo. 

# Lab 3 (Week 7)

**Train  and  fine-tune  a  Decision  Tree  for  the  moons  dataset  by  following  these steps:**

a.Use make_moons(n_samples=10000, noise=0.4) to generate a moons dataset.

b.Use train_test_split() to split the dataset into a training set and a test set.

c.Use  grid  search  with  cross-validation  (with  the  help  of  the  GridSearchCVclass)  to  find  good  hyperparameter  values  for  a  DecisionTreeClassifier.Hint: try various values for max_leaf_nodes.

d.Train  it  on  the  full  training  set  using  these  hyperparameters,  and  measure your model’s performance on the test set. You should get roughly 85% to 87%accuracy.

Solucion: https://colab.research.google.com/drive/12-7Jvecku0U8nPUk1V47lcCzQOkyMyxp?usp=sharing

# Lab 4 (Week 8)

**1. The  TensorFlow  Playground  is  a  handy  neural  network  simulator  built  by  theTensorFlow team. In this exercise, you will train several binary classifiers in just a few  clicks,  and  tweak  the  model’s  architecture  and  its  hyperparameters  to  gain some  intuition  on  how  neural  networks  work  and  what  their  hyperparameters do. Take some time to explore the following:**

![inicio](<./images/inicio.png>) 

a. The patterns learned by a neural net. Try training the default neural network by clicking the Run button (top left). Notice how it quickly finds a good solu‐tion  for  the  classification  task.  The  neurons  in  the  first  hidden  layer  have learned  simple  patterns,  while  the  neurons  in  the  second  hidden  layer  have learned  to  combine  the  simple  patterns  of  the  first  hidden  layer  into  more complex patterns. In general, the more layers there are, the more complex the patterns can be.

![a](<./images/a.png>) 

b. Activation  functions.  Try  replacing  the  tanh  activation  function  with  a  ReLU activation function, and train the network again. Notice that it finds a solution even faster, but this time the boundaries are linear. This is due to the shape of the ReLU function.

![b](<./images/b.png>) 

c. The  risk  of  local  minima.  Modify  the  network  architecture  to  have  just  one hidden layer with three neurons. Train it multiple times (to reset the network weights, click the Reset button next to the Play button). Notice that the train‐ing time varies a lot, and sometimes it even gets stuck in a local minimum.

![c](<./images/c.png>)

![c2](<./images/c2.png>) 

d. What  happens  when  neural  nets  are  too  small.  Remove  one  neuron  to  keep just  two.  Notice  that  the  neural  network  is  now  incapable  of  finding  a  good solution,  even  if  you  try  multiple  times.  The  model  has  too  few  parameters and systematically underfits the training set.

![d](<./images/d.png>) 

e. What happens when neural nets are large enough. Set the number of neurons to eight, and train the network several times. Notice that it is now consistently fast and never gets stuck. This highlights an important finding in neural net‐work  theory:  large  neural  networks  almost  never  get  stuck  in  local  minima,and  even  when  they  do  these  local  optima  are  almost  as  good  as  the  global optimum. However, they can still get stuck on long plateaus for a long time.
 
![e](<./images/e.png>) 

f. The risk of vanishing gradients in deep networks. Select the spiral dataset (the bottom-right dataset under “DATA”), and change the network architecture to have  four  hidden  layers  with  eight  neurons  each.  Notice  that  training  takes much  longer  and  often  gets  stuck  on  plateaus  for  long  periods  of  time.  Also notice  that  the  neurons  in  the  highest  layers  (on  the  right)  tend  to  evolve faster than the neurons in the lowest layers (on the left). This problem, called the “vanishing gradients” problem, can be alleviated with better weight initial‐ization  and  other  techniques,  better  optimizers  (such  as  AdaGrad  or  Adam),or Batch Normalization (discussed in Chapter 11).

![f](<./images/f.png>) 

**5. Name three popular activation functions. Can you draw them?**
 
1. Hyperbolic tangent function: tanh
2. Sigmoid
3. The Rectified Linear Unit function: ReLU

![func](<./images/Activation functions.png>)

**7. How many neurons do you need in the output layer if you want to classify email into spam or ham? What activation function should you use in the output layer? If instead you want to tackle MNIST, how many neurons do you need in the out‐put layer, and which activation function should you use? What about for getting your network to predict housing prices, as in Chapter 2?**

1. Únicamente necesita 1 neurona en la capa de salida de una red neuronal, por ejemplo, la que establece la probabilidad de que el correo electrónico sea spam.
 
2. Podría utilizar la función de activación logística en la capa de salida.
 
3. Necesita 10 neuronas en la capa de salida y debe usar la función de activación “Softmax”, porque esta puede manejar múltiples clases, generando una probabilidad por clase.
 
4. Necesita una neurona de salida que no utilice ninguna función de activación.
