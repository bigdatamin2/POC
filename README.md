# POC

개요

본 실험은 PhalangesOutlinesCorrect 데이터셋에서 특정 비율로 샘플링을 수행한 결과입니다. 해당 데이터셋은 이진 분류 문제이며, 클래스 불균형을 고려하여 클래스별로 서로 다른 비율의 샘플링을 진행하였습니다.

📁phalangesoutlinescorrect_makedata.ipynb

원본데이터를 업로드하고 데이터 크기 축소해주기(Sample Data 생성)


📁phalangesoutlinescorrect_basic.ipynb

Sample Data를 읽어서 DTW, KNN 수행하고 예측


📁phalangesoutlinescorrect_bsmote.ipynb

(시계열 방식X) 데이터를 증폭시키는 방법(SMOTE로 증폭시키고 DTW, KNN 수행하고 예측) 

-> 정확도가 1이 나올수가 없음. 프로그램 체크 필요(수정 완료)

수정 사항: compute_dtw_matrix함수에서 y_train_resampled을 X1또는 X2로 전달하는 것은 오류
train_dtw_matrix = compute_dtw_matrix(X_train_resampled, y_train_resampled)이 부분을 train_dtw_matrix = compute_dtw_matrix(X_train_resampled, X_train_resampled)로 수정


📁phalangesoutlinescorrect_tsaug.ipynb

시계열 고려해서 두 시계열 데이터 간의 평균을 구한 후 DTW, KNN 수행하고 예측
