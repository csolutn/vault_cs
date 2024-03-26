### 1. 서론
### 2. 연구 방법
#### 2.1. 연구자료
#### 2.2. 분석모델
* 합성곱 신경망과 지도학습에 의한 이미지 분류
* 전이학습, Google Inception V3 소개
* Inception V3 를 이용한 기존 연구
* 혼동행렬과 목표 : AUC를 우선적으로 고려 + 채점결과가 불리하지 않게 Recall 고려
	* AUC (Area Under the **ROC** Curve)
	* ROC Curve : FPR에 따른 TPR
	* CA (Classification Accuracy): (TP + TN)/(TP+FP+TN+FN)
	* Precision : TP(TP + FP) True로 분류된 것중에 참True 비율
	* Recall : TP/(TP+FN) 참True 중 True 분류 비율
	* F1 : 2 $\times$ (Precision $\times$ Recall)/(Precision+Recall)
#### 2.3. 분석 도구
* Orange Datamining + Image Analysys
* 전처리 : Image Embedding (Inception V3 포함 6가지 모형을 통한 특징 추출)
* 군집 분리 및 평가 : KNN, SVM, Random Forest, Logistic Reg., Neural Network
* Figure2(오렌지 화면)설명 및 오렌지를 이용한 도구 소개

### 3. 연구 결과





![[합성곱 신경망(CNN)을 활용한 그래픽 답안 자동 채점 가능성 탐색.pdf]]
