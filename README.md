# Advanced_Algorithm_Trading_Lecturenotes
Lecturenotes for the Book Advanced Algorithm Trading

<p align="center">
    <a href="https://github.com/elegantcoin/Advanced_Algorithm_Trading_Lecturenotes"><img src="https://img.shields.io/badge/status-updating-brightgreen.svg"></a>
    <a href="https://github.com/python/cpython"><img src="https://img.shields.io/badge/Python-3.7-FF1493.svg"></a>
    <a href="https://github.com/elegantcoin/Advanced_Algorithm_Trading_Lecturenotes"><img src="https://img.shields.io/badge/platform-Windows%7CLinux%7CmacOS-660066.svg"></a>
    <a href="https://opensource.org/licenses/mit-license.php"><img src="https://badges.frapsoft.com/os/mit/mit.svg"></a>
    <a href="https://github.com/elegantcoin/Advanced_Algorithm_Trading_Lecturenotes/stargazers"><img src="https://img.shields.io/github/stars/elegantcoin/Advanced_Algorithm_Trading_Lecturenotes.svg?logo=github"></a>
    <a href="https://github.com/elegantcoin/Advanced_Algorithm_Trading_Lecturenotes/network/members"><img src="https://img.shields.io/github/forks/elegantcoin/Advanced_Algorithm_Trading_Lecturenotes.svg?color=blue&logo=github"></a>
    <a href="https://www.python.org/"><img src="https://upload.wikimedia.org/wikipedia/commons/c/c3/Python-logo-notext.svg" align="right" height="48" width="48" ></a>
</p>
<br />

## :fire: 1.第一章 简介
- 量化交易的三大主要领域：
    - Bayesian Statistics （贝叶斯统计）
        - 根据资产价格预测未来价格和走势，会用到[`PyMC3`](https://github.com/pymc-devs/pymc3)这个包
        - 共轭 conjugate
        - 马尔可夫蒙特卡洛 Markov Chain Monte Carlo（priors and posterior）
        - 贝叶斯随机波动 stochastic volatility
    - Time Series Analysis （时间序列分析）
        - 时序分析的主要思想就是序列相关性`serial correlation`
        - 白噪声（White Noise）和随机游走（Random Walk）
        - 整合移动平均自回归模型 Autoregressive Integrated Moving Average (ARIMA) 
        - 广义自回归条件异方差模型 Generalised Autoregressive Conditional Heteroskedastic (GARCH)
        - cointegration
        - 隐马尔可夫模型（Hidden Markov Models）和卡尔曼滤波器（Kalman Filters）
    - Machine Learning （机器学习）
        - 支持向量机和随机森林，前者核心是核技术，后者属于集成学习下的bagging分支([人工智能的江湖](https://mp.weixin.qq.com/s?__biz=MzU4MjQ3MDkwNA==&mid=2247487227&idx=1&sn=76ac217473fa092abb4fcdd1fee43cd5&chksm=fdb6936ccac11a7a10726c21c64c7bc463550638ede5afb02cc2132421964f61627c1df6c2bc&scene=21#wechat_redirect)),这些工具用来生成Alpha（alpha generation）和风险管理（risk management）
        - 非线性方法：决策树，支持向量机和随机森林
        - 无监学习：K均值聚类


- 所需要的技术栈：
    - 数学：线代、微积分、概率论
    - 编程：C C++ C# Java Python R Matlab
    - 应该先看 [`Successful Algorithmic Trading`](https://www.quantstart.com/)这本书，某经济论坛有翻译版，可以对照看。
    - 了解基本的假设检验、回测术语，构建回测系统。
    - 原书作者的库，模块化做的好，主要用于风险管理和投资组合研究：[QSTrader](https://github.com/mhallsmoore/qstrader)
    - 推荐python 的算法交易库：[PyAlgoTrade](http://gbeced.github.io/pyalgotrade/docs/v0.20/html/tutorial.html)
    - [Quantopian](https://www.quantopian.com) 在线回测平台
    - [Zipline](https://github.com/quantopian/zipline)
    - [PySystemTrade](https://github.com/robcarver17/pysystemtrade)


## :fire: 2.第二章 贝叶斯统计
- 传统频率论和贝叶斯概率论：
    - 频率论认为概率是随机事件在长期重复试验中的频率
    - 贝叶斯概率论认为我们对某事件有个先验的认知，但是当新的证据出现时，我们需要更新对事件的认知（有点`学习`的味道）
    - 频率论通过提供预估（estimates）来减少不确定性
    - 贝叶斯概率论通过根据新证据来调整自己对事件的认知来不断减小不确定性。
    - 伯努利试验
    
## :fire: 3.第三章 二项式贝叶斯
- 贝叶斯概率检验步骤：
    - 1.假设
    - 2.先验概率
    - 3.实验（数据）
    - 4.后验概率
    - 5.推论
    
- 似然函数：
    - `Bernoulli`分布似然函数：![](https://www.nowcoder.com/equation?tex=P(k%7C%CE%B8)%20%3D%20%5Ctheta%5E%7Bk%7D(1-%5Ctheta)%5E%7B1-k%7D&preview=true)
    - N次实验后：![](https://www.nowcoder.com/equation?tex=P(z%2CN%7C%CE%B8)%20%3D%20%5Ctheta%5E%7Bz%7D(1-%5Ctheta)%5E%7BN-z%7D&preview=true)
    
- 先验概率：
    - `Beta`分布：![](https://www.nowcoder.com/equation?tex=P(%5Ctheta%7C%5Calpha%2C%5Cbeta)%20%3D%20%5Ctheta%5E%7B%5Calpha-1%7D(1-%5Ctheta)%5E%7B%5Cbeta-1%7D%2FB(%5Calpha%2C%5Cbeta)&preview=true)

- 共轭先验

- 贝叶斯定律计算后验概率
    
    
## :fire: 4.第四章 马尔可夫蒙特卡洛
    
    
    
    
