데이터 시각화
===========
---
title: "day 4"
date: 2020-01-23
categories: blog
---

# 이번 강의에선, residuals를 plotting한다.
>선형 회귀에서 y(bar) - y_i = (y(bar)-y(hat)_i) - (y_i - y(hat)_i)이다.
y(bar) : 모 회귀식
y_i : data
y(hat)_i : 추정 회귀식

SSE(Sum of Squares due to Errors)에 해당하는 부분, 즉 잔차에 대한 부분을 visualization하는 것이 해당 그래프라고 할 수 있다.
이는 잔차그림이라고도 하는데, 잔차그림의 역할은 마찬가지로 직관력에 대한 이해도를 높일 수 있다.

Multivariable Linear Regression에서 diagnosis의 항목은 다음과 같다.
1. 선형성
2. 독립성
3. 정규성
4. 다중공산성
5. 이상점
6. 영향관측값

이 중, residual plot은 독립성과 잔차 히스토그램은 정규성에대한 직관적 판단에 용이하다.


## 코드 첨부
<pre>
<code>
import numpy as np
import seaborn as sns
sns.set(style="whitegrid")

# Make an example dataset with y ~ x
rs = np.random.RandomState(7)
x = rs.normal(2, 1, 75)
y = 2 + 1.5 * x + rs.normal(0, 2, 75)

# Plot the residuals after fitting a linear model
sns.residplot(x, y, lowess=True, color="g")
</code>
</pre>

## 코드 설명
이도 그렇듯... 사실 크게 다를바가 없다. 여기서 rs는 RandomState를 지정한 것인데, 이를 7과 같이 지정하게 되면,
동일한 데이터가 생성되므로, 실행시켰을때 맞게 했는지 파악하기 쉽다.

그 밑에는 데이터셋을 numpy의 normal함수를 이용해 normalization을 하였다.

seaborn의 residplot함수를 이용하여 plotting하였는데, 여기서 lowess라는 parameter는 local regression에 해당한다고 할 수 있다.

## 말해뭐하겠냐만...
함수의 parameter를 하나하나 외우는 것보다는 그때그때 찾아서 쓰는게 가장 효율적이지 않을까 싶다...

회귀진단에 대해 많은 것을 알지는 못하지만, 그래도 대충은 알아둬야 나중에 큰 오차가 발생했을 때, influential observasion을 제거하거나, 
변수변환을 통해 각종 diagnosis의 항목들을 해결하는 실마리를 찾을 수 있다.

결국 머신러닝은 수학이자 통계가 아닐까 싶다 ㅠㅠ
