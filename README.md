# IA-laboratories
Laboratorios evaluados de las semanas 5-6-7-8 del curso de Inteligencia Artificial del II Semestre del 2020 en el Instituto Tecnologico de Costa Rica 

# Lab 1 (Week 5)

1. Try  to  build  a  classifier  for  the  MNIST  dataset  that  achieves  over 97%  accuracy on  the  test  set.  Hint:  the  KNeighborsClassifier  works  quite well  for  this  task;you  just  need  to  find  good  hyperparameter  values  (try a  grid  search  on  the weights and n_neighbors hyperparameters).
 
2.Write a function that can shift an MNIST image in any direction (left, right, up,or down) by one pixel.5 Then, for each image in the training set, create four shif‐ted copies (one per direction) and add them to the training set. Finally, train your best model on this expanded training set and measure its accuracy on the test set.You should observe that your model performs even better now! This technique of artificially  growing  the  training  set  is  called data  augmentation  or  training  set expansion.
 
Solucion: https://colab.research.google.com/drive/1qdfWozldUK2Mdn68hDVX4IbWeE45OHf_?usp=sharing

# Lab 2 (Week 6)

**1.Which  Linear  Regression  training  algorithm  can  you  use  if  you  have  a  training set with millions of features?**
 
Puede usar “Descenso de gradiente estocástico” o “Descenso de gradiente de mini-lote”, en algunos casos también se recomienda “Descenso de gradiente por lotes” si el conjunto de datos de entrenamiento cabe en la memoria. Además, cabe destacar, que NO puede usar una ecuación normal porque la complejidad computacional crece muy rápido.
 
# 3.Can  Gradient  Descent  get  stuck  in  a  local  minimum  when  training  a  Logistic Regression model?
 
No se puede porque la función de costo es convexa, esto quiere decir que si se dibuja una línea recta entre dos puntos cualesquiera de la curva, la línea nunca cruza la curva.
 
# 5.Suppose  you  use  Batch  Gradient  Descent  and  you  plot  the  validation  error  at every  epoch.  If  you  notice  that  the  validation  error  consistently  goes  up, what  is likely going on? How can you fix this?
 
Significa que la tasa de aprendizaje es demasiado alta y el algoritmo diverge. 
 
Si el error de entrenamiento también aumenta, entonces, este es el problema y para solucionarlo se debe reducir la tasa de aprendizaje, pero si el error de entrenamiento no aumenta, es porque el conjunto de datos de entrenamiento está sobreajustado y en ese caso se debe detener por completo el entrenamiento para solucionarlo.
 
# 7.Which  Gradient  Descent  algorithm  (among  those  we  discussed)  will  reach  the vicinity  of  the  optimal  solution  the  fastest?  Which  will  actually converge?  How Can you make the others converge as well?
 
El “Estocástico”, porque considera solo una instancia de entrenamiento a la vez, por lo que generalmente es el primero en alcanzar la vecindad del óptimo global. 
 
Únicamente el “Descenso de gradiente por lotes” va a converger.
 
Ningún otro algoritmo puede llegar a converger normalmente, solo se acercan al mínimo global, al menos de que se reduzca gradualmente la tasa de aprendizaje 
 
# 9.Suppose  you  are  using  Ridge  Regression  and  you  notice  that  the  training error and the validation error are almost equal and fairly high. Would you say that the model suffers from high bias or high variance? Should you increase the regularization hyperparameter α or reduce it?
 
Si el error de entrenamiento y el error de validación son casi iguales y bastante altos, es probable que el modelo NO se ajuste al conjunto de entrenamiento, lo que significa que tiene un alto sesgo. 
 
Debería reducirlo. 

# Lab 3 (Week 7)

![Guía Parte 1](<./assets/1.png>) 
# Lab 4 (Week 8)
