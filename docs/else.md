# \- else

## 范式
```
- else:
  执行语句
```
您可以通过**else**标签来执行不满足条件判断的语句

## 属性
无

## 用法
```yaml
- put: { path: '/input', value: '1' }
- if: '$/input < 2'
- then:
  - echo: '"less then!"'
- elif: '$/input == 2'
- then:
  - echo: '"equal!"'
- else:
  - echo: '"great then!"'
```
