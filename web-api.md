# 9158交易所KPI文档

2018年6月22日

## 获取币场行情（GET）

**获取指定币场的行情及交易限制，价格限制等，返回值说明请参考下文中的【返回结果说明】。**

**交易区及币场关系说明：**

币场 SEER\_EOS的交易区为 **EOS** ，交易区ID为1。

币场USDT\_BTC的交易区为 **BTC** ，交易区ID为2。

** URL：** http:// www.topbtch.com/zh/api/open/get/marketlist?marketType=X&amp;coinType=xxx

**传参：**

**marketType： 必须， 交易区ID**

开放交易区：

 1：EOS  EOS交易区                                 2：BTC      BTC交易区

3：ETH   ETH交易区                                5：CCNY   CCNY交易区

**coinType: 非必须， 币场名字**

开放币场：

SEER\_EOS, EOSDAC\_EOS, ENU\_EOS, QASH\_ETH, OMG\_ETH, ICX\_ETH, EOS\_ETH,ZRX\_BTC, ICX\_BTC, EOS\_BTC, ETH\_BTC, KPL\_BTC, MMO\_ETH, DOGE\_ETH, ETC\_ETH, USDT\_ETH, TCO\_ETH, WLN\_ETH, ADE\_ETH, HOT\_EOS, ADE\_EOS, KPL\_EOS, USDT\_EOS, USDT\_BTC, BCH\_BTC, LTC\_BTC, DASH\_BTC, MHN\_BTC, TXH\_BTC, BTC\_CCNY, ETH\_CCNY, EOS\_CCNY, LTC\_CCNY, ETC\_CCNY, BCH\_CCNY

**返回结果示例：**

**{**

&quot;error&quot;:0,

&quot;data&quot;:[{&quot;name&quot;:&quot;HOT\_EOS&quot;,&quot;round\_price&quot;:8,&quot;round\_num&quot;:0,&quot;fee\_buy&quot;:0.2,&quot;fee\_sell&quot;:0.2,&quot;buy\_min&quot;:1.0e-6,&quot;round\_cny&quot;:4,&quot;buy\_max&quot;:&quot;99999999.00000000&quot;,&quot;sell\_min&quot;:1.0e-6,&quot;sell\_max&quot;:99999999,&quot;trade\_min&quot;:1,&quot;trade\_max&quot;:99999999,&quot;old\_price&quot;:&quot;1.00000000&quot;,&quot;new\_price&quot;:&quot;1.00000000&quot;,&quot;buy\_price&quot;:&quot;0.00000000&quot;,&quot;sell\_price&quot;:&quot;0.00000000&quot;,&quot;min\_price&quot;:&quot;0.00000000&quot;,&quot;max\_price&quot;:&quot;0.00000000&quot;,&quot;volume&quot;:&quot;0.00&quot;,&quot;index\_order&quot;:0,&quot;cny\_price&quot;:72,&quot;change\_price&quot;:&quot;0.00&quot;,&quot;trade\_coin&quot;:&quot;72.0000&quot;,&quot;market\_coin&quot;:&quot;72.00&quot;}]

**}**

**返回结果说明：**

**error: 错误ID    0：请求成功返回（无错误）**

**data:结果数组**

**name : 币场名自                                        round\_price：交易量保留小数位**

**round\_num：交易数量保留小数位                        fee\_buy：买入手续费**

**fee\_sell ：卖出手续费                                buy\_min：最小买入额**

**round\_cny ：人民币价格小数位                        buy\_max：最大买入额**

**sell\_min：最小卖出额                                sell\_max ：最大卖出额**

**trade\_min：最小交易额,                                trade\_max：最大交易额,**

**old\_price：24小时前价格                        new\_price：当前最新价**

**buy\_price：买入价格（暂未使用）                        sell\_price：卖出价格（暂未使用）       **

**min\_price：最低价                                max\_price：最高价**

**volume：24小时累计成交量                        index\_order：币场排序**

**cny\_price：最新人民币价格                        change\_price：24小时价格变动值**

**trade\_coin：币场前币人民币价格                        market\_coin：币场后币人民币价格**

**注意事项：**

1. 1、接口为 **POST** 请求。
2. 2、参数marketType必须填写，coinType为非必须。不填写coinType则返回指定交易区的所有币场的行情信息。
3. 3、（ **trade\_min/ trade\_max** ）交易额 = （委托）价格  \* （委托）数量，用于委托挂单限制交易总额。





## 获取币场最新成交记录（GET）

**URL：** http:// www.topbtch.com/zh/api/open/get/tradelog

**传参：**

**market**** ：必须， 币场名字**

开放币场：

SEER\_EOS, EOSDAC\_EOS, ENU\_EOS, QASH\_ETH, OMG\_ETH, ICX\_ETH, EOS\_ETH,ZRX\_BTC, ICX\_BTC, EOS\_BTC, ETH\_BTC, KPL\_BTC, MMO\_ETH, DOGE\_ETH, ETC\_ETH, USDT\_ETH, TCO\_ETH, WLN\_ETH, ADE\_ETH, HOT\_EOS, ADE\_EOS, KPL\_EOS, USDT\_EOS, USDT\_BTC, BCH\_BTC, LTC\_BTC, DASH\_BTC, MHN\_BTC, TXH\_BTC, BTC\_CCNY, ETH\_CCNY, EOS\_CCNY, LTC\_CCNY, ETC\_CCNY, BCH\_CCNY

**返回结果示例：**

{

&quot;error&quot;:0,

&quot;data&quot;:[

{&quot;fee\_buy&quot;:0.00074,&quot;price&quot;:&quot;41012.93&quot;,&quot;num&quot;:&quot;0.3700&quot;,&quot;peerid&quot;:27633,&quot;date&quot;:&quot;10:17:38&quot;,&quot;market&quot;:&quot;BTC\_CCNY&quot;,&quot;fee\_sell&quot;:30.3495682,&quot;userid&quot;:197,&quot;mum&quot;:15174.7841,&quot;type&quot;:1},

{&quot;fee\_buy&quot;:0.00136,&quot;price&quot;:&quot;41168.93&quot;,&quot;num&quot;:&quot;0.6800&quot;,&quot;peerid&quot;:27937,&quot;date&quot;:&quot;10:17:38&quot;,&quot;market&quot;:&quot;BTC\_CCNY&quot;,&quot;fee\_sell&quot;:55.9897448,&quot;userid&quot;:197,&quot;mum&quot;:27994.8724,&quot;type&quot;:1},

{&quot;fee\_buy&quot;:0.00014,&quot;price&quot;:&quot;41180.93&quot;,&quot;num&quot;:&quot;0.0700&quot;,&quot;peerid&quot;:54500,&quot;date&quot;:&quot;10:17:38&quot;,&quot;market&quot;:&quot;BTC\_CCNY&quot;,&quot;fee\_sell&quot;:5.7653302,&quot;userid&quot;:197,&quot;mum&quot;:2882.6651,&quot;type&quot;:1},

{&quot;fee\_buy&quot;:0.0016,&quot;price&quot;:&quot;41180.93&quot;,&quot;num&quot;:&quot;0.8000&quot;,&quot;peerid&quot;:83312,&quot;date&quot;:&quot;10:17:38&quot;,&quot;market&quot;:&quot;BTC\_CCNY&quot;,&quot;fee\_sell&quot;:65.889488,&quot;userid&quot;:197,&quot;mum&quot;:32944.744,&quot;type&quot;:1}

……

]

}

**返回结果说明：**

**error: 错误ID    0：请求成功返回（无错误）**

**data:结果数组**

fee\_buy：买入手续费（比例）                        fee\_sell：卖出手续费（比例）

num：交易数量                                price：成交价

userid：买家ID                                peerid：卖家ID

date：交易时间（非日期）                        market： 币场名字

mum ：交易总额                                type：交易种类（1：买入， 2：卖出）

**注意事项：**

1、接口为 **POST** 请求。

2、交易完成，收取买卖双方一定比例的手续费（fee\_buy：买入手续费，fee\_sell：卖出手续费）

3、交易种类(type)，1：买入，2：卖出

4、date为交易时间，非交易日期。如：10:08:08

5、币场最新成交记录不分页显示，最多显示40条







## 获取币场委托挂单（GET）

**URL：** http:// www.topbtch.com/zh/api/open/get/tradenew

获取指定币场的买入委托挂单和卖出委托挂单，价格相同的挂单合并，买入挂单按照价格由大到小排序，卖出挂单按照价格由小到大排序。

**传参：**

**market**** ：必须， 币场名字**

开放币场：

SEER\_EOS, EOSDAC\_EOS, ENU\_EOS, QASH\_ETH, OMG\_ETH, ICX\_ETH, EOS\_ETH,ZRX\_BTC, ICX\_BTC, EOS\_BTC, ETH\_BTC, KPL\_BTC, MMO\_ETH, DOGE\_ETH, ETC\_ETH, USDT\_ETH, TCO\_ETH, WLN\_ETH, ADE\_ETH, HOT\_EOS, ADE\_EOS, KPL\_EOS, USDT\_EOS, USDT\_BTC, BCH\_BTC, LTC\_BTC, DASH\_BTC, MHN\_BTC, TXH\_BTC, BTC\_CCNY, ETH\_CCNY, EOS\_CCNY, LTC\_CCNY, ETC\_CCNY, BCH\_CCNY

**返回结果示例：**

{

&quot;error&quot;:0,

&quot;data&quot;:{

&quot;buy&quot;:[

{&quot;price&quot;:&quot;339.09000000&quot;,&quot;num&quot;:&quot;1&quot;,&quot;sum&quot;:&quot;339.09000000&quot;},

{&quot;price&quot;:&quot;339.08000000&quot;,&quot;num&quot;:&quot;1&quot;,&quot;sum&quot;:&quot;339.08000000&quot;},

{&quot;price&quot;:&quot;339.07000000&quot;,&quot;num&quot;:&quot;1&quot;,&quot;sum&quot;:&quot;339.07000000&quot;},

{&quot;price&quot;:&quot;339.06000000&quot;,&quot;num&quot;:&quot;1&quot;,&quot;sum&quot;:&quot;339.06000000&quot;}

……

],

&quot;sell&quot;:[

{&quot;price&quot;:&quot;639.11000000&quot;,&quot;num&quot;:&quot;1&quot;,&quot;sum&quot;:&quot;639.11000000&quot;},

{&quot;price&quot;:&quot;639.12000000&quot;,&quot;num&quot;:&quot;1&quot;,&quot;sum&quot;:&quot;639.12000000&quot;},

{&quot;price&quot;:&quot;639.13000000&quot;,&quot;num&quot;:&quot;1&quot;,&quot;sum&quot;:&quot;639.13000000&quot;},

{&quot;price&quot;:&quot;639.14000000&quot;,&quot;num&quot;:&quot;1&quot;,&quot;sum&quot;:&quot;639.14000000&quot;}

……

]

}

}

**返回结果说明：**

error：错误ID    0：请求成功返回（无错误）

data：结果数组

buy：买入委托数组                                卖出：卖出委托数组

price：委托价格                                num：委托数量

sum：委托总额

**注意事项：**

1. 1、接口为 **POST** 请求。
2. 2、返回委托数组为买1到买15和卖1到卖15的所有委托挂单。
3. 3、买入委托数组按价格由大到小排序，卖出委托数组按价格由小到大排序







## 用户登录（POST）

用户登录接口，按照指定要求发送参数，登录成功返回用户相关信息及登录信息。返回值中的id和token分别为用户的唯一标识ID和登录令牌，录成功后妥善保存到本地，下文中涉及到的接口多数需要传递uid和token进行登录确认。

URL：http://www.topbtch.com/zh/api/open/mobile/login

**传参：**

app\_id ：必须， 注册APP\_ID

timestamp：必须， 时间戳

sign：必须，签名

data：加密数据

{

mobile：必须， 注册手机号码

password：必须，密码

}

- **※※**** RSA加密：必须**

**用公钥加密数据（openssl\_public\_encrypt）**

**私钥签名（openssl\_sign）**

**返回结果示例：**

**※返回值非加密数据**

{

    &quot;error&quot;: 0,

    &quot;id&quot;: 111,

    &quot;mobile&quot;: &quot;13920659963&quot;,

    &quot;name&quot;: null,

    &quot;nickname&quot;: &quot;用户DR7M&quot;,

    &quot;avatar&quot;: &quot;1527840325.jpg&quot;,

    &quot;avatar\_path&quot;: &quot;upload/file/jpg/20180601/&quot;,

    &quot;remember\_token&quot;: &quot;aa507dcb531d90784ccd0e2e03a84f7d5183b5ff&quot;,

    &quot;invite&quot;: &quot;E5LS&quot;,

    &quot;is\_remote&quot;: 0,

    &quot;prefix&quot;: &quot;86&quot;

}

**返回结果说明：**

error：错误ID    0：请求成功返回（无错误）

id：用户号                                        mobile：注册手机号

name：用户名（暂未开放）                        nickname：昵称

avatar：头像名字                                avatar\_path：头像保存路径

remember\_token：token                        invite：邀请码

is\_remote：远程登录（暂未开放）                prefix：手机区号

**注意事项：**

1. 1、Id为用户唯一标识，登陆成功后妥善保存本地。
2. 2、Token为登陆令牌，每次登陆成功重置token。
3. 3、 App\_id由平台发布并统一管理，可通过9158官网客服系统申请。
4. 4、成为开发者后，平台提供与开发者唯一匹配app\_id，客户端公钥、客户端私钥。
5. 5、Sign是由客户端公钥生成的签名文件，参考时限可参考本文最后的示例
6. 6、Data为加密数据，由客户端私钥加密生成，参考时限可参考本文最后的示例

7、返回值非加密为json格式字符串。

## 个人资产（POST）

**获取用户资产信息。**

**URL：** [http://www.topbtch.com/zh/api/open/my/property](http://47.75.53.242:8080/zh/api/open/my/property)

**传参：**

app\_id ：必须， 注册APP\_ID

timestamp：必须， 时间戳

sign：必须，签名

data：加密数据

{

        uid ：必须，用户号

token：必须，令牌

}

- **※※**** RSA加密：必须**

**用公钥加密数据（openssl\_public\_encrypt）**

**私钥签名（openssl\_sign）**

**返回结果示例：**

**※返回值非加密数据**

{

**error** ：0,

**data** ：[

{&quot;coin&quot;:&quot;CCNY&quot;,&quot;num&quot;:9499950358,&quot;num\_d&quot;:399792734,&quot;cny\_price&quot;:&quot;9899743092.00&quot;,&quot;icon&quot;:&quot;ccny.png&quot;},

{&quot;coin&quot;:&quot;BTCH&quot;,&quot;num&quot;:920000,&quot;num\_d&quot;:80000,&quot;cny\_price&quot;:&quot;1000000.00&quot;,&quot;icon&quot;:&quot;btch.png&quot;},

{&quot;coin&quot;:&quot;USDT&quot;,&quot;num&quot;:999377.8343558,&quot;num\_d&quot;:0,&quot;cny\_price&quot;:&quot;7765165.77&quot;,&quot;icon&quot;:&quot;usdt.png&quot;},

{&quot;coin&quot;:&quot;BTC&quot;,&quot;num&quot;:1000001.89746534,&quot;num\_d&quot;:20,&quot;cny\_price&quot;:&quot;41013828079.21&quot;,&quot;icon&quot;:&quot;btc.png&quot;}

],

&quot;user\_count\_cny&quot;: &quot;281641977595850.81&quot;,

&quot;shouyi&quot;: {

        &quot;licai&quot;: &quot;232.87&quot;,

        &quot;fenhong&quot;: &quot;0&quot;

   },

&quot;notice&quot;: [

               {

            &quot;notice&quot;: &quot;复制邀请码，邀请好友获取更多奖励！&quot;

                }

 ],

&quot;invitecode&quot;: &quot;【余币宝】是9158推出的数字货币理财产品。\n可以有效的帮助投资人分散风险，是新手入门区块链投资的最佳通道。\n注册链接：\nhttp://www.topbtch.com/registry?referral\_code=&quot;,

&quot;btc\_cny&quot;: &quot;50.58&quot;

 }

**返回结果说明：**

**error** ：错误ID    0：请求成功返回（无错误）

**data** ：资产列表

        **coin** ：币种名字

        **num** ：可用数量

        **num\_d** ：冻结数量（ **委托冻结+理财冻结** ）

        **cny\_price** ：资产人民币估值

        **icon** ：币种icon

**user\_count\_cny** ：用户总资产的人民币估值

  **shouyi** ：理财收益及邀请的理财分红

**licai** ：理财收益

  **Fenhong** ：理财邀请分红

**notice** ：用户资产页公告，前端显示使用

**notice** ：复制邀请码，邀请好友获取更多奖励

**invitecode** ：余币宝邀请广告

**btc\_cny** ：0.001个比特币的人民币估值，用于控制前端币种的显示

**注意事项：**

1. 1、资产接口的返回值中包含一些前端显示用信息，如 **invitecode，btc\_cny, notice** 等
2. 2、用户资产由两部分构成，可用资产和冻结资产。
3. 3、冻结资产由两部分构成，委托冻结和理财冻结。









## 追加委托（POST）

追加指定币场的委托挂单。追加委托时，系统对购入、卖出的数量，数量和价格的保留小数位有限制，具体限制的条件在所选币场的详细信息中有记录，请参考【获取币场行情（GET）】了解具体限制。

**URL：** http://www.topbtch.com/zh/api/open/entrust

**传参：**

app\_id ：必须， 注册APP\_ID

timestamp：必须， 时间戳

sign：必须，签名

data：加密数据

{

        uid ：必须，用户号                       token：必须，令牌

market：必须，币场名                type：必须，委托种类（1：买入2：卖出）

num：必须，委托数量                price：委托价格

}

- **※※**** RSA加密：必须**

**用公钥加密数据（openssl\_public\_encrypt）**

**私钥签名（openssl\_sign）**

**返回结果示例：**

**※返回值非加密数据**

成功：

{

    &quot;error&quot;: 0,

    &quot;error\_msg&quot;: &quot;委托成功&quot;

}

失败：

{

&quot;error&quot;: 1,

&quot;error\_code&quot;: 1,

&quot;error\_msg&quot;: &quot;账户余额不足.&quot;

 &quot;is\_auth&quot;:1

}

**返回结果说明：**

**error** ：错误ID    0：请求成功返回（无错误）

**error\_code：** 请求错误ID（暂未使用）

**error\_msg** ：请求结果MSG

**注意事项：**

1. 1、error\_code为错误ID，此功能暂未使用。
2. 2、error\_msg 请求结果信息，委托成功返回【委托成功】，委托失败则返回具体的失败原因。

## 撤销委托（POST）

撤销指定币场和ID的委托挂单，如果币场和指定ID的委托币场不一致，撤单失败。

**URL：** [http://www.topbtch.com/zh/api/open/canceltrade](http://47.75.53.242:8080/zh/api/open/canceltrade)

**传参：**

app\_id ：必须， 注册APP\_ID

timestamp：必须， 时间戳

sign：必须，签名

data：加密数据

{

        uid ：必须，用户号                               token：必须，令牌

market：必须，币场名                tradeId：必须，委托ID

}

- **※※**** RSA加密：必须**

**用公钥加密数据（openssl\_public\_encrypt）**

**私钥签名（openssl\_sign）**

**返回结果示例：**

**※返回值非加密数据**

**撤销委托成功：**

{

    &quot;error&quot;: 0,

    &quot;data&quot;: {

        &quot;tradeId&quot;: &quot;2515707&quot;

    }

}

**撤销委托失败：**

{

    &quot;error&quot;: 1,

    &quot;error\_code&quot;: &quot;NotClickAgain&quot;,（暂未使用）

    &quot;error\_msg&quot;: &quot;请勿重复点击&quot;,

    &quot;is\_auth&quot;: 1

}

**返回结果说明：**

1. 1、error\_code为错误ID，此功能暂未使用。
2. 2、error\_msg 请求结果信息，撤销委托成功返回撤销委托ID，委托失败则返回具体的失败原因。











## 一键撤销委托（POST）

撤销指定币场的全部委托挂单。

**URL：** http://www.topbtch.com/zh/api/open/cancelall

**传参：**

app\_id ：必须， 注册APP\_ID

timestamp：必须， 时间戳

sign：必须，签名

data：加密数据

{

        uid ：必须，用户号                               token：必须，令牌

market：必须，币场名

}

- **※※**** RSA加密：必须**

**用公钥加密数据（openssl\_public\_encrypt）**

**私钥签名（openssl\_sign）**

**返回结果示例：**

**※返回值非加密数据**

**一键撤销成功：**

{

    &quot;error&quot;: 0,

    &quot;data&quot;: {

        &quot;tradeId&quot;: &quot;[53590,53591,53592]&quot;

    }

}

**一键撤销失败：**

{

    &quot;error&quot;: 1,

    &quot;error\_code&quot;: &quot;NotClickAgain&quot;,（暂未使用）

    &quot;error\_msg&quot;: &quot;请勿重复点击&quot;,

    &quot;is\_auth&quot;: 1

}

**返回结果说明：**

1. 1、error\_code为错误ID，此功能暂未使用。
2. 2、error\_msg 请求结果信息，撤销委托成功返回撤销委托ID列表，委托失败则返回具体的失败原因。













## 委托列表（POST）

获取指定的币场的委托列表及详细。

**URL：** http://www.topbtch.com/zh/api/open/usertrade

**传参：**

app\_id ：必须， 注册APP\_ID

timestamp：必须， 时间戳

sign：必须，签名

data：加密数据

{

        uid ：必须，用户号                               token：必须，令牌

market：必须，币场名

type：委托种类（1当前委托，2历史委托，3全部委托）

page：必须，页码                        perPage：非必须，每页显示数量

}

- **※※**** RSA加密：必须**

**用公钥加密数据（openssl\_public\_encrypt）**

**私钥签名（openssl\_sign）**

**返回结果示例：**

**※返回值非加密数据**

**无委托数据：**

{

&quot;error&quot;:0,

&quot;totalPages&quot;:0,

&quot;data&quot;:[]

}

**有委托数据  ：**

{

&quot;error&quot;:0,

&quot;totalPages&quot;:1,

&quot;data&quot;:[

{&quot;id&quot;:175027,&quot;userid&quot;:111,&quot;market&quot;:&quot;BTC\_CCNY&quot;,&quot;price&quot;:&quot;45515.07000000&quot;,&quot;num&quot;:&quot;10.00000000&quot;,&quot;deal&quot;:&quot;0.00000000&quot;,&quot;mum&quot;:&quot;455150.70000000&quot;,&quot;type&quot;:2,&quot;date&quot;:&quot;2018-06-15 14:41:48&quot;,&quot;status&quot;:0},

{&quot;id&quot;:175028,&quot;userid&quot;:111,&quot;market&quot;:&quot;BTC\_CCNY&quot;,&quot;price&quot;:&quot;45500.77000000&quot;,&quot;num&quot;:&quot;10.00000000&quot;,&quot;deal&quot;:&quot;0.00000000&quot;,&quot;mum&quot;:&quot;455007.70000000&quot;,&quot;type&quot;:2,&quot;date&quot;:&quot;2018-06-15 14:41:48&quot;,&quot;status&quot;:0}

]

}

**获取委托列表失败：**

{

    &quot;error&quot;: 1,

    &quot;error\_code&quot;: &quot;NO\_AUTH&quot;,

    &quot;error\_msg&quot;: &quot;请先登录&quot;,

    &quot;is\_auth&quot;: 0

}

**返回结果说明：**

totalPages:最大页数

id：委托ID（单号）

market： 交易市场

price： 委托价格

num：委托数量

deal：已成交数量

type：委托类型： 1 买入 2 卖出

date：委托时间

status：委托状态： 0 交易中 1 已成交 2 已撤销

**注意事项：**

1. 1、error\_code为错误ID，此功能暂未使用。

2、error\_msg 请求结果信息，获取委托列表成功返回委托列表或空，获取失败则返回具体的失败原因。

3、用户委托分页显示，默认每页显示8条，可通过设定参数perPage变更。

4、Type区分。

传参中的type，想要获取委托的状态：

1：当前委托 交易中委托

2：历史委托 全部成交和撤销的委托

3：全部委托 交易中、全部成交和撤销的委托

返回值中的type，委托的类型:

委托类型： 1 买入 2 卖出





## 成交记录（POST）

获取用户的指定币场的成交记录。

**URL：** [http://www.topbtch.com/zh/api/open/deallist](http://47.75.53.242:8080/zh/api/open/deallist)

**传参：**

app\_id ：必须， 注册APP\_ID

timestamp：必须， 时间戳

sign：必须，签名

data：加密数据

{

        uid ：必须，用户号                               token：必须，令牌

market：必须，币场名                page：必须，页码

perPage：非必须，每页显示数量

}

- **※※**** RSA加密：必须**

**用公钥加密数据（openssl\_public\_encrypt）**

**私钥签名（openssl\_sign）**

**返回结果示例：**

**无成交记录：**

{

    &quot;error&quot;: 0,

    &quot;totalPages&quot;: 0,

    &quot;data&quot;: []

}

**有成交记录：**

{

&quot;error&quot;:0,

&quot;totalPages&quot;:3,

&quot;data&quot;:

[

{&quot;market&quot;:&quot;DOGE\_ETH&quot;,&quot;price&quot;:&quot;0.00001683&quot;,&quot;num&quot;:&quot;1000.00000000&quot;,&quot;date&quot;:&quot;2018-06-15 14:37:33&quot;,&quot;mum&quot;:&quot;0.01683000&quot;,&quot;type&quot;:2},

{&quot;market&quot;:&quot;DOGE\_ETH&quot;,&quot;price&quot;:&quot;0.00001583&quot;,&quot;num&quot;:&quot;10000.00000000&quot;,&quot;date&quot;:&quot;2018-06-15 13:33:55&quot;,&quot;mum&quot;:&quot;0.15830000&quot;,&quot;type&quot;:2}

……

]

}

**请求失败：**

{

    &quot;error&quot;: 1,

    &quot;error\_code&quot;: &quot;Security\_Exception&quot;,

    &quot;error\_msg&quot;: &quot;安全异常，请重新登陆&quot;,

    &quot;is\_auth&quot;: 0

}

**返回值说明：**

1. 1、totalPages：总页数
2. 2、market：币场名
3. 3、price：成交价
4. 4、num：成交数量
5. 5、date：成交日期
6. 6、mum：成交总额
7. 7、type：类型 1：买入 2：卖出

**注意事项：**

1. 1、error\_code为错误ID，此功能暂未使用。

2、error\_msg 请求结果信息，获取成交列表成功返回成交列表或空，获取失败则返回具体的失败原因。















## RSA测试接口（GET）

根据用户的app\_id和所传参数，生成加密数据及签名，此接口用于测试用户生成的加密数据及签名是否正确。

**URL:** http://www.topbtch.com/zh/api/rsa/show

示例：http:// www.topbtch.com/zh/api/rsa/show?app\_id=15208\*\*\*\*38987&amp;params={&quot;uid&quot;:001,&quot;token&quot;:&quot;a24ac70b044b3a6a1c26cffbfb8bb015fbd0d283&quot;}

**传参：**

app\_id ：必须，注册APP\_ID

params：必须，参数，JSON格式

timestamp：必须，时间戳

**返回结果示例：**

**请求成功：**

{

&quot;error&quot;: 0,

&quot;data&quot;: &quot;{\&quot;token\&quot;:\&quot;a24ac70b044b3a6a1c26cffbfb8bb015fbd0d283\&quot;,\&quot;uid\&quot;:111}&quot;,

    &quot;encrypt&quot;: &quot;iqhHlpekAncmwzVK93XLtix6jT215+WvbNYruuIEabKiUZBVLoEMz0usjNSAevaLYj9hJxgHYcYA90WL/VK8KoAflcPFq7+oVsAynhxg2L5DXOC+DWyBYkeYD9xOfCk9332k6IcxyjAW9blS28JUKakztMx6iKJpTikcLWHGXUo=&quot;,

    &quot;sign&quot;: &quot;jwBBuvNk86fNgtSAqTIKuZnppChr+0LuA+THCj8U7s3wd5TLA+PscQsHIX0As5tjxvI0D029tQMvINo3vpdhuJEqwEUZ291yS5K6JtOGysc5nWV/vzlzPx1iICzQN3+IYXoRW0p3KZfTFdcrRJ7pSurIOFCHhNVI+PvmR7Mh3Mw=&quot;

}

请求失败：

{

    &quot;error&quot;: 1,

    &quot;error\_code&quot;: &quot;appid\_error&quot;,

    &quot;error\_msg&quot;: &quot;APP\_ID不存在！&quot;,

    &quot;is\_auth&quot;: 1

}

**返回值说明：**

data：原始数据

encrypt：加密数据

sign：签名

注意事项：

1、此接口仅提供验证加密机签名的正确时使用，不可作为工具接口频繁调用。















## OPENSSL加密与签名示例（PHP）

加密算法参数说明：

$data：需要加密的数据

$publicKey：客户端公钥

$code ：base64 **（默认）**

_/\*\*
 \* RSA公钥加密数据
 \*_ **@param** _string $data 需要加密数据
 \*_ **@param** _string $publicKey 公钥
 \*_ **@param** _string $code 签名编码（base64/hex/bin）
 \*_ **@return** _加密数据
 \*/_

**public function** encrypt($data, $publicKey, $code = **&#39;base64&#39;** )

{

$padding = **OPENSSL\_PKCS1\_PADDING** ;
$result = **false** ;
**if** (_openssl\_public\_encrypt_($data, $result, $publicKey, $padding))  {

        $result = **self** ::_encode_($result, $code);

}
**return** $result;

}

签名算法：

_/\*\*
 \* 私钥签名数据
 \*_ **@param** _String $data 签名数据
 \*_ **@param** _String $privateKey 私钥
 \*_ **@param** _String $code 签名编码（base64/hex/bin）
 \*_ **@return** _签名值
 \*/_ **public static function** sign($data, $privateKey, $code = **&#39;base64&#39;** )
{
    $result = **false** ;
     **if** (_openssl\_sign_($data, $result, $privateKey)) {

        $result = **self** ::_encode_($result, $code);

        }
     **return** $result;
}

# 数据编码

**private static function** encode($data, $code)
{
     **switch** (_strtolower_($code))
    {
         **case**  **&#39;base64&#39;** :
            $data = _base64\_encode_( **&#39;&#39;**. $data);
             **break** ;
         **case**  **&#39;hex&#39;** :
            $data = _bin2hex_($data);
             **break** ;
         **case**  **&#39;bin&#39;** :
         **default** :
    }
     **return** $data;
}