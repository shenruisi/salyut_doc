# \- then

## 范式
```
- then:
  执行语句
```

## 属性
无

## 用法
```yaml
#>then作用示例,条件判断
- if: '1 > 2'
- then:
    - echo: '"1大于2"'
- elif: '1 < 2'
- then:
    - echo: '"1小于2"'
- else:
    - echo: '"1不大于2"' 
```
