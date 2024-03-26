이재봉(한국교육과정평가원), New Physics: Sae Mulli, Vol. 73, No. 2, February 2023, pp. 138∼149
[원문보기](attachments/npsm.73.138.pdf)
### 1. 서론
![](attachments/Pasted%20image%2020240326180742.png)

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
  ![](attachments/Pasted%20image%2020240326180831.png)

### 3. 연구 결과
#### 3.1. 모형의 적합도
* 5,308개 중 2654개(50%)를 성능평가를 위해 사용
* 10-fold 교차검증 (9/10 : 훈련데이터, 1/10 검증 데이터로 반복 실행)
* 공백 답안 : 비슷하게 매우 높음
* 오답의 CA가 정답보다 높음 : 오답 비율이 높기 때문
* Logistic Regression의 AUC가 가장 높으나 재현율이 85.3%로 보강할 방법이 고안될 필요가 있음
* 훈련시 사용되지 않는 데이터의 분류 평가 : 높은 편. 모형이 타당함. 옳은 답안에 대한 재현율Recall이 91%로 다소 낮으므로 실제 적용을 위해서는 개선 또는 자동 채점을 적용하는 절차 마련할 필요가 있음
#### 3.2. 주요 오분류 사례
* 공백 -> 틀림 (2건) : 
* 틀림 -> 공백 (3건) : 물체 3개를 바닥에 그려놓음, 의미없는 표식이 있는 경우
* **틀림 -> 맞음 (43건)** : 일부만 오류가 있는 경우(18개), 3개의 물체를 나란히 표시한 경우(7개), 답안 작성 시 수정내용이 스캔되며 복잡하게 반영(8개), 명확히 틀린 경우(10개)
* 맞음 -> 틀림 (20건) : 물체를 너무 작게 표시하여 글씨를 알아보기 힘든 경우(5개), 특별한 이유가 없는 경우(9개), 수정한 경우(6개)
* 지운 경우를 따로 분류하여 인간의 판단에 맡기는 방안을 고려해볼 수 있음
#### 3.3. 샘플링수별 모형 적합도
* 지도학습을 위해 50% 이상의 채점데이터를 사용하였으므로 실효성이 적음
* 전체 답안 중 5 ~25% (구간 5%p)를 재표집하여 훈련데이터로 사용
* 5% -> 10%일 때 모형적합도 지수의 향상도가 가장 큼