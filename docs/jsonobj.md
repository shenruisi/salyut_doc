# \- jsonobj

## 范式
```
- jsonobj: { path: , value: }
```
您可以通过**jsonobj**标签来将json字符串为Map对象

## 属性
| 属性 | 类型 | 是否必须 | 备注 |
|--------|--------|--------|--------|
|   path   | [path](datatype.md)  |  √ |   |
|   value   | [expr](datatype.md)  |  √ | |


## 用法
```yaml
- jsonobj: { path: '/jsonObj', value: '$/jsonStr' }
```