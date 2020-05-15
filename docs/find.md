# \- find

## 范式
```
- find: { [ele:|target:] [, under:|parent:][, path] }
```
您可以通过**find**标签判断某个节点是否存在

## 属性
| 属性 | 类型 | 是否必须 | 备注 |
|--------|--------|--------|--------|
|   ele   | [selector](datatype.md)  | √ |   |
|   target   | [epxr](datatype.md)  | √ | 功能与ele相同但支持表达式变量，推荐使用  |
|   path   | [path](datatype.md)  |  x |   |
|   under   | [selector](datatype.md)  |  x | 通常用于 [**- loop**](loop.md)标签  |
|   parent   | [expr](datatype.md)  |  x | 功能与under相同但支持表达式变量，推荐使用  |

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
