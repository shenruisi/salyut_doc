# \- loop

## 范式
```
- loop
    in: { [eles:|values:|targets: [, start:][, end:][, step:]][, mutable:][, cond:][, parent:] }
    each:
```
您可以通过**loop**标签来进行循环操作

## 属性
| 属性 | 类型 | 是否必须 | 备注 |
|--------|--------|--------|--------|
|   eles   | [selector](datatype.md)  | x |   |
|   targets   | [expr](datatype.md)  | x |  功能与eles相同但支持变量表达式，推荐使用 |
|   values   | [selector](datatype.md)  | x  |   |
|   cond   | [expr](datatype.md)  |  x |  loop的执行条件 相当于java的while循环,独立使用无法与eles,targets共用 |
|   parent   | [expr](datatype.md)  |  x |  在该节点元素下进行循环 |
|   start   | [number](datatype.md)  |  x | 循环的起始值，Default = 0  |
|   end   | [number](datatype.md)  |  x | Default = len of input |
|   step   | [number](datatype.md)  |  x | 迭代步长， Default = 1  |
|   mutable   | [boolean](datatype.md)  |  x |  loop each操作后，DOM节点是否会产生变化（DOM节点有更新，或者删除）如果没有变化，将该属性设置为$false可以提高效率，Default = $true |


## 特殊变量
### **$e**
> 循环中的当前元素

### **$i**
> 循环中的当前下标

### **$v**
> 循环非web element元素的数值

### **$count**
> loop size

## 用法
### 遍历eles里的节点
```yaml
- loop:
    in: { eles: '.list' }
    each:
      - echo: '$e'
```

### 区间为[start,end),每次增加步长为step，下⾯则输出1到9
```yaml
- loop:
    in: { start: '1', end: '10', step: '1' } 
    each:
      - echo: '$i'
```

## 片段样例
```yaml
- load: '"https://news.baidu.com/"'
#>遍历节点信息
- loop:
    in: { eles: '#pane-news ul li' }
    each:
      - select: { ele: 'a', under: '$e', path: '/tmp' }
      - echo: '$/tmp'
#>遍历节点信息 targets 推荐使用
- put: {path: '/element',value: '"#pane-news ul li"'}
- loop:
    in: { targets: '$/element' }
    each:
      - select: { ele: 'a', under: '$e', path: '/tmp' }
      - echo: '$/tmp'
#>遍历节点信息 cond条件 cond不可以与targets和其他的公用 只能单独使用相当于while循环语句
- put: {path: '/count',value: '0'}
- loop:
    in: {cond: '$/count < 5' }
    each:
      - put: {path: '/count',value: '$i'}
      - echo: '$i'
#>遍历节点信息 parent    
- loop:
    in: {targets: '"a"',parent: '$/element + ".hdline3"' }
    each:
      - select: { ele: '$e', path: '/tmp' }
      - echo: '$/tmp'
#>遍历节点信息 start  end  step	
- loop:
    in: {start: '0',end: '10',step: '1'}
    each:
      - echo: '$i'
```
