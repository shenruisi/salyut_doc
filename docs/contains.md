# \- contains

## 范式
```
- contains: { path:, search: [,regex:][,icase:]}
```
您可以通过**contains**标签来查找某个子串是否存在

## 属性
| 属性 | 类型 | 是否必须 | 备注 |
|--------|--------|--------|--------|
|   path   | [path](datatype.md)  | √ |   |
|   search   | [expr](datatype.md)  | √  |   |
|   regex   | [expr](datatype.md)  | x |   |
|   icase   | [boolean](datatype.md)  | x |   |

## 用法
### 查找子串
```yaml
- contains: {path: '/result', search: '"hello"'}
- if: '$1'
- then:
  - echo: '"contains"' 
```