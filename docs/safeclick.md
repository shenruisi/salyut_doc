# \- safeclick

## 范式
```
- safeclick: { ele: [, under:] }
```
您可以通过**safeclick**标签来复合标签[wait](wait.md)和[click](click.md)

## 属性
| 属性 | 类型 | 是否必须 | 备注 |
|--------|--------|--------|--------|
|   ele   | [selector](datatype.md)  | √ |   |
|   under   | [selector](datatype.md)  |  x |   |

## 用法
### 控件点击
```yaml
- safeclick: { ele: '#button' }

#等价于
- wait: { type: '"clickable"',ele: '#button' }
- click: { ele: '#button' }
```