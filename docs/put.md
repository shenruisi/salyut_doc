# \- put

## 范式
```
- put: { path:, [value:|values:|lambda:] [, regex: [,icase:]] }
```
您可以通过**put**标签来对/path变量进行赋值

## 属性
| 属性 | 类型 | 是否必须 | 备注 |
|--------|--------|--------|--------|
|   path   | [path](datatype.md)  | √ |   |
|   value   | [expr](datatype.md)  | x  |   |
|   values   | [expr](datatype.md)  | x | *(v1,v2,v3)或者(k1:v1,k2:v2,k3:v3)*  |
|   lambda   | [lambda](datatype.md)  |  x |   |
|   regex   | [expr](datatype.md)  |  x | 例如："(\\\d{4}.\\\d{2}.\\\d{2})"  |
|   icase   | [boolean](datatype.md)  |  x |   |

## 用法
### 数组赋值
```yaml
- put: { path: '/list', values: '1,2,3' }
```
### 字典赋值
```yaml
- put: { path: '/dict', values: '"key1":1,"key2":2,"key3":3' }
```
### 正则过滤
```yaml
- put: { path: '/result', value: '"发行日期: 2019-12-12"', regex: '"([\\d|\\-]+)"' }
```
### lambda获取当前时间
```yaml
- put: { path: '/timestamp' ,lambda: 'x -> return new Date().getTime();' }
```
### lambda 类型转换
```yaml
- put: { path: '/stringVal', value: '"10"' }
- put: { path: '/numberVal' , value: '$/stringVal', lambda: 'x -> return Number(x);' }
```