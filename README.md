# NYC Airbnb Price Analysis

뉴욕 Airbnb 데이터를 활용하여 지역별 가격·수익·예약률·공급 구조를 비교하고,  
숙소 특성과 가격 간의 관계를 분석해 **신규 호스트를 위한 가격 및 운영 인사이트를 도출한 팀 프로젝트**입니다.

---

## Project Context

스파르타 내일배움캠프 데이터분석 10기 과정에서 진행한  
**팀 기반 교육 프로젝트**입니다.

뉴욕 Airbnb 시장은 자치구별로 가격, 예약률, 수익성, 숙소 공급 구조가 크게 다르기 때문에  
신규 호스트가 동일한 기준으로 가격을 책정하기 어렵습니다.

본 프로젝트에서는 지역 특성과 숙소 구조를 함께 분석하여  
**어떤 요인이 숙소 가격에 영향을 주는지 파악하고, 합리적인 가격 가이드라인과 운영 전략을 제안하는 것**을 목표로 했습니다.

---

## Business Question

> 신규 Airbnb 호스트는  
> **뉴욕의 지역 및 숙소 특성을 고려해 어떤 기준으로 가격을 책정해야 할까?**

이를 위해 다음 관점에서 분석했습니다.

1. 지역별 가격·수익·예약률·공급 비교
2. 자치구별 시장 특성 분류
3. 숙소 특성과 가격의 관계 분석
4. 머신러닝 기반 가격 영향 변수 분석
5. 숙소 유형별 운영 전략 제안

---

## My Contribution

이 저장소에는 **제가 직접 수행한 분석 노트북**을 공개했습니다.

### 1. Data Preprocessing & Outlier Handling

- 데이터 구조 및 결측치 확인
- 분석에 필요하지 않은 컬럼 정리
- 가격 및 호스트 응답률 관련 컬럼의 수치형 변환
- 가격 로그 변환
- IQR과 Z-score를 함께 활용한 이상치 탐색 및 처리

### 2. Borough-Level Exploratory Analysis

뉴욕 5개 자치구를 기준으로 다음 지표를 비교했습니다.

- 평균 숙소 가격
- 평균 수익
- 평균 예약률
- 숙소 공급량

통계 검정을 통해 지역별 차이가 유의한지 확인하고,  
자치구별 시장 특성을 비교했습니다.

### 3. Statistical Testing

지역 간 차이를 검증하기 위해 다음 방법을 활용했습니다.

- Shapiro-Wilk Test
- Levene Test
- Welch ANOVA
- Games-Howell Post-hoc Test
- Kruskal-Wallis Test
- Welch's t-test
- Spearman Correlation

### 4. Market Segmentation & Host Analysis

- 가격·수익·예약률·공급을 종합해 지역별 시장 특성을 비교
- Superhost 여부와 예약률의 차이 분석
- 숙소 수용 인원과 가격의 관계 분석
- 시장 유형별 리뷰 점수와 예약률 간 상관관계 분석

> 팀 전체 프로젝트에는 머신러닝 기반 가격 예측과 최종 운영 전략 분석이 포함되어 있으며,  
> 이 저장소의 노트북은 그중 제가 수행한 분석 파트를 중심으로 구성되어 있습니다.

---

## Data

뉴욕 Airbnb 숙소 데이터를 활용했습니다.

주요 변수:

- Borough / Neighbourhood
- Property Type
- Room Type
- Accommodates
- Bedrooms
- Bathrooms
- Minimum Nights
- Superhost 여부
- Host Response Rate
- Host Acceptance Rate
- Review Scores
- Estimated Occupancy
- Price

---

## Analysis Workflow

1. 데이터 구조 및 품질 확인
2. 결측치 및 불필요 컬럼 처리
3. 가격 로그 변환 및 이상치 처리
4. 자치구별 가격 비교
5. 자치구별 수익·예약률·공급 분석
6. 통계적 유의성 검정
7. 지역별 시장 구조 비교
8. Superhost·숙소 규모·리뷰 지표 분석
9. 머신러닝 기반 가격 영향 변수 분석
10. 신규 호스트 가격 및 운영 전략 제안

---

## Key Analysis

### 1. Borough Price Differences

지역별 가격 분포를 비교한 결과  
**Manhattan이 다른 지역보다 높은 가격대를 형성**했으며, Brooklyn도 상대적으로 높은 수준을 보였습니다.

Games-Howell 사후검정에서는 Manhattan과 다른 자치구 사이의 가격 차이가 통계적으로 유의하게 나타났습니다.

---

### 2. Revenue, Occupancy & Supply

가격만으로 시장을 판단하지 않고  
자치구별 평균 수익, 예약률, 숙소 공급량을 함께 비교했습니다.

이를 통해 높은 가격과 높은 예약률이 항상 동시에 나타나는 것은 아니며,  
지역마다 서로 다른 시장 구조가 존재함을 확인했습니다.

---

### 3. Market Structure

자치구별 가격·수익·예약률·공급 수준을 종합하여  
시장 특성을 비교했습니다.

- **Manhattan**: 높은 가격과 수익성을 보이는 프리미엄 시장
- **Brooklyn**: 높은 예약률과 수익성을 보이는 주요 시장
- **Queens**: 상대적으로 효율적인 수요 구조를 가진 시장
- **Bronx / Staten Island**: 상대적으로 낮은 성과를 보이는 시장

---

### 4. Host & Listing Characteristics

숙소 운영 특성과 성과 간 관계도 함께 분석했습니다.

- Superhost 여부에 따라 예약률 차이가 나타남
- 숙소 수용 인원이 증가할수록 가격이 상승하는 경향 확인
- 리뷰 항목과 예약률 간 관계는 시장 유형에 따라 다르게 나타남

---

## Machine Learning

팀 프로젝트에서는 숙소 가격에 영향을 주는 변수를 설명하기 위해  
선형회귀와 Random Forest 기반 분석을 수행했습니다.

### Linear Regression

- Train R²: **0.5741**
- Test R²: **0.6500**

### Random Forest

- Train R²: **0.821**
- Test R²: **0.759**

Random Forest 모델에서 주요 가격 영향 변수로는 다음과 같은 요소가 확인되었습니다.

- Accommodates
- Value Group
- Revenue per Person
- Property Type
- Location-related variables
- Bathrooms

---

## Final Insights

분석 결과를 바탕으로 다음과 같은 가격 및 운영 방향을 제안했습니다.

- 숙소 수용 인원이 증가할수록 가격을 단계적으로 조정
- 공간 효율을 고려해 욕실 수 등 핵심 숙소 특성 최적화
- Superhost와 같은 신뢰 지표를 활용한 가격 프리미엄 전략
- 지하철 등 주요 관광·교통 인프라 접근성을 가격 책정에 반영
- 지역의 시장 구조에 따라 가격 전략을 차별화

프로젝트 최종 결과에서는 숙소를  
**효율형 / 균형형 / 매출형** 관점으로 구분하여  
각 유형에 맞는 가격 및 운영 전략을 제안했습니다.

---

## Repository Files

### `notebooks/jaehee_analysis.ipynb`

제가 수행한 뉴욕 Airbnb 분석 노트북입니다.

주요 내용:

- 전처리 및 이상치 처리
- 자치구별 가격·수익·예약률·공급 분석
- 지역별 통계 검정
- 시장 특성 비교
- Superhost 및 숙소 특성 분석
- 리뷰 점수와 예약률 상관관계 분석

### `images/`

README에 사용할 프로젝트 결과 시각화 이미지를 저장하는 폴더입니다.

---

## Tools

### Data Analysis
- Python
- Pandas
- NumPy

### Statistics
- SciPy
- Statsmodels
- Pingouin

### Machine Learning
- Scikit-learn
- Linear Regression
- Random Forest

### Visualization
- Matplotlib
- Seaborn

---

## Repository Structure

```text
nyc-airbnb-price-analysis/
│
├── README.md
│
├── notebooks/
│   └── jaehee_analysis.ipynb
│
└── images/
    └── .gitkeep
```

---

## Project Type

- **Educational Team Project**
- Sparta Data Analysis Bootcamp
- Data Analysis 10th Cohort

> This repository contains the analysis files from a team project.  
> The notebook in this repository focuses on the analysis work I personally performed.
