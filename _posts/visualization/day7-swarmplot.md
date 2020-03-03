데이터 시각화
===========
---
title: "day 7"
date: 2020-01-26
categories: blog
---

# 이번 강의는 swarmplot에 대해서 다룬다.
swarmplot은 scatterplot의 일종이다. 일반적인 scatterplot을 조금 변형한 형태랄까...?

세부 항목에 대해 종류를 나누고 그에 따라서 swarmplot을 plotting하면 세부항목과 관련된 산점도의 분산정도를 볼 수 있다.
코드를 보면서 설명하는게 더 빠를 것 같당...

## 코드 첨부
<pre>
<code>
import pandas as pd
import seaborn as sns
sns.set(style="whitegrid", palette="muted")

# Load the example iris dataset
iris = sns.load_dataset("iris")

# "Melt" the dataset to "long-form" or "tidy" representation
iris = pd.melt(iris, "species", var_name="measurement")

# Draw a categorical scatterplot to show each observation
sns.swarmplot(x="measurement", y="value", hue="species",
              palette=["r", "c", "y"], data=iris)
</code>
</pre>

## 코드 설명
여기서 iris data를 pd.melt 즉, pandas의 melt메소드를 통해 data를 변형하는 것을 볼 수 있는데, 
이렇게 해야만, 세부 항목에 대해 종류를 나눌 수 있고 swarmplot을 사용하는 효과를 볼 수 있다.

마찬가지로 seaborn의 swarmplot을 사용하는데 여기서 x축은 measurement y축은 value hue는 species로 지정하여 데이터를 plotting하였다.

## 너무 짧아서 violinplot하고도 비교를 해보자
뭐 사실 violinplot하고 크게 다를 것이 없다. violinplot은 연속적인 그래프였다면, swarmplot은 이산적인 그래프라고 볼 수 있다.

## 코드 첨부2
<pre>
<code>
import seaborn as sns
sns.set(style="whitegrid", palette="pastel", color_codes=True)

# Load the example tips dataset
tips = sns.load_dataset("tips")

# Draw a nested violinplot and split the violins for easier comparison
sns.violinplot(x="day", y="total_bill", hue="smoker",
               split=True, inner="quart",
               palette={"Yes": "y", "No": "b"},
               data=tips)
sns.despine(left=True)

sns.swarmplot(x = 'day', y = 'total_bill', hue = 'smoker', data = 'tips')
</code>
</pre>

## 코드 설명
swarmplot이전까지는 기존의 violinplot과 다를 것이 없다. 동일한 데이터를 가지고 swarmplot으로 plotting했을때의 결과를 violinplot과
비교해보면, 상당히 유사하다는 것을 볼 수 있다.

## 각각의 장단점
violinplot은 각각요소에 대해서 가운데를 기준으로 확연하게 나눠놔서 조금 더 시각화의 효과가 크다고 볼 수 있다.
swarmplot의 경우, 파란점과 주활색점이 섞여잇는 것을 볼 수 있는데. 이는 혼동의 여지가 있다.
따라서 나는 시각화와 관련해서는 violinplot을 권장한당!!

### 설날 마지막날...
다들, 새해복 많이받으세욥.!
