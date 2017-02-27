# 打印机数据接口
  传送检测到的打印机数据
## URL
   测试环境地址:https://demo.maxfun.co/maxfunpay/services/printer_content
## Method
   POST

## Headers
```
   Content-type=application/json
```

## Request
```
{
	"devices_key":"3363c762-f7dc-11e6-bf52-00163e003235",
  "content":"天王盖地虎，小鸡炖蘑菇"
}

```
<table data-tablesaw-sortable>
    <thead>
        <tr>
            <th data-tablesaw-sortable-col data-tablesaw-sortable-default-col>字段名称</th>
            <th data-tablesaw-sortable-col>类型</th>
            <th data-tablesaw-sortable-col>描述</th>
            <th data-tablesaw-sortable-col>是否必填</th>
        </tr>
		<tr>
            <td>devices_key</th>
            <td>字符型</th>
            <td>设备标识符</th>
            <td>是</th>
        </tr>
		<tr>
            <td>content</th>
            <td>字符型</th>
            <td>打印内容</th>
            <td>是</th>
        </tr>
    </thead>
<table>


## Response
```
{
  "status": {
    "code": "200",
    "message": "success"
  },
  "result": "success"
}
```
<table data-tablesaw-sortable>
    <thead>
        <tr>
            <th data-tablesaw-sortable-col data-tablesaw-sortable-default-col>字段名称</th>
            <th data-tablesaw-sortable-col>类型</th>
            <th data-tablesaw-sortable-col>描述</th>
        </tr>
		<tr>
			<td>code</th>
			<td>字符型</th>
			<td>为200则成功，其他则失败</th>
		</tr>
		<tr>
			<td>message</th>
			<td>字符型</th>
			<td>返回信息，例如错误信息</th>
		</tr>
    </thead>
<table>
