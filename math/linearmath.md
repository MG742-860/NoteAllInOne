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
    \end{vmatrix}=(-1)^{m n}|A||B|=\begin{vmatrix}
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
## ？？？
加法、乘法，没有除法，矩阵的幂运算和一般数的幂运算一样。

**转置**：对称矩阵：$A^T=A$，反对称矩阵：$A^T=-A$。
$$
\begin{aligned}
    (A^T)^T=A,\quad (A+B)^T=A^T+B^T,\quad (kA)^T=kA^T,\quad (AB)^T=B^TA^T
\end{aligned}
$$
**行列式：** 矩阵$A$的行列式记为$|A|、det(A)$。$|A|$=0就称其为奇异的，否则为非奇异的。
## 伴随矩阵、矩阵的逆
$$

$$
