# 核销优惠券

核销优惠券

## URL
   {BASE_URL}/tp/services/consume_coupon

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
    "coupon_id_list":["1","abc"]
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
            <td>coupon_id_list</th>
            <td>数组</th>
            <td>优惠券id列表</th>
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
