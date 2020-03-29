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
- put: { path: '/list', values: '1,2,3,4,5'}
- loop:
    in: {values: '$/list'} 
    each:
      - if: '$/list[$i] == 3' 
      - then:
        - continue:
      - else:
        - echo '$v' 
```