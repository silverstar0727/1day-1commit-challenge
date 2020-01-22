데이터 시각화
===========
---
title: "day 3"
date: 2020-01-20
categories: blog
---

# 이번 강의에선 scatter plot을 seaborn으로 plotting하는 법에 대해서 배운다.

## scatter plot은 직관적 도구로서 핵심적인 역할을 한다.
scatter plot은 사실 matplotlib으로도 충분히 할 수 있지만, 이번 강의를 통해서 조금더 쉬운 방법으로 plotting할 수 있다는 것을 배운당.
scatter plot이 수행하는 것들은 기본적으로 이상점을 확인 할 수도있고, 선형회귀를 한다면 선형회귀의 diagnosis에서
Influential observation이라고 불리는 영향관측값에 대한 것을 확인 할 수도 있다.
이는 선형회귀의 굉장히 큰 요인으로 작용하기 때문에 data set에서 elimination후 적용해야하고, 그렇기에 scatter plot은 기초적이지만,
중요한 역할을 한다고 볼 수 있다!!

## 코드 첨부
<pre>
<code>
import seaborn as sns
sns.set()

# Load the example iris dataset
planets = sns.load_dataset("planets")

cmap = sns.cubehelix_palette(rot=-.2, as_cmap=True)
ax = sns.scatterplot(x="distance", y="orbital_period",
                     hue="year", size="mass",
                     palette=cmap, sizes=(10, 200),
                     data=planets)
</code>
</pre>

## 코드 설명
사실 뭐 지난번과 크게 다를 게 없는 것은 마찬가지이다. 조금 특이한 점이 있다면 sctter plot의 palette 파라미터의 value를 보면 cmap으로 지정되어있다.
여기서 cmap은 위에 지정된 값인데, 밝기에 대한 정도를 나타낸 것이다.

이렇게 하면 좋은점이 무엇이냐!! 바로 프린트를 흑백으로 하더라도 수치에 대한 구분이 잘 간다는 것이다.

나머지는 크게 다를 것이 없당...

## 산점도, 직관적 해석
사실 학문의 모든 분야에서 직관적인 해석은 굉장히 중요하다 할 수 있다.
직관적으로 어떠한 경향성을 띠고 있는지 확인해야 문제에 대한 파악을 할 수 있기 때문이다.
이에 대한 논리적 논증은 추후의 일이 될 것이다. 그렇기 때문에 scatter plot은 더욱 중요하다.
해당 코드는 산점도를 크기별로하여 그 분포까지 알 수 있도록 해주었는데, 이를 통해 직관력을 더 올릴 수 있었다

## 함수에 내장된 parameter를 적극적으로 활용하자.
앞서 말한 것들을 실현시키기 위해서는 parameter를 적극적으로 활용해야 한다.
jupyter lab으로 코드를 실행하였는데, jupyter lab에서는 shift + tab을 누르면 그 함수 내부의 파라미터를 볼 수 있다.
만약 그게 여의치 않으면, "sns.sctterplot?"을 실행시키면 설명까지 볼 수 있으니 적극적으로 활용해보자.
