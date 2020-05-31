# \- remove

## 范式
```
- remove: { path: }
```
您可以通过**remove**移除path中的数值

## 属性
| 属性 | 类型 | 是否必须 | 备注 |
|--------|--------|--------|--------|
|   path   | [path](datatype.md)  | √ |   |

## 用法
### 移除数值
```yaml
 - copy: {path: '/name',value: '"trico真棒"'}
 - echo: '$/name'
 - remove: {path: '/name'}
 - echo: '$/name'
```