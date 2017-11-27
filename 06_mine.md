#### 个人信息
获取个人信息详情

**接口地址：**`api/v1/user/detail`

**请求参数**

`无`

**响应参数**

|参数| 参数类型 |是否可选 | 参数说明 |
|---|:---:|----|---|
|rowId | int | 否 | userId,用户唯一标识 |
|nickname | string| 否 | 用户昵称 |
|avatar | string | 否 | 用户头像 |
|levelCode | string | 否 | 会员等级 |
|levelName | string | 否 | 等级名称 |
|isAuthReal| string | 否 | 是否实名认证，`0：否，1：true`|
|point | int | 否 | 会员积分 |
|sexual | string | 否 | 用户性别，`男，女`|
|phone | string | 否 | 手机号 |
|realName| string | 否 | 真实姓名 |
|idcard | string | 否 | 身份证号|
|isEligibleInvestor| string | 否 | 是否是合格投资人|

**响应示例**
```json
{
  rowId: 1,
  nickname: "张三",
  avatar: "用户头像",
  levelCode: "diamond",
  levelName: "黄金会员",
  isAuthReal: "1",
  point: 1000,
  sexual: "男",
  phone: "13776668376",
  realName: "王帅",
  idcard: "340823199608390893",
  isEligibleInvestor: 1
}
```
---

#### 实名认证
用于认证用户的真实身份，客户端需要校验身份证的格式有效性

**接口地址：**`api/v1/user/auth`

**请求参数**

|参数| 是否可选 | 参数说明 |
|--|--|--|
|realName  | 否 | 真实姓名 |
|idcard | 否 | 身份证号 |

**响应参数**

`无`

---

#### 基金收藏列表
获取收藏的基金列表，不分页

**接口地址：**`api/v1/fund/favorite`

**请求参数**

`无`

**响应参数**

|参数| 参数类型 |是否可选 | 参数说明 |
|---|:---:|----|---|
| - | array | 是| 数组 |
|rowId | int | 否| 收藏记录唯一标识|
|fundId | string | 否 | 基金名称 |
|type | int | 否 | 基金类型（0:股权，1：债权） |
|fundName| string | 否 | 基金名称|
|tags| string | 否 | 标签，`逗号拆分`|
|incomeRate | string| 否| 收益率 |
|investCycle | int| 否| 投资期限，单位：月 |
|startingAmount | int| 否| 起投金额，单位：万 |
|salesStatus| int | 否 | 基金销售状态，`0:预售，1：在售，2：售罄`|

** 响应示例 **

``` json
[{
  rowId: 1,
  fundId: 1,
  type: 0,
  name: "德瑞1期",
  tags: "洛德,市场",
  incomeRate: "2.8%+",
  investCycle: 12,
  startingAmount: 120,
  salesStatus: 1
}]
```
---

#### 基金收藏取消
批量取消基金收藏

**接口地址：**`api/v1/fund/favorite/delete`

**请求参数**

|参数| 是否可选 | 参数说明 |
|--|--|--|
|fundId | 否 | 收藏记录ID，多个fundId表示批量取消 |

**响应参数**

`无`

---

#### 地产收藏列表
获取收藏的地产列表，不分页

**接口地址:**  `api/v1/estate/favorite`

**请求参数**

`无`

** 响应参数 **

|参数| 参数类型 |是否可选 | 参数说明 |
|---|:---:|----|---|
| - | array | 是| 数组 |
|rowId | int | 否| 唯一标识|
|estateId | int | 否 | 地产唯一标识 |
|estateName | string | 否 | 地产名称|
|pic | string | 否 | 楼盘图片 |
|price| decimal | 否 | 楼盘价格 |
|tags| string | 否 | 标签，`逗号拆分`|

** 响应示例 **

``` json
[{
  rowId: 1,
  pic: "hdhjhbjhd.jpg",
  price: 20000,
  tags: "近地铁,精装",
  estateName: "云树公馆",
  estateId: 1
}]
```
---

#### 地产收藏取消
批量取消地产收藏,值传递多个estateId相同的值

**接口地址：**`api/v1/user/estate/favorite/delete`

**请求参数**

|参数| 是否可选 | 参数说明 |
|--|--|--|
|estateId | 否 | 地产ID，多个estateId表示批量取消 |

**响应参数**

`无`

---

#### 我的活动
获取我参加的活动列表

**接口地址:**  `api/v1/user/activity`

**请求参数**

`无`

** 响应参数 **

|参数| 参数类型 |是否可选 | 参数说明 |
|---|:---:|----|---|
|-| array | 否 | 数组 |
|activitySignId| int | 否| 报名记录唯一标识|
|rowId | int | 否 | 活动唯一标识 |
|title| string | 否 | 活动标题|
|typeName| string | 否| 活动类型： `地产、基金`|
|thumb| string | 否 | 缩略图|
|beginTime| string | 否 | 活动开始时间，`格式:yyyy-MM-dd HH:mm:ss`, 移动端删除`:ss` |
|endTime | string | 否 | 活动结束时间，`格式:yyyy-MM-dd HH:mm:ss`, 移动端删除`:ss` |
|address| string | 否| 活动地址 |
|activityStatus | string | 否| 活动状态，`0:未开始,1:活动中,2:已结束` |

** 响应示例 **

``` json
[{
  activitySignId: 1,
  rowId: 1,
  title: "皇家游轮会员活动",
  typeName: "地产",
  thumb: "活动图.png",
  beginTime: "2017-06-07 14:48:20",
  endTime: "2017-06-08 14:48:20",
  address: "郁金香路30号吉美思大厦701",
  activityStatus: 0
}]
```

---

#### 删除我的活动

**接口地址:**  `api/v1/user/remove`

**请求参数**

|参数| 是否可选 | 参数说明 |
|--|--|--|
|activitySignId | 否 | 活动报名ID，多个activitySignId表示批量取消 |

** 响应参数 **

`无`

---


#### 我的地产
获取用户购买的楼盘地产列表

**接口地址:**  `api/v1/user/estate`

**请求参数**

`无`

**响应参数**

|参数| 参数类型 |是否可选 | 参数说明 |
|---|:---:|----|---|
|-| array | 否 | 数组 |
|estateId| int | 否| 楼盘ID |
|estateName| string | 否| 楼盘名称 |
|num | int | 否 | 购买数量 |

** 响应示例 **

``` json
[{
  estateId: 1,
  estateName: "云树公馆",
  num: 2
}]
```

---

#### 基金投资资产
获取用户基金资产信息

**接口地址：**`api/v1/fund/assets`

**请求参数**

`无`

**响应参数**

|参数| 参数类型 |是否可选 | 参数说明 |
|---|:---:|----|---|
|capital | int | 否 | 投资本金，单位万元 |
|income | decimal | 否 | 累计收益，4位小数，单位万元 |

**响应示例**

```json
{
    capital: 500,
    income: 1.2774
}
```

---

#### 我的基金订单
获取用户认购的基金列表

**接口地址：**`api/v1/fund/order`

**请求参数**

`无`

**响应参数**

|参数| 参数类型 |是否可选 | 参数说明 |
|---|:---:|----|---|
|-| array | 否 | 数组 |
|rowId | int | 否| 订单ID |
|fundId| int | 否| 基金ID |
|fundCode | string | 否 | 基金编号 |
|fundName | string | 否 | 基金名称|
|amount | int | 否 | 认购金额，单位：万元 |
|userId| int | 否 | 用户ID |
|buyDate| string | 否 | 认购日期，`格式:yyyy-MM-dd HH:mm:ss`|
|income | decimal | 否 | 收益，单位：万元,4位小数 |

**响应示例**

```json
[{
  rowId: 1,
  fundId: 1,
  fundCode: "基金编号",
  fundName: "基金名称",
  amount: 120,
  userId: 12,
  buyDate: "2017-06-09 21:33:00",
  income: 1.2345
}]
```
---

#### 基金订单详情
获取基金订单的详情，动态信息

**接口地址：**`api/v1/fund/order/detail`

**请求参数**

|参数| 是否可选 | 参数说明 |
|--|--|--|
|rowId | 否 | 订单Id |


**响应参数**

|参数| 参数类型 |是否可选 | 参数说明 |
|---|:---:|----|---|
|rowId | int | 否| 订单ID |
|fundId| int | 否| 基金ID |
|fundCode | string | 否 | 基金编号 |
|fundName | string | 否 | 基金名称|
|amount | int | 否 | 认购金额，单位：万元 |
|userId| int | 否 | 用户ID |
|buyDate| string | 否 | 认购日期，`格式:yyyy-MM-dd HH:mm:ss`|
|userName| string | 否 | 客户姓名 |
|moments| array | 是 | 订单动态 |
|moments.moment | string | 否 | 动态内容 |
|moments.createTime | string | 否 | 动态时间,`格式：yyyy-MM-dd HH:mm:ss` |

**响应示例**

```json
{
  rowId: 1,
  fundId: 1,
  fundCode: "基金编码",
  fundName: "基金名称",
  amount: 120,
  userId: 13,
  buyDate: "2017-06-09 21:59:00",
  userName: "客户姓名",
  moments: [{
    moment: "认购成功",
    createTime: "2017-06-08"
  },{
    moment: "产品成立，进入存续期",
    createTime: "2017-06-30"
  }]
}
```

---

### 客服聊天
#### 客服聊天记录
客服聊天记录，分页获取

**接口地址:**  `api/v1/custom/service/log`

**请求参数**

|参数| 是否可选 | 参数说明 |
|---|---|---|
|pageNo | 否| 分页码 |
|type | 否| 咨询业务类型：0：地产，1：基金 |

** 响应参数 **

|参数| 参数类型 |是否可选 | 参数说明 |
|---|:---:|----|---|
|-| array | 是| 数组|
|rowId| int | 否 | 客服聊天记录唯一标识 |
|chatId| int | 否 | 客服聊天唯一标识 |
|chatUserId| int | 否 | 聊天用户ID |
|content| int | 否 | 聊天内容|
|flag| string | 否 | 聊天用户标识：1：用户,0:客服|
|status| int | 否 | 聊天状态：0：未回复，1：已回复，2：关闭|
|createTime| string | 否 | 消息发送时间，格式:`yyyy-MM-dd HH:mm:ss`|

** 响应示例 **

``` json
[ {
        "rowId": 1,
        "createTime": "2017-06-29 18:59:17",
        "chatId": 2,
        "chatUserId": 1,
        "content": "aa",
        "flag": "1",
        "status": 0
    },
    {
        "rowId": 2,
        "createTime": "2017-06-29 19:00:08",
        "chatId": 2,
        "chatUserId": 2,
        "content": "b",
        "flag": "0",
        "status": 0
    }]
```
---
#### 发送消息

**接口地址:**  `api/v1/custom/service/send`

**请求参数**

|参数| 是否可选 | 参数说明 |
|---|---|---|
|cotent | 否| 发送内容 |
|chatId | 否| 客服聊天ID |

** 响应参数 **

`无`
