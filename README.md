# GETI 프로젝트

식물 질병을 분류하고, 분류된 질병에 대한 솔루션을 제공하는 
프로젝트입니다.


----

### ⏰ 프로젝트 기간
2023.11.30 ~ 2023.12.12

----

### 📂 데이터 수집

- KAGGLE의 Plant disease 데이터 사용

----

### 🗂️ 데이터 전처리
- 학습 대상 : 토마토, 감자, 장미 3개의 클래스 사용

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

각 품목당 Train, Val, TEST 비율을 (0.7, 0.2, 0.1)로 맞춤

### 💻 모델 학습

- CNN(Convolutional neural network) 을 이용해 프로젝트를 진행
- 객체탐지가 아닌 품종의 질병을 분류하는 프로그램을 제작이 목적이였기에 사용
- 