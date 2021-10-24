# Ch5

## 1
> 分别求出$K_{2n}$和$K_{n,n}$中不同完美匹配的个数。

$K_{2n}$的完备匹配个数等于将$2n$个元素划分成$n$个大小为2的集合，个数为
$\frac{\prod_{i=0}^{n-1} \binom{2n-2i}{2}}{n!}=(2n-1)!!$
$K_{n,n}$的完备匹配可以对第一部分标号，第二部分与第一部分的匹配可以看成全排列，个数为$n!$.





## 2
>树至多有一个完备匹配

证明：
假设存在两个完备匹配$M$和$M'$，设$S=\{e|e \in M, e \notin M \bigcap M'\}，T=\{e|e \in M', e \notin M \bigcap M'\}$，$S$与$T$的顶点集合相同，任取一个顶点$u$，在$S$与$T$中各有一个与其相连的边，设这两条边的另一个顶点为$u_1, v_1$. 在$T$中有一条与$u_1$相连的边，在$S$中有一条与$v_1$相连的边，若这两条边的另一个顶点相同，设这个顶点为$v$，则$uu_1vv_1u$为圈，与树中无圈矛盾。若这两条边的顶点不同，设为$u_2, v_2$，以此类推，必然会出现顶点相同的情况，$uu_1u_2...u_kvv_k...v_2v_1u$为圈，与树中无圈矛盾。
故树之多有一个完备匹配。





## 7
>证明：二分图有完备匹配的充要条件是，对任意$S \in V\{G\}$，都有$\mid N(S) \mid \geq \mid S \mid$。这个条件对一般图是否成立？

证明：
设$V(G)=X \bigcup Y, X \bigcap Y=\emptyset, S_X=S \bigcap X, S_Y=S \bigcap Y$,
则$|S|=|S_X|+|S_Y|, |N(S)|=|N(S_X)|+|N(S_Y)|$.
（必要性）：
因为二分图$G$有完备匹配，所以$X$中的顶点都被许配。
由$Hall$定理，有$|N(S_X)| \geq |S_X|$. 同理，$|N(S_Y)| \geq |S_Y|$.
$|N(S)|=|N(S_X)|+|N(S_Y)| \geq |S_X|+|S_Y|=|S|$
（充分性）：
不妨设$|X| \geq |Y|$，取$S \subset X$，由$Hall$定理，存在匹配$M$，使得$X$中的顶点都被匹配。
$\because |X| \geq |Y|$
$\therefore Y$中的顶点也相应地都被匹配。所以匹配$M$即为二分图$G$的完备匹配。
对一般图不成立，例如$K_3$满足$|N(S)| \geq S$，但是没有完备匹配。





## 9

>矩阵的一行或一列称为矩阵的一条线。证明：0-1矩阵中包含所有1所需的最少线数等于没有两个1在同一条线上的1的最大个数

证明：对0-1矩阵$M$,构造相应的二分图G,$M_{ij}=1$指第i行代表的顶点与第j列代表的顶点相邻
则包含所有1的最小线数等价于二分图G的最小覆盖，不在同一线上的1的最大个数等价于二分图G的最大匹配
由二分图最小覆盖等于最大匹配得，这两者相等





## 13
>用$Tutte$定理来证明$Hall$定理。

$Tutte$定理：图$G$（G为一般图，不一定是二分图）由完备匹配$\Leftrightarrow \forall S \subseteq V(G)$，都有$o(G-S) \leq |S|$.
$Hall$定理：二分图$G, V(G)=X \bigcup Y$，且$X \bigcap Y=\emptyset$，存在将$X$中的顶点都许配的匹配$\Leftrightarrow \forall S \subseteq X$都有$|N(S)| \geq |S|$，其中$N(S)$为$S$的邻顶集合。
证明：
对二分图$G=(X,Y,E)$，当$v$为偶数时，加一些边使得$Y$为完全图；当$v$时奇数时，加一些边和顶点$y_0$使得$Y \bigcup y_0$是完全图。图$G$变成完全图$H$，$G$中存在将$X$中所有顶点都许配的匹配的充要条件是$H$有完备匹配。此时$Hall$定理等价于$H$有完备匹配的充要条件是$\forall S \subseteq X, |N_H(S)| \geq |S|$.
（必要性）：
$\forall S \subseteq X$, 由$Tutte$定理，$o(H-N_H(S)) \leq |N_H(S)|$
在$H-N_H(S)$中，$S$中点都是孤立点，所以$|S| \leq o(H-N_H(S))$
$\therefore |N_H(S)| \geq |S|$.
（充分性）：
对$\forall S \subseteq V(H)$，并设$S=S_1 \bigcup S_2$，且$S_1 \bigcup X, S_2 \bigcup Y$.
因为$Y$是一个完全图，则在$H$中删去$S_1$不会增加连通片个数，且最多产生一个奇片. 删去$S_2$可能会使得$X$中有孤立顶点，设此时$X$中的孤立顶点为$S_3$，则$|N(S_3)| \leq |S_2|$，则有$|S_3| \leq |N(S_3)| \leq |S_2|$
若$|S_3|=|S_2|$，则$o(H-S_2)=|S_3|=|S_2|$；
若$|S_3| \leq |S_2|-1$，则$o(H-S_2) \leq |S_3|+1 \leq |S_2|$；
若$|S_1|$为偶数，则$o(H-S)=o(H-S_2) \leq |S_2| \leq |S|$；
若$|S_1|$为奇数，则$o(H-S)=o(H-S_2)+1 \leq |S_2|+1 \leq |S|$；
综上，对$\forall S \subseteq V(H)$，都有$o(H-S) \leq |S|$. 由$Tutte$定理，$H$为有完备匹配的图。





## 14
>证明：树$T$有完备匹配，当且仅当对任意$v \in V(T)$，都有$o(T-v)=1$。

证明：
（必要性）：
$\because$树T有完备匹配，由$Tutte$定理，$\forall S \subseteq V(T)$, 都有$o(T-S) \leq |S|$.
令$S=\{v\}$，则$o(T-v) \leq 1$.
由于树T由完备匹配，即$|T|$为偶数，则$|T-v|$为奇数。
$\therefore o(T-v) \geq 1$.
综上，$o(T-v)=1$.
（充分性）：
$\forall v \subseteq V(T)$，都有$o(T-v)=1$，则$V(T)$为偶数。
删去$v$后，树$T$被划分成若干个连通片，且只有一个连通片为奇片，设奇片中与$v$相连的顶点为$u$，在树$T$中，确定一个$v$后，由于$o(T-v)=1$，所以$u$被唯一确定。
$\therefore e=uv$被唯一确定。
$\because v$是任意的
$\therefore$ 所有$v$相对应的$e$的集合就是T的完备匹配。
综上，树$T$具有完备匹配。





## 17
>设有四个人$A, B, C, D$，有四分工作$a, b, c, d$，每个人做某份工作的效率如下面的矩阵所示，试求最佳的工作分配方案

![Ch5-17-1](./images/Ch5-17-1.png)
按照$Kuhn-Munkreas$算法一步步计算即可。
构造相等子图$G_l$
![Ch5-17-2](./images/Ch5-17-2.png)
$G_l$无完备匹配，取D为未被许配的点，可得：
$Z=\{B, D, c\}$
$S=\{B, D\}$
$T=\{c\}$
$\alpha_l=6$，重新构造相等子图：
![Ch5-17-3](./images/Ch5-17-3.png)
最佳分配方案为：$A-a, B-d, C-b, D-c, \omega=99+87+93+86=365$.





## 19
>证明：$Kuhn-Munkreas$算法中修改顶标后，$\widehat{l}$仍然是可行顶标。

证明：
修改的可行顶标
$$
\widehat{l}=
\begin{cases}
l(v)-\alpha_l& \text{v ∈ S}\\
l(v)+\alpha_l& \text{v ∈ T}\\
l(v)& \text{其他}
\end{cases}
$$
$\alpha_l = min_{x \in S, y \notin T}\{l(x) + l(y) - \omega(x,y)\}$

对$\forall v \in S, u \in Y$,
(1) 若$u \in T$，则$\widehat{l}(v)+\widehat{l}(u)=l(v)-\alpha_l+l(u)+\alpha_l=l(v)+l(u) \geq \omega(u,v)$.
(2) 若$u \in Y \bigcap u \notin T$，
$\because \alpha_l \leq l(v) + l(u) - \omega(u,v)$，
$\therefore \widehat{l}(v)+\widehat{l}(u)=l(v)-\alpha_l+l(u) \geq l(v)+l(u)-(l(v)+l(u)-\omega(u,v)) \geq \omega(u,v)$.
对$\forall v \notin S, u \in Y$,
$\widehat{l}(v)=l(v), \widehat{l}(u) \geq l(u), \widehat{l}(v)+\widehat{l}(u) \geq \omega(u,v)$.
综上，$Kuhn-Munkreas$算法修改顶标后，$\widehat{l}$仍然是可行顶标。