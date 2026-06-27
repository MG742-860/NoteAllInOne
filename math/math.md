# 第十章
## 重积分的应用
### 基本原理
#### 1. 求曲顶柱体的体积
$$
\begin{aligned}
    &{\small公式一：二重积分}： V_{柱}=\iint_Df(x,y)dxdy \\
    &{\small公式二：三重积分}： V_{\Omega}=\iiint_D1dzdydz
\end{aligned}
$$
对于公式一：$f(x,y)$是高，$d\sigma \,$(或者说 $dxdy$ )是面积微元。
计算时一般化为：
$$
V=\int_a^bdx\int_{\phi_1(x)}^{\phi_2(x)}f(x,y)dy
$$
公式二则是物体密度均匀时，也就是$\rho$恒定时，质量=密度的表示。
#### 2. 计算曲面面积
设曲面$S$由方程$z=f(x,y)$给定，$D_{xy}$为$S$在$xOy$面的投影，则：
$$
\text{曲面S的面积A}=\iint_{D_{xy}}\sqrt{1+z_x^2+z_y^2}dxdy
$$
曲面面积与高度$z(x,y)$无关，只计算面积微元区域内的曲率(也就是这里的求导)，所以被积的是$\sqrt{1+z_x^2+z_y^2}$。

曲线弧长公式$s=\int_a^b \sqrt{(1+{y^{'}}^2)}dx$和这个是一样的。
#### 3. 质心
(1)平面薄片$D$的密度为$\rho(x,y)$，则质心坐标$(\overline{x},\overline{y})$的坐标公式为：
$$
\begin{aligned}
  &\overline{x}=\frac{\iint_D x \rho(x,y)dxdy}{\iint_D \rho(x,y)dxdy} \quad , \quad \overline{y}=\frac{\iint_D y \rho(x,y)dxdy}{\iint_D \rho(x,y)dxdy}  \\
  \\
  &\text{如果是均匀薄片，则} \rho (x,y)=常数=1
\end{aligned}
$$
以上可以推广到三维物体中，即($\overline{x},\overline{y},\overline{z}$)

    形心坐标公式如上，将密度设为常数，所求得的坐标就是形心。

#### 4. 转动惯量
设立体$\Omega$的密度为$\rho(x,y,z)$，则立体在$x,y,z$轴的转动惯量分别为：
$$
\begin{aligned}
    &I_x=\iiint_{\Omega}(y^2+z^2)\rho(x,y,z)dv \\
    &I_y=\iiint_{\Omega}(x^2+z^2)\rho(x,y,z)dv \\
    &I_z=\iiint_{\Omega}(x^2+y^2)\rho(x,y,z)dv    
\end{aligned}
$$
# 第十一章
## 通用化简方法
### 第一类曲线/曲面化简方法
1. 可以将曲线/曲面方程带入被积函数f(x,y,..)中进行化简，但是将曲线/曲面积分化为(重)积分后，就不能再代入被积函数中！！！

2. 第一类曲线积分适用对称性：偶倍奇零。第二类不适用！！！
*** 
    即：当曲线/曲面关于轴/面对称的时候，如果函数是关于这个轴/面的奇偶函数时，就可以使用这个性质。比如f(x,y)，如果曲线L关于y轴对称，就只有f(x,y)中有关x项才能使用奇偶性。如果是f(x,y,z)中，曲线关于xOy对称，就只有f(x,y,z)中z项能使用奇偶性。

3. 轮换对称性
*** 
    即按照顺序：x→y→z→...→x。按照顺序替换后，比如x+y=0，x替换y，y替换x后变为y+x=0，与原方程相等(关于x=y对称)，就称曲线L:x+y=0具有轮换对称性。此时被积函数就可以顺序替换x,y,z,...。
### 第二类曲线/曲面化简方法
1. 代入化简，和第一类的一样。
2. 奇偶性：不建议用，简单理解为积分对象是矢量，不适用。
3. 利用两种曲线/曲面积分关系：
$$
\begin{aligned}
    &{\small曲线：}\int_LP(x,y)dx+Q(x,y)dy=\int_L[P(x,y)cos\alpha+Q(x,y)cos\beta]dS \\ 
    &{\scriptsize其中}cos\alpha、cos\beta {\scriptsize是曲线}L{\scriptsize切向量的方向余弦}\\
    &{\small曲面：}\iint_{\Sigma}Pdydt+Qdxdz+Rdxdy=\iint_{\Sigma}(Pcos\alpha+Qcos\beta+Zcos\gamma)dS \\
    &{\scriptsize其中}cos\alpha、cos\beta、cos\gamma{\scriptsize是}\Sigma{\scriptsize在}(x,y,z){\scriptsize处法向量的方向余弦}
\end{aligned}
$$
***
    额外补充：一定要善用定义，不管第一类还是第二类的曲线/曲面，当被积函数为1的时候就是求它的弧长/面积，根据定义去求解，有时候甚至不用算，比如第一类曲线积分，当被积函数为1的时候就不需要用投影法(简单的话)，直接计算立体空间下的面积就行。
## 对弧长的曲线积分-第一类曲线积分
### 定义
对弧长的曲线积分：$\int_Lf(x,y)dS=\lim_{\lambda \to 0}\sum_{i=1}^{n}f(\xi_i,\eta_i)\Delta S_i$，又称为第一类曲线积分。

$\Leftrightarrow$线密度为$u=f(x,y)$的曲线构件质量，质量元：$dM=f(x,y)dS$。

上述中：$dS$称为曲线微元，$dM$为质量元，二者关系为$dM=f(x,y)dS$。
***
$\int_Lf(x,y)dS \quad$：

$L$是弧线(段)，$f(x,y)$是曲线密度，$dS$是曲线微元，当密度$f(x,y)$为常数$k$时，可以理解为求该线段$k$倍长度：$k\int_L dS$。

可以将$dS$近似看作直线，则有：$dS=\sqrt{1+(\frac{dy}{dx})^2}dx$

**注意：**
1. 如果$f(x,y)$在曲线$L$上连续$\Rightarrow$则$\int_Lf(x,y)dS$存在。
2. 可以推广到空间曲线$\Gamma$：$\int_{\Gamma}f(x,y,z)dS$。
### 计算方法
1. 直角坐标系

给定：$y=y(x)，a \leq x \leq b。$则有以下关系：
$$
\begin{aligned}
    \Rightarrow \int_Lf(x,y)dS &= \int_a^bf(x,y(x)) \sqrt{1+(\frac{dy}{dx})^2}dx \\
    dS&=\sqrt{1+(\frac{dy}{dx})^2}dx
\end{aligned}
$$
上述关系公式将第一类曲线积分转化为一次定积分。
$$
2. {\small如果L是参数方程}
\begin{cases}
    x = x(t) \\
    y = y(t)
\end{cases}
， \alpha \leq t \leq \beta，{\small只需要将}dS{\small改为}\sqrt{(\frac{dx}{dt})^2+(\frac{dy}{dt})^2}dt，{\small并且相对应地改变积分上下限为}\beta、\alpha即可：
$$
$$
\begin{aligned}
    \Rightarrow \int_Lf(x,y)dS &= \int_{\alpha}^{\beta}f(x(t),y(t)) \sqrt{(\frac{dx}{dt})^2+(\frac{dy}{dt})^2}dt \\
    \\
    dS & =\sqrt{(\frac{dx}{dt})^2+(\frac{dy}{dt})^2}dt
\end{aligned}
$$

    也就是说，直角坐标系下本质上是确定积分变量、确定积分上下限，曲线要从哪里积分到哪里、要对谁进行积分。

3. 如果是极坐标系

与参数方程类似：$r=r(\theta)，\alpha \leq \theta \leq \beta$：
$$
\begin{aligned}
    \Rightarrow \int_Lf(x,y)dS &= \int_{\alpha}^{\beta}f(rcos\theta,rsin\theta) \sqrt{r^2+(\frac{dr}{d\theta})^2}d\theta \\
    \\
    dS & =\sqrt{r^2+(\frac{dr}{d\theta})^2}d\theta
\end{aligned}
$$
## 对坐标的曲线积分-第二类曲线积分
### 定义
$$
\begin{aligned}
\left.
\begin{aligned}
    &\int_LP(x,y)dx=\lim_{\lambda \to 0}\sum_{i=1}^{n}P(\xi_i,\eta_i)\Delta x_i \\
    &\int_LQ(x,y)dy=\lim_{\lambda \to 0}\sum_{i=1}^{n}P(\xi_i,\eta_i)\Delta y_i \\
    &\text{\small合并}\Rightarrow \int_L P(x,y)dx+Q(x,y)dy
\end{aligned}
\right\}
\end{aligned}
\Leftrightarrow
\begin{cases}
    &1.{\small变力做功=力}\times{\small距离} \\
    &2.{\small设}\overrightarrow{F}=\{P(x,y),Q(x,y)\}，d\overrightarrow{S}=\{ds,dy\} \\
    &3.{\small也就是求变力沿着x和y方向做的功}
\end{cases}
$$
也就是说，我们要求做的功，就是要对功元$dw=\overrightarrow{F}\times d\overrightarrow{S}$求积分，这个积分对比第一类曲线积分，增加了方向要求(因为力是矢量)。
### 计算方法
1. 一般情况下给出$y=y(x)，L$起点为$\alpha$，终点$\beta$，则有：
$$
\int_LP(x,y)dx+Q(x,y)dy=\int_{\alpha}^{\beta}[P(x,y(x))+Q(x,y(x))\cdot y'(x)]dx
$$
2. 参数方程给出时，给出下列转化为定积分的公式：
$$
\begin{cases}
    x=x(t) \\
    y=y(t)
\end{cases}
\Rightarrow L对应起点\alpha，终点对应\beta，有以下：\\
\int_LP(x,y)dx+Q(x,y)dy=\int_{\alpha}^{\beta}[P(x(t),y(t))\cdot x'(t)+Q(x(t),y(t))\cdot y'(t)]dt
$$
以上两种情况中，曲线$L$一定是对应起点和终点！！而不是$\alpha \leq x,t \leq \beta$！！

    与第一类曲线积分类似，都是要搞清楚在哪里积分、要对谁积分、积分函数是什么。
    此性质可以推广到三维空间L(x,y,z)中。
## 格林公式、积分路径无关
### 格林公式
1. 区域D由(分段)光滑**闭曲线**围成。
2. 函数$P(x,y),Q(x,y)$在D上具有一阶连续偏导数。
则有：
$$
\begin{aligned}
    &\int_LP(x,y)dx+Q(x,y)dy=\pm\iint_D(\frac{\delta Q}{\delta x}-\frac{\delta P}{\delta y})dxdy \\
    \\
    &{\small当L方向是逆时针(正向)时，符号取正。}
\end{aligned}
$$
    格林公式将第二类曲线积分与二重积分建立了联系，注意：是第二类曲线积分L和二重积分区域D！

**注意要求：**

1. $L$必须是封闭曲线，如果不是封闭的，要手动加上一条线使它封闭。
2. $P，Q$必须是在$D$上具有一阶连续片导数的函数。
比如：
$$
\int_L\frac{ydx+xdy}{x^2+y^2},\quad L:x^2+y^2=R^2
$$
此时$P,Q$在$(0,0)$点没有定义，函数不连续。要把奇点$(0,0)$点挖去。
#### 简单计算上述例子
1. 挖去奇点：在奇点周围用一条闭曲线围起来，如一个圆$C_{\epsilon}：x^2+y^2=\epsilon^2，\epsilon$足够小，$C_{\epsilon}$方向和曲线$L$一致。
2. 在挖去奇点后的区域应用格林公式：$\oint_{L+C_{\epsilon}^{-}}Pdx+Qdy=\iint_D(\frac{\delta Q}{\delta x}-\frac{\delta P}{\delta y})dxdy=k=0$(此处结果为0)。
注意此处$C_{\epsilon}$取了反方向。
3. 然后计算$\iint_{D^{'}}-\oint_{C_{\epsilon}^-}$
4. 计算$\oint_L$总揽：
$$
\begin{aligned}
    &\oint_L P(x,y)dx+Q(x,y)dy=\int_{L+C_{\epsilon}^-}P(x,y)dx+Q(x,y)dy-\oint_{C_{\epsilon}^-}P(x,y)dx+Q(x,y)dy \\
    &\int_{L+C_{\epsilon}^-}P(x,y)dx+Q(x,y)dy=\iint_{D^{'}}(\frac{\delta Q}{\delta x}-\frac{\delta P}{\delta y})dxdy \quad ... \quad {\small格林公式} \\
    \Leftrightarrow &\oint_L=\int_{L+C_{\epsilon}^-}-\oint_{C_{\epsilon}^-}=\iint_{D^{'}}-\oint_{C_{\epsilon}^-}=\iint_{D^{'}}+\oint_{C_{\epsilon}} \quad ... \quad {\small注意C的方向}
\end{aligned}
$$
***
**再来一个例子**：$I=\oint_L\frac{xdy-ydx}{4x^2+y^2}，L$是以$(1,0)$为原点，2为半径的圆，取逆时针。
$$
\begin{aligned}
    &1.{\small取逆时针}l_1：4x^2+y^2=\epsilon^2,\epsilon{\small充分小(l_1{\scriptsize只需要能包含奇点即可，不一定要圆})} \\
    &2.{\small计算偏导数：}\frac{\delta Q}{\delta x}=\frac{\delta P}{\delta y}=\frac{y^2-4x^2}{(4x^2+y^2)^2}\Rightarrow\oint_L\frac{xdy-ydx}{4x^2+y^2}=\oint_{l_1}\frac{xdy-ydx}{4x^2+y^2} \\
    &3.{\small先代后算：}\oint_{l_1}\frac{xdy-ydx}{4x^2+y^2}=\oint_{l_1}\frac{xdy-ydx}{\epsilon^2}=\frac{1}{\epsilon^2}\oint_{l_1}xdy-ydx \\
    &4.{\small计算区域D^{'}面积：} \frac{1}{\epsilon^2}\iint_{D^{'}}1-(-1)dxdy=\frac{2}{\epsilon^2}\times\pi\times\frac{\epsilon}{2}\times\epsilon=\pi
\end{aligned}
$$
### 曲线积分与路径无关
设$P(x,y),Q(x,y)$在单连通区域$D$内具有一阶连续偏导数，则：
$$
\begin{aligned}
    &1.\quad \int_LP(x,y)dx+Q(x,y)dy{\small与路径无关} \\
    \Leftrightarrow&2.\quad {\small在D内恒有}\frac{\delta Q}{\delta x}=\frac{\delta P}{\delta y} \\
    \Leftrightarrow&3. \quad {\small对D内任意封闭曲线，均有}\oint_C Pdx+Qdy=0 \\
    \Leftrightarrow&4. \quad {\small存在二元函数}u(x,y)，{\small使得}du(x,y)=P(x,y)dx+Q(x,y)dy，{\small且}：\\
    &u(x,y)=\int_{(x_0,y_0)}^{(x,y)}P(x,y)dx+Q(x,y)dy=\int_{x_0}^{x}P(x,y_0)dx+\int_{y_0}^{y}Q(x,y)dy \\
    & A(x_0,y_0)\rightarrow C(x,y_0)\rightarrow B(x,y)，{\small所以}P(x,y_0){\small是}\int_{x_0}^x，{\small再到Q}(x,y)的\int_{y_0}^y。
\end{aligned}
$$
**注意：** 如果区域$D$为复连通区域(含有奇点),若$\frac{\delta P}{\delta y}=\frac{\delta Q}{\delta x}$，则有：

$\oint_L Pdy+Qdx=\oint_l Pdy+Qdx，l$是$L$内的、同方向的、包括奇点的、足够小的闭曲线。

原因就在于$\frac{\delta P}{\delta y}=\frac{\delta Q}{\delta x}$，导致使用格林公式后$\iint_{D}=0$，所以
$$
\begin{aligned}
    &\oint_L=\int_{L+C_{\epsilon}^-}-\oint_{C_{\epsilon}^-}=\iint_{D^{'}}-\oint_{C_{\epsilon}^-}=\iint_{D^{'}}+\oint_{C_{\epsilon}}=0+\oint_{C_{\epsilon}} \quad ... \quad {\small注意C的方向} \\
    &{\small也就是化简为}：\oint_L=\oint_{C_{\epsilon}}
\end{aligned}
$$
## 对面积的曲面积分-第一类曲面积分
### 定义
对面积的曲面积分：$\iint_{\Sigma}f(x,y)dS=\lim_{\lambda \to 0}\sum_{i=1}^{n}f(\xi_i,\eta_i,\zeta_i)\Delta S_i$，又称为第一类曲线积分。

$\Leftrightarrow$面密度为$u=f(x,y,z)$的曲线构件质量，质量元：$dM=f(x,y,z)dS$。

上述中：$dS$称为曲线微元，$dM$为质量元，二者关系为$dM=f(x,y,z)dS$。

**注意：** 若$f(x,y,z)$在光滑曲面上连续 $\Rightarrow$则$\iint_{\Sigma}f(x,y,z)dS$存在。
### 计算方法-投影法
1. 曲面方程为$z=f(x,y)，{\small则面积元}dS=\sqrt{z_x^2+z_y^2+1}dxdy$。令曲面在$xOy上的投影区域为D_{xy}$，那么：
$$
\iint_{\Sigma}f(x,y,z)dS=\iint_{D_{xy}}f(x,y,z(x,y))\sqrt{z_x^2+z_y^2+1}dxdy
$$

**解释：** 设曲面$dS{\small 与平面dxdy的夹角为\gamma}$
$$
\begin{aligned}
    \Rightarrow&{\small则}dxdy=dS{\cdot}cos\gamma\Leftrightarrow dS=\frac{1}{cos\gamma}dxdy ，\Sigma{\small的法向量}\vec{n}=\{-z_x,-z_y,1\} \\
    &\vec{n}=\{-\frac{z_x}{\sqrt{z_x^2+z_y^2+1}},-\frac{z_y}{\sqrt{z_x^2+z_y^2+1}},\frac{1}{\sqrt{z_x^2+z_y^2+1}}\}=\{cos\alpha,cos\beta,cos\gamma\}
\end{aligned}
$$
2. 若曲面$\Sigma$的方程为$y(x,z)、x(y,z)$，则$dS$按照上述解释的原理进行相应余弦角求解即可。
## 对坐标的曲面积分-第二类曲面积分
### 定义
$$
\begin{aligned}
\left.
\begin{aligned}
    &1.\iint_{\Sigma}P(x,y,z)dydz=\lim_{\lambda \to 0}\sum_{i=1}^{n}P(\xi_i,\eta_i,\zeta_i)(\Delta S_i)_{yz} \\
    &2.\iint_{\Sigma}Q(x,y,z)dxdz=\lim_{\lambda \to 0}\sum_{i=1}^{n}Q(\xi_i,\eta_i,\zeta_i)(\Delta S_i)_{xz} \\
    &3.\iint_{\Sigma}R(x,y,z)dxdy=\lim_{\lambda \to 0}\sum_{i=1}^{n}R(\xi_i,\eta_i,\zeta_i)(\Delta S_i)_{xy} \\
    &\Rightarrow{\small合并}\iint_{\Sigma}Pdydz+Qdxdz+Rdxdy{\scriptsize(第二类曲线积分)}
\end{aligned}
\right \}
\end{aligned}
\Leftrightarrow
\begin{cases}
    &1.{\small物理意义上值的是通过该曲面的流量} \\
    &2.{\small流量}\Phi={\small速度\times面积} \\
    &3.{\small设速度\vec{V}}=\{P,Q,R\} \\
    & \quad d\vec{S}=\{dydz,dxdz,dxdy\}，{\small合并有：} \\
    &\Rightarrow d\Phi=\vec{V}\cdot d\vec{S}=Pdydz+Qdxdz+Rdxdy
\end{cases}
\\
{\small曲面\Sigma的方向与所对应的轴的方向同向称为正方向，反之为负方向}
$$
### 计算方法-投影法
1. 对于$\iint_{\Sigma}R(x,y,z)dxdy$，如果曲面方程为$z=z(x,y)$，投影在$xOy$平面上的区域为$D_{xy}$则：
$$
\begin{aligned}
    &\iint_{\Sigma}R(x,y,z)dxdy=\pm\iint_{D_{xy}}R(x,y,z(x,y))dxdy \\
    &\qquad \qquad \qquad \qquad {\scriptsize右侧就是二重积分}\\
    &{\small(1)这里的符号为：上侧为正，下侧为负。看方向是否与z轴相同} \\
    &{\small(2) 其他轴(P、Q)上的计算方法与此类似，不再赘述。}
\end{aligned}
$$
2. 转化投影法
$$
\begin{aligned}
    &\iint_{\Sigma}Pdydz+Qdxdz+Rdxdy=\iint_{D_{xy}}\{P,Q,R\}\cdot \vec{n}dxdy \\
    &{\small其中}\vec{n}=\pm \{-z_x,-z_y,1\}，{\small上侧为正，下侧为负} \\
    &{\small (1)以上侧为例，}\because dxdy=cos\gamma dS,dydz=cos\alpha dS \\
    &(2) \therefore dydz=\frac{cos\alpha}{cos\gamma}dxdy=-z_xdxdy。{\small以此类推...} \\
    &(3) \therefore \iint_{\Sigma}Pdydz+Qdxdz+Rdxdy=\iint_{\Sigma}\{P(-z_x)+Q(-z_y)+R\cdot 1\}dxdy \\
    &=\iint_{D_{xy}}\{P,Q,R\}\cdot \vec{n}\quad dxdy{\scriptsize \qquad注意等式的积分对象的变化}

\end{aligned}
$$
## 高斯公式
### 定义
1. 空间闭区域$\Omega$是有分片光滑的闭曲面$\Sigma$所围成
2. 函数$P(x,y,z),Q(x,y,z),R(x,y,z)$在$\Omega$上具有一阶连续偏导数，则：
$$
\begin{aligned}
&\oiint_{\Sigma}Pdydz+Qdxdz+Rdxdy=\pm \iiint_{\Omega}(\frac{\delta P}{\delta x}+\frac{\delta Q}{\delta y}+\frac{\delta R}{\delta z})dxdydz \\
&{\small当\Sigma取外侧时为正，内侧时为负}  
\end{aligned}
$$
**注意要求：**
* 取面一定要封闭，不封闭就要“加面”使之封闭(记得减去)
* P、Q、R必须具有一阶连续偏导数
$$
{\small比如}\oiint_{\Sigma_{球}}\frac{xdydz+ydxdz+zdxdy}{(x^2+y^2+z^2)^{\frac{3}{2}}}，{\small就要使用“挖洞法”将奇点挖去}
$$
*** 
**例题：** 求$\iint_{\Sigma}xdydz+ydxdz+zdxdy，{\small其中}\Sigma：x^2+y^2+z^2=a^2(z\geq0，{\small取上侧})$
$$
\begin{aligned}
    &{\small(1)补面使之封闭：设}\Sigma_1=\{x^2+y^2\leq a^2,z=0\}{\small，取下侧} \\
    &{\small(2)则}\iint_{\Sigma}xdydz+ydxdz+zdxdy= \\
    &\qquad \oiint_{\Sigma+\Sigma_1}xdydz+ydxdz+zdxdy-\iint_{\Sigma_1}xdydz+ydxdz+zdxdy \\
    &{\small高斯公式}\Rightarrow \iiint_{\Omega}(1+1+1)dxdydz-0=2\pi a^3
\end{aligned}
$$
**例题：** 求$I=\oiint_{\Sigma}\frac{xdydz+ydxdz+zdxdy}{(x^2+y^2+z^2)^{\frac{3}{2}}}，{\small其中}\Sigma：x^2+\frac{y^2}{4}+\frac{z^2}{9}=1$，取外侧。
$$
\begin{aligned}
    &(1)\Sigma{\small包含奇点}(0,0,0)，{\small函数在此处不连续。} \\
    &(2){\small取}\Sigma_1:x^2+y^2+z^2=\epsilon^2({\small\epsilon很小，取内侧}) \\
    &(3)\frac{\delta P}{\delta x}=\frac{x^2+y^2+z^2-3x^2}{(x^2+y^2+z^2)^{\frac{5}{2}}}，\frac{\delta P}{\delta x}+\frac{\delta Q}{\delta y}+\frac{\delta R}{\delta z}=0 \\
    &(4) \oiint_{\Sigma+\Sigma_1}Pdydz+Qdxdz+Rdxdy=\iiint_{\Omega}(\frac{\delta P}{\delta x}+\frac{\delta Q}{\delta y}+\frac{\delta R}{\delta z})dV=0 \\
    &(5)\because \oiint_{\Sigma+\Sigma_1}=\oiint_{\Sigma}+\oiint_{\Sigma_1}=0，\therefore \oiint_{\Sigma}=\oiint_{\Sigma_1^{-}} \\
    &(6)I=\oiint_{\Sigma}\frac{xdydz+ydxdz+zdxdy}{(x^2+y^2+z^2)^{\frac{3}{2}}}=\oiint_{\Sigma_1^{-}}\frac{xdydz+ydxdz+zdxdy}{(x^2+y^2+z^2)^{\frac{3}{2}}} \\
    &\quad=\epsilon^{2\cdot \frac{3}{2}}\oiint_{\Sigma_!^{-}}xdydz+ydxdz+zdxdy=\epsilon^3\iiint_{\Omega}(1+1+1)dV \\
    &\quad =3\epsilon^3 \cdot \frac{4}{3} \pi \cdot \epsilon^3=4\pi
\end{aligned}
$$
***
## 斯托克斯公式、散度、旋度、通量
### 斯托克斯公式-格林公式的推广
1. 曲线$\Gamma$是分段光滑的空间有向**闭曲线**，$\Sigma$是以$\Gamma$为边界的有向曲面(其中$\Gamma$的正向与$\Sigma$的侧向符合右手规则)。
2. 函数$P(x,y,z),Q(x,y,z),R(x,y,z)，{\small在}\Sigma$上具有一阶连续偏导数。
则：
$$
\begin{aligned}
    &\oint_{\Gamma}Pdydz+Qdxdz+Rdxdy \\
    &=\iint_{\Sigma}(\frac{\delta R}{\delta y}-\frac{\delta Q}{\delta z})dydz+(\frac{\delta P}{\delta z}-\frac{\delta R}{\delta x})dxdz+(\frac{\delta Q}{\delta x}-\frac{\delta P}{\delta y})dxdy \\
    &=\iint_{\Sigma}\begin{vmatrix}
        dydz & dxdz & dxdy \\
        \frac{\delta}{\delta x} & \frac{\delta}{\delta y} & \frac{\delta}{\delta z} \\
        P & Q & R
    \end{vmatrix} = {\small分别计算第一行的代数余子式并相加} \\
    &=\iint_{\Sigma}(-1)^{1+1}dydz(\frac{\delta R}{\delta y}-\frac{\delta Q}{\delta z})+(-1)^{1+2}dxdz(\frac{\delta R}{\delta x}-\frac{\delta P}{\delta z})+(-1)^{1+3}dxdy(\frac{\delta Q}{\delta x}-\frac{\delta P}{\delta y})
\end{aligned}
$$
    斯托克斯公式将空间闭曲线和第二类曲面积分联系了起来。
### 散度、旋度、通量
**散度：**

设向量$\vec{A}=P\vec{i}+Q\vec{j}+R\vec{k}$，称$div\vec{A}=\frac{\delta P}{\delta x}+\frac{\delta Q}{\delta y}+\frac{\delta R}{\delta z}{\small为}\vec{A}$的散度。

**旋度：**
${\small称}rot\vec{A}=\begin{vmatrix}
\vec{i} & \vec{j} & \vec{k} \\
\frac{\delta}{\delta x} & \frac{\delta}{\delta y} & \frac{\delta}{\delta z} \\
P & Q & R
\end{vmatrix}{\small为向量场}\vec{A}{\small的旋度。}$

**通量：** 设$\vec{A}=\{P,Q,R\},\vec{n}=\{cos\alpha,cos\beta,cos\gamma \}$为曲面$\Sigma$的单位法向量，
称$\oiint_{\Sigma}\vec{A}\cdot \vec{n}dS=\oiint_{\Sigma}(Pcos\alpha+Qcos\beta+Rcos\gamma)dS$为$\vec{A}{\small通过}\Sigma$的通量。