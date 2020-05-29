# \- scroll

## 范式
```
- scroll: { [x: ], [y: ]  }
```
您可以通过**scroll**标签滚动页面, 

## 属性
| 属性 | 类型 | 是否必须 | 备注 |
|--------|--------|--------|--------|
|   x   | [expr](datatype.md)  | x |  要在窗口文档显示区左上角显示的文档的 x 坐标。 |
|   y   | [expr](datatype.md)  | x |  要在窗口文档显示区左上角显示的文档的 y 坐标。  |
#### Tips: 属性x、y必须要有一个

## 用法
### 向下滚动100像素
```yaml
- scroll: { x: '0', y: '100'}
```

## 示例
### 动态滚动
```yaml
- segment:
    name: '"testToken"'
    package: '"example"'
    body:
        - load: '"https://app.trico.cloud/buying/item/20"'
        - wait: { ele: '.page-view', type: '"visibility"', timeout: '1000'}
        - put: { path: '/scrollTop', value: '200'}
        # js滚动页面
        - js: '"window.scrollTo(0, "+$/scrollTop+")"'
        # scroll 滚动页面
        - scroll: {y: '$/scrollTop+200'}
```