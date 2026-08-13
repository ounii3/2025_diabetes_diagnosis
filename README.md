# 💡 성별 제약 없는 당뇨병 위험도 예측 시뮬레이션

> **보건 탐구 프로젝트**  
> **기술 스택:** Python, Streamlit, Scikit-learn, Pandas  
> **핵심 주제:** 인공지능 머신러닝을 활용한 보건 지표 분석 및 성별 제약(임신 변수)을 제거한 일반화 당뇨병 위험도 예측 Web App

---

## 📌 프로젝트 배경 및 목적 (Overview)

기존의 **피마 인디언 당뇨병 데이터셋(Pima Indians Diabetes Dataset)**은 '임신 횟수(Pregnancies)' 변수를 포함하고 있어 남성이나 임신 경험이 없는 대상에게 적용하기 어렵다는 한계가 있었습니다.

본 프로젝트는 보건 수업 탐구의 일환으로 **'임신 횟수' 변수를 제거**하고, 남녀노소 누구나 적용 가능한 **7가지 보편적 생체 지표**만을 활용하여 당뇨병 발병 위험도를 예측하는 머신러닝 모델을 구축했습니다.

---

## ✨ 주요 특징 (Key Features)

* **성별 편향 없는 일반화 모델**: `Pregnancies` 변수를 제외하여 남성과 여성 모두에게 보편적으로 적용 가능
* **직관적인 인터페이스**: Streamlit 기반 슬라이더를 통해 자신의 생체 지표를 손쉽게 조정하고 테스트
* **실시간 당뇨병 위험도 계산**: 랜덤 포레스트(Random Forest) 분류 모델을 사용하여 발병 확률(%)을 즉시 계산
* **자동 모델 생성 및 캐싱**: 최초 실행 시 모델을 자동 학습하여 `pickle` 파일로 저장 후 빠르게 재사용

---

## 📊 입력 생체 지표 (Features)

| 지표명 (Feature) | 설명 | 입력 범위 |
| :--- | :--- | :--- |
| **혈당 수치 (Glucose)** | 공복 혈당 농도 | 50 ~ 200 mg/dL |
| **혈압 (Blood Pressure)** | 이완기 혈압 | 30 ~ 130 mmHg |
| **피하지방 두께 (SkinThickness)** | 삼두근 피부 주름 두께 | 0 ~ 100 mm |
| **인슐린 수치 (Insulin)** | 혈청 인슐린 농도 | 0 ~ 900 mu U/ml |
| **BMI** | 체질량 지수 (체중 / 키²) | 10.0 ~ 60.0 |
| **당뇨 유전 영향도 (DPF)** | 당뇨병 내력 적응도 함수 | 0.0 ~ 2.5 |
| **나이 (Age)** | 만 나이 | 10 ~ 100세 |

---

## 🛠️ 기술 스택 (Tech Stack)

* **Language**: Python 3.x
* **Web Framework**: Streamlit
* **Machine Learning**: Scikit-Learn (`RandomForestClassifier`)
* **Data Processing**: Pandas, NumPy
* **Model Serialization**: Pickle

---

## 📂 파일 구조 (Directory Structure)

```text
├── app.py                      # Streamlit 웹 애플리케이션 메인 코드
├── diabetes.csv                # 당뇨병 원본 데이터셋
└── diabetes_model_no_preg.pkl  # [자동 생성] 임신 변수가 제외된 학습 모델
