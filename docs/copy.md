# \- copy

## 范式
```
- copy: { path:, value: }
```
您可以通过**copy**标签进行值拷贝

## 属性
| 属性 | 类型 | 是否必须 | 备注 |
|--------|--------|--------|--------|
|   path   | [path](datatype.md)  | √ |   |
|   value   | [expr](datatype.md)  | √  |   |

## 用法
### 数值拷贝
```yaml
#>copy示例 
 - copy: {path: '/name',value: '"trico真棒"'}
 - echo: '$/name'
 - copy: {path: '/newName',value: '$/name + ",是真的棒"'}
 - echo: '$/newName'
```