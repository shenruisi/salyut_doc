# \- switchtab

## 范式
```
- switchtab: { index: } 
```
您可以通过**switchtab**标签来切换到第N个标签页

## 属性
| 属性 | 类型 | 是否必须 | 备注 |
|--------|--------|--------|--------|
|   index   | [number](datatype.md)  | √ |  页面编号 1...N, -1为最近新开的标签页 |



## 片段样例
```yaml
- load: '"https://news.baidu.com/"'
- wait: { type: '"time"',millis: '3000' }
- click: { ele: '#pane-news ul li.hdline0 a.a3' }
- switchtab: { index: '2' } 
```


