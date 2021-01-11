# How To Optimize Single Object Image Classification Model Accuracy using Tensorflow 2
*Last updated: 01/11/2021*

<!-- using https://www.codecogs.com/latex/eqneditor.php -->
Table : Comparative Analysis of Classification Accuracy 
| activation function | loss function | Optimizer | learning rate | learning rate dacay | epoch | total loss | learning time | final accuracy |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| Relu | MSE | Gradient descent | 0.01 | every 50, \*=0.96 | 100 | 0.001 | 2h | 98% |
||
||

Table : Procedure
| index | 1 | 2 | 3 |
|:---:|:---:|:---:|:---:|
| 1 | layer | normalization | activation function |
| 2 | normalization | activation function | convolution layer |


<br><hr><br>

Table : Loss Functin and Optimizer Equation
| activation function | activation equation | loss function | loss equation | Optimizer | Optimizer notation |
|:---:|:---:|:---:|:---:|:---:|:---:|
| Sigmoid |
| Relu | <img src="https://latex.codecogs.com/gif.latex?f(x)=max(0,x)" title="f(x)=max(0,x)" /> | MSE | <img src="https://latex.codecogs.com/svg.latex?\frac{1}{n}\sum_{1}^{n}\left&space;(&space;y_{i}-t_{i}\right&space;)^2" title="\frac{1}{n}\sum_{1}^{n}\left ( y_{i}-t_{i}\right )^2" /> | Gradient descent | <img src="https://latex.codecogs.com/gif.latex?W:=W-\alpha&space;\frac{\partial}{\partial&space;W}cost(W)" title="W:=W-\alpha \frac{\partial}{\partial W}cost(W)" /> |
| Leacky Relu | <img src="https://latex.codecogs.com/gif.latex?f(x)=max(\alpha&space;x,x)" title="f(x)=max(\alpha x,x)"/> |
| ELU |
| tanh |
| maxout |

<!--
Relu = https://www.codecogs.com/eqnedit.php?latex=f(x)=max(0,x)
MSE = https://www.codecogs.com/eqnedit.php?latex=\frac{1}{n}\sum_{1}^{n}\left&space;(&space;y_{i}-t_{i}\right&space;)^2
Gradient descent = https://www.codecogs.com/eqnedit.php?latex=W:=W-\alpha&space;\frac{\partial}{\partial&space;W}cost(W)
-->

<br>

Table : Weight Initialization
| Weight Initialization | notation | code |
|:---:|:---:|:---:|
| Random Normal | <img src="https://latex.codecogs.com/gif.latex?Mean=0,&space;Variance=1"/> | `tf.keras.initializers.RandomNormal()` |
| Xavier (=Glorot) | <img src="https://latex.codecogs.com/gif.latex?Mean=0,&space;Variance=&space;\frac{2}{Channel\_in&space;&plus;&space;Channel\_out}"/> | `tf.keras.glorot_uniform()` |
| He (for Relu) | <img src="https://latex.codecogs.com/gif.latex?Mean=0,&space;Variance=&space;\frac{4}{Channel\_in&space;&plus;&space;Channel\_out}"/> | `tf.keras.initializers.he_uniform()` |

<br>

Table : Regularization
| Regularization | notation | code |
|:---:|:---:|:---:|
| Dropout | Random Node Turn off | `tf.keras.layers.Dropout(rate)` (0.0<rate<1.0) |
| L1 Regularization |
| L2 Regularization |
| Early stoppoing |

<br>

Table : Internal Covariate Shift Solution
| Method | notation | code |
|:---:|:---:|:---:|
| Batch Normalization (Not use Dropout) | <img src="https://latex.codecogs.com/gif.latex?\bar{x}=\frac{x-\mu_B}{\sqrt{\sigma&space;_{B}^{2}&plus;&space;\epsilon&space;}},&space;\hat{x}=\gamma&space;\bar{x}&plus;\beta" title="\bar{x}=\frac{x-\mu_B}{\sqrt{\sigma _{B}^{2}+ \epsilon }}, \hat{x}=\gamma \bar{x}+\beta" /> | `tf.keras.layers.BatchNormalization()` | 
