#### 接口数据类型

| 数据类型  | 含义        | 说明                     |
| :-------- | :---------: | :------:                 |
| string    | 字符串      | 空值：null               |
| int       | 整数        | 空值：null               |
| decimal   | 浮点数      | 空值：null，decimal(2,3) |
| array     | 集合        | 空值：null               |
| object    | 对象        | 空值：null               |

!> 注意：移动端注意null值对程序的影响

-----

#### 接口请求头

| 请求头     | 含义          | 说明                        |
| :--------  | :---------:   | :------:                    |
| X-Token    | 授权令牌      | 未登录不需要传递            |
| X-OS       | 操作系统      | `ios` or `android`          |
| X-Sign     | 签名          | 见接口签名方式              |
| X-Req-Time | 请求时间      | 格式：`yyyyMMddHHmmssSSS`   |
| X-Phone    | 手机号        |                             |
| X-Noncestr | 随机6位字符串 |                             |
| X-App      | app类型       | 原生APP接口调用值为：native |

#### 接口响应头

| 响应头      |     含义    |     说明     |
| :--------  | :---------: |   :------:   |
| X-Resp-Time |    响应时间   |    格式：`yyyyMMddHHmmssSSS`  |
| X-Resp-Code   |   错误码   |     000成功响应，4位为业务处理错误需要提示用户，5位为内部系统错误    |
| X-Point | 奖励积分 | 当X-Point非空且大于0时，表示奖励积分。移动端需要提示用户奖励积分|

!> 注意：不管是请求头和响应头都携带在HTTP协议的头部

-----
#### 接口签名
第一步: 所有参数按字典顺序排序使用&拼接,paramString = (a=1&b=1&b1=2)

第二步：x-sign = md5(token + x-reqtime前14位 + x-noncestr后四位 + paramString )后小写

#### 接口错误响应
响应头包含`X-Resp-Code:10013`

响应体:
``` json
{
  msg: "请求头x-sign不能为空"
}
```

#### 接口版本
格式：api/版本/xxxx

例子：api/v1/index/banner
