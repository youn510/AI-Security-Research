# [Review] SySeVR: A Framework for Using Deep Learning to Detect Software Vulnerabilities

## 1. Basic Info (기본 정보)
- **Title:** SySeVR: A Framework for Using Deep Learning to Detect Software Vulnerabilities
- **Source:** IEEE Transactions on Dependable and Secure Computing (TDSC), 2021 (Originally NDSS 2018)
- **Tags:** #System_Hacking #Buffer_Overflow #Program_Slicing #Deep_Learning #BGRU #C/C++
- **Date:** 2026.02.16

## 2. One-Line Summary (한 줄 요약)
> **"C/C++ 소스 코드 전체를 분석하는 대신, 해킹과 관련된 핵심 코드 조각(SeVC)만 잘라내어(Slicing) BGRU 모델에 학습시킴으로써 15개의 제로데이(Zero-day) 취약점을 발견한 프레임워크."**

## 3. Key Concepts (핵심 개념)

### 3.1. The "Region Proposal" Analogy (SyVC & SeVC)
* **Image AI:** 사진에서 배경을 버리고 물체(Object)가 있을 법한 영역만 분석함.
* **SySeVR:** 코드에서 주석이나 무관한 로직을 버리고, 취약점이 의심되는 영역(SyVC)과 그와 연관된 문맥(SeVC)만 추출함.
* **Effect:** 노이즈를 제거하여 AI가 해킹 패턴에만 집중하게 만듦.

### 3.2. Program Slicing & PDG (코드 자르기)
* **PDG (Program Dependence Graph):** 코드를 데이터 흐름(Data Flow)과 제어 흐름(Control Flow)의 그래프로 변환.
* **Slicing:** 위험한 지점(Sink)을 기준으로, 데이터가 어디서 왔는지(Source) 역추적(Backward Slicing)하여 인과관계가 있는 줄만 남김.
* **Result:** 수백 줄의 코드 중, 버퍼 오버플로우와 직접 관련된 10~20줄의 핵심 코드만 남음.

### 3.3. 4 Types of Vulnerabilities (해킹의 4대 요소)
1.  **FC (Function Call):** 위험한 API 호출 (e.g., `strcpy`, `system`)
2.  **AU (Array Usage):** 배열 인덱스 접근 (Buffer Overflow의 주원인)
3.  **PU (Pointer Usage):** 포인터 연산 및 주소 조작
4.  **AE (Arithmetic Expression):** 정수 오버플로우 (Integer Overflow)

## 4. Model Architecture (모델 구조)
* **Model:** **BGRU (Bidirectional Gated Recurrent Unit)**
* **Input:** 벡터로 변환된 정제된 코드 조각 (SeVC Vectors).
* **Why BGRU?**
    * **Bidirectional (양방향):** 코드를 위에서 아래로(Forward), 아래에서 위로(Backward) 읽으며 문맥을 파악.
    * **GRU (Memory):** 변수 선언(Start)과 취약점 발생(End) 사이의 거리가 멀어도, 변수의 속성을 끝까지 기억함.

## 5. Key Results (성과)
* 기존의 정적 분석 도구(Checkmarx 등)보다 오탐(False Positive)이 적음.
* NVD(국가 취약점 DB)에 보고되지 않은 15개의 제로데이 취약점을 실제 오픈소스 라이브러리(LibPNG, FFmpeg 등)에서 발견함.

## 6. My Insight (나의 생각 & 적용점)
**새롭게 알게 된 점:** 해킹은 단순히 위험한 함수를 썼다고 발생하는 것이 아니다. "데이터가 어디서 입력되어, 어떻게 변조되고, 어디로 전달되는지" 그 흐름을 놓치지 않는 것이 핵심이라고 생각한다.
* **앞으로의 계획:** 앞으로는 AI와 보안을 접목시킨 부분에 대해서 상세하게 서술한 논문에 대해서 더욱 알아볼 예정이다.

---
*Reference: Z. Li et al., "SySeVR: A Framework for Using Deep Learning to Detect Software Vulnerabilities," IEEE TDSC, 2021.*
