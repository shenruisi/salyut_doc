# \- closetab

## 范式
```
- closetab: 
```
您可以通过**closetab**标签来关闭当前窗口

## 属性
无

## 片段样例
```yaml
- load: '"https://news.baidu.com/"'
- wait: { type: '"time"', millis: '3000' }
#打开了新窗口
- click: { ele: '#pane-news ul li.hdline0 a.a3' }
- closetab:
```


