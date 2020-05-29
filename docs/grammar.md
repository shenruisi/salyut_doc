# Salyut基本语法

## 第一个Salyut程序
```
- echo: '"hello world!"'
```

## 与YAML的关系
Salyut遵循YAML语法，并根据YAML语法进行解析。Salyut主要使用YAML的[序列特性](https://yaml.org/spec/1.2/spec.html#sequence//)和[散列特性](https://yaml.org/spec/1.2/spec.html#mapping//)构成了基本语法。
```
- segment: #This is a trico script sample. A web calculator.
    name: '"calc"'
    package: '"baidu"'
    args: {0: '/input'}
    body:
        - load: '"http://www.baidu.com"' #load page of Baidu
        - wait: {ele: '#su', type: '"presence"'} #wait element appear
        - fill: {ele: '#kw', value: '$/input'}
        - click: {ele: '#su'} #click search button
        - wait: {ele: '.op_new_val_screen_result', type: '"presence"'} #fetch the result
        - select: {ele: '.op_new_val_screen_result', path: '/result'}
        - put: { path: '/resultInt', value: '$/result', lambda: 'x -> return parseInt(x)'}
        - return: '$/resultInt'
- callin: {seg: '"calc"', package: '"baidu"', 0: '"1+1"'} #call the segment named 'calc' and pass the argument '1+1'
- return: '$1'
```
Salyut的代码段由多个标签组成(**- segment, - load ...**)

## 注释
### 单行注释
```
# this is a single line comment
```

### 多行注释
> 不支持多行注释，如果要为多行提供注释，可以执行此操作，如下例所示
```
# this
# is a multiple
# line comments
```