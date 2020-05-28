# \- dropdown

## 范式
```
- dropdown: { ele:, value: }
```
您可以通过**dropdown**标签选择下拉列表

## 属性
| 属性 | 类型 | 是否必须 | 备注 |
|--------|--------|--------|--------|
|   ele   | [selector](datatype.md)  | √ |   |
|   value   | [expr](datatype.md)  |  √ |   |

## 用法
```yaml
- dropdown: { ele: '#dropdown', value: '"select me"' }
```
## 示例
```
- segment:
    name: '"dropdown_test"'
    body:
    - load: '"https://www.w3school.com.cn/tiy/t.asp?f=html_dropdownbox"'
    - js: '"document.getElementById(\"iframewrapper\").innerHTML=document.querySelector(\"#iframeResult\").contentDocument.querySelector(\"form\").innerHTML"'
    - dropdown: { ele: 'select', value: '"Saab"'}
- callin: { seg: '"dropdown_test"' }
```