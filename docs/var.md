# Salyut变量
Salyut中的变量遵循path规则，不需要提前声明。通过`$`符号进行取值操作。

## 变量类型
Salyut变量有三种类型：全局变量，局部变量， 保留字变量

### 全局变量
> 在path`/_G/`下的为全局变量，不受segment作用域的影响
```
- put: { path: '/_G/globalVar', value: '"trico"'}
- segment:
    name: 'globalVarTest'
    args: {}
    body:
        - echo: '$/_G/globalVar'
- callin: { seg: '"globalVarTest"' }
```

### 局部变量
> 在**- segment**标签 body代码块中的变量为局部变量，作用域从body代码块开始到结束。
```
- segment:
    name: 'segmentVarTest'
    args: {}
    body:
        - put: { path: '/localVar', value: '"trico"' }
- callin: { seg: '"segmentVarTest"' }
- echo: '$/localVar'
```

### 保留字变量
| 变量名 | 释义 |
|--------|--------|
|   $0     |   上一个标签名     |
|   $1     |   上个标签的执行结果     |
|   $e     |   **- loop**标签的迭代网页元素     |
|   $v     |   **- loop**标签的迭代数值     |
|   $i     |   **- loop**标签的迭代下标     |
|   $count     |   **- loop**标签的迭代大小     |
|   $true     |   布尔值true    |
|   $false     |   布尔值false    |
|   $now     |   当前系统时间   |
|   $null     |   空值   |


## 字典类型
```
- put: { path: '/map/key1' , value: '"value1"' }
- put: { path: '/map/key2' , value: '"value2"' }
```
> $/map为字典


## 数组类型
```
- put: { path: '/arr[-1]' , value: '"value1"' }
- put: { path: '/arr[-1]' , value: '"value2"' }
```
> $/arr为数组

## 字典访问
```
- echo: '$/map/key1'
```

## 数组访问
```
- echo: '$/arr[0]'
```