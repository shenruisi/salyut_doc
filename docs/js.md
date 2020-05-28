# \- js

## 范式
```
- js: expr
```
您可以通过**js**标签执行js脚本语句

## 属性
无

## 用法
### 写入cookie
```yaml
- js: '"document.cookie=\"my_cookie = value\""'
```

## 示例
### 使用trico变量,添加dom标签属性,获取返回值
```yaml
- segment:
    name: '"testToken"'
    package: '"example"'
    body:
        - load: '"https://app.trico.cloud/buying/item/20"'
        - wait: { ele: '.page-view', type: '"visibility"', timeout: '1000'}
        - put: { path: '/scrollTop', value: '200'}
        # 使用变量滚动页面高度,
        - js: '"window.scrollTo(0, "+$/scrollTop+")"'
        # 添加dom标签属性值
        - js: '"document.querySelector(\".page-view\").setAttribute(\"id\",\"Jpage\")"'
        # js返回数据
        - js: '"function getScrollTop(){ return 300;} let x=getScrollTop(); return x"'
        # 获取js返回数据
        - echo: '$1'
```