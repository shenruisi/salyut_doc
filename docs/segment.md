# \- segment

## 范式
```
- segment: 
    package: '"包名"'
    name: '"函数名"'
    args: {[0:][, 1:][, 2:]...[, 49:]}
    body:
        执行语句
```
您可以通过**segment**标签来定义函数

## 属性
| 属性 | 类型 | 是否必须 | 备注 |
|--------|--------|--------|--------|
|   package   | [string](datatype.md)  | √ |   |
|   name   | [string](datatype.md)  | √ |   |
|   args   |   | √  |   |
|   body   |  | √ |  |

## 用法
### 自定义concat函数
```yaml
- segment:
    package: '"trico"'
    name: '"concat"' 
    args: {0: '/x',1: '/y'} 
    body:
      - put: {value: '$/x+$/y',path: '/z'}
      - return: '$/z'
```
