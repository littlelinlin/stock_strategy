### 羊驼策略1

#### 基本原理####
 - 在本策略中，每天按照收益率从小到大对股票池中的所有股票进行排序，起始时买入num_of_stocks只股票，然后每天在整个股票池中选出收益率前num_of_stocks，如果这些股票已持有，则继续持有，如果未持有则买入，并卖掉收益率不是排在前num_of_stocks的股票 

#### 策略实现
 - 选取市盈率在0~20之间的股票，作为待选股（若用所有股票，计算量过于庞大），一共332支股票
 - 初始资金100万，时间段为：2016-01-01~2018-05-01
 - 设置策略参数，初始买入的股票数num_of_stocks，收益率计算所用天数period
 - 其中收益率=昨天的收盘价/period天之前的收盘价
 - 将股票池内的股票按照收益率排序，买入收益率最高的num_of_stocks只股票（num_of_stocks默认为10)各1000股。
 - 之后的每天都将所有股票按收益率排序，如果股票池中有处于收益率前num_of_stocks而未持有的则买入，并卖掉收益率不处于前num_of_stocks的

 - （一天操作股票数量为20）运行截图：
  ![](https://i.imgur.com/Zh33xSK.png)

 - （一天操作股票数量为10）运行截图：
  ![](https://i.imgur.com/qOXxjAj.png)
