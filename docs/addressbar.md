# \- addressbar

## 范式
```
- addressbar: { path: }
```
您可以通过**addressbar**标签将地址栏内容存入path中

## 属性
| 属性 | 类型 | 是否必须 | 备注 |
|--------|--------|--------|--------|
|   path   | [path](datatype.md)  |  √ |   |


## 用法
### 存储地址栏内容
```yaml
- load: '"https://news.baidu.com/"'
- addressbar: { path: '/currentAddress' }
```