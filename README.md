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

## :fire: 1.第一章
- 量化交易的三大主要领域：
    - Bayesian Statistics （贝叶斯统计）
        - 根据资产价格预测未来价格和走势，会用到[`PyMC3`](https://github.com/pymc-devs/pymc3)这个包
        - 共轭 conjugate
        - 马尔可夫蒙特卡洛 Markov Chain Monte Carlo（priors and posterior）
        - 论贝叶斯随机波动 stochastic volatility
    - Time Series Analysis （时间序列分析）
        - 时序分析的主要思想就是序列相关性`serial correlation`
        - 白噪声（White Noise）和随机游走（Random Walk）
        - 整合移动平均自回归模型 Autoregressive Integrated Moving Average (ARIMA) 
        - 广义自回归条件异方差模型 Generalised Autoregressive Conditional Heteroskedastic (GARCH)
        - cointegration
        - 隐马尔可夫模型（Hidden Markov Models）和卡尔曼滤波器（Kalman Filters）
    - Machine Learning （机器学习）
        - 支持向量机和随机森林，前者核心是核技术，后者属于集成学习下的bagging分支[人工智能的江湖](https://mp.weixin.qq.com/s?__biz=MzU4MjQ3MDkwNA==&mid=2247487227&idx=1&sn=76ac217473fa092abb4fcdd1fee43cd5&chksm=fdb6936ccac11a7a10726c21c64c7bc463550638ede5afb02cc2132421964f61627c1df6c2bc&scene=21#wechat_redirect),这些工具用来生成Alpha（alpha generation）和风险管理（risk management）
        - 非线性方法：决策树，支持向量机和随机森林
        - 无监学习：K均值聚类
- 

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

    
