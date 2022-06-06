# 第一章 



## 1、相干

- 单色性度量$\frac{\Delta \lambda}{\lambda} = \frac{\Delta \nu}{\nu}$

- 测不准关系
  $$
  \begin{cases}
  	\begin{aligned}
  		\Delta t \cdot \Delta \nu &= 1  \\
  		\Delta x \cdot \Delta p_x &= \hbar \\
  		\Delta E \cdot \tau &= \hbar
  	\end{aligned}
  \end{cases}
  $$

- 光自简并度：$\overline{n} = \frac{1}{\exp(\frac{h\nu}{KT} - 1)} = \frac{W_{21}}{A_{21}}$

- 模密度：$n_\nu = \frac{8\pi\nu^2}{c^3}$

- 单色能量密度：$\rho_\nu = n_\nu\overline{n}\cdot h\nu = \frac{8\pi\nu^2}{c^3} \frac{1}{\exp(\frac{h\nu}{KT} - 1)}h\nu$

- 光强度：$I= \rho_\nu c$

- 光波模式：谐振腔中稳定的场分布。$L' = q \frac{\lambda}{2} = q\frac{c}{2\nu_q}$

- 相同的光波模式：相干体积、波矢空间基元$\Delta k_x \Delta k_y \Delta k_z = \frac{\pi^3}{V}$

## 2、跃迁

- 跃迁概率公式
  $$
  \begin{cases}
  	\begin{aligned}
  		\Big(\frac{dn_2}{dt}\Big)_{sp} &= A_{21} n_2 \quad \text{自发辐射}\\
  		\Big(\frac{dn_2}{dt}\Big)_{st} &= w_{21} n_2\quad \text{受激辐射}\\
  		\Big(\frac{dn_1}{dt}\Big)_{st} &= A_{12} n_1\quad \text{受激吸收}\\
		\Big(\frac{dn_2}{dt}\Big)_{sr} &= S_{21} n_2\quad \text{无辐射跃迁}\\
  		
  	\end{aligned}
  \end{cases}
  $$
  

- 爱因斯坦唯像公式(后面还有升级)
  $$
  \begin{cases}
  	\begin{aligned}
  	W_{21} &= B_{21} \rho_\nu\\
  	W_{12} &= B_{12} \rho_\nu\\
  	\end{aligned}
  \end{cases}
  $$
  

- $A_{21}、B_{21}、B_{12}$之间的关系
  $$
  \begin{cases}
  	\begin{aligned}
  		B_{12}f_1 &= B_{21}f_2 \quad \text{(其中$f_1,f_2$是$E_1,E_2$的统计诠释)}\\
  		\frac{A_21}{B_21} &= n_\nu \cdot h \nu
  	\end{aligned}
  \end{cases}
  $$

- 原子能级寿命：$\tau = \frac{1}{A_{21}}$

## 3、辐射的受激放大

- 增益曲线：$g(z) = \frac{dI(z)}{dt}\frac{1}{I} = \Delta n \sigma_{21}$
- 小信号增益：$g^0$
- 光强：$I(z) = I_0 e^{g(z)}$
- 增益饱和：$n_2(z) - n_1(z) = \frac{n_2^0 - n_1^0}{1+\frac{I_\nu}{I_s}}$
- 损耗：$\alpha =- \frac{dI(z)}{dt}\frac{1}{I} = -\Delta n \sigma_{21}$
- 平均单程损耗：$\delta  = \alpha l$

## 4、激光特性，三好一高

- 空间相干性好=方向性好=光源相干面积大
  $$
  A_{cs} = (\Delta x)^2 \leq (\frac{\lambda}{\Delta \theta})^2
  $$

- 时间相干性好 = 单色性好 = 相干长度长
  $$
  L_c = \frac{c}{\Delta \nu}\\
  \Delta \nu \cdot \Delta t = 1
  $$
  