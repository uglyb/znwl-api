#### 未读消息数
查询用户的未读消息数量

**接口地址：**`api/v1/msg/unread`

**请求参数**

`无`

**响应参数**

| 参数  | 参数类型 | 是否可选 | 参数说明       |
| ---   | :---:    | ----     | ---            |
| count | int      | 否       | 未读消息通知数 |

**响应示例**

```json
{
  count: 1
}
```
---

#### 首页概览
返回首页概览信息

**接口地址:**  `api/v1/banner/index`

**请求参数**

`无`

** 响应参数 **

| 参数        | 参数类型 | 是否可选 | 参数说明                                                                                   |
| ---         | :---:    | ----     | ---                                                                                        |
| -           | array    | 是       | 轮播广告集合                                                                               |
| pic         | string   | 否       | 轮播图片                                                                                   |
| drillable   | string   | 否       | 是否可钻取：0:false,1:true                                                                 |
| drillModule | string   | 否       | 钻取模块，[见附录](/appendix?id=app%e9%92%bb%e5%8f%96%e6%a8%a1%e5%9d%97%e5%ae%9a%e4%b9%89) |
| drillType   | int      | 否       | 钻取类型(0：列表，1：明细)                                                                 |
| drillValue  | string   | 否       | 钻取参数                                                                                   |

** 响应示例 **

``` json
[{
  pic: "banner/hfhga748377bvg.png",
  drillable: "1",
  drillModule: "10001",
  drillType: 1,
  drillValue: "1"
}]
```

---

#### 场景模式

查询用户首页场景列表

**接口地址:**  `api/v1/scene/index`

**请求参数**

`无`

** 响应参数 **

|参数| 参数类型 |是否可选 | 参数说明 |
|---|:---:|----|---|
|-| array | 是| 数组|
|moduleCode| string | 否 | 模块编码 |
|moduleName| string | 否 | 模块名称|
|modulePhoto| string | 否 | 模块图片|
|moduleMethod| string | 否 | 模块方法 |

** 响应示例 **

``` json
[{
  moduleCode: "company",
  moduleName: "公司动态",
  modulePhoto: "module/hfhga748377bvg.png",
  moduleMethod: "CompanyViewController"
}]
```

---

#### 常用设备
返回用户常用设备列表

**接口地址:**  `api/v1/news/index`

**请求参数**

`无`

** 响应参数 **

|参数| 参数类型 |是否可选 | 参数说明 |
|---|:---:|----|---|
|-| array | 是| 数组|
|title| string | 否 | 模块编码 |
|rowId| int | 否 | 投条唯一标识|

** 响应示例 **

``` json
[{
  title: "洛德德瑞基金二期上线啦！",
  rowId: 1
}]
```
!> 今日投条：在首页显示且是热门的资讯

---


#### 常用设备添加
添加用户常用设备

**接口地址:**  `api/v1/middleAd/index`

**请求参数**

`无`

** 响应参数 **

|参数| 参数类型 |是否可选 | 参数说明 |
|---|:---:|----|---|
| type | int | 否| 类型(3:3张广告，5：5张广告位)|
|item | array | 否 | 广告集合 |
|item.pic| string | 否 | 图片|
|item.drillable| string| 否| 是否可钻取 |
|item.drillModule| string| 是| 钻取模块，[见附录](/appendix?id=app%e9%92%bb%e5%8f%96%e6%a8%a1%e5%9d%97%e5%ae%9a%e4%b9%89)|
|item.drillType| int| 是| 钻取类型(0：列表，1：明细) |
|item.drillValue| string| 是| 钻取值|

** 响应示例 **

``` json
{
  type: 3,
  item: [
    {
      pic: "hfhga748377bvg.png",
      drillable: "1",
      drillModule: "1002",
      drillType: 1,
      drillValue: "12"
    }
  ]
}
```
---


#### 设备列表
获取所选网关下所有设备列表

**接口地址:**  `api/v1/fund/index`

**请求参数**

`无`

** 响应参数 **

|参数| 参数类型 |是否可选 | 参数说明 |
|---|:---:|----|---|
| - | array | 是| 数组 |
|rowId | int | 否| 唯一标识|
|type | int | 否 | 基金类型（0:股权，1：债权） |
|name| string | 否 | 基金名称|
|tags| string | 否 | 标签，`逗号拆分`|
|incomeRate | string| 否| 收益率 |
|investCycle | int| 否| 投资期限，单位：月 |
|startingAmount | int| 否| 起投金额，单位：万 |

** 响应示例 **

``` json
[{
  rowId: 1,
  type: 0,
  name: "德瑞1期",
  tags: "洛德,市场",
  incomeRate: "2.8%+",
  investCycle: 12,
  startingAmount: 120
}]
```
