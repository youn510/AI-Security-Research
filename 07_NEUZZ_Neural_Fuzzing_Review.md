# [Review] NEUZZ: Efficient Fuzzing with Neural Program Smoothing

## 1. Basic Info (기본 정보)
- **Title:** NEUZZ: Efficient Fuzzing with Neural Program Smoothing
- **Source:** IEEE Symposium on Security and Privacy (S&P), 2019
- **Tags:** #System_Hacking #Fuzzing #Neural_Network #Zero_Day #AI_Security

## 2. One-Line Summary (한 줄 요약)
> **"기존 퍼저의 무작위 변이 방식이 가진 한계를 극복하기 위해, 타겟 프로그램의 조건문을 인공신경망으로 부드럽게 깎아내고 기울기 기반 수학적 최적화로 단번에 취약점을 터뜨리는 스마트 퍼징 기술."**

## 3. Key Concepts (핵심 개념)

### 3.1. The Limit of Evolutionary Fuzzers (기존 해킹의 한계)
* **문제점:** C/C++ 프로그램의 `if`나 `switch` 같은 조건문은 수학적으로 불연속적인 절벽과 같다.
* **AFL의 맹점:** 기존 진화형 퍼저는 지형을 파악하지 못하고 단순히 입력값을 무작위로 바꾸기만 하므로, 깊은 곳에 숨겨진 까다로운 버그를 도달하는 데 엄청난 시간을 낭비한다.

### 3.2. Neural Program Smoothing (신경망 스무딩)
* **해결책:** 인공신경망의 보편적 근사 능력을 활용해, 원래 프로그램의 거친 절벽 구조를 모방한 부드러운 대리 함수를 생성한다.
* **효과:** 불연속점이 사라져 수학적으로 미분이 가능한 상태로 탈바꿈한다.

### 3.3. Gradient-guided Optimization (기울기 기반 최적화)
* **작동 원리:** 부드러워진 가짜 타겟 모델 위에서 경사 하강법 등 AI의 강력한 최적화 무기를 사용한다.
* **해킹 적용:** 어느 방향으로 입력값을 조작해야 원하는 취약점을 수학적으로 계산해 내어, 단숨에 크래시를 유발하여 찾아낸다.

## 4. Incremental Learning (실시간 진화)
* **Bootstrapping:** 초기에는 기존 퍼저가 만든 쓰레기 입력값과 커버리지 데이터로 AI를 기초 훈련시킨다.
* **Catastrophic Forgetting 방지:** 공격 중 새로운 데이터가 들어올 때 옛날에 뚫었던 길을 잊어버리는 치명적 망각 현상을 막기 위해, 과거 데이터의 엑기스를 뽑아 새로운 데이터와 함께 점진적으로 훈련시킨다.

## 5. Key Results (성과)
* 최고 수준의 그레이박스 퍼저 10개를 압도하는 속도와 커버리지 달성.
* 기존 도구들이 찾지 못했던 실제 세상의 31개 제로데이 버그를 10개의 리눅스 프로그램(readelf, mupdf 등)에서 단 24시간 만에 발견.

## 6. My Insight (나의 생각 & 적용점)
* **새롭게 알게 된 점:** 불연속적인 C/C++의 로직을 수학적인 곡선으로 치환하여 AI에 학습시킨 후 AI를 활용하여 공격한다는 발상이 대단한 것 같다.
* **앞으로의 계획:** 나도 이러한 AI를 이용하여 보안을 막는 방법 혹은 공격하는 방법들을 찾아보고 싶다.

---
*Reference: D. She et al., "NEUZZ: Efficient Fuzzing with Neural Program Smoothing," 2019 IEEE Symposium on Security and Privacy (SP), 2019.*
