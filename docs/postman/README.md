# OpenSign Master Key Postman Collection

如果返回 `<!DOCTYPE html>...`，通常不是鉴权问题，而是 **URL 路径错误**（请求打到了前端 SPA）。

## 正确调用顺序（很关键）
1. 先执行 `00-Start-Here/health-check`
   - 预期：返回 JSON。
   - 如果仍返回 HTML，说明 `parseBaseUrl` 不正确，或网关未暴露 Parse 挂载路径。
2. 对需要用户上下文的接口，执行 `loginuser`
   - 从返回里取 `result.sessionToken`，填到 collection variable: `sessionToken`。
3. 再执行业务函数（`01-Cloud-Functions/*`）
   - 这类接口很多会读取 `sessiontoken` 请求头（源码里是自定义头，不总是 Parse 标准头）。

## parseBaseUrl 的正确格式
必须包含 Parse 挂载路径：
- 自托管默认：`http://localhost:8080/app`
- 反向代理常见：`https://your-domain/api/app`

不能只写：
- `https://your-domain`
- `https://your-domain/api`

## 必需请求头
- `X-Parse-Application-Id: {{appId}}`
- `X-Parse-Master-Key: {{masterKey}}`

## 可选但常用（很多函数会用）
- `sessiontoken: {{sessionToken}}`
- `X-Parse-Session-Token: {{sessionToken}}`
