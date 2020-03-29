# \- find

## 范式
```
- find: { ele: [, under:][, path] }
```
您可以通过**find**标签判断某个节点是否存在

## 属性
| 属性 | 类型 | 是否必须 | 备注 |
|--------|--------|--------|--------|
|   ele   | [selector](datatype.md)  | √ |   |
|   path   | [path](datatype.md)  |  x |   |
|   under   | [selector](datatype.md)  |  x | 通常用于 [**- loop**](loop.md)标签  |


## 用法
### 查找某个元素是否存在
```yaml
- find: { ele: '#button' }
```

### 查找某个元素是否存在并存入path
```yaml
- find: { ele: '#button', path: '/found' }
```

## 片段样例
```yaml
- load: '"https://news.baidu.com/"'
- find: { ele: '#menu' }
- if: '$1'
- then:
  - echo: '"find menu"'
- else:
  - echo: '"not found"'
```
