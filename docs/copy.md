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
- copy: { path: '/result', value:'$/tmp' }
```