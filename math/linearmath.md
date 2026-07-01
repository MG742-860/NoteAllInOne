# 第一章 行列式
## 行列式的定义
### 前置概念
* 排列：把$n$个不同元素排成一列，称为这$n$个元素的$n$级排列，简称**排列**，一共有$n!$种不同的排列。
* 逆序：一个$n$级排列中不管是不是相邻，只要是前面有一个数比他大，那么那个大的数和这个数就构成一个**逆序**，一个排列的逆序总数称为该排列的**逆序数**。记为$\tau(n)，n$指的是一个排列。
* 对换：排列中对任意的两个数进行位置调换，就称为对排列进行了一次**对换**。
* 奇/偶排列：排列的逆序数是奇的还是偶的。
>对排列进行一次对换，排列的奇偶性就发生一次改变。
### 行列式的计算
对角线法则：主减副，只适用于二、三阶行列式。

对于三阶以上的四五六阶，就只能使用以下方法：
$$
\begin{aligned}
    &\begin{vmatrix}
        &a_{11} &a_{12} &\dots &a_{1n} \\
        &a_{21} &a_{22} &\dots &a_{2n} \\
        &\vdots &\vdots & &\vdots \\
        &a_{n1} &a_{n2} &\dots &a_{nn}
    \end{vmatrix} = \sum_{j_1j_2\dots j_n}(-1)^{\tau(j_1j_2\dots j_n)}a_{1j_1}a_{2j_2}\dots a_{nj_n}\\
    &1. 每项a_{1j_1}a_{2j_2}\dots a_{nj_n}表示不同行不同列的n个元素相乘。 \\ 
   &2.每项的符号取决于逆序数(-1)^{\tau(j_1j_2\dots j_n)}。\\
   &3.\sum_{j_1j_2\dots j_n}表示一共有n!项相加。
\end{aligned}
$$
因为是不同行不同列相乘，所以可以使用树形图法：

>对于三角行列式(上、下三角行列式)，其值就等于主对角元素之积，根据具体情况确定前面的符号$(-1)^{\tau(n)}$
## 行列式的性质
1. 行列式的行与列互换，也就是转置，其值不变。
2. 行列式任意两行（或者列）进行互换，行列式的值变号。
3. 行列式的行（或者列）中提取出一个公因子，可以将其提取到行列式外。
$$
\begin{aligned}
    \begin{vmatrix}
        & a_{11} &a_{12} \\ &3a_{21} &3a_{22}
    \end{vmatrix}=3 \begin{vmatrix}
        & a_{11} &a_{12} \\ &a_{21} &a_{22}
    \end{vmatrix}
\end{aligned}
$$
>行列式某一行或者一列的所有元素都是零，则该行列式为零。

4. 行列式中有任意两行（或者列）成比例，则该行列式的值为零。
5. 行列式的某一行（或者列）的元素均为两数之和，则这个行列式可以拆成两个行列式：
$$
\begin{vmatrix}
    & &* &  \\ &a_{i1}+b_{i1} &a_{i2}+b_{i2} &\dots & a_{in}+b_{in} \\ & &* &
\end{vmatrix}=\begin{vmatrix}
    & &* &  \\ &a_{i1} &a_{i2} &\dots & a_{in} \\ & &* &
\end{vmatrix}+\begin{vmatrix}
    & &* &  \\ &b_{i1} &b_{i2} &\dots & b_{in} \\ & &* &
\end{vmatrix}
$$
6. 把行列式的某一行（或者列）乘以$k$倍后加到另一行（列）中，行列式的值不变。
## 行列式的展开
1. 余子式：去掉行列式的$a_{ij}$所在的行和列后剩下的$(n-1)$行和列所构成的新的$(n-1)$阶行列式，称为$a_{ij}$的余子式，记为$M_{ij}$。
2. 代数余子式：$N_{ij}=(-1)^{i+j}M_{ij}$
>$a_{ij}、M_{ij}、N_{ij}$三者没有大小关系。
3. 行列式展开定理：行列式的值等于他任意一行或者一列进行对应元素乘以其代数余子式的乘积求和的值。
$$
\begin{aligned}
    D&=a_{i1}N_{i1}+a_{i2}N_{i2}+\dots+a_{in}N_{in}
    =a_{1j}N_{1j}+a_{2j}N_{2j}+\dots+a_{nj}N_{nj} \\ \\
    &D=\begin{vmatrix}
        &a_{11} & a_{12} &\dots &a_{1n} \\
        &\vdots &\vdots &\vdots &\vdots \\
        &a_{i1} & a_{i2} &\dots &a_{in} \\
        &\vdots &\vdots &\vdots &\vdots \\
        &a_{n1} & a_{n2} &\dots &a_{nn} \\
    \end{vmatrix}\stackrel{按第i行}{\underset{展开}{=}}a_{i1}N_{i1}+\dots+a_{in}N_{in}=\sum_{j=1}^na_{ij}N_{ij}
\end{aligned}
$$
*** 
$$
\begin{aligned}
&\text{例. 设 } D = \begin{vmatrix} 3 & 0 & 4 & 0 \\ 2 & 2 & 2 & 2 \\ 0 & -7 & 0 & 0 \\ 5 & 3 & -2 & 2 \end{vmatrix}, \text{ 求 } (1) N_{41}+N_{42}+N_{43}+N_{44}, \quad (2) M_{41}+M_{42}+M_{43}+M_{44}.
\\
&\text{解：替换法：}
\\
&(1) \quad N_{41}+N_{42}+N_{43}+N_{44} = \begin{vmatrix} 3 & 0 & 4 & 0 \\ 2 & 2 & 2 & 2 \\ 0 & 7 & 0 & 0 \\ 1 & 1 & 1 & 1 \end{vmatrix} = 0.\\
& \quad 这里就是把所求的代数余子式的系数回代到原行列式计算
\\
&(2) \quad \text{由 } N_{ij} = (-1)^{i+j} M_{ij}, \text{ 则 } M_{ij} = (-1)^{i+j} N_{ij}.
\\
&\quad M_{41} = (-1)^{4+1} N_{41} = -N_{41}.
\\
&\quad M_{41}+M_{42}+M_{43}+M_{44} = -N_{41}+N_{42}-N_{43}+N_{44}.
\\
&\quad M_{41}+M_{42}+M_{43}+M_{44} = -N_{41}+N_{42}-N_{43}+N_{44} = \begin{vmatrix} 3 & 0 & 4 & 0 \\ 2 & 2 & 2 & 2 \\ 0 & -7 & 0 & 0 \\ -1 & 1 & -1 & 1 \end{vmatrix}.
\\
&\quad \text{展开按第三行：} = (-7)(-1)^{3+2} \begin{vmatrix} 3 & 4 & 0 \\ 2 & 2 & 2 \\ -1 & -1 & 1 \end{vmatrix} = 7 \begin{vmatrix} 3 & 4 & 0 \\ 2 & 2 & 2 \\ -1 & -1 & 1 \end{vmatrix}.
\\
&\quad r_2 - 2r_3: \text{ 得 } 7 \begin{vmatrix} 3 & 4 & 0 \\ 4 & 4 & 0 \\ -1 & -1 & 1 \end{vmatrix}.
\\
&\quad \text{再按第三列展开：} = 7 \begin{vmatrix} 3 & 4 \\ 4 & 4 \end{vmatrix} = 7(12 - 16) = -28.
\end{aligned}
$$
>行列式某一行（或者列）乘以另一行的代数余子式再求和，结果为零。
>利用替换法你会发现结果中的行列式是对应成比例的，所以为零。
## 典型行列式
### 范德蒙德行列式
第一行全是1，第二行就是不同的数，后面每一行都是前面行的$n$次方：
$$
\begin{aligned}
    \begin{vmatrix}
        &1 &1 &\dots &1 \\ &x_1 &x_2 &\dots &x_n \\
        &\vdots&\vdots & &\vdots \\ &x_1^{n-1} &x_2^{n-1} &\dots &x_n^{n-1}
    \end{vmatrix}
\end{aligned}
$$
* 第一行（或者列）全是1，因为是0次方
* 每列（或者行）元素为等比数列，公比在第二行（列）
* 结果是所有公比元素做差再相乘。（$x_{大}-x_{小}$，注意是下标大小而不是$x$本身大小）
### 三对角线性
两种方法：化为三角形法，递推法

1. 化为三角形法：利用行列式的初等变换与性质将其化为三角行列式
2. 递推法：就是行列式展开（对应元素乘以代数余子式再求和）套娃
### 分块的三角行列式
$$
\begin{aligned}
    &\begin{vmatrix}
        &A_n &0 \\ &* &B_m
    \end{vmatrix}=|A|\cdot |B|=\begin{vmatrix}
        &A_n &* \\ &0 &B_m
    \end{vmatrix}\quad（拉普拉斯公式）\\
    &\quad上述的A、B都是行列式，和分块矩阵一样分块了而已。\\
    &推广：\begin{vmatrix}
        &0 &A_n \\ &B_m &0
    \end{vmatrix}=(-1)^{m\cdot n}|A||B|=\begin{vmatrix}
        &* &A_n \\ &B_m &0
    \end{vmatrix}=\begin{vmatrix}
        &0 &A_n \\ &B_m &*
    \end{vmatrix}
\end{aligned}
$$
## 克拉默法则
$$
\begin{aligned}
    &设n元非齐次方程组：\left\{\begin{aligned}
        &a_{11}x_1+a_{12}x_2+\dots+a_{1n}x_n=b_1 \\
        &a_{21}x_1+a_{22}x_2+\dots+a_{2n}x_n=b_2 \\
        &\dots \quad \dots \\
        &a_{n1}x_1+a_{n2}x_2+\dots+a_{1n}x_n=b_n \\
    \end{aligned} \right.其系数行列式D=\begin{vmatrix}
        &a_{11} & a_{12} &\dots &a_{1n} \\
        &a_{21} & a_{22} &\dots &a_{2n} \\
        &\vdots &\vdots &\vdots &\vdots \\
        &a_{n1} & a_{n2} &\dots &a_{nn} \\
    \end{vmatrix} \quad\rightarrow Ax=b\\
    &如果其D\neq0，则方程组有唯一解：x_1=\frac{D_1}{D}，x_2=\frac{D_2}{D}，\dots，x_n=\frac{D_n}{D}\\
    &D_j表示用常数列b=(x_1,x_2,...,x_n)^T替换系数行列式中的第j列得到的行列式 \\
    &D=0时方程有无穷解或只有零解 \\ \\
    &对于齐次：Ax=0\rightarrow\left\{\begin{aligned}
        |A|\neq0\Leftrightarrow只有零解 \\
        |A|=0\Leftrightarrow有非零解
    \end{aligned}\right.
\end{aligned}
$$
# 第二章 矩阵
## 基础
加法、乘法，没有除法，矩阵的幂运算和一般数的幂运算一样。

**转置**：对称矩阵：$A^T=A$，反对称矩阵：$A^T=-A$。
$$
\begin{aligned}
    (A^T)^T=A,\quad (A+B)^T=A^T+B^T,\quad (kA)^T=kA^T,\quad (ABC)^T=C^TB^TA^T
\end{aligned}
$$
**行列式：** 矩阵$A$的行列式记为$|A|、det(A)$。$|A|$=0就称其为奇异的，否则为非奇异的。
### 矩阵行列式小寄巧
1. $|A^T|=|A|$
2. $|kA_{n\times n}|=k^n|A|$
3. $|AB|=|A|\cdot|B|$
## 伴随矩阵
### 基础定义
$$
\begin{aligned}
    &（1）设A_{3\times3}=\begin{pmatrix}
        &a_{11} &a_{12} &a_{13} \\ &a_{21} &a_{22} &a_{23} \\ &a_{31} &a_{32} &a_{33}
    \end{pmatrix}，称A^*=\begin{pmatrix}
        &A_{11} &A_{12} &A_{13} \\ &A_{21} &A_{22} &A_{23} \\ &A_{31} &A_{32} &A_{33}
    \end{pmatrix}^T为矩阵A的伴随矩阵。 \\
    &\qquad注意这里A^*=\begin{pmatrix}
        &A_{11} &A_{21} &A_{31} \\ &A_{12} &A_{22} &A_{32} \\ &A_{13} &A_{23} &A_{33}
    \end{pmatrix}，与正常排序不一样，为了和正常排序一样所以加了转置方便记忆。\\
    &（2）其中A_{ij}是|A|中元素a_{ij}的代数余子式，注意这里A是行列式，代数余子式前面有(-1)^{i+j}符号：A_{ij}=(-1)^{i+j}\cdot M_{ij}\\ \\
    &\quad二阶快速计算：A=\begin{pmatrix}
        a &b \\ c &d
    \end{pmatrix}=\begin{pmatrix}
        d &-c \\ -b &a
    \end{pmatrix}，两对角线互换，副对角线反号
\end{aligned}
$$
### 一些性质
$AA^*=A^*A=|A|\cdot E$，展开后就会发现这是某行乘以它的代数余子式，一共三行：
$$
\begin{aligned}
    AA^*=\begin{pmatrix}
        a_{11} &a_{12} &a_{13} \\ a_{21} &a_{22} &a_{23} \\ a_{31} &a_{32} &a_{33}
    \end{pmatrix}\begin{pmatrix}
        A_{11} &A_{21} &A_{31} \\ A_{12} &A_{22} &A_{32} \\ A_{13} &A_{23} &A_{33}
    \end{pmatrix}=\begin{pmatrix}
        |A| &0 &0 \\ 0 &|A| &0 \\ 0 &0 &|A|
    \end{pmatrix}=|A|\cdot E
\end{aligned}
$$
## 逆矩阵
### 定义
对于一个$n阶方阵A，存在一个同阶矩阵B，使得AB=E(或BA=E)，则称A是可逆的，且称B为A的逆矩阵，记为A^{-1}，即B=A^{-1}，A=B^{-1}$。


**拓展结论：**
* 如果矩阵可逆，那么这个矩阵的逆唯一。
* $ABC=E，ABC都可逆，有A^{-1}=BC，B^{-1}=CA，C^{-1}=AB$
### 小寄巧
#### 充要条件
* 矩阵$A可逆\Leftrightarrow|A|\neq0$
* 矩阵$A可逆，则A^{-1}=\frac{1}{|A|}A^*$
#### 性质
* 矩阵$A可逆\Rightarrow(A^{-1})^{-1}=A，并且|A^{-1}|=\frac{1}{|A|}$
* $k\neq0时，(kA)^{-1}=\frac{1}{k}A^{-1}$
* 如果$A、B均可逆，则(AB)^{-1}=B^{-1}A^{-1}。类似的：(ABC)^{-1}=C^{-1}B^{-1}C^{-1}$
* 如果$A可逆\Rightarrow A^T，A^*也可逆，且(A^T)^{-1}=(A^{-1})^T，(A^*)^{-1}=(A^{-1})^*=\frac{1}{|A|}A$

#### 某些推论
有$n$阶方阵：

1. $A^*=|A|\cdot A^{-1}$
2. $|A^*|=|A|^{n-1}$
3. $(kA)^*=k^{n-1}A^*$
4. $(AB)^*=B^*A^*$
5. $(A^*)^T=(A^T)^*$
6. $(A^*)^*=|A|^{n-2}\cdot A$
## 分块矩阵
### 分块矩阵运算：

1. 相加：不仅大矩阵要同形，小矩阵也要，然后对应位置相加。
2. 乘法：常数和平常的一样，矩阵间相乘也要满足大矩阵和小矩阵在行列上都满足定义，然后按照平常的乘法去相乘。
3. 转置：大矩阵转置后，内部小矩阵也要转置。

### 求逆
$$
\begin{aligned}
    （1）&设A=\begin{pmatrix}
        A_1 &0 \\ 0 &A_2
    \end{pmatrix}，如果A_1、A_2可逆\Rightarrow A^{-1}=\begin{pmatrix}
        A_1^{-1} &0 \\ 0 &A_2^{-1}
    \end{pmatrix} \\ \\
    （2）&设A=\begin{pmatrix}
        0 &A_1 \\ A_2 &0
    \end{pmatrix}，如果A_1、A_2可逆\Rightarrow A^{-1}=\begin{pmatrix}
        0 &A_1^{-1} \\ A_1^{-1} &0 
    \end{pmatrix} \\ \\
    （3）&A、B均可逆，则\begin{pmatrix}
        A &0 \\ C &B
    \end{pmatrix}^{-1} = \begin{pmatrix}
        A^{-1} &0 \\ -B^{-1}CA^{-1} &B^{-1}
    \end{pmatrix}
\end{aligned}
$$
## 矩阵初等变换
### 初等变换方法
1. 交换两行、两列
2. 某行/列乘以数$k$
3. 某一行/列乘以数$k$后再加到另一行/列中
>求解方程的时候，变换尽量用行变换，这样对应未知数$x_1、x_2…$不会把位置搞混。
### 初等矩阵
#### 定义
**初等矩阵**就是单位矩阵进行一次初等变换后的矩阵。

初等矩阵分类：
* 初等交换阵：$E_{23}$，表示单位阵第2、3行/列进行了交换（两者结果一样）
* 初等数乘阵：$E_2(k)$，表示单位阵第2行/列乘以了数$k$
* 初等倍加阵：$E_{12}(k)$，表示第1行乘以数$k$后再加到第2行上，或者第2行乘以数$k$再加到第1行上

#### 作用
>作用就是将矩阵$A$进行对应的一次初等变换，比如左乘一个初等行/列变换阵$P$，相当于对$A$进行了一次和$P$一样的初等行变换。如果是右乘，那就是初等列变换。
>“左行右列”
#### 求逆
1. 初等矩阵的逆还是初等矩阵
2. 初等交换阵的逆是它本身，没有任何变换，逆就是自己
3. 初等数乘阵的逆就是其本身“取倒数”：
$$
\begin{aligned}
    P=\begin{pmatrix}
        1 &0 &0 \\ 0 &2 &0 \\ 0 &0 &1
    \end{pmatrix}，那么其逆P^{-1}=\begin{pmatrix}
        1 &0 &0 \\ 0 &\frac{1}{2} &0 \\ 0 &0 &1
    \end{pmatrix} \\
    对应数乘位置进行倒数
\end{aligned}
$$
4. 初等倍加阵，其逆就是“取负号”：
$$
\begin{aligned}
    P=\begin{pmatrix}
        1 &0 &0 \\ 3 &1 &0 \\ 0 &0 &1
    \end{pmatrix}，那么其逆P^{-1}=\begin{pmatrix}
        1 &0 &0 \\ -3 &1 &0 \\ 0 &0 &1
    \end{pmatrix} \\
    对应数乘位置求相反数
\end{aligned}
$$
### 利用初等变换求矩阵的逆
构造矩阵$(A|E)$，对$A$进行初等**行**变换，当$A$变成单位阵时，$E$也就变成了$A^{-1}：(E|A^{-1})$
>推广：$(A|B)进行对A求E后，会变为：(E|A^{-1}B)$
### 矩阵的等价
#### 定义
如果矩阵$A$能通过有限次初等变换变成矩阵$B$，就称$A、B$是等价的，记为：$A\cong B$

关于等价有三种说法：

1. $A\cong B\Leftrightarrow A$经过一系列初等变换化成$B$
2. $A\cong B\Leftrightarrow$存在一些初等阵$E_1···E_n与F_1···F_s$，使得$E_1···E_nAF_1···F_s=B$
3. $A\cong B\Leftrightarrow$存在可逆阵$P,Q$使得$PAQ=B$

#### 性质
1. 反身性：$A=A$，自身等价
2. 对称性：如果$A\cong B，那么B\cong A$
3. 传递性：如果$A\cong B，B\cong C，那么有A\cong C$
### 一些特殊矩阵
1. 行阶梯矩阵：矩阵中每一行的非0首元所在的列比下一行的非0首元靠前。比如$\begin{pmatrix}
    1 &2 &2 &4 \\ 0 &1 &2 &3 \\ 0 &0 &1 &2
\end{pmatrix}$
2. 行最简形：每一行的非0首元为1，且非0首元所在的列的其他元素为0。比如$\begin{pmatrix}
    1 &0 &3 &4 \\ 0 &1 &2 &1 \\ 0 &0 &0 &0
\end{pmatrix}$、$\begin{pmatrix}
    1 &0 &0 &4 \\ 0 &1 &0 &1 \\ 0 &0 &1 &2
\end{pmatrix}$
## 矩阵的秩
### k阶子式
$设A_{m\times n}，任取k行k列的支点上的k^2个元素，按照原顺序构成的k阶行列式成为矩阵A的一个k阶子式$
$$比如A=\begin{pmatrix}
    1 &2 &2 &3 \\ 0 &1 &2 &3 \\ 0 &0 &0 &0
\end{pmatrix}：（1）A中不含4阶子式、（2）A中所有3阶子式全为0、（3）A中有2阶子式不为0$$
### 秩
#### 定义
$矩阵A中有一个r阶子式不为0，但是所有的r+1阶子式全为0，则称r为矩阵A的秩，记为r(A)=r，或者R(A)=r$

>实际意义：秩的大小就是方程组中有效方程的个数

1. 秩的本质：矩阵$A$中非0子式的最高阶数
2. $R(A_{m\times n})\leq \min\{m,n\}$
#### 性质
1. 任意初等变换不会改变矩阵的秩序
2. 转置后秩也不变：$R(A^T)=R(A)$
3. 如果$A是n阶方阵：R(A)=n(满秩)\Leftrightarrow|A|\neq0\Leftrightarrow A可逆$，
4. 分块矩阵的秩：$R(A,B)\geq R(A)并且R(A,B)\geq R(B)，也就是R(A,B)\geq \max\{R(A),R(B)\}$。矩阵的秩一定不小于子块的秩
5. 两矩阵相加，$R(A+B)\leq R(A)+R(B)$，和矩阵的秩小于原来两个矩阵的秩的和
6. 两矩阵相乘，$R(AB)\leq R(A)，R(AB)\leq R(B)，即R(AB)\leq \min\{R(A),R(B)\}$，矩阵的秩越乘越小
7. 如果$A_{m\times n}B_{n\times s}=0\Rightarrow$则$R(A)+R(B)\leq n$
>第7条推广：$B$的每一列向量都是$Ax=0$的解
#### 利用初等变换求秩
将矩阵进行初等变换，化为行阶梯矩阵，阶梯级数（非0行的行数）就是矩阵的秩。

# 第三章 线性方程组的解
## 消元法
就是利用**初等行变换**将矩阵变为阶梯矩阵进行逐项消元。

* **不能使用列变换！！！**
* **不能使用列变换！！！**
* **不能使用列变换！！！**
* **后面的解(齐次/非齐)线性方程也是！！！**
## 线性方程组解的判定（存在性）
齐次：$Ax=0$。非齐次：$Ax=b$。这两种形式中的$A$不一定是方阵
### 非齐次线性方程组
$Ax=b，其中A是系数矩阵，(A|b)是增广矩阵，也记为\widetilde{A}$。

1. 无解：$R(A_{m\times n})\neq R(\widetilde{A})$，或者$R(A_{m\times n})< R(\widetilde{A})$
2. 唯一解：$R(A_{m\times n})=R(\widetilde{A})=n$，多少个未知数就有多大的秩（列数和秩的大小相等）
3. 无穷解：$R(A_{m\times n})=R(\widetilde{A})<n$，有效方程组个数小于未知数个数，多出的未知数设为自由变量，可以自由取值

**特别的，当矩阵是方阵时：**

1. $|A|=0\Leftrightarrow根据矩阵的秩确定解的存在性$
2. $|A|\neq0\Leftrightarrow有唯一解$

**注意：**
* $Ax=b有解\Leftrightarrow R(A)=R(A|b)$
* $AX=B有解\Leftrightarrow R(A)=R(A|B)，注意这里X、B是矩阵而非列向量$

### 齐次线性方程组
$Ax=0，没有b，b是零向量$，没有增广矩阵,且一定有解，但是一定没有唯一解

1. 只有$0解：R(A_{m\times n})=n$
2. 有非$0解：R(A_{m\times n})<n$，有效方程组个数小于未知数个数，一定有自由变量

特别的，当$A$为方阵的时候：

1. 只有$0解\Leftrightarrow R(A_{m\times n})=n \Leftrightarrow|A|\neq0$
2. 有非$0解\Leftrightarrow R(A_{m\times n})<n\Leftrightarrow|A|=0$ 
## 线性方程组的结构
这里只讨论方程组有无穷多解的情况下，这些解之间的关系
### 齐次Ax=0
**性质：**

1. 加法封闭性：$\xi_1、\xi_2是Ax=0的解，则\xi_1+\xi_2也是Ax=0的解$
2. 数乘封闭性：如果$\xi是Ax=0的解，那么k\xi也是Ax=0的解$

**基础解系：** 设$\xi_1，\xi_2，...，\xi_P是Ax=0的解，如果有以下$

1. $\xi_1，\xi_2，...，\xi_P$ **线性无关**

2. $Ax=0的任何一个解可以由\xi_1，\xi_2，...，\xi_P$线性表示

$\Rightarrow则称\xi_1，\xi_2，...，\xi_P是Ax=0的基础解系，k_1\xi_1+k_2\xi_2+...+k_P\xi_P是Ax=0的通解$

$Ax=0的基础解系所含有的向量个数为n-R(A)$，注意这里说的是**基础**解系，是最最最基本、最原始的解：
$$
\begin{aligned}
    &\left\{\begin{aligned}
        x_1&+x_2+x_3=0 \\ 2x_1&+2x_2+2x_3=0 \\3x_1&+3x_2+3x_3=0
    \end{aligned} \right.\xRightarrow{有效方程} \left\{\begin{aligned}
        &x_1+x_2+x_3=0\\
        &x_1=-x_2-x_3\\
        &x_2=k_1\quad x_3=k_2\\
        &x_1=-k_1-k_2
    \end{aligned}\right. \Rightarrow X=\begin{pmatrix}
        -k_1-k_2 \\ k_1 \\ k_2
    \end{pmatrix}=\begin{pmatrix}
        -k_1 \\ k_1 \\ 0
    \end{pmatrix}+\begin{pmatrix}
        -k_2 \\ 0 \\ k_2
    \end{pmatrix} \\ 
    &X=k_1\begin{pmatrix}
        -1 \\ 1 \\0
    \end{pmatrix}+k_2\begin{pmatrix}
        -1 \\ 0 \\ 1
    \end{pmatrix}，此时\xi_1=\begin{pmatrix}
        -1 \\ 1 \\0
    \end{pmatrix}，\xi_2=\begin{pmatrix}
        -1 \\ 0 \\ 1
    \end{pmatrix}，\xi_1、\xi_2就是基础解系
\end{aligned}
$$
#### 解基础解系
1. 把矩阵化为阶梯行（或最简形）
2. 如果$R(A)=n$，那么$Ax=0$只有0解，没有基础解系
3. 如果$R(A)<n$，就把阶梯形每行中非拐弯列对应变量作为自由变量，依次取为$\begin{pmatrix}
    1\\0\\ \vdots \\ 0
\end{pmatrix}，\begin{pmatrix}
    0\\1\\ \vdots \\ 0
\end{pmatrix}，...，\begin{pmatrix}
    0\\0\\ \vdots \\ 1
\end{pmatrix}$，然后代入阶梯形方程组，得到基础解系
>上述取列向量的值中是不包括这个向量之前的行的，比如上面那个解释中，自由变量取值就是$\begin{pmatrix}
    1\\0
\end{pmatrix}和\begin{pmatrix}0 \\ 1 \end{pmatrix}$，没有包括第一行，第一行不是自由变量所在行，不需要表示出来，$x_1$是由$x_2、x_3$表示的最终结果就是：非自由变量+自由变量列向量：
>
>1. 找出自由变量
>2. $\xi$ 对应的自由变量位置留空（留空位置不需要连续，中间可以插入已知变量）
>3. 在对应留空位置填入上面第3点的取值：$(1\quad 0 \dots0)^T、(0\quad 1 \dots0)^T、(0\quad 0 \dots1)^T$
>4. 非留空位置就是已知变量，用自由变量表示就行了
### 非齐次Ax=b
**性质：**
1. $\alpha_1,\alpha_2都是Ax=b的解\Rightarrow则\left\{\begin{aligned}
    &\alpha_1-\alpha_2也是Ax=b的解 \\ &\frac{\alpha_1+\alpha_2}{2}也是Ax=b的解 \\
    &k_1\alpha_1+k_2\alpha_2也是Ax=b的解\Leftrightarrow k_1+k_2=1
\end{aligned} \right.$

2. $设\eta是Ax=b的解，\xi是Ax=0的解\Rightarrow\eta+\xi是Ax=b的解$（齐解+非齐=非齐解）

$\Rightarrow非齐的通解：(k_1\xi_1+...+k_p\xi_p)+\eta$（齐次通解+非齐次特解）
#### 解非齐次通解
1. 把增广矩阵$(A|b)$化为行阶梯形（或最简形）
2. 如果$R(A)\neq R(A|b)$，则无解。
3. 如果$R(A)= R(A|b)=n$，则有唯一解（此时无须求通解）
4. 如果$R(A)= R(A|b)<n$，有无穷多解，通解$x=k_1\xi_1+...+k_p\xi_p+\eta$
5. 特解一般是将自由变量设为0的解。
>其实是和齐次一样求通解，然后再多求一个特解

# 第四章 向量组的相关性及向量空间
本章不按书中《新工科数学基础三》的进度进行复习
***
## 4.1 向量组及其线性组合
### 向量定义
1. 什么是向量：行向量、列向量
2. 向量的加减和数乘：对应位置相加、所有元素数乘（就是矩阵的加减、数乘）
### 向量的线性组合
1. 线性组合：给定$\alpha_1,\alpha_2,...,\alpha_m$，对于任意的一组实数$k_1,k_2,...,k_m$，则$k_1\alpha_1+k_2\alpha_2+...+k_m\alpha_m$成为向量$\alpha_1,\alpha_2,...,\alpha_m$的线性组合
2. 线性表示：如果向量$\beta=k_1\alpha_1+k_2\alpha_2+...+k_m\alpha_m$，则称$\beta$能由向量$\alpha_1,\alpha_2,...,\alpha_m$线性表示
>向量组中任何一个向量均可由该向量组本身表示：$\alpha_i=0\alpha_1+0\alpha_2+...+1\alpha_i+...+0\alpha_m$
>
>如果$\beta可以由\alpha_1,\alpha_2,...,\alpha_n$中的一部分表示，则$\beta$可以由全部向量表示
3. 判定方法：
$$
 \begin{aligned}
    &3.1：\beta能由\alpha_1,\alpha_2,...,\alpha_m线性表示\Leftrightarrow存在一组系数k_1,k_2,...,k_m，使得k_1\alpha_1+k_2\alpha_2+...+k_m\alpha_m=\beta\\
    \qquad&\Leftrightarrow线性方程组(\alpha_1,\alpha_2,...,\alpha_m)x=\beta有解（Ax=\beta有解）\Leftrightarrow R(A)=R(A|\beta)\\
    &3.2：向量组\beta_1,\beta_2,...,\beta_t能由\alpha_1,\alpha_2,...,\alpha_m线性表示\Leftrightarrow每个向量\beta_j（j=1,2,...,t）均可由\alpha_1,...,\alpha_m表示：\\
    &\Leftrightarrow\left\{\begin{aligned}
        &\beta_1=k_{11}\alpha+k_{21}\alpha_2+\cdots+k_{m1}\alpha_m \\
        &\beta_2=k_{12}\alpha+k_{22}\alpha_2+\cdots+k_{m2}\alpha_m \\ 
        &\cdots \\
        &\beta_t=k_{1t}\alpha+k_{2t}\alpha_2+\cdots+k_{mt}\alpha_m
    \end{aligned}\right.\Rightarrow即(\beta_1\; \beta_2\;\cdots\;\beta_t)=(\alpha_1\; \alpha_2\;\cdots\;\alpha_m)\begin{pmatrix}
        k_{11} &k_{12} &\cdots &k_{1t} \\
        k_{21} &k_{22} &\cdots &k_{2t} \\
        \vdots &\vdots & &\vdots \\
        k_{m1} &k_{m2} &\cdots &k_{mt}
    \end{pmatrix}\\
    &注意方程中和矩阵中的k排序不一样，有个“转置”关系！
 \end{aligned}
$$

### 向量组的等价
1. $\beta_1,\beta_2,...,\beta_t和\alpha_1,\alpha_2,...,\alpha_m可以相互表示\Leftrightarrow称向量组\Beta和\Alpha等价$
2. 判定：
   1. $向量组\Beta可以由\Alpha表示\Leftrightarrow\Alpha x=\Beta$有解$\Leftrightarrow R(\Alpha)=R(\Beta|\Alpha)$
   2. $向量组\Alpha可以由\Beta表示\Leftrightarrow\Beta x=\Alpha$有解$\Leftrightarrow R(\Beta)=R(\Alpha|\Beta)$
   3. $\Alpha与\Beta相互表示（等价）\Leftrightarrow R(\Alpha)=R(\Beta|\Alpha)=R(\Beta)$
   4. 上述矩阵的秩符合秩的性质
3. 定理：$如果向量组\Beta的秩R(\Beta)能由向量组\Alpha表示：R(\Beta)\leq R(\Alpha)$

## 4.2 向量组的线性相关性
### 定义
**线性相关：** 这组向量中存在不全为零的系数$k_1,k_2,...,k_m使得组合k_1\alpha_1+k_2\alpha_2+...+k_m\alpha_m=0$

**线性无关：** $k_1,k_2,...,k_m使得组合k_1\alpha_1+k_2\alpha_2+...+k_m\alpha_m=0$的系数只能全是零。
### 经典结论
1. $\alpha_1，\alpha线性相关（无关\Leftrightarrow \alpha_1,\alpha_2成比例（不成比例）\xLeftrightarrow{几何}\alpha_1,\alpha_2共线（不共线）$
2. 包含零向量的向量组一定线性相关

### 性质
1. 线性相关$\Leftrightarrow$至少有一个向量可以被其他向量表示
2. $\alpha_1,\alpha_2,...,\alpha_m线性相关\Leftrightarrow齐次方程组\Alpha x=0有解$
   1. 逆命题：线性无关则只有零解，$R(\Alpha)=n$
   2. $\Alpha是方阵：\alpha_1,...,\alpha_m线性无关\Leftrightarrow R(\Alpha)=n\Leftrightarrow |\Alpha|\neq0$
   3. 向量个数=未知数个数；向量维数=方程个数
   4. 任意$n+1$个$n$维向量必相关，因为方程个数<未知数个数
3. 如果向量组$\alpha_1,..,\alpha_n线性无关，\alpha_1,..,\alpha_n,\beta$线性相关，则$\beta一定可以由\alpha_1,...,\alpha$线性表示，且表示法唯一。
4. 向量组中一部分线性相关，则整个向量组线性相关。
5. 设 $\alpha_1, \alpha_2, \cdots, \alpha_s$ 是 $m$ 维向量, $\beta_1, \beta_2, \cdots, \beta_s$ 是 $n$ 维向量, 记：
$\gamma_1 = \begin{pmatrix} \alpha_1 \\ \beta_1 \end{pmatrix}, \gamma_2 = \begin{pmatrix} \alpha_2 \\ \beta_2 \end{pmatrix}, \gamma_3 = \begin{pmatrix} \alpha_3 \\ \beta_3 \end{pmatrix}, \cdots, \gamma_s = \begin{pmatrix} \alpha_s \\ \beta_s \end{pmatrix}$ 是 $m+n$ 维向量组，
若 $\gamma_1, \gamma_2, \gamma_3, \cdots, \gamma_s$ 线性相关 $\Rightarrow$ 则 $\alpha_1, \alpha_2, \alpha_3, \cdots, \alpha_s$ 线性相关.（高维相关 $\Rightarrow$ 低维相关）
如：$\gamma_1 = \begin{pmatrix} 1 \\ 2 \\ 3 \\ 4 \\ 5 \end{pmatrix}, \gamma_2 = \begin{pmatrix} 2 \\ 4 \\ 6 \\ 8 \\ 10 \end{pmatrix}$，显然 $\gamma_1, \gamma_2$ 相关 $\Rightarrow \begin{pmatrix} 1 \\ 3 \\ 5 \end{pmatrix}, \begin{pmatrix} 2 \\ 4 \\ 6 \end{pmatrix}$ 必相关。

>注：（逆否命题）低维无关 $\Rightarrow$ 高维无关
## 4.3 向量组的秩
### 1.极大无关组
设向量组$\alpha_1,\alpha_2...,\alpha_s有一部分组\alpha_{i1},\alpha_{i2},...,\alpha_{ir}$满足：
1. $\alpha_{i1},\alpha_{i2},...,\alpha_{ir}$线性无关
2. $\alpha_1,\alpha_2...,\alpha_s中任意一个向量\alpha_j均可由\alpha_{i1},\alpha_{i2},...,\alpha_{ir}表示$

$\Rightarrow则称\alpha_{i1},\alpha_{i2},...,\alpha_{ir}是向量组\alpha_1,\alpha_2...,\alpha_s的极大无关组$
>注意：
>1. 极大无关组不唯一
>2. 极大无关组所包含的向量个数一定唯一
### 2.向量组的秩
向量组$\alpha_1,\alpha_2...,\alpha_s的极大无关组所含有的向量的个数称为秩，记为r(\alpha_1\cdots\alpha_s)$
1. $r(\alpha_1\cdots\alpha_s)\leq s$
2. 如果$r(\alpha_1\cdots\alpha_s)=r，则\alpha_1,\alpha_2,...,\alpha_s中任意r个无关的部分组均可作为极大无关组$

### 3.向量组秩的性质
1. 如果$\alpha_1,\alpha_2,...,\alpha_s线性无关\Leftrightarrow r(\alpha_1\cdots\alpha_s)=s$（自己就是极大无关组）
2. 如果$向量组\beta_1,\beta_2,...,\beta_t可以由\alpha_1,\alpha_2,...,\alpha_s线性表示，则：r(\beta_1\cdots\beta_t)\leq r(\alpha_1\cdots\alpha_s)$
    1. 也就是说$\Alpha x=\Beta有解，R(\Alpha)=R(\Alpha|\Beta)\geq R(\Beta)，R(\Beta)\leq R(\Alpha)，r(\beta_1\cdots\beta_t)\leq r(\alpha_1\cdots\alpha_s)$
    2. 如果向量组$\Alpha与\Beta等价\Rightarrow R(\Alpha)=R(\Beta)$，无法反推
 3. 如果向量组$\beta_1,\beta_2,...,\beta_t可以由\alpha_1,...\alpha_s表示，且t>s\Rightarrow则向量组\beta_1\cdots\beta_t一定线性相关$
 4. 矩阵$A=(\alpha_1\;\alpha_2\cdots\alpha_n)，作初等变换变化为B=(\beta1\;\beta_2\cdots\beta_n)\Rightarrow则A与B有相同的线性相关性$