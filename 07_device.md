#### 设备列表
获取所选网关下所有设备列表

**接口地址:**  `api/v1/device/list`

**token 验证:**  `是`

**请求参数**

|    参数   | 是否可选 |    参数说明    |
|-----------|----------|----------------|
| projectId | 否       | 项目 ID  |
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
| deviceModel    | string   | 否       | 设备型号                                     |
| deviceModelId  | int      | 否       | 设备型号 ID                                             |


** 响应示例 **

``` json
[{
  rowId: 1,
  name: "空调",
  icon: "gdsgksldgkjsl.png",
  roomName: "房间一",
  status: 0,
  deviceModel:"kdkg-1000",
  deviceModelId:101
}]
```
---

#### 设备分类筛选
获取设备分类筛选条件

**接口地址:**  `api/v1/device/filter/list`

**token 验证:**  `是`

**请求参数**

|    参数   | 是否可选 |    参数说明    |
|-----------|----------|----------------|
| projectId | 否       | 项目 ID  |

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

**接口地址：**`api/v1/device/command/list`

**token 验证:**  `是`

**请求参数**

|   参数  | 是否可选 |  参数说明  |
|---------|----------|------------|
| deviceId | 否       | 设备ID |

**响应参数**

| 参数                 | 参数类型 | 是否可选 | 参数说明 |
| ---                  | :---:    | ----     | ---      |
| -                    | array    | 否       | 通道     |
| rowId                | int      | 否       | 通道 ID  |
| number               | int      | 否       | 通道号   |
| name                 | string   | 否       | 通道名称   |
| command              | array    | 否       | 指令集合 |
| command.commandId    | int      | 否       | 指令 ID  |
| command.commandName  | string   | 否       | 指令名称 |
| command.commandValue | string   | 否       | 指令值   |



**响应示例**

```json
[
    {
        rowId: 1, 
        number: 1, 
        name:"开关"
        command: [
            {
                commandId: 1, 
                commandName: "启动", 
                commandValue: 1
            }, 
            {
                commandId: 1, 
                commandName: "启动", 
                commandValue: 1
            }
        ]
    }, 
    {
        rowId: 2, 
        number: 1, 
        name:"空调"
        command: [
            {
                commandId: 1, 
                commandName: "启动", 
                commandValue: 1
            }
        ]
    }
]
```
---

#### 常用设备列表
通过该接口获取用户常用设备列表

**接口地址:**  `api/v1/device/favorite/list`

**token 验证:**  `是`

**请求参数**

|    参数   | 是否可选 | 参数说明 |
|-----------|----------|----------|
| projectId | 否       | 项目 ID  |

** 响应参数 **

| 参数        | 参数类型 | 是否可选 | 参数说明                                     |
| ---         | :---:    | ----     | ---                                          |
| -           | array    | 是       | 数组                                         |
| rowId       | int      | 否       | 唯一标识                                     |
| name        | string   | 否       | 设备名称                                     |
| icon        | string   | 否       | 设备图标                                     |
| roomName    | string   | 否       | 所属房间                                     |
| status      | int      | 否       | 设备状态 0：设备在线 1：设备离线 2：设备故障 |
| model       | string   | 否       | 设备型号                                     |
| is_favorite | int      | 否       | 是否常用设备 0：否 1：是                     |

** 响应示例 **

``` json
[{
  rowId: 1,
  name: "空调",
  icon: "gdsgksldgkjsl.png",
  roomName: "房间一",
  status: 0,
  model:"kdkg-1000",
  is_favorite:0
}]
```

---


#### 编辑常用设备
通过该接口编辑我的常用设备（添加、删除）

**接口地址:**  `api/v1/device/favorite/edit`

**token 验证:**  `是`

**请求参数**

|   参数   | 是否可选 |         参数说明        |
|----------|----------|-------------------------|
| deviceIds | 否       | 设备 ID，`只传选中的设备,以逗号分隔` |

** 响应参数 **

`无`

** 响应示例 **

`无`

---

#### 分类设备列表
通过该接口获取用户分类设备列表

**接口地址:**  `api/v1/device/class/list`

**token 验证:**  `是`

**请求参数**

|    参数   | 是否可选 | 参数说明 |
|-----------|----------|----------|
| projectId | 否       | 项目 ID  |

** 响应参数 **

| 参数                 | 参数类型 | 是否可选 | 参数说明                                     |
| ---                  | :---:    | ----     | ---                                          |
| -                    | array    | 是       | 数组                                         |
| typeName             | string   | 否       | 设备分类名称                                 |
| typeCode             | string   | 否       | 设备分类编码                                 |
| device               | array    | 是       | 设备分组                                     |
| device.rowId         | int      | 否       | 唯一标识                                     |
| device.name          | string   | 否       | 设备名称                                     |
| device.icon          | string   | 否       | 设备图标                                     |
| device.roomName      | string   | 否       | 所属房间                                     |
| device.status        | int      | 否       | 设备状态 0：设备在线 1：设备离线 2：设备故障 |
| device.workingMode   | string   | 否       | 设备当前工作模式，仅当设备在线时有值         |
| device.workingStatus | string   | 否       | 设备当前工作状态，仅当设备在线时有值         |
| device.model         | string   | 否       | 设备型号                                     |
| device.modelId       | int      | 否       |  设备型号 id                                             |

** 响应示例 **

``` json
[{
  typeName:"空调",
  typeCode:"kongtiao",
  device:[{
          rowId: 1,
          name: "空调",
          icon: "gdsgksldgkjsl.png",
          roomName: "房间一",
          status: 0,
          workingMode:"制热",
          workingStatus:"26℃",
          model:"kdkg-1000",
          modelId:10
        }]
}]
```

---
