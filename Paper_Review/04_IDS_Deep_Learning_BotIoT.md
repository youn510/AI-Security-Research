# [Review] Cyber Security Intrusion Detection using Deep Learning

## 1. Basic Info (기본 정보)
- **Title:** Cyber Security Intrusion Detection Using Deep Learning Approaches, Datasets, Bot-IOT Dataset
- **Source:** IEEE Access
- **Date:** 2026.02.11 (Read Date)
- **Tags:** #Intrusion_Detection #IDS #Deep_Learning #Bot-IoT #AutoEncoder #CNN

## 2. One-Line Summary (한 줄 요약)
> **"최신 IoT 보안 위협을 탐지하기 위해 'Bot-IoT 데이터셋'을 활용하여 Deep Auto-Encoder와 CNN 모델의 성능을 비교 분석한 연구"**

## 3. Key Components (핵심 요소)

### 3.1. Datasets (사용된 데이터셋)
* **Bot-IoT Dataset (핵심):**
    * 기존의 오래된 데이터(KDD Cup 99)와 달리, 최신 **IoT 네트워크 환경(MQTT 프로토콜, Node-RED)**에서 발생한 실제 공격 트래픽을 담고 있음.
    * DDoS, DoS, OS Scan, Keylogging 등 실질적인 위협을 포함함.
* **NSL-KDD / UNSW-NB15:** 성능 비교를 위한 벤치마크 데이터셋으로 사용됨.

### 3.2. Approaches & Models (주요 모델)
* **Deep Auto-Encoder (DAE):**
    * 데이터의 특징을 압축했다가 복원하는 과정에서, 학습하지 않은 공격(이상치)을 탐지하는 'Anomaly Detection' 기법 사용.
* **CNN (Convolutional Neural Network):**
    * 네트워크 트래픽을 이미지 패턴처럼 인식하여 공격을 분류함.
* **Other Models:** RNN, DBN(Deep Belief Network) 등도 비교 대상에 포함됨.

## 4. Experimental Results (실험 결과)
**[Bot-IoT 데이터셋 기준 성능 비교]**
1.  **Deep Auto-Encoder (DAE):** **98.394%** (정확도 1위)
    * *특징:* 학습 시간이 적게 걸리고, 미세한 이상 징후 탐지에 가장 탁월함.
2.  **CNN:** **98.371%** (정확도 2위)
    * *특징:* 은닉 노드 100개, 학습률 0.5 설정에서 매우 높은 성능을 보임.

## 5. My Insight (나의 생각 & 적용점)
* **새롭게 알게 된 점:** 아무리 좋은 AI 모델이라도 20년 전 데이터(KDD99)로는 최신 IoT 해킹을 막을 수 없음을 깨달았다.
* **앞으로의 계획:** 조금 더 많은 다양한 분야의 보안과 AI가 접목된 논문들을 더 읽어나가며 나의 방향성을 조금씩 굳혀 나아가야겠다.

---
*Reference: IEEE Access, "Cyber Security Intrusion Detection Using Deep Learning Approaches, Datasets, Bot-IOT Dataset"*
