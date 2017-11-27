#### 全部场景
获取用户所有场景模式列表，包括系统默认、用户自定义场景。

**接口地址：**`api/v1/point/prod`

**请求参数**

|参数| 是否可选 | 参数说明 |
|---|---|---|
|pageNo | 否 | 分页码 |

**响应参数**

|参数| 参数类型 |是否可选 | 参数说明 |
|---|:---:|----|---|
|-| array | 是| 商品集合 |
|rowId| int | 否| 商品ID |
|nsortName| string | 否| 二级分类名称 |
|nsortId | int | 否| 二级分类ID |
|photo| string | 否| 列表图 |
|name| string| 否 | 商品名称 |
|stocks| int | 否 | 商品库存|
|norms | string | 否 | 规格：个、次、张等等|

**响应示例**
``` json
[{
  rowId: 1,
  nsortName: "会员专享",
  nsortId: 2,
  photo: "prod.png",
  name: "打车优惠券",
  stocks: 182,
  norms: "个"
}]
```
---

#### 场景详情
获取场景详情

**接口地址：**`api/v1/point/prod/detail`

**请求参数**

|参数| 是否可选 | 参数说明 |
|---|---|---|
|rowId | 否 | 商品ID |

**响应参数**

|参数| 参数类型 |是否可选 | 参数说明 |
|---|:---:|----|---|
|rowId | int | 否 | 商品ID |
|name | string| 否 | 商品名称 |
|fileName | string | 否 | 商品图片 |
|photo | string | 否 | 商品缩略图 |
|isLimitLevel | string | 否| 是否限制会员等级,`0:不限制，1:限制` |
|stocks | int| 否| 商品库存量 |
|content | string | 否 | 商品介绍 |
|point | int | 否 | 价值积分 |
|haveLevel | string | 否 | 是否有级别兑换,isLimitLevel为限制时，判断用户是否有等级兑换 |
|levelPoints | array | 是 | 等级积分列表 |
|levelPoints.levelCode| string | 否 | 等级代码 |
|levelPoints.levelName| string | 否 | 等级名称 |
|levelPoints.point| int | 否 | 等级兑换积分 |
|levelPoints.description | int | 否 | 等级兑换描述 |
|deliveryModes | array | 否 | 配送方式列表 |
|deliveryModes.code| string | 否| 配送方式代码 |
|deliveryModes.value| string | 否 | 配送方式说明 |

**响应示例**

```json
{
  rowId: 1,
  name: "商品名称",
  fileName: "商品图片.png",
  photo: "商品缩略图片.png",
  isLimitLevel: "1",
  stocks: 20,
  content: "商品详情介绍",
  point: "价值积分",
  haveLevel: "1",
  levelPoints: [{
    levelCode: "diamond",
    levelName: "钻石会员",
    point: 200,
    description: "200金豆兑换",
  },{
    levelCode: "VIP",
    levelName: "至尊VIP",
    point: 100,
    description: "100金豆兑换",
  }],
  deliveryModes: [{
    code: "self",
    value: "自提"
  },{
    code: "express",
    value: "快递送货"
  }]
}
```
---

#### 场景详情修改
通过该修改场景动作、名称、图标（名称、图标只有用户自定义场景才可修改）

**接口地址：** `api/v1/point/prod/exchange`

**请求参数**

|参数| 是否可选 | 参数说明 |
|---|---|---|
|prodId | 否 | 商品ID |
|deliveryMode | 否 | 配送方式 |
|subName| 否 | 联系人 |
|subTel| 否 | 联系电话 |
|subAdds| 否 | 联系地址 |

**响应参数**

`无`

---

#### 场景选择
通过该接口选择执行场景

**接口地址：** `api/v1/point/prod/exchange`

**请求参数**

|参数| 是否可选 | 参数说明 |
|---|---|---|
|prodId | 否 | 商品ID |
|deliveryMode | 否 | 配送方式 |
|subName| 否 | 联系人 |
|subTel| 否 | 联系电话 |
|subAdds| 否 | 联系地址 |

**响应参数**

`无`

---


#### 用户偏好场景
编辑用户偏好场景模式，显示在首页

**接口地址：**`api/v1/point/prod/exchangeDetail`

**请求参数**

|参数| 是否可选 | 参数说明 |
|---|---|---|
|rowId | 否 | 兑换记录唯一标识 |

**响应参数**

|参数| 参数类型 |是否可选 | 参数说明 |
|---|:---:|----|---|
|rowId | int | 否 | 兑换记录唯一标识 |
|voucherCode | string| 否 | 订单编号 |
|subName | string | 否 | 联系人 |
|subTel | string | 否| 联系电话 |
|subAdds | string| 否| 联系地址 |
|status| string | 否 | 兑换状态，`01:已兑换、02:发货中、03:已完成` |
|deliveryMode | string | 否 | 领取方式 |
|expressNo| string | 是 | 快递单号，`非空是显示` |
|prodId | int | 否 | 商品ID |
|prodName | string| 否 | 商品名称 |
|photo | string | 否 | 商品缩略图片 |
|point | int | 否| 兑换积分 |
|num | int| 否| 兑换数量 |

**响应示例**

```json
{
  rowId: 1,
  voucherCode: "P994836253401",
  subName: "张三",
  subTel: "13776668293",
  subAdds: "郁金香路30号吉美思大厦",
  status: "01",
  deliveryMode: "快递配送",
  expressNo: "快递单号",
  prodId: 1,
  prodName: "商品名称",
  photo: "商品缩略图.png",
  point: 100,
  num: 1
}
```

---

#### 场景设备
获取设备列表

**接口地址：**`api/v1/point/prod/exchangeDetail`

**请求参数**

|参数| 是否可选 | 参数说明 |
|---|---|---|
|rowId | 否 | 兑换记录唯一标识 |

**响应参数**

|参数| 参数类型 |是否可选 | 参数说明 |
|---|:---:|----|---|
|rowId | int | 否 | 兑换记录唯一标识 |
|voucherCode | string| 否 | 订单编号 |
|subName | string | 否 | 联系人 |
|subTel | string | 否| 联系电话 |
|subAdds | string| 否| 联系地址 |
|status| string | 否 | 兑换状态，`01:已兑换、02:发货中、03:已完成` |
|deliveryMode | string | 否 | 领取方式 |
|expressNo| string | 是 | 快递单号，`非空是显示` |
|prodId | int | 否 | 商品ID |
|prodName | string| 否 | 商品名称 |
|photo | string | 否 | 商品缩略图片 |
|point | int | 否| 兑换积分 |
|num | int| 否| 兑换数量 |

**响应示例**

```json
{
  rowId: 1,
  voucherCode: "P994836253401",
  subName: "张三",
  subTel: "13776668293",
  subAdds: "郁金香路30号吉美思大厦",
  status: "01",
  deliveryMode: "快递配送",
  expressNo: "快递单号",
  prodId: 1,
  prodName: "商品名称",
  photo: "商品缩略图.png",
  point: 100,
  num: 1
}
```

---

#### 设备动作
获取设备动作列表

**接口地址：**`api/v1/point/prod/exchangeDetail`

**请求参数**

|参数| 是否可选 | 参数说明 |
|---|---|---|
|rowId | 否 | 兑换记录唯一标识 |

**响应参数**

|参数| 参数类型 |是否可选 | 参数说明 |
|---|:---:|----|---|
|rowId | int | 否 | 兑换记录唯一标识 |
|voucherCode | string| 否 | 订单编号 |
|subName | string | 否 | 联系人 |
|subTel | string | 否| 联系电话 |
|subAdds | string| 否| 联系地址 |
|status| string | 否 | 兑换状态，`01:已兑换、02:发货中、03:已完成` |
|deliveryMode | string | 否 | 领取方式 |
|expressNo| string | 是 | 快递单号，`非空是显示` |
|prodId | int | 否 | 商品ID |
|prodName | string| 否 | 商品名称 |
|photo | string | 否 | 商品缩略图片 |
|point | int | 否| 兑换积分 |
|num | int| 否| 兑换数量 |

**响应示例**

```json
{
  rowId: 1,
  voucherCode: "P994836253401",
  subName: "张三",
  subTel: "13776668293",
  subAdds: "郁金香路30号吉美思大厦",
  status: "01",
  deliveryMode: "快递配送",
  expressNo: "快递单号",
  prodId: 1,
  prodName: "商品名称",
  photo: "商品缩略图.png",
  point: 100,
  num: 1
}
```

---
