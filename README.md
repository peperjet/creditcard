# Credit Card Default Prediction (신용카드 연체 예측)

## 📌 프로젝트 개요

신용카드 사용자 데이터를 기반으로 고객의 연체 여부(credit)를 예측하는 머신러닝 모델을 구축했다.
데이터 전처리, Feature Engineering, 모델 학습까지 전체 흐름을 직접 수행했다.

---

## 📂 데이터 구성

* `train.csv` : 학습 데이터 (정답 포함)
* `test.csv` : 예측 데이터 (정답 없음)
* `sample_submission.csv` : 제출 형식

---

## 🔧 데이터 전처리

### 1. Feature 파악

* `DAYS_BIRTH` → 나이로 변환 (`age`)
* `DAYS_EMPLOYED` → 근속연수로 변환 (`employment_year`)

---

### 2. 결측치 처리

* `occyp_type` → `"Unknown"`으로 대체

---

### 3. 이상치 처리

* `income_total` → 로그 변환 (`log1p`)
* `DAYS_EMPLOYED`의 이상값(365243) → 0으로 변경

---

### 4. Feature Engineering

* 나이(age), 근속연수(employment_year) 생성
* 불필요 컬럼 제거 (`DAYS_BIRTH`, `DAYS_EMPLOYED`, `index`)

---

### 5. 왜도(Skewness) 개선

* `child_num`, `family_size`, `employment_year` → 로그 변환

---

### 6. 인코딩

* 범주형 변수 → One-Hot Encoding (`pd.get_dummies`)

---

## 🤖 모델링

* 모델: `RandomForestClassifier`
* 학습 데이터: train
* 예측 데이터: test

---

## 📊 결과 생성

* test 데이터 예측 수행
* submission.csv 파일 생성

---

## 📌 핵심 정리

* 데이터 전처리가 모델 성능에 큰 영향을 준다
* 범주형 데이터는 반드시 인코딩 필요
* 이상치 및 왜도 처리가 중요하다

---

## 🛠 사용 기술

* Python
* Pandas, NumPy
* Scikit-learn

---
