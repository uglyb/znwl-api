#### 房间列表
获取网关下的房间列表

**接口地址:**  `api/v1/activity`

**请求参数**

|  参数  | 是否可选 | 参数说明 |
|--------|----------|----------|
| pageNo | 否       | 分页码   |


** 响应参数 **

|参数| 参数类型 |是否可选 | 参数说明 |
|---|:---:|----|---|
|-| array | 否 | 数组 |
|rowId| int | 否| 活动唯一标识|
|title| string | 否 | 活动标题|
|typeName| string | 否| 活动类型： `地产、楼盘`|
|thumb| string | 否 | 缩略图|
|beginTime| string | 否 | 活动开始时间，`格式:yyyy-MM-dd HH:mm:ss`, 移动端删除`:ss` |
|address| string | 否| 活动地址 |

** 响应示例 **

``` json
[{
  title: "皇家游轮会员活动",
  typeName: "地产",
  thumb: "活动图.png",
  beginTime: "2017-06-07 14:48:20",
  address: "郁金香路30号吉美思大厦701"
}]
```

---

#### 房间详情
获取房间详情，展示温、湿度，PM2.5,二氧化碳浓度等传感信息；房间设备列表。

**接口地址:**  `api/v1/activity/detail`

**请求参数**

|参数| 是否可选 | 参数说明 |
|---|---|---|
|rowId| 否 | 活动Id |

** 响应参数 **

|参数| 参数类型 |是否可选 | 参数说明 |
|---|:---:|----|---|
|rowId| int | 否| 活动唯一标识|
|title| string | 否 | 活动标题|
|thumb| string | 否 | 缩略图|
|beginTime| string | 否 | 活动开始时间，`格式:yyyy-MM-dd HH:mm:ss`, 移动端删除`:ss` |
|endTime| string| 否| 活动结束时间，`格式:yyyy-MM-dd HH:mm:ss`, 移动端删除`:ss`|
|address| string | 否| 活动地址 |
|content| string | 否| 活动介绍内容 |
|canJoin| string | 否| 是否可以报名，`0：不可报名，1：可报名` |
|cantJoinReason | string | 是 | 不可报名说明 |
|closeJoin | string | 否 | 是否截止报名 |
|lon | decimal | 否 | 坐标经度 |
|lat | decimal | 否 | 坐标维度 |
|isJoin| string | 否| 是否已报名，`0：未报名，1：已报名`|

** 响应示例 **

``` json
{
  title: "皇家游轮会员活动",
  thumb: "活动图.png",
  beginTime: "2017-06-07 14:48:20",
  endTime: "2017-06-09 14:48:20",
  address: "郁金香路30号吉美思大厦701",
  content: "活动内容",
  canJoin: "0",
  cantJoinReason: "截止报名",
  closeJoin: "1",
  isJoin: "0",
  lon: 2847376366734.114747
  lat: 178364729382.2251
}
```


