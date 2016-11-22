# 修改用户信息接口

 修改用户信息接口

## URL
   {BASE_URL}/tp/services/customer_info

## Method
   POST

## Headers
```
   Content-type=application/json
```

## Request
```
{
	"developer_key":"developer_key",
	"customer_identifier":"customer_identifier",
	"gender":"female",
	"customer_nick_name":"zzz",
	"year_of_birth":"1990",
	"month_of_birth":"11",
	"day_of_birth":"11",
	"customer_country":"中国",
	"customer_city":"深圳",
	"customer_province":"广东",
	"customer_phone_number":"13800138000"
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
            <td>developer_key</th>
            <td>字符型</th>
            <td>开发者key</th>
            <td>是</th>
        </tr>
		<tr>
            <td>customer_identifier</th>
            <td>字符型</th>
            <td>用户的唯一标识</th>
            <td>是</th>
        </tr>
		<tr>
            <td>gender</th>
            <td>字符型</th>
            <td>性别 male表示男，female表示女</th>
            <td>否</th>
        </tr>
		<tr>
            <td>customer_nick_name</th>
            <td>字符型</th>
            <td>用户名称</th>
            <td>否</th>
        </tr>
		<tr>
            <td>customer_country</th>
            <td>字符型</th>
            <td>用户国家</th>
            <td>否</th>
        </tr>
		<tr>
            <td>customer_province</th>
            <td>字符型</th>
            <td>用户省份</th>
            <td>否</th>
        </tr>
        <tr>
            <td>customer_city</th>
            <td>字符型</th>
            <td>用户城市</th>
            <td>否</th>
        </tr>
		<tr>
			<td>customer_phone_number</th>
			<td>字符串</th>
			<td>用户手机号码</th>
			<td>否</th>
		</tr>
		<tr>
			<td>year_of_birth</th>
			<td>字符串</th>
			<td>出生年</th>
			<td>否</th>
		</tr>
		<tr>
			<td>month_of_birth</th>
			<td>字符串</th>
			<td>出生月</th>
			<td>否</th>
		</tr>
		<tr>
			<td>day_of_birth</th>
			<td>字符串</th>
			<td>出生日</th>
			<td>否</th>
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
