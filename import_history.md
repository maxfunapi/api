# 历史数据导入

本接口用于历史数据导入

## URL
   {BASE_URL}/tp/services/import_transaction_history

## Method
   POST

## Headers
```
   Content-type=application/json
```

## Request
```
  {
 	"transaction_list":[
		{"customer_identifier":"13800138000",
		"customer_created_date":"20165-05-05 13:21:21",
		"purchase_time":"20165-05-05 13:24:21",
		"purchase_amount":18.5,
		"gender":"male",
		"customer_nick_name":"nick",
		"customer_country":"中国",
		"customer_province":"广东",
		"customer_city":"深圳",
		"identifier_type":"3",
		"transaction_id":1001
		},
		{...}
	]
 }
 * transaction_list 数组长度最大为1000，超过1000会报错。
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
		<td>customer_identifier</th>
		<td>字符型</th>
		<td>用户唯一标识符</th>
		<td>是</th>
	</tr>
	<tr>
		<td>customer_created_date</th>
		<td>字符型</th>
		<td>用户创建日期 格式(yyyy-MM-dd HH:mm:ss)</th>
		<td>是</th>
	</tr>
	<tr>
		<td>purchase_time</th>
		<td>数字型</th>
		<td>用户消费日期 格式(yyyy-MM-dd HH:mm:ss)</th>
		<td>是</th>
	</tr>
	<tr>
		<td>purchase_amount</th>
		<td>数字型</th>
		<td>用户消费金额</th>
		<td>是</th>
	</tr>
	<tr>
		<td>gender</th>
		<td>字符型</th>
		<td>性别 (male或者female)</th>
		<td>否</th>
	</tr>
	<tr>
		<td>customer_nick_name</th>
		<td>字符型</th>
		<td>用户昵称</th>
		<td>否</th>
	</tr>
	<tr>
		<td>customer_country</th>
		<td>字符型</th>
		<td>国家</th>
		<td>否</th>
	</tr>
	<tr>
		<td>customer_province</th>
		<td>字符型</th>
		<td>省份</th>
		<td>否</th>
	</tr>
	<tr>
		<td>customer_city</th>
		<td>字符型</th>
		<td>城市</th>
		<td>否</th>
	</tr>
	<tr>
		<td>identifier_type</th>
		<td>数字型</th>
		<td>用户类型：1表示微信；2表示支付宝；3表示电话号码；</th>
		<td>是</th>
	</tr>
	<tr>
		<td>transaction_id</th>
		<td>数字型</th>
		<td>交易流水ID(不能重复)</th>
		<td>是</th>
	</tr>
    </thead>
<table>


## Response
```
{
	"status": {
		"code": "200"
	},
	"result": "process done. total process 1000 record."
}
```



 

 

