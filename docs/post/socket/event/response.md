### LoginResponse

| 字段值              | 字段类型      | 是否必须 | 字段描述                                                                             |
|------------------|-----------|------|----------------------------------------------------------------------------------|
| user_id          | string    | 是    | 用户ID                                                                             |
| username         | string    | 是    | 用户名称                                                                             |
| avatar           | string    | 是    | 用户头像                                                                             |
| is_admin         | bool      | 是    | 是否管理员                                                                            |
| status           | string    | 是    | 在线状态 离线(Offline) 在线(Online)                                                      |
| first_login_time | time.Time | 是    | 用户首次登录时间                                                                         |
| last_login_time  | time.Time | 是    | 用户最后登录时间                                                                         |
| last_login_ip    | string    | 是    | 用户最后登录IP                                                                         |
| repeat_login     | bool      | 是    | 在此之前用户是否已登录状态 (如果用户此前未登录将返回false); 如果返回true, 表示服务端并不会更新登录信息, 只是把上次登录成功的信息返回给客户端。 |

### LogoutResponse

| 字段值           | 字段类型      | 是否必须 | 字段描述           |
|---------------|-----------|------|----------------|
| user_id       | string    | 是    | 用户ID           |
| logout_time   | time.Time | 是    | 用户登出时间         |
| forced_logoff | bool      | 是    | 用户是否被迫下线(被挤下线) |

### LoginStatusResponse

| 字段值     | 字段类型   | 是否必须 | 字段描述                        |
|---------|--------|------|-----------------------------|
| user_id | string | 是    | 用户ID, 未登录返回空字符串             |
| status  | string | 是    | 登录状态 已登录(Login) 未登录(Logout) |