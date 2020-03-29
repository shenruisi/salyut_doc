# \- return

## 范式
```
- return:  expr
```
您可以通过**return**标签来返回结果

## 属性
无

## 用法
### 返回常量
```yaml
- return: '"hello world!"'
```

### 返回变量
```yaml
- return: '$/path'
```

### 返回空
```yaml
- return: 
```