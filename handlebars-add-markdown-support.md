handlebars-add-markdown-support

handlebars加入markdown文件的支持,显示段落
段落可以分中英文

解决方案:
1. 修改handlebars源码, 加入md文件的过滤 {{markdownfile.md}}.
2. 如果字符串以".md"结尾进入markdown文件转化逻辑
3. 将转化后的html文件去电html, body等外围数据,只保留md文件内的<div>数据
4. 将生成的<div>数据替换handlebars模板中的md文件


最终:
生成以yaml作为页面框架, md作为段落内容相结合的方式,转化为静态html呈现出来.
实现高度定制化.

-----------------------------------------------------------------------------------------

看了下handlebars的源码,感觉改起来不是很容易,so, 换一个更加容易的方案.

1. handlebars的模板文件中加入<markdown>标签
2. 写外部程序,首先替换<markdown>标签中的内容, 转化文件替换markdown
3. 经过上一步处理的文件,便是一个纯粹的handlebars模板

这样在不修改handlebars源码的基础上,实现二者的结合.

