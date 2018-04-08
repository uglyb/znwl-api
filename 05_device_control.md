#### 设备通道
通过该接口获取设备通道数据，客户端通过设备类型来控制进入哪个设备操作页面。

`客户端相关设备类型定义，需要与后台一致`

**接口地址:**  `api/v1/device/control/channel`

**token 验证:**  `是`

**请求参数**

|      参数     | 是否可选 | 参数说明 |
|---------------|----------|----------|
| deviceId      | 否       | 设备 ID  |



** 响应参数 **

| 参数                      | 参数类型 | 是否可选 | 参数说明                                                                                          |
| ---                       | :---:    | ----     | ---                                                                                               |
| channelInfo               | array    | 是       | 通道数组                                                                                          |
| channelInfo.channelNum    | string   | 否       | 通道号                                                                                            |
| channelInfo.channelName   | string   | 否       | 通道名称                                                                                          |
| channelInfo.channelValue  | string   | 否       | 通道值                                                                                            |
| channelInfo.channelStatus | string   | 否       | 通道状态                                                                                          |
| channelInfo.channelIcon   | string   | 否       | 通道图标                                                                                          |
| channelInfo.commandType   | string   | 否       | 指令类型：Default，Palette，GetPower，Zigbee_485，Infrared                                                  |
| channelInfo.zigbeeType    | string   | 是       | 表示红外设备功能键类型，只有当commandType为`Infrared`时有效；识别功能键，放在界面的哪个区域  。 |
| command                   | array    | 否       | 指令定义                                                                                          |
| command.type              | string   | 否       | 指令类型：Default，Palette，GetPower，Zigbee_485，Infrared                                                  |
| command.value             | string   | 否       | 指令值                                                                                            |




** 指令类型 **

|   字段值   |             字段说明             |
|------------|----------------------------------|
| Default    | 默认（包括开关设备，指示牌显示） |
| Palette    | 调节灯光色彩                     |
| GetPower   | 获取电量 ，计量插座设备          |
| Zigbee_485 | Zigbee透传                       |
| Infrared   | 红外设备                         |


** 指令值说明 **

    commandValue字段值解释：commandValue表示对设备的操作，如开关设备中0表示关，1表示开，
    在调光设备中表示调光值，在调色设备中表示RGB值，在红外设备中表示红外发送通道号。

** 响应示例 **
``` json
{
    channelInfo:[
        {
            channelNum: "1",
            channelName: "厕所灯",
            channelValue: "1",
            channelStatus: "1",
            channelIcon:"icon_code1",
            commandType:"Default",
            zigbeeType:"vol+"
        },{
            channelNum: "2",
            channelName: "客厅灯",
            channelValue: "0",
            channelStatus: "1",
            channelIcon:"icon_code2",
            commandType:"Default",
            zigbeeType:"vol+"
        }
    ],
    command:[
        {
            type: "Default",
            value: "0"
        },{
            type: "Default",
            value: "1"
        },{
             type: "GetPower",
             value: "11"
        }
  ]
}
```

---

#### 设备控制 `（服务端透传）`
通过该接口发送设备控制命令

`客户端相关设备类型定义，需要与后台一致`

**接口地址:**  `api/v1/device/control/command`

**token 验证:**  `是`

**请求参数**

|     参数     | 是否可选 | 参数说明 |
|--------------|----------|----------|
| deviceId     | 否       | 设备 ID  |
| channelNum   | 否       | 通道号   |
| channelValue | 否       | 通道值   |
| commandType  | 否       | 指令类型 |

** 指令类型 **

|   字段值   |             字段说明             |
|------------|----------------------------------|
| Default    | 默认（包括开关设备，指示牌显示） |
| Palette    | 调节灯光色彩                     |
| GetPower   | 获取电量 ，计量插座设备          |
| Zigbee_485 | Zigbee透传                       |
| Infrared   | 红外设备                         |

** channelNum字段值解释：**

    channelNum是在多路设备中，选择需要控制的第n路设备，如4路开关中，需控制第三路开关，
    则Channel为3。其他则默认为1。

** 响应参数 **

`无`

** 响应示例 **

`无`