
# 页面嵌入
我们会提供一序列页面，让第三方能方便的把这些页面嵌入到自己系统中，无缝衔接。

##URL

###移动端
```
测试： http://qa.maxfun.co/mobile?page=1&style=1&token={token}
正式： https://tp.maxfun.co/mobile?page=1&style=1&token={token}
```

###PC端
```
测试： http://qa.maxfun.co/pc?page=1&style=1&token={token}
正式： https://tp.maxfun.co/pc?page=1&style=1&token={token} 
```


##参数说明
<table data-tablesaw-sortable>
    <thead>
        <tr>
            <th data-tablesaw-sortable-col data-tablesaw-sortable-default-col>参数名称</th>
            <th data-tablesaw-sortable-col>类型</th>
            <th data-tablesaw-sortable-col>描述</th>
            <th data-tablesaw-sortable-col>是否必填</th>
        </tr>
	<tr>
            <td>page</th>
            <td>数字型</th>
            <td>需要嵌入的页面，1表示数据魔方，2表示满乐智能</th>
            <td>是</th>
        </tr>
	<tr>
            <td>token</th>
            <td>字符型</th>
            <td>店铺身份标识，通过之前的接口获取</th>
            <td>是</th>
        </tr>
	<tr>
            <td>style</th>
            <td>数字型</th>
            <td>页面样式风格，默认为1 （现在暂时仅支持1，稍后会增加更多）</th>
            <td>否</th>
        </tr>
    </thead>
<table>

### Demo展示

####1.移动端数据魔方  (http://qa.maxfun.co/mobile?style=1&page=1&token=123456)
<img src="http://7xnvcz.com1.z0.glb.clouddn.com/demo/demo.jpg" width="50%" height="50%">



####2.PC端数据魔方  (http://qa.maxfun.co/pc?style=1&page=1&token=123456)
<img src="http://7xnvcz.com1.z0.glb.clouddn.com/demo/demo1.jpg" width="50%" height="50%">

