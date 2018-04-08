#### 未读消息数
查询用户的未读消息数量

**接口地址：**`api/v1/msg/unread`

**token 验证:**  `是`

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

#### 首页接口
返回我的首页场景模式、常用设备、设备运行数量

**接口地址:**  `api/v1/home/index`

**token 验证:**  `是`

**请求参数**

|    参数   | 是否可选 | 参数说明 |
|-----------|----------|----------|
| projectId | 否       | 项目 ID  |

**响应参数**

| 参数                 | 参数类型 | 是否可选 | 参数说明                                     |
| ---                  | :---:    | ----     | ---                                          |
| workingDeviceCount   | int      | 否       | 工作中设备数量                               |
| scene                | array    | 否       | 我的情景模式数组                             |
| scene.id             | int      | 否       | 情景id                                       |
| scene.icon           | string   | 否       | 情景图标                                     |
| scene.name           | string   | 否       | 情景名称                                     |
| scene.status         | int      | 否       | 情景状态，0：默认状态 1：运行状态            |
| device               | array    | 否       | 常用设备数组                                 |
| device.id            | int      | 否       | 设备 ID                                      |
| device.name          | string   | 否       | 设备名称                                     |
| device.roomName      | string   | 否       | 所属房间                                     |
| device.icon          | string   | 否       | 设备图标                                     |
| device.status        | int      | 否       | 设备状态 0：设备离线 1：设备在线 2：设备故障 |
| device.workingMode   | string   | 否       | 设备当前工作模式，仅当设备在线时有值         |
| device.workingStatus | string   | 否       | 设备当前工作状态，仅当设备在线时有值         |
| device.model         | string   | 否       | 设备型号                                             |


** 响应示例 **

``` json
{
  workingDeviceCount:3,
  scene:[{
        id:101,
        icon:"1k4ljldksjlfjdl.png",
        name:"上班",
        status:0
    }],
  device:[{
        id:111,
        name:"空调",
        roomName:"客厅",
        icon:"lkdgjlskdjgldsj.png",
        status:0,
        workingMode:"制热",
        workingStatus:"26℃",
        mode:"KDH-2000"
    }]
}
```

---

