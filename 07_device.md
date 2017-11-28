#### 设备列表
获取所选网关下所有设备列表

**接口地址:**  `api/v1/device/list`

**请求参数**

|    参数   | 是否可选 |    参数说明    |
|-----------|----------|----------------|
| gatewayId | 否       | 网关 ID        |
| roomId    | 是       | 房间 ID,默认-1 |
| groupId   | 是       | 分组 ID,默认-1 |
| pageNo    | 否       | 页码           |

** 响应参数 **

| 参数     | 参数类型 | 是否可选 | 参数说明                                     |
| ---      | :---:    | ----     | ---                                          |
| -        | array    | 是       | 数组                                         |
| rowId    | int      | 否       | 唯一标识                                     |
| name     | string   | 否       | 设备名称                                     |
| icon     | string   | 否       | 设备图标                                     |
| roomName | string   | 否       | 所属房间                                     |
| status   | int      | 否       | 设备状态 0：设备在线 1：设备离线 2：设备故障 |
| model    | string   | 否       | 设备型号                                     |


** 响应示例 **

``` json
[{
  rowId: 1,
  name: "空调",
  icon: "gdsgksldgkjsl.png",
  roomName: "房间一",
  status: 0,
  model:"kdkg-1000"
}]
```
---

#### 设备分类筛选
获取设备分类筛选条件

**接口地址:**  `api/v1/device/filterList`

**请求参数**

|    参数   | 是否可选 |    参数说明    |
|-----------|----------|----------------|
| gatewayId | 否       | 网关 ID        |

** 响应参数 **

| 参数        | 参数类型 | 是否可选 | 参数说明 |
| ---         | :---:    | ----     | ---      |
| room        | array    | 否       | 房间     |
| room.rowId  | int      | 否       | 唯一标识 |
| room.name   | string   | 否       | 房间名称 |
| group       | array    | 否       | 分组     |
| group.rowId | int      | 否       | 唯一标识 |
| group.name  | string   | 否       | 组名称   |

** 响应示例 **

``` json
{
  room:[{
      rowId:1,
      name:"房间一"
    }],
  group:[{
      rowId:1,
      name:"灯"
    }]
}
```
---

#### 设备指令动作
通过该接口获取设备指令列表

**接口地址：**`api/v1/device/orderList`

**请求参数**

|     参数    | 是否可选 | 参数说明 |
|-------------|----------|----------|
| deviceModel | 否       | 设备型号 |

**响应参数**

| 参数      | 参数类型 | 是否可选 | 参数说明 |
| ---       | :---:    | ----     | ---      |
| -         | array    | 否       | 指令集合 |
| rowId     | int      | 否       | 指令 ID  |
| orderName | string   | 否       | 指令名称 |


**响应示例**

```json
[
    {
      rowId:1,
      orderName:"启动"
    },{
      rowId:2,
      orderName:"制热模式"
    }
]
```
---

#### 编辑常用设备
通过该接口编辑我的常用设备（添加、删除）

**接口地址:**  `api/v1/device/favorite/edit`

**请求参数**

|   参数   | 是否可选 |         参数说明        |
|----------|----------|-------------------------|
| deviceIds | 否       | 设备 ID，`只传选中的设备,以逗号分隔` |

** 响应参数 **

`无`

** 响应示例 **

`无`

---
