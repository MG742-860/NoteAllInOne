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
## 线性无关/相关
**线性无关：** 这几个向量解不能相互之间被其他向量解表示，或者说没有任何一个向量可以被其他向量通过“缩放”和“相加”组合出来(加减数乘)。

**线性相关：** 这组向量中至少有一个向量是“多余”的。它可以通过其他向量的线性组合(加减数乘)来完全表示。这意味着这组向量在空间中出现了信息重叠或冗余。
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

1. $\xi_1，\xi_2，...，\xi_P$线性无关
2. $Ax=0的任何一个解可以由$\xi_1，\xi_2，...，\xi_P线性表示$

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
### 非齐次Ax=b