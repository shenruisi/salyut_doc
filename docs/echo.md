# \- echo

## 范式
```
- echo: expr
```
您可以通过**echo**标签打印变量

## 属性
无

## 用法
### 打印常量
```yaml
- echo: '"hello world!"'
```
### 打印变量
```yaml
- select: { ele: '#button', path: '/buttonName' }
- echo: '$/buttonName'
```