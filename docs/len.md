# \- len

## 范式
```
- len: expr
```
您可以通过**len**标签来计算对象长度

## 属性
无

## 用法
### 计算字符串常量
```yaml
- len: '"hello world!"'
- echo: '$1'
```
### 计算变量
```yaml
- put: { path: '/list[-1]' , value: '1' }
- put: { path: '/list[-1]' , value: '2' }
- len: '$/list'
- echo: '$1'
```