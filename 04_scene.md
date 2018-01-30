#### 全部场景
获取用户所有场景模式列表，包括系统默认、用户自定义场景。

**接口地址：**`api/v1/scene/all`

**请求参数**

`无`

**响应参数**

| 参数               | 参数类型 | 是否可选 | 参数说明                 |
| ---                | :---:    | ----     | ---                      |
| myScene            | array    | 否       | 显示的情景模式数组       |
| myScene.id         | int      | 否       | 情景id                   |
| myScene.icon       | string   | 否       | 情景图标                 |
| myScene.name       | string   | 否       | 情景名称                 |
| myScene.isDefault  | int      | 否       | 是否默认0：默认1：自定义 |
| allScene           | array    | 否       | 所有情景模式数组         |
| allScene.id        | int      | 否       | 情景id                   |
| allScene.icon      | string   | 否       | 情景图标                 |
| allScene.name      | string   | 否       | 情景名称                 |
| allScene.isDefault | int      | 否       | 是否默认0：默认1：自定义 |



**响应示例**
``` json
{
  myScene:[{
        id:101,
        icon:"1k4ljldksjlfjdl.png",
        name:"上班",
        isDefault: 0
    }],
    allScene:[
    {
        id:101,
        icon:"1k4ljldksjlfjdl.png",
        name:"上班",
        isDefault: 0
    },{
        id:102,
        icon:"1k4ljldksjlfjdl.png",
        name:"我的场景",
        isDefault: 1
    }
    ]
}
```
---

#### 场景详情
获取场景详情

**接口地址：**`api/v1/scene/detail`

**请求参数**

|  参数 | 是否可选 | 参数说明 |
|-------|----------|----------|
| rowId | 否       | 场景ID   |

**响应参数**

| 参数       | 参数类型 | 是否可选 | 参数说明 |
| ---        | :---:    | ----     | ---      |
| -          | array    | 否       | 数组     |
| deviceName | string   | 否       | 设备名称 |
| deviceId   | int      | 否       | 设备 ID  |
| orderId    | int      | 否       | 指令ID   |
| orderName  | string   | 否       | 指令名称 |


**响应示例**

```json
[
  {
    deviceId:1,
    deviceName:"空调",
    orderId:11,
    orderName:"启动"
  }，{
    deviceId:1,
    deviceName:"空调",
    orderId:12,
    orderName:"制热模式"
  }
]
```
---

#### 编辑场景详情
通过该接口新增或编辑场景动作、名称、图标（名称、图标只有用户自定义场景才可修改）

**接口地址：** `api/v1/scene/edit`

**请求参数**

|       参数      | 参数类型 | 是否可选 |           参数说明           |
|-----------------|----------|----------|------------------------------|
| rowId           | int      | 是       | 场景ID，编辑时有，新增时没有 |
| icon            | string   | 是       | 场景图标编码                 |
| name            | string   | 是       | 场景名称                     |
| action          | array    | 否       | 场景动作                     |
| action.deviceId | int      | 否       | 设备 ID                      |
| action.orderId  | int      | 否       | 指令 ID                      |


**响应参数**

`无`

---

#### 删除场景
通过该接口删除用户自定义场景

**接口地址：** `api/v1/scene/delete`

**请求参数**

|  参数 | 是否可选 | 参数说明 |
|-------|----------|----------|
| rowId | 否       | 场景ID   |


**响应参数**

`无`

---



#### 用户偏好场景选择
通过该接口选择用户偏好场景模式，显示在首页

**接口地址：**`api/v1/scene/set`

**请求参数**

|  参数  | 是否可选 |      参数说明     |
|--------|----------|-------------------|
| rowIds | 否       | 首页场景ID,号分隔 |

**响应参数**

`无`

---

#### 场景执行
通过该接口选择执行场景

**接口地址：** `api/v1/scene/exec`

**请求参数**

|  参数 | 是否可选 | 参数说明 |
|-------|----------|----------|
| rowId | 否       | 场景ID   |

**响应参数**

`无`

---
