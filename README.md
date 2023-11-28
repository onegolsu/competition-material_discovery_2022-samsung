# 2022 Samsung AI Challenge (Materials Discovery)
[2022.08.08 ~ 2022.09.16 11:59]

## Result
    
    1. Smile 형식을 Rdkit을 통해, tensor로 처리
    2. Keras모듈로 GRU를 사용하여 답안 제시
    
    개인으로 참여하여 (17/213)


## Theme

    유기분자 구조로부터 Reorganization Energy를 예측하는 AI 알고리즘 개발

## 구현사항

    1. mol file을 읽어오는 전처리 과정
        - atom 개수 bond 개수
        - atom들의 location, element_type (x,y,z,element_type)
        - bond결합 atom구조, (atom_1,atom_2,bond_type) 
    
    2. smile 형식을 적절하게 전처리 하는 과정
        - by rdkit (reference to 2021 Competition)
        - by hugging face model


## Trials

### mol file 기반의 ml 모델

    1. mol file을 read_line 을 통해 parsing
        1.1 구조에 따라 원자좌표, 원자 결합 종류등을 파악한다.
    2. 이를 array 형태로 broadcasting 
        2.1 broadcasting은 데이터의 크기는 제일 큰것을 기준으로 맞춘다
    3. broadcasting된 array 기반으로 TensorFlow 기반의 회귀 분석진행

결과물이 유의미하지 못함.

### SMILE 기반의 ml 모델

    1. SMILE 형식의 데이터 전처리
        1.1 rdkit을 통한 데이터 전처리
        1.2 Hugging Face에서 얻어온 모델로 NLP 처리
    2. Tensor형식으로 전처리
    3. Tensor를 GRU 모델을 통해 처리

### Final

    Keras모듈로 GRU를 사용하여 답안 제시
    개인으로 참여하여 (17 / 213)
