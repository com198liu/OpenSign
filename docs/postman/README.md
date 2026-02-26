# OpenSign Master Key Postman Collection

你提到需要 **templatelist** 接口，这版已补充：
- `00-Start-Here/templatelist`
- 调用路径：`GET {{parseBaseUrl}}/classes/contracts_Template?...`
- 用 Master Key 即可分页获取模板列表。

## 使用顺序
1. `00-Start-Here/health-check`
   - 必须返回 JSON；若返回 HTML，说明 `parseBaseUrl` 还是前端地址。
2. `00-Start-Here/loginuser`（需要用户上下文时）
   - 把返回里的 `result.sessionToken` 复制到变量 `sessionToken`。
3. `00-Start-Here/templatelist`（模板列表）
4. 调用 `01-Cloud-Functions-with-Param-Templates/*`（具体业务函数）

## 关键变量
- `parseBaseUrl`: 必须带 Parse 挂载路径（如 `https://your-domain/api/app` 或 `http://localhost:8080/app`）
- `appId`
- `masterKey`
- `sessionToken`（部分接口需要）
- `limit` / `skip`（templatelist 分页）

## 参数来源说明
- Cloud Function 请求的 Description 都写了：
  - Required params（推导/人工校正）
  - Source（对应函数源码文件）
- 完整索引见：`docs/postman/PARAMS_REFERENCE.md`

## 注意
- 这是基于源码静态分析生成的参数模板，复杂嵌套对象（如 `Documents`、`details`、`organization`）给的是最小示例，你需要按业务补全字段。
