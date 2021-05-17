# \- try

## 范式
```
- try
    do: 
    each:
```
您可以通过**try**标签来捕获异常

## 用法
### 捕获点击可能产生的异常
```
- try:
    do:
        - click: { ele: '#button' }
    catch:
        - echo: '"Unable to click element."'
```