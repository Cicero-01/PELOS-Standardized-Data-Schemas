# PELOS-Standardized-Data-Schemas
A standardized data schemas form on Quant Research, which could be recognized by our TOOLS

## 1.下载数据 / Download Data
`df_raw = (k线函数)`
由交易所/数据商接口直接得到的数据dataframe统一记为`df_raw`

为了将列名转换为符合PELOS规则的标准列名，可以使用`df_raw.rename()`对列名进行修改。

## 2.列名标准化

**标准化原则**：
1. 所有从交易所原生API获得的数据，命名时若长度超过一个词，单词之间用空格连接（2.1），例如`'Open Time'`
2. 所有因子类数据（计算所得），命名时若单词长度超过一个词，单词之间用`-`符号连接（2.2），例如`df['Prev_Close']=df['Close'].shift(1)`

### 2.1 交易所原生数据：

| Standard_Name                | 含义          | 解释        |
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


### 2.2 因子 / Factors

(Not finished)

## **免责声明 / Disclaimer:** 

本工具仅供研究学习使用，**不构成任何投资或财务建议**。开发者及贡献者对因使用本软件或其中代码所造成的任何直接或间接财务损失，不承担任何法律责任。金融市场交易具有极高风险，请在真实交易前进行充分测试，并自行承担所有风险 (DYOR)。

This project and its tools are provided for educational and research purposes only and **do not constitute financial or investment advice**. The developers and contributors assume no legal responsibility or liability for any direct or indirect financial losses incurred from the use of this software. Trading in financial markets involves significant risk. Always do your own research (DYOR) and test thoroughly before real trading.
