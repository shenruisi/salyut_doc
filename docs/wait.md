# \- wait

## 范式
```
- wait: { ele:, type: [, millis][, timeout]}
```
您可以通过**wait**标签实现等待功能

## 属性
| 属性 | 类型 | 是否必须 | 备注 |
|--------|--------|--------|--------|
|   ele   | [selector](datatype.md)  | √ |   |
|   type   | [string](datatype.md)  |  √ |  presence*(元素出现)*, visibility*(元素显示)*, time*(时间等待)* |
|   millis   | [number](datatype.md)  | x | 等待的毫秒数  |
|   timeout   | [number](datatype.md)  | x | 超时毫秒数 Default = 60000 |

## 用法
### 等待某个元素出现
```yaml
- wait: { type: '"presence"', ele: '#button' }
```
### 等待某个元素显示
```yaml
- wait: { type: '"visibility"',ele: '#username' }
```
### 等待一段时间
```yaml
- wait: { type: '"time"', millis: '2000' }
```

## 片段样例
```yaml
- load: '"https://news.baidu.com/"'
#do something as you like
- wait: { type: '"presence"', ele: '#headline-tabs' }
- wait: { type: '"presence"', ele: '#channel-all div.menu-list', timeout: '1000' }
- wait: { type: '"visibility"', ele: '#headline-tabs li.active' }
- wait: { type: '"time"', millis: '3000' 
```