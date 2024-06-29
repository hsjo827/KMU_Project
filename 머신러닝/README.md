본 KML Challenge 2023F(Kaggle)는 **'2023-2 머신러닝 수업'** 에서 진행한 Competition입니다.

<br/>

## 👬 팀원
- 조현식, 이정현, 우서연

## 🕓 기간
- 2023년 2학기

## 📑 주제
- 설문(Survey) 데이터와 패널(Panel) 데이터를 통해 패널이 설문조사에 응답할지를 예측하는 프로젝트
- 평가지표 : Accuracy

## 🖥 역할 
- 조장, Feature Preprocessing, Feature Engineering, Modeling

<br/>

### Competiton 과정
<br/>

1. 다양한 feature를 생성하여 모델 예측 성능 향상
   - **ex) Silhouette 계수를 사용하여 feature 별 최적의 군집 개수를 찾음**

<br/>
    
2. 불필요한 feature 제거 및 scaler를 사용하여 수치형 데이터 처리

<br/>

3. **SHAP 라이브러리**를 사용하여 feature 중요도 계산 (중요도가 0 이상인 feature 선택)

<br/>
 
4. 여러 번의 Boost 계열 모델 실험을 통해 LGBM, CatBoost 성능이 제일 좋은 것을 확인
   - **LGBM의 5-fold 평균 Accuracy: 0.867762551465618 (OOF)**
   - **CatBoost의 5-fold 평균 Accuracy: 0.8678006513857308 (OOF)**

<br/>

5. 하지만 OOF에만 의지하기에는 성능이 불안정하여 다른 계열 모델인 **DNN과 앙상블하여 성능의 안정성을 높이고자 함**

<br/>

6. DNN의 평균 성능을 얻고자 **seed ensemble (DNN_MODELS=20)**을 하여 0.9 극 초반대로 매우 좋은 성능을 보였으나 과적합 현상 발생

<br/>

7.  과적합 방지를 위해 **LGBM, CatBoost, DNN 모델 각각의 예측 결과를 Power Mean Ensemble 수행**

<br/>

8.  최종 결과 **Public:0.86032, Private:0.86009** (분반 7등, 총 12팀)

<br/>

### 배운 점

- 여러 종류 모델을 Ensemble하면 일반적으로 성능이 올라가지만, 각 모델끼리의 성능 차이가 크다면 오히려 여러 모델을 합치는 것이 해가 될 수 있음. 자신만의 판단 기준을 잘 세워서 결정해야 함.
- feature 생성에 있어 양보다 질이 중요한 거 같음.
- 모델 성능을 높이는 데 있어 EDA가 큰 비중을 차지한다고 느낌.
