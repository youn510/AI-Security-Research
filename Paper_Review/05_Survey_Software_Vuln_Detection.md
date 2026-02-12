# [Review] Software Vulnerability Detection Using Deep Neural Networks: A Survey

## 1. Basic Info (기본 정보)
- **Title:** Software Vulnerability Detection Using Deep Neural Networks: A Survey
- **Source:** IEEE (Proceedings of the IEEE / Access 등 확인 필요)
- **Year:** 2020
- **Tags:** #Vulnerability_Detection #Buffer_Overflow #Deep_Learning #Survey #AST #CFG #PDG

## 2. One-Line Summary (한 줄 요약)
> **"소스 코드의 보안 취약점(Buffer Overflow 등)을 탐지하기 위해 사용되는 딥러닝 기법들과, 코드를 AI에게 이해시키는 4가지 표현 방식(Feature Representation)을 체계적으로 정리한 논문."**

## 3. Key Concepts (핵심 개념)

### 3.1. The Semantic Gap (의미론적 격차)
* 사람이 코드를 이해하는 방식(의미)과 기계가 코드를 읽는 방식(문법) 사이의 차이.
* 딥러닝은 이 격차를 줄여서, 단순한 키워드 매칭이 아니라 코드의 맥락(Context)을 파악하는 것을 목표로 함.

### 3.2. 4 Types of Feature Representations (코드 표현 방식)
1.  **Graph-based (그래프 기반):**
    * **AST (추상 구문 트리):** 코드의 문법 구조.
    * **CFG (제어 흐름 그래프):** 실행 경로.
    * **PDG (프로그램 의존 그래프):** 데이터의 흐름 추적 (버퍼 오버플로우 탐지에 필수).
2.  **Sequence-based (시퀀스 기반):** 함수 호출 순서나 실행 로그(Trace) 활용.
3.  **Text-based (텍스트 기반):** 소스 코드를 자연어(NLP)처럼 처리 (정확도 낮음).
4.  **Mixed (혼합형):** 위 방식들을 결합하여 성능을 극대화함 (SOTA).

## 4. Deep Learning Models (주요 모델)
* **Bi-LSTM / RNN:** 코드의 긴 문맥(Long-term dependency)을 기억하여, 변수 선언과 사용 사이의 거리가 멀어도 취약점을 탐지함.
* **CNN:** 코드의 국소적인 패턴(위험한 함수 사용 등)을 이미지처럼 포착함.
* **Deep Belief Network (DBN):** 복잡한 특징을 추출하는 데 사용됨.

## 5. Challenges & Future Directions (한계와 미래)
* **Explainability (해석 가능성):** AI가 취약점을 탐지했을 때, "왜 위험한지" 설명하지 못하는 'Black Box' 문제가 있음. (XAI 연구 필요)
* **Data Scarcity (데이터 부족):** 실제 해킹 데이터(Real-world)가 부족하여 합성 데이터(SARD)에 의존함.
* **Graph Neural Networks (GNN):** 코드를 평탄화(Flattening)하지 않고, 그래프 구조 그대로 학습하는 GNN이 유망함.

## 6. My Insight (나의 생각 & 적용점)
* **새롭게 알게 된 점:** Buffer Overflow 원리를 AI로 잡으려면, 단순히 텍스트를 읽는 게 아니라 PDG를 통해 변수의 흐름을 추적해서 추출 후 Bi-LSTM이나 GNN을 넣어야 하지만, XAI가 문제가 됨을 알게 되었다.
* **앞으로의 계획:** 논문에서 제시된 새로운 개념들인 PDG나 Bi-LSTM, GNN 등에 대해서 더욱 공부할 예정이다.

---
*Reference: "Software Vulnerability Detection Using Deep Neural Networks: A Survey", 2020.*
