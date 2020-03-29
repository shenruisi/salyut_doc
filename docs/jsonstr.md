# \- jsonstr

## 范式
```
- jsonstr: { path: , value: }
```
您可以通过**jsonstr**标签来将对象转化为json字符串

## 属性
| 属性 | 类型 | 是否必须 | 备注 |
|--------|--------|--------|--------|
|   path   | [path](datatype.md)  |  √ |   |
|   value   | [expr](datatype.md)  |  √ | |

## 用法
```yaml
- jsonstr: { path: '/jsonStr', value: '$/jsonObj' }
```