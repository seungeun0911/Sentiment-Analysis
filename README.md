# Sentiment Analysis
 네이버 영화 리뷰 크롤링을 통한 감성분석\
 \
 긍정/부정 각각 10만 데이터 확보 진행 중\

1. Tensorflow/keras\
\
[2023.01.25]\
1 to 4: 부정, 8 to 10: 긍정\
긍정: 31558개, 부정: 8894개로 테스트 진행(train data : test data = 8 : 2)\
파라미터: BATCH_SIZE = 512, NUM_EPOCHS = 10, VALID_SPLIT = 0.1\
모델: CNNClassfier / 컴파일: 손실함수, 옵티마이저 - adam, 지표 - accuracy\
모델 평가: 0.8673\
\
[2023.01.26]\
1 to 4: 부정, 8 to 10: 긍정\
긍정: 8894개, 부정: 8894개로 테스트 진행(train data : test data = 8 : 2)\
파라미터, 모델 및 컴파일: 위와 동일\
모델 평가: 0.8280\
\
1 to 4: 부정, 8 to 10: 긍정\
빈도가 2번 이하인 희귀 단어 제거\
긍정: 31558개, 부정: 8894개로 테스트 진행(train data : test data = 8 : 2)\
임베딩 벡터 차원: 100, 은닉 상태 크기: 128\
파라미터: BATCH_SIZE = 64, NUM_EPOCHS = 15, VALID_SPLIT = 0.2\
모델: LSTM / 컴파일: 손실함수, 옵티마이저 - adam, 지표 - accuracy\
모델 평가: 0.9022\
\
1 to 4: 부정, 8 to 10: 긍정\
긍정: 8894개, 부정: 8894개로 테스트 진행(train data : test data = 8 : 2)\
파라미터, 모델 및 컴파일: 위와 동일\
모델 평가: 0.8709\
\
[2023.01.30]\
1 to 6: 부정, 8 to 10: 긍정\
긍정: 39999개, 부정: 14956개로 테스트 진행(train data : test data = 8 : 2)\
파라미터, 모델 및 컴파일: 위와 동일\
모델 평가: 0.9052\
\
[2023.01.31]\
Naver sentiment movie corpus(20만개 데이터셋(긍정 부정 각각 10만개), 1 to 4: 부정, 9 to 10: 긍정) + 크롤링 데이터셋(50889개 데이터셋(긍정 39047개, 부정 11842개), 1 to 5: 부정, 8 to 10: 긍정)\
전처리 이후: 243280개(긍정 134705개, 부정 108575개) => 각각 10만개씩 재조정\
train data : test data = 8 : 2\
LogisticRegression 모델 평가: 0.84\
불용어사전 추가 버전 LogisticRegression 모델 평가: 0.8586\
\
[2023.02.02]\
Naver sentiment movie corpus(20만개 데이터셋(긍정 부정 각각 10만개), 1-4점 부정, 9-10점 긍정) + 크롤링 데이터셋(50889개 데이터셋(긍정 40916개, 부정 12425개), 1-5점 부정, 8-10점 긍정)\
전처리 이후: 245637개(긍정 136500개, 부정 109137개) => 동일하게 1:1 비율로 조정\
train data : test data = 8 : 2\
파라미터: BATCH_SIZE = 512, EPOCHS = 10\
모델: 기본적인 신경망 모델\
모델 평가: 0.7211\
\
Naver sentiment movie corpus(20만개 데이터셋(긍정 부정 각각 10만개), 1-4점 부정, 9-10점 긍정) + 크롤링 데이터셋(50889개 데이터셋(긍정 40916개, 부정 12425개), 1-5점 부정, 8-10점 긍정)\
전처리 이후: 245637개(긍정 136500개, 부정 109137개) => 동일하게 1:1 비율로 조정\
train data : test data = 8 : 2\
파라미터: BATCH_SIZE = 512, EPOCHS = 8\
모델: 기본적인 신경망 모델 / 컴파일: 손실함수, 옵티마이저 - adam, 지표 - accuracy\
모델 평가: 0.8378\
\
[2023.02.08]\
1-D Convolution Neural Network (1-D CNN)\
accuracy: 0.9546, loss: 0.1502\
GlobalMaxPooling1D\
accuracy: 0.9572, loss: 0.1386\
RNN\
accuracy: 0.9313, loss:0.1836\
1-D CNN + RNN\
accuracy: 0.9523, loss: 0.1537\
\
2. Pytorch
