## AIFFEL 프로젝트 발표 - 인공지능을 활용한 서술형 수학문제 풀이
https://www.youtube.com/watch?v=p_nJ91ssLcM
#### 분석
* koGPT2의 성능이 높음
* seq2tree모델의 경우 class1(단순 연산)에서 최고점
* OpenAI사의 verifier : 생성된 솔루션이 정답일 가능성을 측정하는 모델 
  (문제 푸는 성능은 0.22로 매우 낮음)
  
#### 효과가 있었던 실험 과정
* 데이터 정제 (틀린 데이터를 수작업으로 수정)
* random_int_aug

#### 결과 :  최고 Accuray score 0.52
* koGTP2 base
* 데이터 정제 후 randint 숫자 치환 data-augmentation
* batch_size = 128
* warmup_step = 400, weight_decay = 0.1

![|750](attachments/Pasted%20image%2020240418120129.png)

#### 수행가능한 문제 예시
가로가 15cm, 세로가 50cm인 직사각형의 둘레(또는 넓이)를 구하시오.
#### 결과

#### GPT-4의 결과
Prompt

가로가 15cm, 세로가 50cm인 직사각형의 둘레(또는 넓이)를 구하시오.

ChatGPT
---

가로가 15cm이고 세로가 50cm인 직사각형의 둘레는 130cm이고, 넓이는 750cm²입니다.
```
# 가로의 길이
width = 15
# 세로의 길이
height = 50

# 둘레 계산
perimeter = 2 * (width + height)
# 넓이 계산
area = width * height

perimeter, area

Result

(130, 750)
```
---