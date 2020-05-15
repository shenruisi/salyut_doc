# \- select

## 范式
```
- select: { [target:|targets:] [, ele:|eles:], path: [, parent:][, under:][, attr:][, regex:] }
```
您可以通过**select**标签将CSS Selector选中的节点中的文本或属性值放入path中。

## 属性
| 属性 | 类型 | 是否必须 | 备注 |
|--------|--------|--------|--------|
|   ele   | [selector](datatype.md)  | x |  与eles属性之间必须出现一个 |
|   eles   | [selector](datatype.md)  | x  |  与ele属性之间必须出现一个 |
|   target   | [expr](datatype.md)  | x |  与targets属性之间必须出现一个 与ele功能相同但支持表达式变量，推荐使用 |
|   targets   | [expr](datatype.md)  | x |  与target属性之间必须出现一个 与eles功能相同但支持表达式变量，推荐使用 |
|   path   | [path](datatype.md)  |  √ |   |
|   under   | [selector](datatype.md)  |  x | 通常用于 [**- loop**](loop.md)标签  |
|   parent   | [expr](datatype.md)  |  x |与under功能相同但支持表达式变量，推荐使用  |
|   attr   | [expr](datatype.md)  |  x | 如果没有该属性将会返回$null  |
|   regex   | [expr](datatype.md)  |  x | 例如："(\\\d{4}.\\\d{2}.\\\d{2})"  |

## 用法
### 选取css selector⾥单个内容存⼊path
```yaml
- select: {ele: '#button', path: '/buttonName'}
```

### 选取css selector内所有内容存入path
```yaml
- select: {eles: 'div.dd p.info',path: '/arr'}
```

### 选取css selector里attribute的内容存入path
```yaml
- select: {ele: '#header-strip input',path: '/attr_id',attr: 'id'}
```

### 选取某个节点下的内容
```yaml
- loop:
    in: {eles: 'div.info-wrap'}
    each:
      - select: {ele: 'div.dd',path: '/info',under: '$e'}
```

## 片段样例
```yaml
- load: 'https://news.baidu.com/'
#do something as you like
- select: {ele: '#headline-tabs li.active', path: '/R/test1'}
- select: {eles: '#pane-news ul li a', path: '/R/info'}
- select: {eles: '#pane-news ul li a', path: '/R/info_url',attr: '"href"'}
- select: {ele: '#headline-tabs li.active a', path: '/R/test_attr',attr: '"data-control"'}
- loop:
    in: {eles: '#pane-news ul li'}
    each:
      - select: {ele: 'a',under: '$e',path: '/tmp'}
      - echo: '$/tmp'
- echo: '$/R'
```
