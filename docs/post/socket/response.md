<b>连接 IM 服务后, 服务端会主动推送消息给到客户端, 响应的数据格式统一如下</b>

> 格式参考示例: `{"seq":"2938372621","event":"ping","response":{"code":200,"message":"OK","data":"PONG"}}`

| 字段值      | 字段类型                     | 是否必须 | 字段描述                         |
|----------|--------------------------|------|------------------------------|
| seq      | string                   | 是    | 消息唯一ID                       |
| event    | string                   | 是    | 消息事件, 该值请参考 [消息事件](#消息事件) 解析 |
| response | [MessageResponse](#消息内容) | 是    | 消息内容                         |

### 消息事件

| 事件名称        | 事件内容                                                                      | 事件描述                |
|-------------|---------------------------------------------------------------------------|---------------------|
| ping        | 固定字符串 "PONE"                                                              | 正常 Socket PING 心跳状态 |
| login       | [LoginResponse](/post/socket/event/response?id=loginresponse)             | 账号登录                |
| logout      | [LogoutResponse](/post/socket/event/response?id=logoutresponse)           | 账号登出                |
| loginStatus | [LoginStatusResponse](/post/socket/event/response?id=loginstatusresponse) | 账号登录状态              |

### 消息内容

| 字段值     | 字段类型      | 是否必须 | 字段描述                         |
|---------|-----------|------|------------------------------|
| code    | uint32    | 是    | 响应状态码, 该值请参考 [响应状态码](#响应状态码) |
| message | string    | 是    | 响应描述                         |
| data    | interface | 是    | JSON 数据包                     |

### 响应状态码

| CODE | MESSAGE |
|------|---------|
| 200  | 响应成功    |