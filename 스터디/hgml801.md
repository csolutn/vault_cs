---
css: css/style.css
margin: 0.2
width: 1200
---
<grid drag="100 3" drop="0 5" bg="#555555">
ML Study<!-- element style="font-size:13pt;color:white;"pad="10px" -->
</grid>

<grid drag="100 50" drop="0 20">
# 합성곱 신경망의 구성요소
</grid>
<grid drag="100 5" drop="0 70" >
<center>컴퓨터교육과 정솔 <br>
2024.06.03.(화)</center>
</grid>

---
## 합성곱 신경망 (Convolution NN)

![](https://saturncloud.io/images/blog/a-comprehensive-guide-to-convolutional-neural-networks-the-eli5-way.webp)

### 학습 목표
* 정의 : **필터(Filter)**, 패딩(Padding), 스트라이드(Stride)
* 과정 : **합성곱(Convolution) 연산**, 풀링(Pooling) 연산

---

## 합성곱 신경망의 연산 
### **예제1** 다음과 같은 input과 filter가 주어졌을 때 output을 계산하시오. (단, stride = (1, 1))
![|350](atts/ex1.png)
### **문제1** 다음과 같은 input과 filter가 주어졌을 때 output을 계산하시오. (단, stride = (2, 2))
![|400](atts/q1.png)<!-- element style="margin-top:-20px;"-->


---
## 합성곱 연산과 필터의 역할
![|750](atts/f1.png)
![|750](atts/f2.png)<!-- element style="margin-top:-20px;"-->

---
## 패딩Padding
### 필요성 : 패딩이 없다면 모서리와 가운데 입력값이 연산에 반영되는 횟수에 차이가 나게 됨
### 패딩의 종류 : valid(패딩안함), same패딩
### **예제1**