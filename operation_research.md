## Reference
- 참고 GitHub: TeamLab/Gachon_CS50_OR_KMOOC 
- 참고 블로그: https://realpython.com/linear-programming-python/
  
## Introduction to Operations Research
- OR(Operation Research) : 최적화. 수학적 모델을 이용해 가장 적합한 값(최대, 최소)을 찾는 것
- MS: Management Science
- 모델: 수학적 모델 즉 공식에서 적합한 값 찾는 방정식
  - 최대값 최소값이 무엇인가? 방정식으로 풀기
  - 컴퓨터가 알아서 풀어줌
- 주요 개념
  - 목적함수와 제약조건
  - 의사결정변수
  - 제약조건
  - 매개변수 → 상수값
- 비교
  - 서로 영향을주지 않는 Static model vs dynamic
  - Linear 1차식 및 Non-linear
  - Integer model 닶이 실수인지 정수인지 vs float 인지
  - deterministic vs stochastic
- OR 테크닉/프로세스
  - 현실문제를 추상화 - 틀릴수 있음
  - 문제정의 -> 모형찾기 -> 해 찾기 -> 검증 -> 적용
- OR 역량: 분석능력, 모델링, 닶 찾기, 적용(컴)

## Linear Algebra
- 선형대수
  - 벡터 : 크게와 방향을 가지는 것
  - 행렬 : 한 개 이상의 벡터로 구성되며 행과 열을 가짐


## Linear Programming & LP Application #1
- 모델링 예시 및 프로세스
  - (1) Decision variable 정의: 만들 군인 인형, 만들 기차 인형
  - (2) Objective function: Profit 인형 만들때 얻는 profit 식
  - (3) Constrains: 마감 시간 최대 100시간, 목공 시간 최대 80시간, 군인 인형 최대 40개

- 가정
  - proportionality: decision variable은 비례적으로 증가
  - additivity: decision variable 은 서로에게 독립적 증가
  - divisibility: 값의 fraction을 허용하는가 안하는가
  - certainty: 계수나, RHS는 반드시 명확해야함
 
<img src="https://github.com/songhunhwa1/Bayesian-Optimization/blob/main/img/img17.png" width="500"/>

- isoprofit(maximize), isocost(minimize)
- binding: constraints의 값이 potimal value와 치환 가능할때 (=constraints1, 2의 교차점이 optimal일때)
- convex set: 어떠한 두 점을 연결했을때 feasible rigion 내에 있는 경우 (LP는 convex set 내에서만 작동)

## LP Application #2
- LP Application #2: 최적화 기법 적용 사례
  - Inventory problems: 주어진 demand에 대응하기 위한 연간 sailboat 생산량이 한정된 상황임. 인건비를 고려했을 때 분기당 얼마나 많은 생산을 해야할까?
  - Multiperiod Financial Models: 향후 3년간 투자전략 포트폴리오를 어떻게 구성해야 이익이 가장 높을까?

##  Simplex Algorithm
- Simplex Algorithm
  - Standard Form: 작다나 크다 대신 = 으로 바꾸고 slack 변수를 추가
  - Basic Variable & Non-Basic Variable
  - m < n 인 경우 해결이 가능
  - NBV: 우선 variable을 0으로 설정한 변수
  - BV: 0으로 설정하지 않은 나머지 변수
- Simplex Algorithm Process
  - Slack 변수 추가 → BV 로 설정, Slack 이외 변수를 NBV로 설정
  - 한 단위 증가할때 Z에 가장 큰 영향을 주는 변수를 entering varilable로 설정 (이 값의 최대치: Ratio Test)
  - entering variable 이 가장 작은 row(pivot row) 가 BV로 이동
  - Gauss Elinmination

## Network Model
- 변수간 관계를 Node, Arc 로 표현후 Matrix 로 변경해서 문제를 푸는 방식

<img src="https://github.com/songhunhwa1/Bayesian-Optimization/blob/main/img/img18.png" width="600"/>

- Assignment: Machine 에 어떤 job을 할당할지
- Transportation
- Transshipment: 수송, 경유지, 도착지에 대한 수송

## Genetic Algorithm

- 찰스 다윈의 진화론에서 영감을 받아 만들어짐. 즉, 앞선 세대의 유전자를 지속적으로 재생산 하면서 최적의 유전자가 남는 방식을 알고리즘으로 구현한 것
- 아래의 다섯가지 단계를 반복하여 최적의 individual을 찾아가는 과정
  - Initial population
  - Fitness function
  - Selection
  - Crossover
  - Mutation
