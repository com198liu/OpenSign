# OpenSign Master Key Postman Collection

If you get HTML (`<!DOCTYPE html>...`) instead of JSON, you are calling the frontend URL.

Use:
- `parseBaseUrl = https://app.opensignlabs.com/api/app` (hosted)
- or `parseBaseUrl = http://localhost:8080/app` (default self-hosted)

Do **not** use only `https://app.opensignlabs.com` or `http://localhost:3000`.

All requests in the collection call:

`POST {{parseBaseUrl}}/functions/{functionName}`

with headers:
- `X-Parse-Application-Id: {{appId}}`
- `X-Parse-Master-Key: {{masterKey}}`
