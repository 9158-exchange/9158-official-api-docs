# 9158交易所KPI文档（2018-6-22）

## 获取币场行情（GET）

**获取指定币场的行情及交易限制，价格限制等，返回值说明请参考下文中的【返回结果说明】。**

**交易区及币场关系说明：**

币场 SEER\_EOS的交易区为 **EOS** ，交易区ID为1。

币场USDT\_BTC的交易区为 **BTC** ，交易区ID为2。

**URL** http://www.topbtch.com/zh/api/open/get/marketlist?marketType=X&coinType=xxx

**传参：**

**marketType： 必须， 交易区ID**

开放交易区：

1：**EOS** EOS交易区

2：**BTC** BTC交易区

3：**ETH** ETH交易区

5：**CCNY** CCNY交易区

**coinType: 非必须， 币场名字**

开放币场：

SEER\_EOS, EOSDAC\_EOS, ENU\_EOS, QASH\_ETH, OMG\_ETH, ICX\_ETH, EOS\_ETH,ZRX\_BTC, ICX\_BTC, EOS\_BTC, ETH\_BTC, KPL\_BTC, MMO\_ETH, DOGE\_ETH, ETC\_ETH, USDT\_ETH, TCO\_ETH, WLN\_ETH, ADE\_ETH, HOT\_EOS, ADE\_EOS, KPL\_EOS, USDT\_EOS, USDT\_BTC, BCH\_BTC, LTC\_BTC, DASH\_BTC, MHN\_BTC, TXH\_BTC, BTC\_CCNY, ETH\_CCNY, EOS\_CCNY, LTC\_CCNY, ETC\_CCNY, BCH\_CCNY

**返回结果示例：**

```json
{
  "error": 0,
  "data": [
    {
      "name": "HOT_EOS",
      "round_price": 8,
      "round_num": 0,
      "fee_buy": 0.2,
      "fee_sell": 0.2,
      "buy_min": 0.000001,
      "round_cny": 4,
      "buy_max": "99999999.00000000",
      "sell_min": 0.000001,
      "sell_max": 99999999,
      "trade_min": 1,
      "trade_max": 99999999,
      "old_price": "1.00000000",
      "new_price": "1.00000000",
      "buy_price": "0.00000000",
      "sell_price": "0.00000000",
      "min_price": "0.00000000",
      "max_price": "0.00000000",
      "volume": "0.00",
      "index_order": 0,
      "cny_price": 72,
      "change_price": "0.00",
      "trade_coin": "72.0000",
      "market_coin": "72.00"
    }
  ]
}
```

**返回结果说明：**

**error: 错误ID    0：请求成功返回（无错误）**

**data:结果数组**

name : 币场名

round\_price：交易量保留小数位

round\_num：交易数量保留小数位

fee\_buy：买入手续费

fee\_sell ：卖出手续费

buy\_min：最小买入额

round\_cny ：人民币价格小数位

buy\_max：最大买入额

sell\_min：最小卖出额

sell\_max ：最大卖出额

trade\_min：最小交易额

trade\_max：最大交易额

old\_price：24小时前价格

new\_price：当前最新价

buy\_price：买入价格（暂未使用）

sell\_price：卖出价格（暂未使用）

min\_price：最低价

max\_price：最高价

volume：24小时累计成交量

index\_order：币场排序

cny\_price：最新人民币价格

change\_price：24小时价格变动值

trade\_coin：币场前币人民币价格

market\_coin：币场后币人民币价格

**注意事项：**

1、接口为 **POST** 请求。

2、参数marketType必须填写，coinType为非必须。不填写coinType则返回指定交易区的所有币场的行情信息。

3、（ **trade\_min/ trade\_max** ）交易额 = （委托）价格  \* （委托）数量，用于委托挂单限制交易总额。




## 获取币场最新成交记录（GET）

**URL：** http://www.topbtch.com/zh/api/open/get/tradelog

**传参：**

**market**** ：必须， 币场名字**

开放币场：

SEER\_EOS, EOSDAC\_EOS, ENU\_EOS, QASH\_ETH, OMG\_ETH, ICX\_ETH, EOS\_ETH,ZRX\_BTC, ICX\_BTC, EOS\_BTC, ETH\_BTC, KPL\_BTC, MMO\_ETH, DOGE\_ETH, ETC\_ETH, USDT\_ETH, TCO\_ETH, WLN\_ETH, ADE\_ETH, HOT\_EOS, ADE\_EOS, KPL\_EOS, USDT\_EOS, USDT\_BTC, BCH\_BTC, LTC\_BTC, DASH\_BTC, MHN\_BTC, TXH\_BTC, BTC\_CCNY, ETH\_CCNY, EOS\_CCNY, LTC\_CCNY, ETC\_CCNY, BCH\_CCNY

**返回结果示例：**

```json
{
  "error": 0,
  "data": [
    {
      "fee_buy": 0.00074,
      "price": "41012.93",
      "num": "0.3700",
      "peerid": 27633,
      "date": "10:17:38",
      "market": "BTC_CCNY",
      "fee_sell": 30.3495682,
      "userid": 197,
      "mum": 15174.7841,
      "type": 1
    },
    {
      "fee_buy": 0.00136,
      "price": "41168.93",
      "num": "0.6800",
      "peerid": 27937,
      "date": "10:17:38",
      "market": "BTC_CCNY",
      "fee_sell": 55.9897448,
      "userid": 197,
      "mum": 27994.8724,
      "type": 1
    },
    {
      "fee_buy": 0.00014,
      "price": "41180.93",
      "num": "0.0700",
      "peerid": 54500,
      "date": "10:17:38",
      "market": "BTC_CCNY",
      "fee_sell": 5.7653302,
      "userid": 197,
      "mum": 2882.6651,
      "type": 1
    },
    {
      "fee_buy": 0.0016,
      "price": "41180.93",
      "num": "0.8000",
      "peerid": 83312,
      "date": "10:17:38",
      "market": "BTC_CCNY",
      "fee_sell": 65.889488,
      "userid": 197,
      "mum": 32944.744,
      "type": 1
    }
  ]
}
```

**返回结果说明：**

**error: 错误ID    0：请求成功返回（无错误）**

**data:结果数组**

fee\_buy：买入手续费（比例）

fee\_sell：卖出手续费（比例）

num：交易数量

price：成交价

userid：买家ID

peerid：卖家ID

date：交易时间（非日期）

market： 币场名字

mum ：交易总额

type：交易种类（1：买入， 2：卖出）

**注意事项：**

1、接口为 **POST** 请求。

2、交易完成，收取买卖双方一定比例的手续费（fee\_buy：买入手续费，fee\_sell：卖出手续费）。

3、交易种类(type)，1：买入，2：卖出。

4、date为交易时间，非交易日期。如：10:08:08。

5、币场最新成交记录不分页显示，最多显示40条。




## 获取币场委托挂单（GET）

**URL：** http://www.topbtch.com/zh/api/open/get/tradenew

获取指定币场的买入委托挂单和卖出委托挂单，价格相同的挂单合并，买入挂单按照价格由大到小排序，卖出挂单按照价格由小到大排序。

**传参：**

**market**** ：必须， 币场名字**

开放币场：

SEER\_EOS, EOSDAC\_EOS, ENU\_EOS, QASH\_ETH, OMG\_ETH, ICX\_ETH, EOS\_ETH,ZRX\_BTC, ICX\_BTC, EOS\_BTC, ETH\_BTC, KPL\_BTC, MMO\_ETH, DOGE\_ETH, ETC\_ETH, USDT\_ETH, TCO\_ETH, WLN\_ETH, ADE\_ETH, HOT\_EOS, ADE\_EOS, KPL\_EOS, USDT\_EOS, USDT\_BTC, BCH\_BTC, LTC\_BTC, DASH\_BTC, MHN\_BTC, TXH\_BTC, BTC\_CCNY, ETH\_CCNY, EOS\_CCNY, LTC\_CCNY, ETC\_CCNY, BCH\_CCNY

**返回结果示例：**

```json
{
  "error": 0,
  "data": {
    "buy": [
      {
        "price": "339.09000000",
        "num": "1",
        "sum": "339.09000000"
      },
      {
        "price": "339.08000000",
        "num": "1",
        "sum": "339.08000000"
      },
      {
        "price": "339.07000000",
        "num": "1",
        "sum": "339.07000000"
      },
      {
        "price": "339.06000000",
        "num": "1",
        "sum": "339.06000000"
      }
    ],
    "sell": [
      {
        "price": "639.11000000",
        "num": "1",
        "sum": "639.11000000"
      },
      {
        "price": "639.12000000",
        "num": "1",
        "sum": "639.12000000"
      },
      {
        "price": "639.13000000",
        "num": "1",
        "sum": "639.13000000"
      },
      {
        "price": "639.14000000",
        "num": "1",
        "sum": "639.14000000"
      }
    ]
  }
}
```


**返回结果说明：**

error：错误ID    0：请求成功返回（无错误）

data：结果数组

buy：买入委托数组

sell：卖出委托数组

price：委托价格

num：委托数量

sum：委托总额

**注意事项：**

1、接口为 **POST** 请求。

2、返回委托数组为买1到买15和卖1到卖15的所有委托挂单。

3、买入委托数组按价格由大到小排序，卖出委托数组按价格由小到大排序。




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

```json
{
  "error": 0,
  "id": 111,
  "mobile": "13920659963",
  "name": null,
  "nickname": "用户DR7M",
  "avatar": "1527840325.jpg",
  "avatar_path": "upload/file/jpg/20180601/",
  "remember_token": "aa507dcb531d90784ccd0e2e03a84f7d5183b5ff",
  "invite": "E5LS",
  "is_remote": 0,
  "prefix": "86"
}
```

**返回结果说明：**

error：错误ID    0：请求成功返回（无错误）

id：用户号

mobile：注册手机号

name：用户名（暂未开放）

nickname：昵称

avatar：头像名字

avatar\_path：头像保存路径

remember\_token：token

invite：邀请码

is\_remote：远程登录（暂未开放）

prefix：手机区号

**注意事项：**

1、Id为用户唯一标识，登陆成功后妥善保存本地。

2、Token为登陆令牌，每次登陆成功重置token。

3、 App\_id由平台发布并统一管理，可通过9158官网客服系统申请。

4、成为开发者后，平台提供与开发者唯一匹配app\_id，客户端公钥、客户端私钥。

5、Sign是由客户端公钥生成的签名文件，参考时限可参考本文最后的示例。

6、Data为加密数据，由客户端私钥加密生成，参考时限可参考本文最后的示例。

7、返回值非加密为json格式字符串。




## 个人资产（POST）

**获取用户资产信息。**

**URL：** http://www.topbtch.com/zh/api/open/my/property

**传参：**

app\_id ：必须， 注册APP\_ID

timestamp：必须， 时间戳

sign：必须，签名

data：加密数据

```javascript
{
  uid：必须，用户号
  token：必须，令牌
}
```

- **※※**** RSA加密：必须**

**用公钥加密数据（openssl\_public\_encrypt）**

**私钥签名（openssl\_sign）**

**返回结果示例：**

**※返回值非加密数据**

{

**error** ：0,

**data** ：[

```json
{
	"error": 0,
	"data": [{
		"coin": "CCNY",
		"num": 9499950358,
		"num_d": 399792734,
		"cny_price": "9899743092.00",
		"icon": "ccny.png"
	}, {
		"coin": "BTCH",
		"num": 920000,
		"num_d": 80000,
		"cny_price": "1000000.00",
		"icon": "btch.png"
	}, {
		"coin": "USDT",
		"num": 999377.8343558,
		"num_d": 0,
		"cny_price": "7765165.77",
		"icon": "usdt.png"
	}, {
		"coin": "BTC",
		"num": 1000001.89746534,
		"num_d": 20,
		"cny_price": "41013828079.21",
		"icon": "btc.png"
	}],
	"user_count_cny": "281641977595850.81",
	"shouyi": {
		"licai": "232.87",
		"fenhong": "0"
	},
	"notice": [{
		"notice": "复制邀请码，邀请好友获取更多奖励！"
	}],
	"invitecode": "",
	"btc_cny": "50.58"
}
缩进量：    引号   显示控制
格式化JSON：
{
    "error": 0,
    "data": [
        {
            "coin": "CCNY",
            "num": 9499950358,
            "num_d": 399792734,
            "cny_price": "9899743092.00",
            "icon": "ccny.png"
        },
        {
            "coin": "BTCH",
            "num": 920000,
            "num_d": 80000,
            "cny_price": "1000000.00",
            "icon": "btch.png"
        },
        {
            "coin": "USDT",
            "num": 999377.8343558,
            "num_d": 0,
            "cny_price": "7765165.77",
            "icon": "usdt.png"
        },
        {
            "coin": "BTC",
            "num": 1000001.89746534,
            "num_d": 20,
            "cny_price": "41013828079.21",
            "icon": "btc.png"
        }
    ],
    "user_count_cny": "281641977595850.81",
    "shouyi": {
        "licai": "232.87",
        "fenhong": "0"
    },
    "notice": [
        {
            "notice": "复制邀请码，邀请好友获取更多奖励！"
        }
    ],
    "invitecode": "",
    "btc_cny": "50.58"
}
```

**返回结果说明：**

**error** ：错误ID    0：请求成功返回（无错误）

**data** ：资产列表

coin：币种名字

num：可用数量

num\_d：冻结数量（ **委托冻结+理财冻结** ）

cny\_price：资产人民币估值

icon：币种icon

user\_count\_cny：用户总资产的人民币估值

shouyi：理财收益及邀请的理财分红

licai：理财收益

Fenhong：理财邀请分红

notice：用户资产页公告，前端显示使用

notice：复制邀请码，邀请好友获取更多奖励

invitecode：余币宝邀请广告

btc\_cny：0.001个比特币的人民币估值，用于控制前端币种的显示

**注意事项：**

1、资产接口的返回值中包含一些前端显示用信息，如 **invitecode，btc\_cny, notice** 等。

2、用户资产由两部分构成，可用资产和冻结资产。

3、冻结资产由两部分构成，委托冻结和理财冻结。




## 追加委托（POST）

追加指定币场的委托挂单。追加委托时，系统对购入、卖出的数量，数量和价格的保留小数位有限制，具体限制的条件在所选币场的详细信息中有记录，请参考【获取币场行情（GET）】了解具体限制。

**URL：** http://www.topbtch.com/zh/api/open/entrust

**传参：**

app\_id ：必须， 注册APP\_ID

timestamp：必须， 时间戳

sign：必须，签名

data：加密数据

```javascript
{
  uid：必须，用户号,
  token：必须，令牌,
  market：必须，币场名,
  type：必须，委托种类（1：买入2：卖出）,
  num：必须，委托数量,
  price：委托价格
}
```

- **※※**** RSA加密：必须**

**用公钥加密数据（openssl\_public\_encrypt）**

**私钥签名（openssl\_sign）**

**返回结果示例：**

**※返回值非加密数据**

成功：

```json
{
    "error": 0,
    "error_msg": "委托成功"
}
```

失败：

```json
{
    "error": 1,
    "error_code": 1,
    "error_msg": "账户余额不足.",
    "is_auth": 1
}
```

**返回结果说明：**

**error** ：错误ID    0：请求成功返回（无错误）

**error\_code：** 请求错误ID（暂未使用）

**error\_msg** ：请求结果MSG

**注意事项：**

1、error\_code为错误ID，此功能暂未使用。

2、error\_msg 请求结果信息，委托成功返回【委托成功】，委托失败则返回具体的失败原因。




## 撤销委托（POST）

撤销指定币场和ID的委托挂单，如果币场和指定ID的委托币场不一致，撤单失败。

**URL：** http://www.topbtch.com/zh/api/open/canceltrade

**传参：**

app\_id ：必须， 注册APP\_ID

timestamp：必须， 时间戳

sign：必须，签名

data：加密数据

```jsvascript
{
  uid：必须，用户号,
  token：必须，令牌,
  market：必须，币场名,
  tradeId：必须，委托ID,
}
```

- **※※**** RSA加密：必须**

**用公钥加密数据（openssl\_public\_encrypt）**

**私钥签名（openssl\_sign）**

**返回结果示例：**

**※返回值非加密数据**

**撤销委托成功：**

```json
{
    "error": 0,
    "data": {
        "tradeId": "2515707"
    }
}
```

**撤销委托失败：**

```json
{
    "error": 1,
    "error_code": "NotClickAgain",
    "error_msg": "请勿重复点击",
    "is_auth": 1
}
```

**返回结果说明：**

1、error\_code为错误ID，此功能暂未使用。

2、error\_msg 请求结果信息，撤销委托成功返回撤销委托ID，委托失败则返回具体的失败原因。




## 一键撤销委托（POST）

撤销指定币场的全部委托挂单。

**URL：** http://www.topbtch.com/zh/api/open/cancelall

**传参：**

app\_id ：必须， 注册APP\_ID

timestamp：必须， 时间戳

sign：必须，签名

data：加密数据

```javascript
{
  uid：必须，用户号,
  token：必须，令牌,
  market：必须，币场名
}
```

- **※※**** RSA加密：必须**

**用公钥加密数据（openssl\_public\_encrypt）**

**私钥签名（openssl\_sign）**

**返回结果示例：**

**※返回值非加密数据**

**一键撤销成功：**

```json
{
    "error": 0,
    "data": {
        "tradeId": "[53590,53591,53592]"
    }
}
```

**一键撤销失败：**

```json
{
    "error": 1,
    "error_code": "NotClickAgain",
    "error_msg": "请勿重复点击",
    "is_auth": 1
}
```

**返回结果说明：**

1、error\_code为错误ID，此功能暂未使用。

2、error\_msg 请求结果信息，撤销委托成功返回撤销委托ID列表，委托失败则返回具体的失败原因。




## 委托列表（POST）

获取指定的币场的委托列表及详细。

**URL：** http://www.topbtch.com/zh/api/open/usertrade

**传参：**

app\_id ：必须， 注册APP\_ID

timestamp：必须， 时间戳

sign：必须，签名

data：加密数据

```javascript
{
  uid：必须，用户号,
  token：必须，令牌,
  market：必须，币场名,
  type：委托种类（1当前委托，2历史委托，3全部委托）,
  page：必须，页码,
  perPage：非必须，每页显示数量
}
```

- **※※**** RSA加密：必须**

**用公钥加密数据（openssl\_public\_encrypt）**

**私钥签名（openssl\_sign）**

**返回结果示例：**

**※返回值非加密数据**

**无委托数据：**

```json
{
    "error": 0,
    "totalPages": 0,
    "data": [ ]
}
```

**有委托数据  ：**

```json
{
    "error": 0,
    "totalPages": 1,
    "data": [
        {
            "id": 175027,
            "userid": 111,
            "market": "BTC_CCNY",
            "price": "45515.07000000",
            "num": "10.00000000",
            "deal": "0.00000000",
            "mum": "455150.70000000",
            "type": 2,
            "date": "2018-06-15 14:41:48",
            "status": 0
        },
        {
            "id": 175028,
            "userid": 111,
            "market": "BTC_CCNY",
            "price": "45500.77000000",
            "num": "10.00000000",
            "deal": "0.00000000",
            "mum": "455007.70000000",
            "type": 2,
            "date": "2018-06-15 14:41:48",
            "status": 0
        }
    ]
}
```

**获取委托列表失败：**

```json
{
    "error": 1,
    "error_code": "NO_AUTH",
    "error_msg": "请先登录",
    "is_auth": 0
}
```

**返回结果说明：**

totalPages: 最大页数

id：委托ID（单号）

market：交易市场

price：委托价格

num：委托数量

deal：已成交数量

type：委托类型：1 买入 2 卖出

date：委托时间

status：委托状态：0 交易中 1 已成交 2 已撤销

**注意事项：**

1、error\_code为错误ID，此功能暂未使用。

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

**URL：** http://www.topbtch.com/zh/api/open/deallist

**传参：**

app\_id ：必须， 注册APP\_ID

timestamp：必须， 时间戳

sign：必须，签名

data：加密数据

```javascript
{
  uid：必须，用户号,
  token：必须，令牌,
  market：必须，币场名,
  page：必须，页码,
  perPage：非必须，每页显示数量
}
```

- **※※**** RSA加密：必须**

**用公钥加密数据（openssl\_public\_encrypt）**

**私钥签名（openssl\_sign）**

**返回结果示例：**

**无成交记录：**

```json
{
    "error": 0,
    "totalPages": 0,
    "data": [ ]
}
```

**有成交记录：**

```json
{
    "error": 0,
    "totalPages": 3,
    "data": [
        {
            "market": "DOGE_ETH",
            "price": "0.00001683",
            "num": "1000.00000000",
            "date": "2018-06-15 14:37:33",
            "mum": "0.01683000",
            "type": 2
        },
        {
            "market": "DOGE_ETH",
            "price": "0.00001583",
            "num": "10000.00000000",
            "date": "2018-06-15 13:33:55",
            "mum": "0.15830000",
            "type": 2
        }
    ]
}
```

**请求失败：**

```json
{
    "error": 1,
    "error_code": "Security_Exception",
    "error_msg": "安全异常，请重新登陆",
    "is_auth": 0
}
```

**返回值说明：**

totalPages：总页数

market：币场名

price：成交价

num：成交数量

date：成交日期

mum：成交总额

type：类型 1：买入 2：卖出

**注意事项：**

1、error\_code为错误ID，此功能暂未使用。

2、error\_msg 请求结果信息，获取成交列表成功返回成交列表或空，获取失败则返回具体的失败原因。




## RSA测试接口（GET）

根据用户的app\_id和所传参数，生成加密数据及签名，此接口用于测试用户生成的加密数据及签名是否正确。

**URL:** http://www.topbtch.com/zh/api/rsa/show

示例：http://www.topbtch.com/zh/api/rsa/show?app_id=15208****38987&params={"uid":001,"token":"a24ac70b044b3a6a1c26cffbfb8bb015fbd0d283"}

**传参：**

app\_id ：必须，注册APP\_ID

params：必须，参数，JSON格式

timestamp：必须，时间戳

**返回结果示例：**

**请求成功：**

```json
{
    "error": 0,
    "data": "{\"token\":\"a24ac70b044b3a6a1c26cffbfb8bb015fbd0d283\",\"uid\":111}",
    "encrypt": "iqhHlpekAncmwzVK93XLtix6jT215+WvbNYruuIEabKiUZBVLoEMz0usjNSAevaLYj9hJxgHYcYA90WL/VK8KoAflcPFq7+oVsAynhxg2L5DXOC+DWyBYkeYD9xOfCk9332k6IcxyjAW9blS28JUKakztMx6iKJpTikcLWHGXUo=",
    "sign": "jwBBuvNk86fNgtSAqTIKuZnppChr+0LuA+THCj8U7s3wd5TLA+PscQsHIX0As5tjxvI0D029tQMvINo3vpdhuJEqwEUZ291yS5K6JtOGysc5nWV/vzlzPx1iICzQN3+IYXoRW0p3KZfTFdcrRJ7pSurIOFCHhNVI+PvmR7Mh3Mw="
}
```

请求失败：

```json
{
    "error": 1,
    "error_code": "appid_error",
    "error_msg": "APP_ID不存在！",
    "is_auth": 1
}
```

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

```php
/**
 * RSA公钥加密数据
 * @param string $data 需要加密数据
 * @param string $publicKey 公钥
 * @param string $code 签名编码（base64/hex/bin）
 * @return 加密数据
 */
public function encrypt($data, $publicKey, $code = 'base64')
{
$padding = OPENSSL_PKCS1_PADDING;
$result = false;
if (openssl_public_encrypt($data, $result, $publicKey, $padding))  {
	$result = self::encode($result, $code);
}
return $result;
}

签名算法：
/**
 * 私钥签名数据
 * @param String $data 签名数据
 * @param String $privateKey 私钥
 * @param String $code 签名编码（base64/hex/bin）
 * @return 签名值
 */
public static function sign($data, $privateKey, $code = 'base64')
{
    $result = false;
    if (openssl_sign($data, $result, $privateKey)) {
	$result = self::encode($result, $code);
	}
    return $result;
}

# 数据编码
private static function encode($data, $code)
{
    switch (strtolower($code))
    {
        case 'base64':
            $data = base64_encode('' . $data);
            break;
        case 'hex':
            $data = bin2hex($data);
            break;
        case 'bin':
        default:
    }
    return $data;
}
```