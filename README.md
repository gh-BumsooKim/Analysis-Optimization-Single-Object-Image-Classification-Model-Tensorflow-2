# How To Optimize Single Object Image Classification Model Accuracy using Tensorflow 2
*Last updated: 12/31/2020*

<!-- using https://www.codecogs.com/latex/eqneditor.php -->
Table : Comparative Analysis of Classification Accuracy 
| loss function | loss equation | Optimizer | Optimizer notation | learning rate | learning rate dacay | epoch | total loss | learning time | final accuracy |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| mean square error(MSE) | <a href="https://www.codecogs.com/eqnedit.php?latex=\frac{1}{n}\sum_{1}^{n}\left&space;(&space;y_{i}-t_{i}\right&space;)^2" target="_blank"><img src="https://latex.codecogs.com/svg.latex?\frac{1}{n}\sum_{1}^{n}\left&space;(&space;y_{i}-t_{i}\right&space;)^2" title="\frac{1}{n}\sum_{1}^{n}\left ( y_{i}-t_{i}\right )^2" /></a> | Gradient descent | <a href="https://www.codecogs.com/eqnedit.php?latex=W:=W-\alpha&space;\frac{\partial}{\partial&space;W}cost(W)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?W:=W-\alpha&space;\frac{\partial}{\partial&space;W}cost(W)" title="W:=W-\alpha \frac{\partial}{\partial W}cost(W)" /></a> | 0.01 | every 50, 0.96 |  |  |  | |
||
||
