线性模型是最简单的模型，但是往往却也是比较有效的模型。线性模型形式简单，建模容易，常作为机器学习的首选模型，因为其蕴含机器学习的重要基本思想。

建模：
给定数据集为D={(x1,y1),(x2,y2),...,(xn,yn)}，其中xi={xi1,xi2,...,xim}, yi∈R，建立模型如下：
yi=hi(θ)=ΘTxi+ϵi
由中心极限定理可知：
ϵi∼N(0,σ2)
即：
P(ϵi)=1(√2πσ)exp(−(ϵi)22σ2)
故：
P(yi|xi,θ)=1(√2πσ)exp(−(yi−ΘTxi)22σ2)
根据最大似然估计，似然函数为：
L(θ=)=∏i=1m1(√2πσ)exp(−(yi−ΘTxi)22σ2)
此时，对数似然函数为：
l(θ)=logL(θ)=mlog1(√2πσ)−1σ212Σmi(yi−ΘTxi)2
将与θ相关的定义为目标函数：
J(θ)=12Σmi(hi(θ)−yi)2
注意：上述过程解释了为什么选用RMSE作为线性回归的目标函数。
求解：
根据最大似然估计求解步骤，对目标函数关于θ求偏导得：
ΔθJ(θ)=Δθ12Σmi(hi(θ)−yi)2=XTXθ−XTy=0
则线性回归中，最小二乘意义下的参数最优解为：
θ=(XTX)−1XTy
由于上式子不易计算，引入梯度下降进行求解θ：
J(θ)=12Σmi(hi(θ)−yi)2
θj=θj−α∂J(θ)∂θ
∂J(θ)∂θi=(hθ(x)−y)xj