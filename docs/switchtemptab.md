# \- switchtemptab

## 范式
```
- switchtemptab: { index: } 
```
您可以通过**switchtemptab**标签来切换到第N个新打开的临时标签页

## 属性
| 属性 | 类型 | 是否必须 | 备注 |
|--------|--------|--------|--------|
|   index   | [number](datatype.md)  | √ |  页面编号 |


## 片段样例
```yaml
- load: '"https://news.baidu.com/"'
- wait: { type: '"time"',millis: '3000' }
- click: { ele: '#pane-news ul li.hdline0 a.a3' }
- switchtemptab: { index: '2' } 
```


