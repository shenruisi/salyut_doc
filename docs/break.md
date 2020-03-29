# \- break

## 范式
```
- break: 
```
您可以通过**break**标签跳出当前的**loop**标签

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
        - break: 
```