# \- find

## 范式
```
- find: { [ele:|target:] [, under:|parent:][, path] }
```
您可以通过**find**标签判断某个节点是否存在

## 属性
| 属性 | 类型 | 是否必须 | 备注 |
|--------|--------|--------|--------|
|  ele   | [selector](datatype.md)  | √ |  css选择器 |
|  target | [expr](datatype.md)  | √ |  与ele功能相同，但支持表达式（推荐使用） |
|  path   | [path](datatype.md)  |  x | 操作结果的存储路径 |
|  under  | [selector](datatype.md)  |  x | 查找范围，通常用于 [**- loop**](loop.md)标签  |
|  parent | [expr](datatype.md)  |  x | 与under功能相同，但支持表达式（推荐使用）|

## 用法
### 查找某个元素是否存在
```yaml
- find: {ele: '#button'}
- find: {target: '"#button"'}
```

### 查找某个元素是否存在，并存入path
```yaml
- find: {ele: '#button', path: '/button'}
```


### 查找指定范围的，某个元素是否存在
```yaml
- find: {ele: 'li', under: '.hotnews'}
- find: {ele: 'li', parent: '".ulist"+" .focuslistnews"'}
```

## 片段样例
```yaml
- load: '"https://news.baidu.com/"'
- find: { ele: '#menu' }
- if: '$1'
- then:
  - echo: '"find menu"'
- else:
  - echo: '"not found"'
```
