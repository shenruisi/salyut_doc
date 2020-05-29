# \- http

## 范式
```
- http: { url: [, media:][, post:][, headers:][, async:][, path:] }
```
您可以通过**http**标签进行网络请求

## 属性
| 属性 | 类型 | 是否必须 | 备注 |
|--------|--------|--------|--------|
|   url   | [expr](datatype.md)  | √ |  发起网络请求的目标地址，可以是http或https开头 |
|   media   | [expr](datatype.md)  | x  |  post数据的媒体类型，默认为`text/plain`,可参考[MIME类型](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Basics_of_HTTP/MIME_types) |
|   post   | [expr](datatype.md)  | x | http请求体 |
|   headers   | [expr](datatype.md)  |  x |  头信息 可参考[HTTP Headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers) |
|   async   | [boolean](datatype.md)  |  x | Default = $false  |
|   path   | [path](datatype.md)  |  x | 返回结果存储路径  |

## 用法
### get请求
```yaml
- http: {url: '"https://api.trico.cloud/echo/get?input=trico"', path: '/resp'}
- echo: '$/resp'
```

### post请求
```yaml
- http: {url: '"https://api.trico.cloud/echo/textPost"', path: '/resp', post: '"plain text body"'}
- echo: '$/resp'
```

### 定义media的post请求
```yaml
- http: {url: '"https://api.trico.cloud/echo/formPost"', media: '"application/x-www-form-urlencoded"', post: '"name=trico"', path: '/resp'}
- echo: '$/resp'
```
```yaml
- put: { path: '/req/name', value: '"trico"' }
- put: { path: '/req/content', value: '"hello, world!"' }
- jsonstr: { path: '/postBody', value: '$/req' }
- http: {url: '"https://api.trico.cloud/echo/jsonPost"', media: '"application/json"', post: '$/postBody', path: '/resp'}
- echo: '$/resp'
```

### 定义headers的get请求
```yaml
- put: { path: '/headers/Content_Type', value: '"text/plain"' }
- put: { path: '/headers/Custom_Param', value: '"custom header value"' }
- http: {url: '"https://api.trico.cloud/echo/customHeader"', headers: '$/headers' , path: '/resp'}
- echo: '$/resp'
```

### 异步请求
```yaml
- http: {url: '"https://api.trico.cloud/echo/get?input=trico"', async: '$true'}
```
