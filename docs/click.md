# \- click

## 范式
```
- click: { ele: [, under:][, js] }
```
您可以通过**click**标签来触发点击事件

## 属性
| 属性 | 类型 | 是否必须 | 备注 |
|--------|--------|--------|--------|
|   ele   | [selector](datatype.md)  | √ |   |
|   under   | [selector](datatype.md)  |  x |   |
|   js   | [boolean](datatype.md)  |  x |  是否通过js函数进行点击，Default=$false |

## 用法
### 控件点击
```yaml
- click: { ele: '#button' }
```

### js点击
```yaml
- click: { ele: '#button', js: '$true' }
```

### 遍历点击
```yaml
- loop:
    in: { eles: 'div.js-sku-box dl' } 
    each:
      - click: { ele: 'div.dd',under: '$e' } 
```

## 片段样例
```yaml
- load: '"https://news.baidu.com/"'
- click: { ele: '#channel-all div.menu-list li:nth-child(3)' }
- loop:
    in: { eles: '#channel-all div.menu-list ul li.lavalamp-item' }
    each:
      - click: { ele: 'a',under: '$e' }
```


