# resource 资源

## 软件资源链接  res
> 1. 链接名称  name
> 2. 软件简介   content
> 3. 链接地址   url
>   0. 某条资源     item
>   1. 资源地址类型   type
>   2. 地址   url
>   3. 提取码   extract
>   4. 更新时间 write-time


## xml 文件示例
```xml
<?xml version="1.0" encoding="utf-8" ?>
<resource>
<res>
    <name>链接名称</name>
    <content>简介</content>
    <url>
        <item>
            <type>百度云</type>
            <url>http://www.baidu.com</url>
            <extract>htcc</extract>
            <write-time>
                <year>2016</year>
                <mouth>7</mouth>
                <day>20</day>
                <hour>15</hour>
                <minute>12</minute>
                <second>32</second>
            </write-time>
        </item>
        ……
    </url>
</res>
……
</resource>
```

