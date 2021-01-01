# Tensorflow2를 통한 단일 객체 이미지 분류 모델 정확도 개선하는 방법
*최근 업데이트: 01/01/2021*

<!-- using https://www.codecogs.com/latex/eqneditor.php -->
표 : 분류 모델 정확도 비교 분석 
| 비용 함수 | 함수 수식 | 최적화 모델 | 모델 수식 | 학습률 | 학습률 조절 | 에포크 | loss | 학습 시간 | 최종 정확도 |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| 평균 제곱 오차(MSE) | <a href="https://www.codecogs.com/eqnedit.php?latex=\frac{1}{n}\sum_{1}^{n}\left&space;(&space;y_{i}-t_{i}\right&space;)^2" target="_blank"><img src="https://latex.codecogs.com/svg.latex?\frac{1}{n}\sum_{1}^{n}\left&space;(&space;y_{i}-t_{i}\right&space;)^2" title="\frac{1}{n}\sum_{1}^{n}\left ( y_{i}-t_{i}\right )^2" /></a> | 경사하강법 | <a href="https://www.codecogs.com/eqnedit.php?latex=W:=W-\alpha&space;\frac{\partial}{\partial&space;W}cost(W)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?W:=W-\alpha&space;\frac{\partial}{\partial&space;W}cost(W)" title="W:=W-\alpha \frac{\partial}{\partial W}cost(W)" /></a> | 0.01 | 50회 마다, \*=0.96 |  |  |  | |
||
||
