
<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=default"></script>

## Naive Bayes Classifiers
朴素贝叶斯分类器

### 简述

- 贝叶斯定理

y有k个分类，x为特征。

$$
P(y=c|x) = \frac{P(y=c)P(x|y=c)}{\sum_{c=1}^{K}{P(y=c)P(x|y=c)}}
$$

根据贝叶斯定理，我们可以使用数据$x$来预测$y=c$。只要能够知道先验分布$P(y=c)$, 似然分布$P(x|y=c)$,以及边缘分布
$$
P(x)=\sum_{c=1}^{K}{P(y=c)P(x|y=c)}
$$
即可。


- 朴素的意思是：直接假设特征之间是独立的，（尽管不一定是独立的），这样就能直接使用贝叶斯定理了。


- 极大似然估计

  - 极大似然估计就是，认为每个数据既然是从同一个模型产生的，并且这些数据彼此独立的。那么就可以找到最好的模型参数 $\theta$ 使这些独立的概率联合分布最大。
$argmax \prod P(D|h)$

  - 在贝叶斯定理的基础上，由于分母边缘分布是一个常数。求最大值可以省略。$P(h|D) \propto P(h)P(D|h)$

  -  似然 $P(D|h)$ 会随着数据量的增加指数减少，而先验分布 $P(D|h)$ 不随数据量变化，因此我们只关心似然。$P(h|D) \propto P(D|h)$, 因此 $argmax \prod P(h|D) = argmax \prod P(D|h)$

- 算法

  - 推断

  - 预测
