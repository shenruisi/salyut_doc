# \- write

## 范式
```
- write: { fpath:, value: [, append]}
```
您可以通过**write**标签将数据写入本地文件

## 属性
| 属性 | 类型 | 是否必须 | 备注 |
|--------|--------|--------|--------|
|   fpath   | [expr](datatype.md)  | √ | 本地文件路径  |
|   value   | [expr](datatype.md)  |  √ |   |
|   append   | [boolean](datatype.md)  |  x | Default = $false  |

## 用法
### 写入本地文件
```yaml
- write: { fpath: '"/tmp/local.txt"', value: '"hello world!"' }
```

## 示例
### 将爬取回来的结果写入到本地文件
```yaml
- segment:
    name: '"testToken"'
    package: '"example"'
    body:
        - put: { path: '/localpath',value: '"/Users/Turbe/Desktop/imgList.txt"' }
        - load: '"https://app.trico.cloud/buying/item/20"'
        - wait: { ele: '.page-view', type: '"visibility"', timeout: '1000'}
        - loop:
            in: { eles: '.buying-item section .thumbnails .thumbnails-item', mutable: '$false'}
            each:
                - select: { ele: '$e', attr: '"src"', path: '/img'}
                - put: { path: '/imgList[-1]', value: '$/img'}
                - remove: { path: '/img'}
        - echo: '$/imgList'
        # 将爬取回来的imgList转换成String
        - jsonstr: { path: '/imgListStr', value: '$/imgList'}
        # 将字符串写入到$/localpath路径的文本文件
        - write: { fpath: '$/localpath', value: '$/imgListStr' }
```

### Tips 还可以用在图搜的一些网站上，主要步骤：1、将图片链接传入segment中，2、把图片链接通过write标签写入到本地的一个路径地址，3、把写入到本地的路劲地址通过upload标签上传至图搜控件。