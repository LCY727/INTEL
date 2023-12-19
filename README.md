# GETI 프로젝트

식물 질병을 분류하고, 분류된 질병에 대한 솔루션을 제공하는 
프로젝트입니다.


----

### ⏰ 프로젝트 기간
2023.11.30 ~ 2023.12.12

----
### ⚙️ 개발 환경
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)

![Visual Studio Code](https://img.shields.io/badge/Visual%20Studio%20Code-0078d7.svg?style=for-the-badge&logo=visual-studio-code&logoColor=white)

![TensorFlow](https://img.shields.io/badge/TensorFlow-%23FF6F00.svg?style=for-the-badge&logo=TensorFlow&logoColor=white)

---
### 📂 데이터 수집

- ![Kaggle](https://img.shields.io/badge/Kaggle-035a7d?style=for-the-badge&logo=kaggle&logoColor=white)의 Plant disease 데이터 사용

----

### 🗂️ 데이터 전처리
- 학습 대상 : `토마토`, `감자`, `장미` 3개의 클래스 사용


1. 토마토
    |disease|질병|
    |---|---|
    |Bactreial spot |세균점무늬병|
    |Early Blight|겹무늬병|
    |Healthy|정상|
    |Late Blight|잎 마름역병|
    |Leaf Mold|잎 곰팡이병|
    |Septoria leaf mold|septoria 마름병|
    |spiders mites Two spotted spider mite|점박이 진드기|
    |Target Spot|표적반점|
    |Mosaic Virus|모자이크 바이러스|
    |Yellow Leaf Curl Virus|황화잎말림바이러스|

2. 감자
    
    |disease|질병|
    |-------|----|
    |Early Blight|겹둥근 무늬병|
    |Late Blight|감자 역병|
    |Healthy|정상|

3. 장미

    |disease|질병|
    |---|---|
    |Black spot|검은 반점|
    |Downy Mildew|노균병|
    |Healthy|정상|

- 토마토 : 10000장의 사진 (10개 클래스)
- 감자 : 4000장의 사진 (3개 클래스)
- 장미 : 5400장의 사진 (3개 클래스)

데이터의 불균형을 방지하기 위해 클래스별로 사진의 수를 맞춤

각 품종당 Train, Val, TEST 비율을 (0.7, 0.2, 0.1)로 맞춤

---

### 📈 모델 학습

- GETI를 사용해 클래스당 10개의 이미지를 학습


- 81%의 정확도를 얻었지만, 좀더 정확도를 올려보고 직접 파라미터 조정등 직접 모델을 설계하기 위해 파이썬코드를 통한 학습 진행
- CNN(Convolutional neural network) 을 이용해 프로젝트를 진행
- 객체탐지가 아닌 품종의 질병을 분류하는 프로그램을 제작이 목적이였기에 사용
```python
from keras import models, layers

model = models.Sequential()
```
- Sequential 모델을 사용하여 학습 진행

- 레이어층을 추가 및 제거 작업을 반복해서 모델 튜닝

```python
reduce_lr = ReduceLROnPlateau(monitor='val_loss', factor=0.2, patience=5, min_lr=0.001)
```
- 진행 중 검증 손실값이 개선이 안되서 학습률을 동적으로 조정하여 학습을 최적화 하는 콜백함수 `ReduceLROnPlateau` 사용

---

### 🖥️ 학습 결과

정확도 테스트 후 검증 결과의 F1 SCORE  
- tomato : 0.81
- potato : 0.93
- rose : 0.91

전체적으로 0.8 이상의 F1 SCORE를 나타낸다.

---

### 📋 프로젝트 후기

- 실제 데이터를 수집해서 사용하고 싶었으나 못해서 아쉽다.
- CNN 프로젝트를 추후에 하게 된다면 전이학습 모델도 사용해보고싶다.
- 이미지상의 특징점`(색상, 패턴)`이 비슷해서 학습 결과가 안좋을거 같았는데 생각보다 결과가 잘 나온거 같다.
- `GETI`툴을 사용해서 객체탐지 프로젝트를 진행해보고 싶다.
