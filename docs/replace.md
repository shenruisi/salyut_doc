# \- replace

## 范式
```
- replace: { path:, regex:, replacement: }
```
您可以通过**replace**标签进行字符串替换

## 属性
| 属性 | 类型 | 是否必须 | 备注 |
|--------|--------|--------|--------|
|   path   | [path](datatype.md)  | √ |   |
|   regex   | [expr](datatype.md)  |  √ | 例如："(\\\d{4}.\\\d{2}.\\\d{2})"  |
|   replacement   | [expr](datatype.md)  |  √ |   |

## 用法
### 字符串替换
```yaml
#>replace示例 
- copy: {path: '/name',value: '"trico真棒"'}
- echo: '$/name'
- replace: {path: '/name',replacement: '"加油"',regex: '"真棒"'}
- echo: '$/name'
```