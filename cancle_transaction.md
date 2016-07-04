# 取消交易接口

如果交易被取消可调用此接口来取消这单交易

## URL
   {BASE_URL}/tp/services/cancle_transaction

## Method
   POST

## Headers
```
   Content-type=application/json
   Authorization: bearer {token}
```

## Request
```
{"tp_transaction_id":"test_transaction_id"}
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
		<td>tp_transaction_id</th>
		<td>字符型</th>
		<td>第三方的交易ID</th>
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
