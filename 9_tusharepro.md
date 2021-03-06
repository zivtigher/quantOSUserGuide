# 我只想使用数据，该怎么做

作者：米哥, symbol, PKUJohnson

如果只想获取一些数据，请使用我们的在线数据服务TusharePro，目前已支持股票、基金、指数、期货等品种的市场数据、参考数据等。

使用非常简单，步骤如下:

1. 成为www.quantos.org的注册用户，注册地址是：[https://www.quantos.org/cas/register.html](https://www.quantos.org/cas/register.html)

2. 下载完整的DataApi。[https://github.com/quantOS-org/DataAPI](https://github.com/quantOS-org/DataAPI)

3. 使用DataApi，从TusharePro获取您需要的研究数据。

以下是简单的使用示例

```python

from DataApi import DataApi

api = DataApi(addr="tcp://data.tushare.org:8910")

api.login("username", "token") 

df, msg = api.daily(
                symbol="600832.SH, 600030.SH", 
                start_date="2012-10-26",
                end_date="2012-11-30", 
                fields="", 
                adjust_mode="post")
```
结果示例(前5条记录)：


|close | code | high    | low   | oi    | open  | settle    | symbol    |trade_date |trade_status   |turnover   |volume |vwap|
| --- | --- | --- |--- |--- |--- |--- |--- |--- |--- |--- |--- |--- |
|5.09|  600832| 5.24|   5.08|   NaN |5.23   |NaN    |600832.SH| 20121026    |交易 |2.779057e+07|  5381800 | 5.16|
|5.10|  600832| 5.15|   5.08|   NaN |5.11   |NaN    |600832.SH| 20121029    |交易 |1.320333e+07|  2582557 | 5.11|
|5.11|  600832| 5.18|   5.08|   NaN |5.12   |NaN    |600832.SH| 20121030    |交易 |1.622705e+07|  3170615 | 5.12|
|5.11|  600832| 5.14|   5.09|   NaN |5.12   |NaN    |600832.SH| 20121031    |交易 |1.072007e+07|  2097770 | 5.11|
|5.18|  600832| 5.20|   5.12|   NaN |5.12   |NaN    |600832.SH| 20121101    |交易 |1.972100e+07|  3814712 | 5.17|

详细接口API，请参看：[http://tushare.org/pro/usage.html](http://tushare.org/pro/usage.html)

