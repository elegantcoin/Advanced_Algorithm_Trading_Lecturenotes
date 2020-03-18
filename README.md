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

- 共轭先验：用来简化后验分布的计算过程

- 贝叶斯定律计算后验概率
    
    
## :fire: 4.第四章 马尔可夫蒙特卡洛(MCMC)
- 简述：
    - 共轭先验条件不满足时，可以使用MCMC计算后验分布。
    - 面对维数灾难，MCMC通过智能跳跃进行无记忆搜索。

- Metropolis算法
- PyMC3库

## :fire: 5.第五章 贝叶斯线性回归
- 简述：
    - 多元线性回归
    - 贝叶斯线性回归
- 贝叶斯线性回归`PyMC3`:
    - 广义线性模型
    
## :fire: 6.第六章 贝叶斯随机波动模型
- 简述：
    - 霍夫曼和盖尔曼的论文[Hoffman, M. D. and Gelman, A. The no-u-turn sampler: Adaptively setting path lengths
in hamiltonian monte carlo.]
    - Salvatier, Fonnesbeck and Wiecki的[PyMC3库](http://
pymc-devs.github.io/pymc3/notebooks/getting_started.html)
    - 随机波动模型可用于预估股票日收益率的波动性。
    - 用`pandas_datareader`的`get_data_yahoo`下载美股的交易数据

# :clipboard: 时间序列分析
## :fire: 7.时间序列分析简介
- 什么是时间序列分析？
- 我们如何在量化金融中应用时间序列分析？
- 时间序列分析软件
- 时间序列分析路线图
- 这与其他统计工具有何关系？
## :fire: 8.串行相关
- 期望 方差和协方差
    - 示例：R中的样本协方差
- 相关性
    - 示例：R中的样本相关
- 时间序列的平稳性
- 串行相关
- 相关图
    - 示例1-固定线性趋势
    - 示例2-重复序列

## :fire: 9.随机游走和白噪声模型
- 时间序列建模过程
- 向后移位和差分运算符
- 白噪声
    - 二阶性质
    - 相关图
- 随机漫步
    - 二阶性质
    - 相关图
    - 使随机游动模型适合财务数据
## :fire: 10.自回归滑动平均模型
- 我们将如何进行？
- 严格固定
- 赤池信息准则
- p阶的自回归（AR）模型
    - 基本原理
    - 自回归过程的平稳性
    - 二阶属性
    - 模拟和相关图
    - 财务数据
- q阶移动均线（MA）模型
    - 基本原理
    - 定义
    - 二阶属性
    - 模拟和相关图
    - 财务数据
    
- p阶的自进移动平均（ARMA）模型；q
    - 贝叶斯信息准则
    - Ljung-Box测试
    - 基本原理
    - 定义
    - 模拟和相关图
    - 选择最佳ARMA（pq）模型
    - 财务数据

## :fire: 11.自回归整合移动平均线和条件异方差模型
- 快速回顾
- p阶的自回归综合移动平均（ARIMA）模型；dq
    - 基本原理
    - 定义
    - 模拟 相关图和模型拟合
    - 财务数据和预测
    
- 挥发性
- 有条件的异方差
- 自回归条件异方差模型
    - ARCH定义
    - 为什么这种模型会波动？
    - 什么时候适合应用ARCH（1）？
    - ARCH（p）模型
- 广义自回归条件异方差模型
    - GARCH定义
    - 模拟 相关图和模型拟合
    - 财务数据

## :fire: 12.协整时间序列
- 均值回归交易策略
- 协整
- 单位根测试
    - 增强Dickey-Fuller测试
    - Phillips-Perron检验
    - Phillips-Ouliaris检验
    - 单位根测试的困难
- 带R的模拟协整时间序列
- 协整增强迪基·富勒测试
- CADF模拟数据
- CADF财务数据
    - EWA和EWC
    - RDS-A和RDS-B

- 约翰逊测试
    - Johansen模拟数据测试
    - Johansen财务数据测试
    
## :fire: 13.状态空间模型和卡尔曼滤波器
- 线性状态空间模型
- 卡尔曼滤波器
    - 贝叶斯方法
    - 预测
- 使用卡尔曼滤波器的ETF对之间的动态对冲比率
    - 通过卡尔曼滤波器进行线性回归
    - 将卡尔曼滤波器应用于一对ETF
    - TLT和ETF
    - ETF价格散点图
    - 时变斜率和截距

- 书目注释

## :fire: 14.隐马尔可夫模型
- 马尔可夫模型
    - 马尔可夫模型数学规范
- 隐马尔可夫模型
    - 隐马尔可夫模型数学规范
    - 隐马尔可夫模型的过滤
- 隐马尔可夫模型的状态检测
    - 市场体制
    - 模拟数据
    - 财务数据

- 书目注释

# :clipboard: 统计机器学习
## :fire: 15.什么是机器学习
- 什么是机器学习？
- 机器学习领域
    - 监督学习
    - 无监督学习
    - 强化学习
- 机器学习技术
    - 线性回归
    - 线性分类
    - 基于树的方法
    - 支持向量机
    - 人工神经网络和深度学习
    - 贝叶斯网络
    - 聚类
    - 降维
- 机器学习应用
    - 预测与预测
    - 自然语言处理
    - 因子模型
    - 影像分类
    - 模型精度
    - 参数和非参数模型
    - 机器学习领域的统计框架
## :fire: 16.监督学习
- 数学框架
- 分类
- 回归
    - 财务实例
- 训练
## :fire: 17.线性回归
- 线性回归
- 概率解释
    - 基础功能扩展
- 最大似然估计
    - 可能性和负对数可能性
    - 普通最小二乘
- 使用Scikit-Learn的模拟数据示例

- 书目注释
## :fire: 18.基于树的方法
- 决策树-数学概述
- 回归决策树
    - 创建回归树并进行预测
    - 修剪树
- 分类决策树
    - 分类错误率/命中率
    - 基尼指数
    - 交叉熵/偏离
- 决策树的优缺点
    - 优点
    - 缺点
- 合奏方法
    - 引导程序
    - 自举聚合
    - 随机森林
    - 助推
    - Python Scikit-Learn实现
- 书目注释

## :fire: 19.支持向量机
- 支持向量机的动机
- SVM的优缺点
    - 优点
    - 缺点
- 线性分离超平面
- 分类
- 派生分类器
- 构造最大保证金分类器
- 支持向量分类器
- 支持向量机
    - 书目注释
## :fire: 20.模型选择和交叉验证
- 偏差偏差权衡
    - 机器学习模型
    - 选型
    - 偏差-偏差权衡
- 交叉验证
    - 交叉验证概述
    - 预测范例
    - 验证集方法
    - k折交叉验证
    - Python实现
    - k折交叉验证
    - 完整的Python代码
## :fire: 21.无监督学习
- 高维数据
- 无监督学习的数学概述
- 无监督学习算法
    - 降维
    - 聚类
- 书目注释
## :fire: 22.聚类方法
- K均值聚类
    - 算法
    - 问题
    - 模拟数据
    - OHLC聚类
- 书目注释

## :fire: 23.自然语言处理
- 总览
- 监督文件分类
- 为分类准备数据集
- 向量化
- 词频逆文档频
- 训练支持向量机
- 性能指标

# :clipboard: 定量交易技术
## :fire: 24. QSTrader简介
- QSTrader的动机
- 设计注意事项
- 安装
## :fire: 25.入门投资组合策略
- 动机
- 交易策略
- 数据
- Python QSTrader实施
    - 每月液体再平衡策略
    - LiquidateRebalancePositionSizer
    - 回测接口

    - 交易成本
    - 美国股票/债券60/40 ETF投资组合
    - “策略性”权重ETF投资组合
    - 等重ETF投资组合

## :fire: 26. ARIMA + GARCH股票市场指数交易策略
- 策略概述
- 策略的执行


## :fire: 27.基于协整的对使用QSTrader进行交易
- 假说
- R中的协整检验
- 交易策略
- 数据
- Python QSTrader实施

    - 交易成本
    - 撕纸

## :fire: 28.基于卡尔曼滤波器的对使用QSTrader进行交易
- 交易策略
    - 数据
- Python QSTrader实施



## :fire: 29.使用QSTrader进行日内收益预测的监督学习
- 机器学习的预测目标
    - 班级失衡
- 建立历史数据预测模型
- QSTrader策略对象
- QSTrader回测脚本



## :fire: 30.使用QSTrader通过Sentdex供应商情绪数据进行情感分析
- 情绪分析
    - Sentdex API和示例文件
- 交易策略
- 数据
- Python实现
    - QSTrader的情绪处理
    - 情绪分析策略代码

    - 交易成本
    - S＆P500科技股的观点
    - 标普500能源股人气
    - S＆P500国防股的观点

## :fire: 31..1隐马尔可夫模型的政权检测
- 隐马尔可夫模型的状态检测
- 交易策略
- 数据
- Python实现
    - QSTrader的退货计算
    - 体制检测实施

    - 交易成本
    - 没有制度检测过滤器
    - HMM模式检测过滤器

## :fire: 32.战略衰退
- 计算年化滚动夏普比率
- Python QSTrader实施

    - 卡尔曼滤波器对交易
    - 铝熔炼一体化策略
    - Sentdex情绪分析策略










