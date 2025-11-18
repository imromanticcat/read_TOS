# read_TOS
2025 새싹 해커톤

# 약관을-읽어주세요: 이용자를 보호하는 약관 분석 경량화 모델

## 0. 환경 구조
VSCode Remote Connection <=> Github Codespace <=> Google Colab Kernel

## 1. 프로젝트 개요 (Overview)
기업의 이용 약관(ToS) 속에 숨겨진 **불공정 조항(Unfair Clauses)**을 실시간으로 탐지하여 사용자에게 알리는 브라우저 확장 프로그램용 AI 모델입니다.

## 2. 문제 해결 전략 (Approach)
### 2.1 Data-Centric Strategy
* **Base Dataset:** `TOS_Dataset` (English)을 기계 번역하여 데이터 양 확보.
* **Gold Standard:** **공정거래위원회(KFTC)** 불공정 약관 심결례 데이터를 수집하여 한국 법률 문맥(Context) 보정.
* **Legal Safety:** 공공데이터 및 연구용 데이터셋을 활용하여 저작권 이슈 완전 해결.

### 2.2 Model Optimization
* **Backbone:** `monologg/koelectra-small-v3-discriminator` (한국어 경량 모델)
* **Compression:** **ONNX Quantization (8-bit)**을 적용하여 모델 크기를 1/4로 축소하고 추론 속도 극대화.
* **Deployment:** Python 서버 없이 **Client-side(Browser)**에서 `onnxruntime-web`으로 구동하여 서버 비용 Zero, 개인정보 유출 방지.

## 3. 탐지하는 불공정 유형 (Detection Classes)
0. **공정 (Fair)**
1. **면책 조항 (Limitation of Liability):** 회사의 책임을 광범위하게 배제
2. **일방적 변경 (Unilateral Change):** 고지 없이 서비스/약관 변경
3. **데이터/저작권 (Content Ownership):** 유저 콘텐츠에 대한 과도한 권리 주장

## 4. 실행 방법 (How to Run)
... (설치 및 실행 코드 작성)

