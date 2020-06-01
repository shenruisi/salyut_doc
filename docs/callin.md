# \- callin

## 范式
```
- callin: { package: , seg: [, 0:][, 1:][, 2:]...[, 49:] }
```
您可以通过**callin**标签来调用定义好的segment函数

## 属性
| 属性 | 类型 | 是否必须 | 备注 |
|--------|--------|--------|--------|
|   package   | [expr](datatype.md)  | √ |   |
|   seg   | [expr](datatype.md)  | √ |   |
|   0...49   | [expr](datatype.md) | x  |   |

## 用法
### 调用自定义concat函数
```yaml
- segment:
    package: '"trico"'
    name: '"concat"' 
    args: {0: '/x',1: '/y'} 
    body:
        - put: {value: '$/x+$/y', path: '/z'}
        - return: '$/z' 
- callin: { package: '"trico"', seg: '"concat"', 0: '"hello"', 1: '" world!"' }
- echo: '$1'
```
