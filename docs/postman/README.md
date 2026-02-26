# OpenSign Master Key Postman Collection

你说得非常对：很多 Cloud Function 需要参数，而且参数名不统一。
这版集合已按源码把每个函数的 body 模板补齐（不再是空 `{}`）。

## 使用顺序
1. `00-Start-Here/health-check`
   - 必须返回 JSON；若返回 HTML，说明 `parseBaseUrl` 还是前端地址。
2. `00-Start-Here/loginuser`（需要用户上下文时）
   - 把返回里的 `result.sessionToken` 复制到变量 `sessionToken`。
3. 调用 `01-Cloud-Functions-with-Param-Templates/*`
   - 每个请求里都放了从源码推导的参数模板。

## 关键变量
- `parseBaseUrl`: 必须带 Parse 挂载路径（如 `https://your-domain/api/app` 或 `http://localhost:8080/app`）
- `appId`
- `masterKey`
- `sessionToken`（部分接口需要）

## 参数来源说明
- 每个请求的 Description 都写了：
  - Required params（推导/人工校正）
  - Source（对应函数源码文件）
- 另外提供完整参数索引：`docs/postman/PARAMS_REFERENCE.md`

## 注意
- 这是基于源码静态分析生成的参数模板，复杂嵌套对象（如 `Documents`、`details`、`organization`）给的是最小示例，你需要按业务补全字段。
