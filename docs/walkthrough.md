
# \- walkthrough

## 范式
```
- walkthrough: { step: [, len:] }
```
您可以通过**walkthrough**标签来按照一定速率从上到下滚动网页

## 属性
| 属性 | 类型 | 是否必须 | 备注 |
|--------|--------|--------|--------|
|   step   | [expr](datatype.md)  |  √ | 滑动步长  |

## 用法
### 100像素一次滚动网页
```yaml
- walkthrough: { step: '100' }
```




