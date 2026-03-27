马约拉纳费米子(Majorana fermion)是一种反粒子就是自身的费米子，由埃托雷·马约拉纳(Ettore Majorana)在1937发表论文提出。
粒子物理里的马约拉纳费米子我不甚了解，但在凝聚态领域，马约拉纳费米子和拓扑超导可谓过去十数年来最热门的话题之一，其中的纷扰和争论更是前所未有，下面让我们一探究竟。
## 二次量子化
从二次量子化出发，费米子可以由产生算符$c_i^{\dagger}$和湮灭算符$c_i$描述，它们的作用和数数差不多，真空态记为$|0\rangle$，那么其中由一个费米子$i$的态就是$c_i^{\dagger}|0\rangle$，如果我们依次在$i=1$到$n$的模式上依序加入费米子，那么态可以写作$\prod_{i=1}^n c_i^\dagger |0\rangle$。需要注意的是，顺序很重要，不同顺序可能导致符号不同$\prod\limits_{i=1}^{n}c^{\dagger}_i|0\rangle$，虽然形式上复杂，但本质上只是描述哪些模式上有费米子，只不过由于反对称性需要关注顺序和符号，其实和数数一样，哪里有一个费米子，就记上一笔。而湮灭$c_i$就相当于一个橡皮，把记上的费米子擦掉。从这个理解出发，以下表达式都是直接的：
$$c_ic_i^{\dagger}|0\rangle=|0\rangle, c_i|0\rangle=0$$
当然和数数和橡皮有点区别的就是，由于费米子本身有交换反对称性和泡利不相容原理，上述算符遵循如下规则
$$\{c_i,c_j\}=0, \{c^{\dagger}_i,c^{\dagger}_j\}=0, \{c_i,c^{\dagger}_j\}=\delta_{ij}$$
即$c_ic_j=-c_jc_i, c^{\dagger}_ic^{\dagger}_j=-c^{\dagger}_jc^{\dagger}_i,c_ic^{\dagger}_j=-c_jc^{\dagger}_i(i\neq j)$(交换反对称)，$c_ic_i=0, c_i^{\dagger}c_i^{\dagger}=0$(泡利不相容)。$c_ic_i^{\dagger}+c^{\dagger}_ic_i=1$是个比较tricky的观察，但是我们注意到$c_ic_i^{\dagger}+c^{\dagger}_ic_i|0\rangle=|0\rangle, c_ic_i^{\dagger}+c^{\dagger}_ic_i\left(c^{\dagger}_i|0\rangle\right)=\left(c^{\dagger}_i|0\rangle\right)$，所以$c_ic_i^{\dagger}+c^{\dagger}_ic_i$作用在任何一个态上都不会改变这个态，所以等于1. 掌握了以上的运算规律，就可以严谨的描述一个费米子系统了！
文章的主角，马约拉纳费米子就是一类比较特殊的费米子，马约拉纳费米子(记其算符为$\gamma$)还满足$\gamma=\gamma^{\dagger}$，那么如何构造这种费米子呢，且看下文分解。
## 一维紧束缚模型
考虑一个一维费米子链，如下图，图中的圆表示费米子的site。
![[1D-tight-binding.png]]
首先，如果每一个费米子之间没有相互作用，那么实空间的哈密顿量可以写为
$$H=\sum_\limits{i=0}^{n}E_ic^{\dagger}_ic_{i}$$
非常好理解，因为$c^{\dagger}_ic_i|0\rangle=0, c^{\dagger}_ic_i\left(c^{\dagger}_i|0\rangle\right)=1$，那么上述哈密顿量作用在一个态上的时候就是把这个态上有费米子的地方的能量加起来。
然后，更进一步，我们可以在哈密顿量中加上一种费米子跃迁项，简便起见，只考虑相邻site之间的跃迁$tc^{\dagger}_ic_{i+1}+t^{*}c^{\dagger}_{i+1}c_{i}$，$t$表示跃迁的能量。哈密顿量变成了如下形式
$$H=\sum_\limits{i=1}^{n}E_ic^{\dagger}_ic_{i}+tc^{\dagger}_ic_{i+1}+t^{*}c^{\dagger}_{i+1}c_{i}$$
求解这个哈密顿量也是简单的，只需要将实空间的哈密顿量进行傅里叶变换，例如假设$E_i$相同，$H_k=\left(E+2|t|cos(ka)\right)c^{\dagger}_kc_k$，本征能量$E(k)=E+|t|cos(ka)$。
现在这个哈密顿量已经很复杂了，但想要神奇的事发生，需要更进一步，继续考虑加入超导相互作用$\Delta c^{\dagger}_{i+1} c^{\dagger}_{i}+\Delta^{*} c_{i+1}c_{i}$，哈密顿量到了非常复杂的
$$H=\sum_\limits{i=1}^{n}E_ic^{\dagger}_ic_{i}+tc^{\dagger}_ic_{i+1}+t^{*}c^{\dagger}_{i+1}c_{i}+\Delta c^{\dagger}_{i+1} c^{\dagger}_{i}+\Delta^{*} c_{i}c_{i+1}$$
如果初中知识还没忘的话，可以看到这个式子是可以因式分解的！为了看得更清楚一些，先算个$(c_i- c^{\dagger}_{i})(c_{i+1}+ c^{\dagger}_{i+1})$压压惊，熟练地运用费米算符的运算律
$$\begin{align*}(c_i- c^{\dagger}_{i})(c_{i+1}+ c^{\dagger}_{i+1})
&=c_ic_{i+1}+c_ic^{\dagger}_{i+1}- c^{\dagger}_{i}c_{i+1}-c^{\dagger}_{i}c^{\dagger}_{i+1}\\
&=-c^{\dagger}_ic_{i+1}-c^{\dagger}_{i+1}c_{i}+c^{\dagger}_{i+1}c^{\dagger}_{i}+c_ic_{i+1}
\end{align*}$$
其中几个符号的变化是因为交换反对称。终于拨云见日，为简便起见，取哈密顿量中$E_1=0$, $t=-\Delta$，那么哈密顿量即
$$H=\sum_{i=1}^{n}t(c_i- c^{\dagger}_{i})(c_{i+1}+ c^{\dagger}_{i+1})$$
如果记$\gamma_{2i-1}=c_i+c^{\dagger}_{i}$, $\gamma_{2i}=-\mathrm{i}\left(c_{i}- c^{\dagger}_{i}\right)$. ($2i-1$,$2i$代表奇偶)，显然，$\gamma_{2i-1}=\gamma^{\dagger}_{2i-1}$，$\gamma_{2i}=\gamma^{\dagger}_{2i}$，$\gamma_{2i-1}$和$\gamma_{2i}$都是马约拉纳费米子！并且有$\{\gamma_i,\gamma_j\}=2\delta_{ij}$.
此时
$$H=it\sum_{i=1}^{n}\gamma_{2j}\gamma_{2j+1}$$
如下图所示
![[majorana-mode.png]]
## 从平凡到拓扑
为求解哈密顿量$H=i\sum_{i=1}^{n}\gamma_{2j}\gamma_{2j+1}$，设$d^{\dagger}_i=\frac{\gamma_{2j}-\mathrm{i}\gamma_{2j+1}}{2}$, $d=\frac{\gamma_{2j}+\mathrm{i}\gamma_{2j+1}}{2}$
$$\begin{align*}d^{\dagger}_id_i
&=\frac{1}{4}\left(\gamma_{2j}\gamma_{2j}+\mathrm{i}\gamma_{2j}\gamma_{2j+1}-\mathrm{i}\gamma_{2j+1}\gamma_{2j}+\gamma_{2j+1}\gamma_{2j+1}\right)\\
&=\frac{1}{2}\left(\mathrm{i}\gamma_{2j}\gamma_{2j+1}+1\right)
\end{align*}$$
所以哈密顿量
$$H=t\sum_{i=1}^{n}(2d^{\dagger}_id_i-1)$$
这不就是最简单的一维紧束缚模型吗？于是通过$\gamma\to d$的变换，又将问题转化到了最简单的模型。于是该哈密顿量的基态就是$d_i|\psi\rangle=0 (t>0)$, $d^{\dagger}_i|\psi\rangle=0 (t<0)$. 换到$\gamma$表达即$\frac{\gamma_{2j}-\mathrm{i}\gamma_{2j+1}}{2}|\psi\rangle=0$, 即$\mathrm{i}\gamma_{2j}\gamma_{2j+1}|\psi\rangle=-|\psi\rangle$.
求解完了，看似平平无奇，但是回过头来定睛一看，哈密顿量里丝毫没有出现最左边和最右边的马约拉纳费米子$\gamma_1$和$\gamma_{2N}$，它们没有与任何东西耦合。任何局域的微扰都无法影响它们，所以它们是拓扑的！这就是马约拉纳零能模(Majorana zero modes)。
马约拉纳零能模是二重简并的，可以通过$\mathrm{i}\gamma_1\gamma_{2N}$的值$\pm 1$判断。
注意到$-\mathrm{i}\gamma_{2i-1}\gamma_{21}=-(c_1+c^{\dagger}_i)(c_i-c^{\dagger}_i)=1-2c^{\dagger}_ic_i=(-1)^{c^{\dagger}_ic_i}$，所以fermion parity
$$P_f=\prod_{i=1}^{n}(-\gamma_i\gamma_{i+1})$$
例如，在基态时，$\gamma_{i}\gamma_{i+1}(i\in[2,2N-2])$都是确定的，所以可以根据$P_f$得到$\mathrm{i}\gamma_1\gamma_{2N}$的信息，进而区分两个简并的零能模。
这个零能模只有在$|E|<2|t|$时成立(上述情况是$E=0$)，$|E|>2|t|$时，系统回归拓扑平庸态。
## 实验与争议
由上述情况可知，实验上实现马约拉纳费米子的要素是1D原子链+超导。所以在实验上有两条路径实现马约拉纳费米子1D半导体+超导，以及量子霍尔效应边缘态+超导。
2017年一篇[RETRACTED: Chiral Majorana fermion modes in a quantum anomalous Hall insulator–superconductor structure | Science](https://www.science.org/doi/full/10.1126/science.aag2792#tab-citations)与2018年一篇[RETRACTED ARTICLE: Quantized Majorana conductance | Nature](https://www.nature.com/articles/nature26142)在顶刊先后发表，宣称在量子反常霍尔效应(QAH)体系中发现了马约拉纳费米子，引起广泛关注。在多次复现无果后引起了怀疑，[Absence of evidence for chiral Majorana modes in quantum anomalous Hall-superconductor devices | Science](https://www.science.org/doi/10.1126/science.aax6361)更是直指要害，2022年，可惜的是上述两篇发现的文章因为涉嫌数据修饰和伪造而撤稿，更可惜的是，两位一作现正在top2进行tenure考察。我在还不知情时上过其中一位的普物实验课，和漩涡中心的人靠得如此之近，也颇有感触。
自这场风波之后，似乎大家都对majorana讳莫如深，[Quantum computing’s reproducibility crisis: Majorana fermions](https://www.nature.com/articles/d41586-021-00954-8)，以后的文章，也是渐渐用topological superconductivity代替majorana。但Microsoft团队今年3月发表的文章[Interferometric single-shot parity measurement in InAs–Al hybrid devices | Nature](https://www.nature.com/articles/s41586-024-08445-2)，宣称在1D半导体+超导中发现马约拉纳费米子，无疑是重新点燃了majorana的希望[Microsoft’s Majorana 1 chip carves new path for quantum computing - Source](https://news.microsoft.com/source/features/innovation/microsofts-majorana-1-chip-carves-new-path-for-quantum-computing/)。这一次，事情将会如何呢？