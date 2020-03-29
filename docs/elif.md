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
