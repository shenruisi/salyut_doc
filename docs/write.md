# \- write

## 范式
```
- write: { fpath:, value: [, append]}
```
您可以通过**write**标签将数据写入本地文件

## 属性
| 属性 | 类型 | 是否必须 | 备注 |
|--------|--------|--------|--------|
|   fpath   | [expr](datatype.md)  | √ | 本地文件路径  |
|   value   | [expr](datatype.md)  |  √ |   |
|   append   | [boolean](datatype.md)  |  x | Default = $false  |

## 用法
### 写入本地文件
```yaml
- write: { fpath: '"/tmp/local.txt"', value: '"hello world!"' }
```