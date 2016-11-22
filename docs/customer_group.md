# 用户RFM分组

 获取商户用户RFM分组

## URL
   {BASE_URL}/tp/services/customer_group

## Method
   GET

## Headers
```
   Authorization=bearer {access_token}
```

## Request
```
```
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
            <td>r_lookup_id</th>
            <td>整型</th>
            <td>分组id</th>
        </tr>
		<tr>
            <td>customer_count</th>
            <td>整型</th>
            <td>分组用户数量</th>
        </tr>
		<tr>
            <td>group_display</th>
            <td>字符型</th>
            <td>分组名称</th>
        </tr>
		<tr>
            <td>sort</th>
            <td>整型</th>
            <td>排序</th>
        </tr>
		<tr>
            <td>color</th>
            <td>字符型</th>
            <td>分组颜色代码</th>
        </tr>
    </thead>
<table>
