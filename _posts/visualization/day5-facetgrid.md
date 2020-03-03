데이터 시각화
===========
---
title: "day 5"
date: 2020-01-24
categories: blog
---

# 이번 강의에선 facetgrid를 배운다

이전의 커밋보다 조금 더 기술적인 부분에 대해서 다룰 것 같다..

facet grid는 말 그대로 분할의 느낌이다. 여러 항목들을 분할 해 봄으로써 조금더 세부적 접근이 가능해 진다는 것이 특징!


## 코드 첨부
<pre>
<code>
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd
sns.set(style="darkgrid")

tips = sns.load_dataset("tips")
g = sns.FacetGrid(tips, row="sex", col="time", margin_titles=True)
bins = np.linspace(0, 60, 13)
g.map(plt.hist, "total_bill", color="steelblue", bins=bins)
</code>
</pre>

## 코드 설명
이번에는 조금 테크니컬(?)하다고 할 수 있을 것 같다.. g에 facetgrid를 집어 넣고, g.map을 활용하여 plotting할 수 있는 것이다.
이를 더 활용할 수도 있을것 같은데, 만약 regplot을 그리고 싶다면, 
>g.map(sns.regplot, 'total_bill', 'smoker')
위와같은 방법으로도 표현할 수 있는것이다.

이밖에도 swarmplot이라던지, scatterplot을 활용할 수도 있다.

이걸 실행하면 여러개의 행과 열로 이루어진 그림들이 아웃풋으로 나오게 되는데, 요소별 시각화를 함으로써 더 세부적인 접근을 할 수 있다.

### 오늘은 설날인데... 독서실에서...
설날에도 독서실행 ㅠㅠㅠ 다음학기는 6전공.... 죽겠따...
