# \- continue

## 范式
```
- continue: 
```
您可以通过**continue**标签跳来进入**loop**的下次循环

## 属性
无

## 用法
```
#>continue作用示例,跳过当前进入下一个
- loop:
    in: {start: '0',end: '10',step: '1'}
    each:
      - if: '$i == 3'
      - then:
          - continue:
      - echo: '$i'
```