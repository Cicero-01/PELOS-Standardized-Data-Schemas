# PELOS-Standardized-Data-Schemas
A standardized data schemas form on Quant Research, which could be recognized by our TOOLS

## 1.引言 / Introduction
`PELOS`是我们设计的一套标准交易数据的命名规则，目的是在不同的量化研究模块间建立一套数据相互兼容的Datapipeline。我们也希望任何使用我们开源工具的用户，只需遵循本套命名规则，即可调用我们的全部工具、使用自己的数据进行研究。

所有标准数据均以 .csv 格式存储，采用典型的时间序列数据结构，**按行划分，即每一行代表一个时间步（样本）**。本规范核心约束的是表格的**列名 (Column Names) 与数据类型 (Data Types)**。

由于研究习惯和便利性，我们**基于`Python-Binance`包的数据命名方式**设计了`PELOS`格式。我们最大程度地保留了Binance原生API的基础数据命名习惯。然而考虑到市场的多样性，我们希望打造无差别市场兼容 (Market-Agnostic) 的工具生态。因此，我们尽可能对对传统股票等其他市场的经典技术指标与因子家族进行了统一的扩展与规定。只要数据本身符合规范，我们的工具并不关心它们正在处理的是哪个市场的数据，尽可能提升了兼容性。对于其他可能出现而本规则没有具体规定的因子，我们也提供了命名规则以供参考。


## 1.列名标准化

### 命名规则 Naming Conventions
1. 所有从交易所原生API获得的数据，命名时若长度超过一个词，单词之间用空格连接（2.1），例如`'Open Time'`

1. All raw data fetched directly from exchange APIs must use a Space between words if the name consists of multiple words. For example: `Open Time`.

2. 所有因子类数据（计算所得）或者有修饰定语的数据，命名时若单词长度超过一个词，单词之间用下划线符号`_`连接（2.2），例如`'Prev_Close', 'Weekly_MA20'`
 
2. For all calculated features, factors, technical indicators or data with qualifier / prefix, must use an Underscore (_) between words. For example: `'Prev_Close', 'Weekly_MA20'`

对于实际研究中出现、本规则没有具体规定的特征数据可以根据上述命名规则扩展。

For features that might appear in research but have not been specifically mentioned below, researchers could name the features on their own following the rules above.

### 1.1 交易所原生数据 Raw API Data：

| Standard Name                | 含义  Meaning        | 解释 Description       | 
| ---------------------------- | ----------- | --------- |
| SYMBOL                       | 交易对         | 基础资产-计价资产 |
| Open Time                    | 开盘时间        |           |
| Open                         | 开盘价（B）      |           |
| Close                        | 收盘价（B）      |           |
| High                         | 最高价（B)      |           |
| Low                          | 最低价（B）      |           |
| Volume                       | 成交量（B）      |           |
| Close Time                   | 收盘时间        |           |
| Quote Asset Volume           | 计价币成交量（Q）   |           |
| Number of Trades             | 成交次数（次）     |           |
| Taker Buy Base Asset Volume  | 主动买入本币量（B）  |           |
| Taker Buy Quote Asset Volume | 主动买入计价币量（Q） |           |


### 1.2 指标与因子 / Factors

#### 1.2.1 均线家族 Moving Average Family

##### SMA: 简单移动平均 / 

##### EMA: 指数移动平均 / Exponnetial Moving Average

##### 布林带

##### 偏离度因子

##### 长短线交叉因子

#### 1.2.2 量价家族

##### VWAP: 成交量加权平均价 / Volume Weighted Average Price

#### 1.2.3 波动率家族

#### 1.2.4 K线形态家族







