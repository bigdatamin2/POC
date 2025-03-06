# POC

개요

본 실험은 PhalangesOutlinesCorrect 데이터셋에서 특정 비율로 샘플링을 수행한 결과입니다. 해당 데이터셋은 이진 분류 문제이며, 클래스 불균형을 고려하여 클래스별로 서로 다른 비율의 샘플링을 진행하였습니다. 실험은 여러 방법을 통해 데이터를 처리하고, 동적 시간 왜곡(DTW)과 K-최근접 이웃(KNN)을 사용하여 예측 모델을 구축하는 것을 목표로 합니다.

📁phalangesoutlinescorrect_makedata.ipynb

원본 데이터를 업로드하고, 데이터 크기를 축소하여 샘플 데이터를 생성합니다.

📁phalangesoutlinescorrect_basic.ipynb

샘플 데이터를 읽어 DTW와 KNN을 적용하여 예측을 수행합니다.


📁phalangesoutlinescorrect_bsmote.ipynb

시계열 방식이 아닌 데이터 증폭 방법인 SMOTE(Synthetic Minority Over-sampling Technique)를 사용하여 데이터를 증폭시키고, 이후 DTW와 KNN을 적용하여 예측을 수행합니다.

수정 사항: compute_dtw_matrix 함수에서 y_train_resampled을 X1 또는 X2로 전달하는 부분에서 오류가 발생했습니다. 이를 train_dtw_matrix = compute_dtw_matrix(X_train_resampled, X_train_resampled)로 수정하였습니다. 이 수정으로 문제를 해결했습니다.


📁phalangesoutlinescorrect_tsaug.ipynb

시계열 데이터를 고려하여, 두 시계열 데이터 간의 평균을 구한 후 DTW와 KNN을 적용하여 예측을 수행합니다.

