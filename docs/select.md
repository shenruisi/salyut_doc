# \- select

## 范式
```
- select: { [target:|targets:] [, ele:|eles:], path: [, parent:][, under:][, attr:][, regex:] }
```
您可以通过**select**标签，获取CSS Selector节点的文本或属性值，并存入path中。

## 属性
| 属性 | 类型 | 是否必须 | 备注 |
|--------|--------|--------|--------|
|   ele   | [selector](datatype.md)  | x |  获取单个元素，与eles属性之间必须出现一个 |
|   eles  | [selector](datatype.md)  | x  |  获取多个元素，与ele属性之间必须出现一个 |
|  target | [expr](datatype.md)  | x |  与ele功能相同，但支持表达式（推荐使用） |
|  targets | [expr](datatype.md) | x |  与eles功能相同，但支持表达式（推荐使用） |
|   path   | [path](datatype.md)  | √ |  操作结果的存储路径 |
|  under  | [selector](datatype.md)  |  x | 查找范围，通常用于 [**- loop**](loop.md)标签  |
|  parent | [expr](datatype.md)  |  x | 与under功能相同，但支持表达式（推荐使用）|
|  attr  | [expr](datatype.md)  |  x | 获取元素的属性值，如果没有该属性，将返回$null  |
|  regex  | [expr](datatype.md)  |  x | 对返回结果进行正则过滤  |

## 用法
### 获取单个css selector的文本
```yaml
- select: {ele: '#button', path: '/buttonText'}
- select: {target: '"#button-"+"1"', path: '/buttonText'}
```

### 获取多个css selector的文本
```yaml
- select: {eles: '.title', path: '/titleTextList'}
- select: {targets: '".title"+"1"', path: '/titleTextList'}
```

### 获取单个css selector的属性值
```yaml
- select: {ele: '.item a', attr: '"href"', path: '/goodsUrl'}
```

### 获取正则表达式过滤后的值
```yaml
- select: {ele: '.comment', regex: '"(\\d+)"', path: '/commentNum'}
```

### 获取多个css selector下的文本
```yaml
- loop:
    in: {eles: 'div.item'}
    each:
        - select: {ele: '.title', under: '$e', path: '/title'}
        - select: {ele: '.price', parent: '$e', path: '/price'}
```

## 片段样例
```yaml
- load: '"https://www.taobao.com"'
- wait: {type: '"presence"', ele: 'body'}
- find: {ele: '#J_SaleBd'}
- if: '$1'
- then:
    - echo: '"找到目标元素"'
- else:
    - echo: '"没有找到目标元素"'
    - return: '0'
- js: '"window.scrollTo(0, document.querySelector(\"#J_SaleBd\").offsetTop)"'
- wait: {type: '"presence"', ele: '#J_SaleBd .item'}
- loop:
    in: {eles: '#J_SaleBd .item'}
    each:
        - select: {ele: '.line-1', under: '$e', path: '/temp/title'}
        - select: {ele: '.line-2 .comment', under: '$e', regex: '"(\\d+)"', path: '/temp/comment'}
        - copy: { path: '/items[-1]', value: '$/temp'}
- echo: '$/items'
```
