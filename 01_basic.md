#### 短信验证码接口
用于发送短信验证码，需要提交发送的验证码类型

**接口地址:**  `api/v1/validCode`

**token 验证:**  `否`

**请求参数**

|参数| 是否可选 | 参数说明 |
|---|---|---|
|phone| 否 | 注册手机号 |
|type| 否 | 验证码类型: register:注册， returnpwd: 找回密码，modifyphone：修改手机号|

** 响应参数 **

`无`

---
#### 登录接口
用户登录APP接口

**接口地址:**  `api/v1/user/login`

**token 验证:**  `否`

**请求参数**

|参数| 是否可选 | 参数说明 |
|---|---|---|
|phone| 否 | 注册手机号 |
|password| 否 | `MD5加密后小写`|

** 响应参数 **

| 参数                  | 参数类型 | 是否可选 | 参数说明     |
| ---                   | :---:    | ----     | ---          |
| token                 | string   | 否       | 授权token    |
| rowId                 | int      | 否       | 用户ID       |
| phone                 | string   | 否       | 用户手机号   |
| nickname              | string   | 否       | 用户昵称     |
| avatar                | string   | 是       | 头像         |
| project               | array    | 否       | 项目         |
| project.id            | int      | 否       | 项目ID       |
| project.name          | string   | 否       | 项目名称     |
| project.bgPic         | string   | 是       | 项目背景图片 |


** 响应示例 **

``` json
{
  token: "591084a549b0d19f8dadb214b70d826c",
  rowId: 1,
  phone: "137776668399",
  nickname: "张三",
  avatar: "avatar/ahfga12bdc.jpg",
  project:[
    {
      id:111,
      name:"东大创客中心",
      bgPic:"pic/ahfga12bdc.jpg"
    }
  ]
}
```

---

#### 自动登录接口
用于APP自动登录功能

**接口地址:**  `api/v1/user/login/auto`

**token 验证:**  `否`

**请求参数**

|参数| 是否可选 | 参数说明 |
|---|---|---|
|phone| 否 | 注册手机号 |
|token| 否 | 登录授权token |

** 响应参数 **

| 参数                  | 参数类型 | 是否可选 | 参数说明     |
| ---                   | :---:    | ----     | ---          |
| token                 | string   | 否       | 授权token    |
| rowId                 | int      | 否       | 用户ID       |
| phone                 | string   | 否       | 用户手机号   |
| nickname              | string   | 否       | 用户昵称     |
| avatar                | string   | 是       | 头像         |
| project               | array    | 否       | 项目         |
| project.id            | int      | 否       | 项目ID       |
| project.name          | string   | 否       | 项目名称     |
| project.bgPic         | string   | 是       | 项目背景图片 |


** 响应示例 **

``` json
{
  token: "591084a549b0d19f8dadb214b70d826c",
  rowId: 1,
  phone: "137776668399",
  nickname: "张三",
  avatar: "avatar/ahfga12bdc.jpg",
  project:[
    {
      id:111,
      name:"东大创客中心",
      bgPic:"pic/ahfga12bdc.jpg"
    }
  ]
}
```

---
#### 注册接口
用户注册APP接口，提交注册信息

**接口地址:**  `api/v1/user/regist`

**token 验证:**  `否`

**请求参数**

|参数| 是否可选 | 参数说明 |
|---|---|---|
|phone| 否 | 注册手机号 |
|password| 否 | `加密`|
|validCode| 否 | 验证码 |

**响应参数**

| 参数                  | 参数类型 | 是否可选 | 参数说明     |
| ---                   | :---:    | ----     | ---          |
| token                 | string   | 否       | 授权token    |
| rowId                 | int      | 否       | 用户ID       |
| phone                 | string   | 否       | 用户手机号   |
| nickname              | string   | 否       | 用户昵称     |
| avatar                | string   | 是       | 头像         |
| project               | array    | 否       | 项目         |
| project.id            | int      | 否       | 项目ID       |
| project.name          | string   | 否       | 项目名称     |
| project.bgPic         | string   | 是       | 项目背景图片 |


** 响应示例 **

``` json
{
  token: "591084a549b0d19f8dadb214b70d826c",
  rowId: 1,
  phone: "137776668399",
  nickname: "张三",
  avatar: "avatar/ahfga12bdc.jpg",
  project:[
    {
      id:111,
      name:"东大创客中心",
      bgPic:"pic/ahfga12bdc.jpg"
    }
  ]
}
```

---

#### 忘记密码验证
忘记密码验证手机号接口

**接口地址：** `api/v1/user/findpwdValid`

**token 验证:**  `否`

**请求参数**

|参数| 是否可选 | 参数说明 |
|--|--|--|
| phone  | 否 | 接收短信手机号 |
| validCode | 否 | 短信验证码 |

**响应参数**

`无`

---

#### 忘记密码修改
验证手机号，修改密码接口

**接口地址：** `api/v1/user/findpwdUpdate`

**token 验证:**  `否`

**请求参数**

|参数| 是否可选 | 参数说明 |
|--|--|--|
| phone  | 否 | 接收短信手机号 |
| validCode | 否 | 短信验证码 |
| password | 否 | 新密码 |

**响应参数**

`无`

---
#### 修改用户基本信息
修改用户的基本信息，调用接口需要提交修改的用户的什么类型的信息

**接口地址：** `api/v1/user/update`

**token 验证:**  `是`

**请求参数**

|参数| 是否可选 | 参数说明 |
|--|--|--|
| type  | 否 | 修改类型：nickname，avatar |
| value | 否 | 修改值 |

**响应参数**

`无`

---

#### 意见反馈
提交用户的意见反馈信息

**接口地址：**`api/v1/feedback`

**token 验证:**  `是`

**请求参数**

|参数| 是否可选 | 参数说明 |
|--|--|--|
| detail  | 否 | 反馈内容 |

**响应参数**

`无`

---

#### 获取图标资源包
通过该接口获取图标资源包

`该接口在应用启动时调用，用于获取图标文件`


**接口地址：**`api/v1/icon`

**token 验证:**  `否`

**请求参数**

`无`

**响应参数**

| 参数    | 参数类型 | 是否可选 | 参数说明       |
| ---     | :---:    | ----     | ---            |
| version | int      | 否       | 资源包版本号   |
| resUrl  | string   | 是       | 资源包 URL地址 |

**资源包结构**

- desc.xml
- iconfolder
  - icon1.png
  - icon2.png
  - icon3.png
  - icon4.png
  
**desc.xml结构定义**

```html
<res>
  <item code="icon1">icon1.png</item>
  <item code="icon2">icon2.png</item>
  <item code="icon3">icon3.png</item>
  <item code="icon4">icon4.png</item>
</res>
```

!> 图标文件只传文件名称，客户端在使用的时候按落地的路径自己拼接。

** 响应示例 **

``` json
{
  version: 1,
  resUrl: "http://www.baidu.com"
}
```
---
