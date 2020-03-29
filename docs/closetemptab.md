# \- closetemptab

## 范式
```
- closetemptab: 
```
您可以通过**closetemptab**标签来关闭临时窗口

## 属性
无

## 片段样例
```yaml
- load: '"https://news.baidu.com/"'
- wait: { type: '"time"', millis: '3000' }
- click: { ele: '#pane-news ul li.hdline0 a.a3' }
- switchtemptab: { index: '2' }
- wait: { type: '"time"', millis: '3000' }
- closetemptab:
```


