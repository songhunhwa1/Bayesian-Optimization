## 최적화 알고리즘 Overview
- 최적화에 대한 기본 개념의 이해 (우선 넓고 얇게)
- 참고: https://darkpgmr.tistory.com/149

## 최적화 목적
- 함수 f(x)의 값을 최소화하는 x* 값(=해)은 무엇인지를 찾는 것
```python
# 선형 최적화(linear optimization)
f(x1,x2,...,xm) = b + a1x1 + a2x2 + ... + amxm 

# 비선형 최적화(nonlinear optimization) 
f(x,y) = ysinx + x,   f(x,y) = x2 + y
# source: https://darkpgmr.tistory.com/149
```
- 최소화하려는 함수 f(x)를 목적함수(objective function), 비용함수(cost function), 손실함수(loss function)
<img src="https://github.com/songhunhwa1/Bayesian-Optimization/blob/main/img/img9.png" width="400"/>

```python
def f1(x):
    return (x - 2) ** 2 + 2
# Source: https://datascienceschool.net/intro.html
```
- 만약 제약조건이 있으면, constrained optimization 없으면 unconstrained optimization 문제
- 예시로 마크다운 최적화 프로젝트로 대입해보면,
- 변수(am): SKU, 시간대, 예측수요, 할인율 등 ..
- 파라메터 값(xm):  하루살이-A*1, 6시*1, 3000, 20 등 .. 
- 목적함수 to minimize: 폐기비용
- 타임프레임: Hourly

| sku | 시간대 | 예측수요 | 할인율 | 판매가격 | ... | min.폐기비용 |
| --- | --- | --- | --- | --- | --- | --- | 
| A01 | 9 | 10 | 5 | 2000 | | 100 |  
| A02 | 9 | 20 | 1 | 1500 | | 20 |  
| A03 | 9 | 14 | 4 | 300 | | 10 |  

## 최적화 원리
- 그리드 서치(Grid Search): 단순하지만 경우의 수가 너무 많고, 시도 횟수가 많음
- 수치적 최적화 (numerical optimization): 가능한 적은 횟수로 최적화 값을 찾는 방법
- 최대경사법(steepest gradient method)
- 이동 방향 및 이동량을 결정하는 파라메터가 가장 중요
<img src="https://github.com/songhunhwa1/Bayesian-Optimization/blob/main/img/img10.png" width="400"/>

- 뉴튼 방법(Newton method), Levenberg-Marquardt 등 다양하게 있으나, 결국 이동 방향 및 이동량을 결정하는 방식에 차이가 있을 뿐

## 기본 수학적 원리
<img src="https://github.com/songhunhwa1/Bayesian-Optimization/blob/main/img/img11.png" width="600"/>

## 1차 미분을 이용한 Gradient Descent
<img src="https://github.com/songhunhwa1/Bayesian-Optimization/blob/main/img/img12.png" width="600"/>

## 2차 미분을 이용한 최적화
<img src="https://github.com/songhunhwa1/Bayesian-Optimization/blob/main/img/img13.png" width="500"/>

- 2차 미분 방식의 문제점
    - f(x) = x3 - 2x + 1라 하고 x0 = 0인 경우, 변곡점(f''=0) 에서 불안정 (식이 정의가 안 되거나 발산해버리는 문제)
    - 1차 미분의 경우 나누기가 없으므로 이러한 문제점이 없음
    - 그리고 f(x) = x3 - 2x + 1의 예에서 x0 = -0.5인 경우, 극소점이 아니 극대점으로 수렴해버릴수도 있음
 
<img src="https://github.com/songhunhwa1/Bayesian-Optimization/blob/main/img/img14.png" width="700"/>

<img src="https://github.com/songhunhwa1/Bayesian-Optimization/blob/main/img/img15.png" width="600"/>

## 비선형 최소자승 문제
- 함수가 비선형인 경우
- f(x) = Σei(x)2   형태의 최소자승(least squares) 문제
- 가우스-뉴턴법(Gauss-Newton method)
- Levenberg-Marquardt 방법: https://darkpgmr.tistory.com/142

## 최종 정리
- https://wikidocs.net/17412 → 제대로 공부하고 싶다면
<img src="https://github.com/songhunhwa1/Bayesian-Optimization/blob/main/img/img16.png" width="800"/> 


