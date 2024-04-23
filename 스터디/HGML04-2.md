---
margin: 0.2
width: 1200
css: css/style.css
---
:::    혼자 공부하는 머신러닝

<grid drag="100 50" drop="0 20">
# 확률적 경사하강법
</grid>
<grid drag="20 5" drop="45 70" >

2024.04.25. (목)

</grid>

---

## 점진적 학습 <!-- element style="align-self:center" -->

훈련한 기존 모델에 새로운 데이터를 추가하여 모델을 업데이트 하는 방법<br>대표적인 알고리즘 : 경사 하강법 <!-- element style="align-self:center" -->

![](https://velog.velcdn.com/images%2Fsset2323%2Fpost%2Fe7b4fe6c-1395-4ea8-88e0-3e7e598e5519%2Fimage.png)

---

<grid drag="50" drop="0 0">
#### 경사하강법을 이용한 학습 예시
```
input = np.array([2, 4, 6, 8, 10, 12, 14])
output = np.array([3, 5, 7, 9, 11, 13, 15])
```
$MSE = \frac{1}{n}\sum \{y_i​−(ax_i​+b)\} ^2$
$$\phantom{MSE} =  \frac{1}{7}[(3−(a×2+b))^2+(5−(a×4+b))^2+\cdots +$$
$$\phantom{MSEME} + (13−(a×12+b))^2+(15−(a×14+b))^2]$$
$$\phantom{MSE} = 80a^2+16ab−176a+b^2−18b+97$$
<!-- element align="left"  -->
![|400](attachments\Pasted%20image%2020240422235053.png)
</grid>

<grid drag = "50 10" drop="55 ">
$MSE_a  = -\frac{2}{n}\sum(y_i-(ax_i+b))x_i$
$$MSE_b = -\frac{2}{n}\sum(y_i-(ax_i+b))$$
```
a, b = 2, 2 # 초기값(출발장소 : 적당히 아무거나)
lr = 0.005 #learning rate (다리길이)
result = [a*i + b for i in input]
error = output - result # (y_i -(ax_i+b))
error = [ -3 -5 -7 -9 -11 -13 -15]
input*error =  [ -6 -20 -42 -72 -110 -156 -210] 
```
$$ a = a - lr*MSE_a$$ <br>
$$b  = b - lr*MSE_b$$
<br>
$a, b$ 값의 변화 : <br>
$(2, 2) \rightarrow(1.56,1.955) \rightarrow (1.30, 1.93)\cdots \rightarrow (0.99,1.123)$


![|400](attachments/Pasted%20image%2020240423000532.png)

</grid>

---
## 손실 함수 (Loss) : 내려가야할 산
회귀함수와 원래 값의 차이를 계산하는 함수 <br>예 : MSE (Mean Squared Error), 크로스 엔트로피(Cross-Entropy), 힌지(hinge) 

::: block
<split even gap="5">

![|250](attachments/Pasted%20image%2020240423010546.png)

![|250](attachments/Pasted%20image%2020240423010325.png)

</split>
:::

---

<grid drag="100 100" drop="5 -40">
## 이진 크로스 엔트로피 (Binary Cross Entropy)
</grid>

<grid darg="40 70" drop="10 10">

$$ \begin{cases} -y\log{p} & \text{if }y = 1 \\ -(1-y)\log(1-p) & \text{if }y = 0 \end{cases} $$<br><br>
$$= -\{y\log{p} + (1-y) \log(1-p) \} $$

$$ CE  = -\frac{1}{n}\sum\{y\log{p} + (1-y) \log(1-p) \} $$

::: block
![|450](attachments/Pasted%20image%2020240423020546.png)
::: <!-- element style="align-self:start" -->

</drag>

<grid drag="80 70" drop="90 10" >

#### 이진 크로스 엔트로피와 시그모이드 사이의 관계

**[Remind]** Linear Regression - MSE
<br>$MSE_a = (-1)\times \rm{mean}(error \times input)$
<br>$MSE_b = (-1)\times \rm{mean}(error) $

**[Discover]** Sigmoid - CE
<br>$CE_a = (-1)\times \rm{mean}(error \times input)$
<br>$CE_b = (-1)\times \rm{mean}(error) $

(증명) https://velog.io/@epsilon/시그모이드-오차함수의-편미분
</grid>

---
## 확률적 경사하강법
하나의 샘플을 랜덤하게 골라 경사도를 계산하고 단계적으로 하강하는 것
* 종류 : 확률적 경사 하강법, 미니배치 경사 하강법, 배치 경사 하강법
* 에포크 : 훈련세트를 한번 모두 사용하는 과정
* .fit()을 .partial_fit()으로 바꿈으로써 구현 가능

![|600](attachments/Pasted%20image%2020240423020016.png)

---
## 에포크와 과대적합

![|650](attachments/Pasted%20image%2020240423190955.png)


---

<grid drag="46 60" drop="0 25" >

```
import numpy as np  
sc= SGDClassifier(lass='log', random_state=42)

train_score= []  
test_score = 0  
classes= np.unique(train_target)

for in range(0, 300):  
sc.partial_fit(train_scaled, train_target, classes=classes) train_score.append(sc.score(train_scaled, train_target)) test_score.append(sc.score(test_scaled, test_target))

import matplotlib.pyplot as plt

plt.plot(train_score) 
plt.plot(test_score) 
plt.xlabel('epoch') 
plt.ylabel('accuracy') 
plt.show()
```
</grid>

<grid drag="46 60" drop="50 25" >
![](attachments/Pasted%20image%2020240423191251.png)
</grid>

---