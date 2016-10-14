# 商户营销功能开关

商户营销功能开关

## URL
   {BASE_URL}/tp/services/merchant_campaign_switch

## Method
   POST

## Headers
```
   Content-type=application/json
   Authorization=bearer {access_token}
```

## Request
```
{
	"developer_key":"maxfun",
	"switch_status":0
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
            <td>用户的唯一标识，如微信的openid</th>
            <td>是</th>
        </tr>
	<tr>
            <td>switch_status</th>
            <td>数字型</th>
            <td>开关状态 0关 1开</th>
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
