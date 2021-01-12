、

# Ch1


## 1

> G是简单图，则有$\varepsilon\left( G \right) \leq \left( \frac{v(G)}{2} \right)$

**方法1（Euler定理）**：

因为G是简单图 所以∀v∈V(G),有deg(v)≤v-1

则$\sum_{v \in V(G)}^{}{\deg\left( V \right) \leq v(v - 1)}$

由Euler定理，$\varepsilon\left( G \right) = \frac{\sum_{v \in V(G)}^{}{\deg\left( V \right)}}{2} \leq \frac{v\left( v - 1 \right)}{2}$，得证

**方法2（组合）：**

在简单图中，任意两顶点之间最多存在一条边

即$\varepsilon\left( G \right) \leq \left( \frac{v(G)}{2} \right)$







##  3

> 画出所有四个顶点不同够的简单图

一共11个（图略）。




## 4*

> 任何至少由两个人构成的群体中，其中有两个人，他们的朋友数一样多。

**证**：将每个人看作顶点，两个人是朋友则在这两人所代表的顶点之间加一条边，因此问题等价于：在对任意满足$V(G) \geq2$的图G中，存在$V_i,V_j \in V(G),i \ne j$，使得$ deg(v_i)=deg(v_j) $.

**反证法**：假设对任意$V_i,V_j \in V(G),i \ne j$，都有$ deg(v_i)\ne deg(v_j) $

deg(v)在G中共有\|V(G)\|个不同的取值

而deg(v)取值范围为0至\|V(G)\|-1，恰好有\|V(G)\|个可能的取值，故每种取值恰好出现一次，分别为0,1,...,
\|V(G)\|-1

所以存在$V_i,V_j \in V(G),i \ne j$，使得$deg(v_i)=0，deg(v_j)= \|V(G)\|-1$

即$v_i$与所有点都不相连，$v_j $与所有点都相连，矛盾，假设不成立。

得证。







## 5

> $2n(n \geq2)$人中，每个人至少与其中的n个人认识，则其中至少有4个人，使得这四个人围桌而坐时，每个人旁边都是他认识的人。

该问题等价于证明图中存在长度为4的圈，等价与存在2个人，他们共同认识的人有两个即以上。

用反证法容易证明。




## 7*

> 证明下面的结论：
>
> (1) $\epsilon(K_{m,n}) = mn$
>
> (2)设G是二分图，$\epsilon(G) \leq v^2(G)/4$

(1)证：不妨设 $ K_{m,n} = K \cup Y, X \cap Y =\emptyset $，其中\|X\|=m，\|Y\|=n

由$K_{m,n}$定义，$\forall u \in X, deg(u) =n$

$\forall v \in Y, deg(u) =m$

则$\sum_{v \in V(Km,n)}^{}{\deg\left( v \right) = \sum_{u \in X}^{}{\operatorname{deg(u)} + \sum_{v \in Y}^{}{\deg\left( v \right) = 2mn}}}$

由Euler定理，$\epsilon(K_{m,n}) = mn$

(2) $\epsilon(G) \leq \epsilon(K_{m,n}),V(G) = m+n$

由(1)可得 $\epsilon(K_{m,n}) = mn$

所以 $\epsilon(G)\leq mn \leq (m+n)^2/4$

即$\epsilon(G) \leq v^2(G)/4$





## 8

> 设G是图，给定$V(G)$的非空真子集V‘。记k为一个端点在V’中，另一个端点在$V(G)-V'$中的变数。若V'中度数为奇数的顶点数为偶数，则k为偶数；否则，k为奇数

设$\epsilon$是V‘的顶点导出子图的边的个数，则k有：
$$
k = \sum_{v \in V_o^{'}}^{}deg(v) + \sum_{v \in V_e^{'}}^{}deg(v) - 2 \epsilon
$$
因为 $2 \epsilon 和\sum_{v \in V_e^{'}}^{}deg(v)$一定是偶数，所以k的奇偶只和$ \sum_{v \in V_o^{'}}^{}deg(v) $有关：若V'中度数为奇数的顶点数为偶数，则k为偶数；否则，k为奇数。



## 9

> 每个顶点的度数都是2的连通图是一个圈。

用最长轨法来证明，设为$P(v_0,v_n)$，显然有$v_0$可得该图中必有圈，并且连接的必然是$v_n$ ，否则某个顶点的度数会是3。



## 10

> 证明活说明下面的结论：
>
> (1) 若$G^c = G$，则称G是自补图。证明：若G是自补图，则$\nu(G) \equiv0或1(mod4)$。
>
> (2)有多少个$\nu(G) = 5$的自补图。

由于同构可以得到如下的结果：
$$
\epsilon(G) = \epsilon(G^c) = \frac{1}{2}\epsilon(K_\nu) =\frac{1}{4}\nu (\nu-1)
$$
则必有：
$$
nu(G) \equiv0或1(mod4)
$$
自补图有2个。



## 11

> 构造以一个二分图G，使得G不与任何K维立方体的子图同构。其中，k为任意正整数。

$K_{1,k+1}$





## 12





## 13

> 任给图G，都满足$\delta(G) \leq 2\epsilon(G)/\nu(G) \leq \Delta(G)$

由定理得：
$$
\sum_{v  \in V(G)} deg(v) = 2 \epsilon(G)
$$
又因为：
$$
\nu \delta \leq \sum_{v  \in V(G)} deg(v) \leq \nu \Delta
$$
可得上述证明式子。





## 14*

> 我们将图G中所有定点的度数按照从大到小的顺序排列，称为图G的度数序列。证明：
>
> (1) 7,6,5,4,3,3,2   和 6,6,5,4,3,3,1都不是简单图的度数序列。
>
> (2) 设$d_1,d_2,\dots,d_n$是简单图的度数序列，则$\sum_{i=1}^{n}d_i$是偶数，且对于任意$1\leq k \leq n$，都有
> $$
> \sum_{i=1}^{k}d_i \leq k(k-1) +\sum_{i=k+1}^{n}min\{k,d_i\}
> $$

(1) 证明：从序列可以看出两个图顶点个数均为7

- 若是简单图，则必有$\Delta \leq 6$，但是存在度数为7的点，则`7,6,5,4,3,3,2`不是简单图。
- 若是简单图，则因为只有7个顶点，序列中的两个度数为6的顶点与图中每个点都相邻，则必有$\delta \geq 2$，但存在度数为1的 点，则不是简单图。

(2) 证明：由书上定理1.1可得
$$
\sum_{v  \in V(G)} deg(v) = 2 \epsilon(G)
$$
显然$\sum_{i=1}^{n}d_i$是偶数。

对于第二个证明式，设顶点依次是$v_1,v2,\dots,v_n$。

然后我们进行拆分，设$\sum_{i=1}^{k}d_i = D_1+D2$，其中：

- $D_1$是$v1,\dots,v_k$的顶导出子图 的度数之和。易得 $D_1 \leq k(k-1)$；
- $D_2$是$v1,\dots,v_k$之间$v_{k+1},\dots,v_n$连线数。并且$v_{k+1},\dots,v_n$ 可以给予的$v1,\dots,v_k$的最大的度数之和是：$\sum_{i=k+1}^{n}min\{k,d_i\}$，所以有：

$$
D_2 \leq \sum_{i=k+1}^{n}min\{k,d_i\}
$$

综上可得：
$$
\sum_{i=1}^{k}d_i = D_1+D2 \leq  k(k-1) +\sum_{i=k+1}^{n}min\{k,d_i\}
$$







## 15

> 任给无环图G，G有一个生成子图H，满足：(1) H是二分图；(2)任给$u \in V(G) = V(H)$，都有$d_H(u) \geq d_G(u)/2$

采用类似“最长轨”的思想，这里假设$H_K$是**边数最多**的二分生成子图$H_k$，并架设命题不成立。

根据假设，$H_K$里存在点$v_o \in V(G)$使得$d_H(v') \lt \frac{1}{2}d_G(v_0)$，并假设此二分图划分为X和Y，且$v_0 \in X$






## 16*

> 假设G是简单图 ，且$\delta(G)\geq k$，则 G中有长为k的轨道。

证明：此题用最长轨法证明，设$P(v_0, v_m)$是该图的最长轨。假设它的长度小于k，即$m \lt k$。

对于$v_0$，因为$\delta(G)\geq k$，除去与轨道$P(v_0, v_m)$上的顶点有连线外，$v_0$ 至少与轨道外的一个顶点的相邻，与最长轨的假设矛盾！

则 G的最长轨长度至少为k，所以存在长为k的 轨道。









## 19*

> (1)证明：任给$\epsilon \in E(G)$，都满足$\omega(G) \leq \omega(G-e) \leq \omega(G)+1$
>
> (2)说明：对于图G的任意顶点v，用$G-v$ 替代$G-e$，(1)中的公示未必成立。

(1)证明：假设e在连通片$G_1$中，若去掉后仍连通，则有：
$$
\omega(G) = \omega(G-e) \lt \omega(G)+1
$$
若使G1分成了两个连通片，则有：
$$
\omega(G) \lt \omega(G-e) = \omega(G)+1
$$
综上有：
$$
\omega(G) \leq \omega(G-e) \leq \omega(G)+1
$$


(2)举反例即可：

- 星
- 含有度数为0的顶点的图







## 26*

> 一个公司在六个城市$c_1,c2,\dots,c_6$有分公司，下面的矩阵$(i,j)$号元素是$c_i$到$c_j$的机票价格，试为该公司制作一张$c_1$ 到每个城市的路线图，使得每个城市的机票价格都最便宜。
> $$
> \begin{pmatrix}
>      0 & 50 & \infin & 40 & 25 & 10 \\
>      50& 0 &15 &20 &\infin &25 \\
>      \infin&15 &0 &10 &20 & \infin \\
>      40&20 &10 &0 & 10&25 \\
>    25  & \infin &20 &10 &0 &55 \\
>      10&25 & \infin &25 &55 &0 \\
> 
>      \end{pmatrix}
> $$



下面用表格来表示迭代

| 迭代次数i | $l(v_2)$ | $l(v_3)$ | $l(v_4)$ | $l(v_5)$ | $l(v_6)$ | S                             |
| --------- | -------- | -------- | -------- | -------- | -------- | ----------------------------- |
| 0         | 50       | $\infin$ | 40       | 25       | 10       | $v_1$                         |
| 1         | 50       | $\infin$ | 50       | 25       | 10       | $v_1, v_6$                    |
| 2         | 35       | 45       | 35       | 25       | 10       | $v_1, v_5, v_6$               |
| 3         | 35       | 45       | 35       | 25       | 10       | $v_1, v_2, v_5, v_6$          |
| 4         | 35       | 45       | 35       | 25       | 10       | $v_1, v_2,v_4, v_5, v_6$      |
| 5         | 35       | 45       | 35       | 25       | 10       | $v_1, v_2,v_3, v_4, v_5, v_6$ |



路径的答案不止一种：

- $v_2$ :$v_1 \rightarrow v_6 \rightarrow v_2$
- $v_3$:
  - $v_1 \rightarrow v_5 \rightarrow v_3$
  - $v_1 \rightarrow v_5 \rightarrow v_4\rightarrow v_3$
  - $v_1 \rightarrow v_6 \rightarrow v_4\rightarrow v_3$
- $v_4$:
  - $v_1 \rightarrow v_5 \rightarrow v_4$
  - $v_1 \rightarrow v_6 \rightarrow v_4$
- $v_5$:$v_1 \rightarrow v_5$
- $v_6$:$v_1 \rightarrow v_6$









