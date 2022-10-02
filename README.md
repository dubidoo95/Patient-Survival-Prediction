# Patient-Survival-Prediction

## 1. Introduction
의료기관에서는 환자를 여러 등급으로 나누어 관리합니다. 흔히 알고있는 예시로는 응급환자를 Black, Red. Yellow, Green으로 나누는 Triage 분류법이 있고 중환자실에서 질병의 중증도를 분류하는 APACHE, SAPS 같은 분류법들이 있습니다. 이들 모두 하나의 공통된 목적을 가지는데, 제한된 인력과 장비를 가지고 최대한의 환자를 살리는 것입니다. 이를 위해서는 소생 가능성이 극히 낮은, 다시 말해 치료를 하더라도 사망할 가능성이 매우 높은 환자를 가려내어 인력과 장비의 낭비를 최소화하는 과정이 필연적입니다. 따라서 저는 환자의 상태를 통해 사망 가능성을 예측하는 모델을 만들었습니다.

## 2. Data
학습에 사용된 데이터의 출처는 다음과 같습니다.

https://www.kaggle.com/datasets/mitishaagarwal/patient

## 3. Hypothesis
학습하기 전 저는 두 가지 가설을 세우고 학습을 진행하였습니다. 첫째로 환자의 나이가 많을수록 환자가 사망할 가능성이 높다는 것, 그리고 환자의 체중이 정상 범주에서 벗어날수록, 다시 말해 심각한 저체중 혹은 과체중일 경우 환자가 사망할 가능성이 높다는 것입니다. 그리고 그 외에 환자의 사망 가능성에 영향을 주는 특성들을 살펴보았습니다. 

## 4. Conclusions
- 환자의 나이는 그 환자의 사망 가능성에 큰 영향을 줍니다.
- 환자의 체중은 그 환자의 사망 가능성에 어느정도 영향을 주기는 하지만 큰 영향을 주지는 못합니다.
- 환자의 사망 가능성을 판단하는데 가장 큰 역할을 하는 특성은 `ventilated_apache`, `gcs_motor_apache`, `age`였습니다. `ventilated_apache`는 환자에게 invasively ventilation 증상이 일어났는지에 대한 여부고, 해당 증상이 발현된 환자의 경우 사망률이 20%에 달한다고 합니다. `gcs_motor_apache`는 환자의 의식 수준 총 6단계로 나눈 지표입니다.
- 해당 모델은 생존 가능성 높은 환자를 사망할 환자로 분류하는 경우가 많아 추가적인 연구가 필요합니다.

## 5. Used Libraries
- pandas
- numpy
- eli5
- matplotlib
- os
- warnings
- scipy
- sklearn
- category_encoders
- xgboost
- pdpbox
- imblearn
