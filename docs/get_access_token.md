# 获取token

获取访问其他API的token.

## URL
   {BASE_URL}/tp/services/token?app_id={app_id}&app_secret={app_secret}

## Method
   GET

## Headers
```
   
```

## Request
<table data-tablesaw-sortable>
    <thead>
        <tr>
            <th data-tablesaw-sortable-col data-tablesaw-sortable-default-col>字段名称</th>
            <th data-tablesaw-sortable-col>类型</th>
            <th data-tablesaw-sortable-col>描述</th>
            <th data-tablesaw-sortable-col>是否必填</th>
        </tr>
	<tr>
            <td>app_id</th>
            <td>字符型</th>
            <td>app_id</th>
            <td>是</th>
        </tr>
	<tr>
            <td>app_secret</th>
            <td>字符型</th>
            <td>app_secret</th>
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
	"result": {
		"access_token":"token"
	}
}
```
