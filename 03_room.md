#### 房间列表
获取网关下的房间列表

**接口地址:**  `api/v1/room/list`

**请求参数**

|    参数   | 是否可选 | 参数说明 |
|-----------|----------|----------|
| gatewayId | 否       | 网关Id   |


**响应参数**

| 参数             | 参数类型 | 是否可选 | 参数说明       |
| ---              | :---:    | ----     | ---            |
| -                | array    | 否       | 数组           |
| rowId            | int      | 否       | 唯一标识       |
| name             | string   | 否       | 房间名称       |
| thumb            | string   | 否       | 房间背景图     |
| deviceCount      | int      | 否       | 设备总数       |
| workingCount     | int      | 否       | 工作中设备数   |
| pmValue          | string   | 是       | PM2.5传感值    |
| co2Value         | string   | 是       | 二氧化碳传感值 |
| temperatureValue | string   | 是       | 温度值         |
| humidityValue    | string   | 是       | 湿度值         |

** 响应示例 **

``` json
[{
  rowId:1,
  name:"客厅",
  thumb:"dkglddgdkssgsgag.png",
  deviceCount:6,
  workingCount:5,
  pmValue:"157ug/m³",
  co2Value:"640ppm",
  temperatureValue:"24℃",
  humidityValue:"60%"
}]
```

---

#### 房间详情
获取房间详情，展示温、湿度，PM2.5,二氧化碳浓度等传感信息；房间设备列表。

**接口地址:**  `api/v1/room/detail`

**请求参数**

|  参数 | 是否可选 | 参数说明 |
|-------|----------|----------|
| rowId | 否       | 房间Id   |

** 响应参数 **

| 参数                 | 参数类型 | 是否可选 | 参数说明                                     |
| ---                  | :---:    | ----     | ---                                          |
| rowId                | int      | 否       | 唯一标识                                     |
| name                 | string   | 否       | 房间名称                                     |
| thumb                | string   | 否       | 房间背景图                                   |
| deviceCount          | int      | 否       | 设备总数                                     |
| workingCount         | int      | 否       | 工作中设备数                                 |
| pmValue              | string   | 是       | PM2.5传感值                                  |
| pmDesc               | string   | 是       | PM2.5数值说明                                |
| pmColor              | int      | 是       | PM2.5说明文字颜色，十六进制0xffffff          |
| co2Value             | string   | 是       | 二氧化碳传感值                               |
| co2Desc              | string   | 是       | 二氧化碳数值说明                             |
| co2Color             | int      | 是       | 二氧化碳说明文字颜色，十六进制0xffffff       |
| temperatureValue     | string   | 是       | 温度值                                       |
| humidityValue        | string   | 是       | 湿度值                                       |
| comfortDesc          | string   | 是       | 舒适度说明，舒适度根据温湿度计算出来         |
| comfortColor         | int      | 是       | 舒适度说明文字颜色，十六进制0xffffff         |
| device               | array    | 是       | 设备                                         |
| device.id            | int      | 否       | 设备 ID                                      |
| device.name          | string   | 否       | 设备名称                                     |
| device.roomName      | string   | 否       | 所属房间                                     |
| device.icon          | string   | 否       | 设备图标                                     |
| device.status        | int      | 否       | 设备状态 0：设备在线 1：设备离线 2：设备故障 |
| device.workingMode   | string   | 否       | 设备当前工作模式，仅当设备在线时有值         |
| device.workingStatus | string   | 否       | 设备当前工作状态，仅当设备在线时有值         |
| device.model         | string   | 否       | 设备型号                                     |
| device.modelId       | int      | 否       | 设备型号 ID                                  |
|                      |          |          |                                              |


** 响应示例 **

``` json
{
  rowId:1,
  name:"客厅",
  thumb:"dkglddgdkssgsgag.png",
  deviceCount:6,
  workingCount:5,
  pmValue:"157ug/m³",
  pmDesc:"污染大",
  pmColor:0xffffff,
  co2Value:"640ppm",
  co2Desc:"舒适",
  co2Color:0xffffff,
  temperatureValue:"24℃",
  humidityValue:"60%",
  comfortDesc:"神清气爽",
  comfortColor:0xffffff,
  device:[{
        id:111,
        name:"空调",
        roomName:"客厅",
        icon:"lkdgjlskdjgldsj.png",
        status:0,
        workingMode:"制热",
        workingStatus:"26℃",
        model:"KDH-2000",
        modelId:10
    }]
}
```


