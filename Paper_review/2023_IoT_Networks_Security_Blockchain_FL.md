# [Review] Ensuring Privacy and Security of IoT Networks Utilizing Blockchain and Federated Learning

## 1. Basic Info (기본 정보)
- **Title:** Ensuring Privacy and Security of IoT Networks Utilizing Blockchain and Federated Learning
- **Source:** FiCloud, 2023
- **Tags:** #IoT_Security #Blockchain #Federated_Learning #Privacy #Zero_Trust

## 2. One-Line Summary (한 줄 요약)
> **"기존 중앙 집중형 AI의 단일 장애점(SPOF)을 극복하기 위해, IoT 기기 단말에서 독립적으로 AI를 학습하는 연합학습(FL)과 그 결과물의 위변조를 막는 블록체인(BC)을 결합한 철통 방어 아키텍처."**

## 3. Key Concepts (핵심 개념)

### 3.1. IoT Security Challenges (기존 IoT 보안의 치명적 약점)
* 수많은 기기에서 수집된 민감한 데이터를 중앙 클라우드 서버로 모두 전송하여 학습하는 기존 방식은, 해커가 중앙 서버 하나만 장악해도 전체 네트워크가 붕괴되는 치명적인 위험을 안고 있다.
* 특히 백도어나 XSS처럼 정상 트래픽으로 위장하여 깊숙이 침투하는 은밀한 공격에 대해 기존 CNN/LSTM 모델은 40~60%대의 처참한 탐지율을 보였다.

### 3.2. Federated Learning (연합 학습의 게릴라 전술)
* 데이터를 중앙으로 보내지 않고, 글로벌 서버에서 AI 모델만 다운받아 각 IoT 기기(Local)에서 직접 학습한다. 
* 해커가 중간에 통신을 가로채더라도 탈취할 원본 데이터가 존재하지 않아 프라이버시가 완벽히 보호된다.

### 3.3. Blockchain Integration (블록체인의 무결성 방패)
* 기기들이 학습한 가중치를 서버로 보낼 때, 해커가 악성 데이터를 섞는 '모델 포이즈닝' 공격을 시도할 수 있다.
* 이를 막기 위해 스마트 컨트랙트(Smart Contracts)를 도입하여, 인증된 기기만 참여할 수 있게 통제하고 전송되는 모든 데이터를 블록체인에 영구 기록하여 위조를 원천 차단했다.

## 4. Architecture / Methodology (스마트 컨트랙트 3중 방어선)
* **Model/System:** FL (CNN/RNN) + Ethereum Smart Contracts + IPFS
* **How it works:**
    1. **Registration SC:** 허가되지 않은 악성 기기의 네트워크 진입을 암호학적으로 차단.
    2. **Local Learning Upload SC:** 로컬 기기에서 학습된 가중치가 훼손 없이 집계 서버로 전달되도록 통제.
    3. **Global Learning Distribution SC:** 취합이 완료된 안전한 글로벌 모델만을 다시 로컬 기기로 배포.

## 5. Key Results (핵심 성과)
* **방어력의 극적 상승:** 연합학습(FL)을 50라운드 반복한 결과, 기존 중앙집중형 모델에서 놓치던 공격들(백도어, XSS 등)에 대한 탐지율이 91~93% 이상으로 비약적으로 상승했다.
* **최초의 블록체인 결합:** 2019~2021년의 기존 IoT IDS 연구들과 비교했을 때, 블록체인을 성공적으로 도입하여 무결성을 보장한 차별화된 모델임을 증명했다.

## 6. My Insight (나의 생각 & 적용점)
* **새롭게 알게 된 :** 블록체인과 연합학습(FL)을 활용하여 새로운 방식으로 보안을 강화할 수 있다는 사실을 알게되었다.
* **앞으로의 계획:** 향후 암호학의 기초(Cryptography)를 다진 후, 파이썬의 PyCryptodome을 이용해 대칭키/비대칭키 암호화를 실습해보고, 블록 체인(BlockChain)에 대해서 학습 및 응용을 할 것이다.

---
*Reference: S. T. et al., "Ensuring Privacy and Security of IoT Networks Utilizing Blockchain and Federated Learning," 2023.*
