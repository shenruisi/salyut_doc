# \- elif

## 范式
```
- elif: expr
```
您可以通过**elif**标签来进行条件判断，必须与**if**,**then**标签连用

## 属性
无

## 用法
```yaml
#>elif作用示例,条件判断
- if: '1 > 2'
- then:
    - echo: '"1大于2"'
- elif: '1 < 2'
- then:
    - echo: '"1小于2"'
- else:
    - echo: '"1不大于2"' 
```
