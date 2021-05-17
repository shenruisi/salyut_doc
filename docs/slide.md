# \- slide

## 范式
```
- slide: { ele: [, len:] }
```
您可以通过**slide**标签来拖动页面滑块

## 属性
| 属性 | 类型 | 是否必须 | 备注 |
|--------|--------|--------|--------|
|   ele   | [selector](datatype.md)  | √ |   |
|   len   | [expr](datatype.md)  |  √ | 拖动距离  |

## 用法
### 拖动某个元素
```yaml
- slide: { ele: '#button', len: '100' }
```


