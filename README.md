该 API 接口用于实时检测域名是否被微信等平台拦截。每次成功调用将消耗您 Key 的一次配额。

接口地址 (Endpoint)
URL:

https://wxck.sososo.vip/api/detect.php
方法 (Method): GET

请求参数 (Parameters)
请通过 GET 请求传递以下参数：

参数名	类型	是否必需	说明
key	string	是	您的 API Key，用于认证和配额扣减。
url	string	是	待检测的域名或完整 URL（建议 URL 编码）。
请求示例:

GET http://wxck.sososo.vip/api/detect.php?key=YOUR_API_KEY_HERE&url=https%3A%2F%2Fwww.example.com
返回结果 (Response)
API 统一返回 JSON 格式数据：{"code": 状态码, "msg": 描述信息}。

Code	说明	HTTP 状态码
-202	✅ **没有拦截该网址*检测通过)	200 OK
0	❌ **微信拦截**	200 OK
401	🚫 认证失败 (API Key 无效/用户未激活)	401 Unauthorized
402	🛑 用量耗尽	402 Payment Required
500	🚨 服务器内部错误	500 Internal Server Error

公开key
e7e678f1089af4358f00ba3257325153a448b1355b15cfa3339b2bae8b628e5d
