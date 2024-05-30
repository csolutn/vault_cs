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
* 이해 : 합성곱 및 풀링 과정이 필요한 이유를 이해하고 설명할 수 있다.

---

## 합성곱 신경망의 연산 - filter(kernel)
### **예제1** 아래와 같은 input과 filter가 주어졌을 때 output을 계산하시오. (단, stride = (1, 1))