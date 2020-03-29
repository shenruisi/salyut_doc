# Salyut数据类型
Salyut的变量不需要定义，只需要为变量赋值。值可以存储在变量中，作为参数或者结果返回。

| 数据类型 | 描述 |
|--------|--------|
|   $null     |   表示一个空值或者无效的值     |
|   boolean     |   包含两个值：$false和$true    |
|   number     |   表示整型数值或是浮点数    |
|   string     |   字符串由一对双引号表示，如果由嵌套请使用`\`转义    |
|   path     |  变量存储路径以`/`开头   |
|   selector     |  css selector表达式   |
|   expr     |  表达式类型，支持$null，boolean，number，string，算术运算符，关系运算符，逻辑运算符，取值运算符   |
|   lambda     |  x -> {}   |


## 实例
```yaml
#path的值`/tmp`为path类型，value的值$null为空类型
- put: { path: '/tmp', value: '$null' }  

#path的值`/tmp`为path类型，value的值$true为boolean类型
- put: { path: '/tmp', value: '$true' }  

#path的值`/tmp`为path类型，value的值1为number类型
- put: { path: '/tmp', value: '1' } 

#path的值`/tmp`为path类型，value的值"hello"为string类型
- put: { path: '/tmp', value: '"hello"' } 

#path的值`/tmp`为path类型，value的值div:nth-child(1)为selector类型
- selector: { path: '/tmp' , ele: 'div:nth-child(1)' } 

- put: { path: '/tmp' , vaule: '"hello"' }
#path的值`/tmp`为path类型，value的值$/tmp+" world!"为expr类型
- put: { path: '/tmp', value: '$/tmp+" world!"' } 
```