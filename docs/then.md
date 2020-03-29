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
