#### 个人信息
获取个人信息详情

**接口地址：**`api/v1/user/detail`

**token 验证:**  `是`

**请求参数**

`无`

**响应参数**

| 参数     | 参数类型 | 是否可选 | 参数说明            |
| ---      | :---:    | ----     | ---                 |
| rowId    | int      | 否       | userId,用户唯一标识 |
| nickname | string   | 否       | 用户昵称            |
| avatar   | string   | 否       | 用户头像            |


**响应示例**
```json
{
  rowId: 1,
  nickname: "张三",
  avatar: "用户头像",
}
```
---

#### 用户绑定网关
该接口用于用户绑定网关 `扫描二维码绑定`

**接口地址：**`api/v1/user/gateway/binding`

**token 验证:**  `是`

**请求参数**

|    参数    | 是否可选 | 参数说明 |
|------------|----------|----------|
| gatewaySeq | 否       | 网关编号 |

**响应参数**

| 参数          | 参数类型 | 是否可选 | 参数说明     |
| ---           | :---:    | ----     | ---          |
| -             | array    | 否       | 项目         |
| project.id    | int      | 否       | 项目ID       |
| project.name  | string   | 否       | 项目名称     |
| project.bgPic | string   | 是       | 项目背景图片 |

**响应示例**

``` json
[{
  id:111,
  name:"东大创客中心",
  bgPic:"pic/ahfga12bdc.jpg"
}]
```

---

#### 用户解绑网关
该接口用于解除用户与网关的绑定

**接口地址：**`api/v1/user/gateway/unbind`

**token 验证:**  `是`

**请求参数**

|    参数    | 是否可选 | 参数说明 |
|------------|----------|----------|
| gatewayId | 否       | 网关ID |

**响应参数**

| 参数          | 参数类型 | 是否可选 | 参数说明     |
| ---           | :---:    | ----     | ---          |
| -             | array    | 否       | 项目         |
| project.id    | int      | 否       | 项目ID       |
| project.name  | string   | 否       | 项目名称     |
| project.bgPic | string   | 是       | 项目背景图片 |

** 响应示例 **
``` json
[{
  id:111,
  name:"东大创客中心",
  bgPic:"pic/ahfga12bdc.jpg"
}]
```

---

#### 我的网关列表
该接口获取我的所有网关列表

**接口地址：**`api/v1/user/gateway/list`

**token 验证:**  `是`

**请求参数**

`无`

**响应参数**

| 参数  | 参数类型 | 是否可选 | 参数说明   |
| ---   | :---:    | ----     | ---        |
| -     | array    | 是       | 网关       |
| id    | int      | 是       | 网关 ID    |
| name  | string   | 是       | 名称       |
| seq   | string   | 是       | 网关序列号 |
| level | int      | 是       | 网关等级   |


** 响应示例 **

``` json
[{
  id:101,
  name:"房间网关",
  seq:"0x0x0x0x0x0x0x0x",
  level:0
}]
```
---


#### 网关详情
该接口获取网关详情

**接口地址：**`api/v1/user/gateway/detail`

**token 验证:**  `是`

**请求参数**

|    参数   | 是否可选 | 参数说明 |
|-----------|----------|----------|
| gatewayId | 否       | 网关ID |

**响应参数**

| 参数                 | 参数类型 | 是否可选 | 参数说明                                     |
| ---                  | :---:    | ----     | ---                                          |
| rowId                | int      | 否       | 唯一标识                             |
| gatewayName          | string   | 否       | 网关名称                                     |
| gatewaySeq           | string   | 否       | 网关编号                                     |
| workingDeviceNum     | int      | 否       | 运行中设备数                                 |
| offlineDeviceNum     | int      | 否       | 离线中设备数                                 |
| faultDeviceNum       | int      | 否       | 故障中设备数                                 |
| device               | array    | 否       | 设备数组                                 |
| device.id            | int      | 否       | 设备 ID                                      |
| device.name          | string   | 否       | 设备名称                                     |
| device.roomName      | string   | 否       | 所属房间                                     |
| device.icon          | string   | 否       | 设备图标                                     |
| device.status        | int      | 否       | 设备状态 0：设备离线 1：设备在线 2：设备故障 |
| device.model         | string   | 否       | 设备型号                                     |


** 响应示例 **

``` json
{
  rowId: 1,
  gatewayName:"",
  gatewaySeq:"",
  workingDeviceNum:10,
  offlineDeviceNum:0,
  faultDeviceNum:0,
  device:[{
        id:111,
        name:"空调",
        roomName:"客厅",
        icon:"lkdgjlskdjgldsj.png",
        status:0,
        mode:"KDH-2000"
    }]
}
```
---
