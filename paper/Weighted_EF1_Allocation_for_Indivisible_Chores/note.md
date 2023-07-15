### Weighted EF1 Allocations for Indivisible Chores

#### Question

m个不可分的任务给n个人，每个人都对任务有一个评估函数

定义 $X_i$ 是 $i$ 被分配到的任务, $i \in N$ 

#### Method

两种研究策略
- Allocation of goods  
- Allocation of chores (本文研究)

实际上就是 goods 是好的，人会倾向于去得到，chores 是不好的，人会倾向于避免。

agents 会对 chores 产生负的评估
agents 对每个 chores 产生非负的成本

- envy-freeness(EF): 分配后没有人想和其他人交换 $c_i(X_i) \leq c_i(X_j)$
- proportionality(PROP): 不会拿超过平均值的 $c_i(X_i) \leq \frac{1}{n} \cdot c_i(M)$

上述策略是不可分任务时不成立，例如 2个人 2个任务，显然能构造数据不成立。

- Envy-freeness up to one item（EF1）：envy 会在移除一个envious agent 的 bundle 后消失
- Envy-freeness up to any item (EFX) ：envy 会在从 bundle 里移除任何一个物品后消失
- PROP1
- PROPX


- Whether EFX allocations exist in general remains one of the biggest open problems.


### Result

- Result1: 对于事务分配给带权重倾向的人，存在一种计算WEF1分配的多项式时间算法。
- Result2: 对于将事务分配给带权重倾向的人，存在一个多项式时间算法，用于计算双值实例的WEF1和PO分配。
- Result3: 对于分配给加权代理的杂务，对于三个或三个以上代理，WEF1的价格是无界的, $\frac{4 + \alpha}{4}$ 是两个代理人的上界，$\alpha = \frac{max\{w_1, w_2 \} }{min\{ w_1, w_2\} }$


### 2. Preliminaries
形式上定义：
$m$个不可划分物品集合$M$，$n$个代理人集合为$N$，对于每个代理人都有 $i \in N$, $w_i > 0$, 并且 $\sum_{i \in N} w_i = 1$. 当 $w_i = \frac{1}{n}$, 这个问题称为 unweighted. 定义物品的子集$X \subseteq M$ 称为 bundle. 对于每个代理人还有一个**可累加**的花费函数 $c_i: 2^M \to \mathbb{R}^+ \cup \{0\}$, 给每个bundle 赋值。用 $c_i(e)$ 表示 $c_i(\{e\})$, 意义是第 i 个代理人对第 e 个物品的花费，因此 $c_i(X) = \sum_{e \in X} c_i(e) $, 对于所有 $X \subseteq M $. 不失一般性地，假设现在的花费函数是标准化的，那么 $c_i(M) = 1$. 用 $w = (w_1, \dots, w_n) $ 和 $c = (c_1, \cdots, c_n) $ 分别表示权重函数和花费函数。

为了简单表示，让 $X + e$ 和 $X - e$ 分别代表 $X \cup \{e\}$ 和 $X \\ \{e\}$，对于一个n部分的划分 $X = (X_1, \cdots X_n\} $，其中 $X_i \cap {X_j} = \empty$,且 $\cup _{i \in N} X_i = M$，这里指 代理人$i$ 分配了任务 $X_i\} $. 给一个 $I = $($N$, $M$, **w**, **c**), 我们希望给出一个分配 $X$ 对于所有代理人 $fair$.

思考：w 的意义是想让每个人单独直接有权重，类似于leader权重更高