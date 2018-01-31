#### <span id="drill-module">设备网关透传定义</span>
!> 消息透传使用json格式传输 

##### 透传消息定义

----------

|       类型       | 类型代码 |           参数           |  类型  | 字段说明 |
|------------------|----------|--------------------------|--------|----------|
| 设备控制消息透传 |     1001 | deviceId                 | string | 设备id   |
|                  |          | deviceModel              | string | 设备类型 |
| 设备主动上传数据 |     2001 | deviceId                 | string | 设备 id  |
|                  |          | deviceModel              | string | 设备类型 |
|                  |          | deviceData               | array  | 设备数据 |
|                  |          | deviceData.channelNumber | string | 通道     |
|                  |          | deviceData.channelValue  | string | 通道值   |
|                  |          | deviceData.channelStatus | string | 通道状态 |

** 固定字段 **

| 字段 |     字段含义     |
|------|------------------|
| type | 表示操作状态     |
| msg  | 表示网关回传消息 |


** type说明 **

|   code  |    说明     |
|---------|------------------|
| success | 操作成功         |
| error   | 操作失败         |
| receive | 设备主动上传数据 |




##### 消息体定义




> ###### 1001

```json
{
    type:"success",
    msg:"灯已打开",
    deviceId:"1",
    deviceModel:"0301"
} 
```


> ###### 2001

```json
 {
    type:"receive",
    msg:"成功",
    deviceId:"1",
    deviceModel:"0303",
    deviceData:[
        {
            channelNumber:"1",
            channelValue:"10",
            channelStatus :"10"
 
        }
    ]
}

```


---
