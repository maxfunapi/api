# 历史消费数据导入

本接口用于历史消费数据导入

导完历史数据后推荐手动调用一次<a href=''>表报计算</a>的接口，才能马上看到报表展示。 我们后台每天凌晨会自动执行一次报表计算的任务。

## URL
   {BASE_URL}/tp/services/import_transaction_history

## Method
   POST

## Headers
```
   Content-type=application/json
   Authorization: bearer {access_token}
```

## Request
```
  {
 	"transaction_list":[
		{
			"customer_identifier":"13800138000",
			"customer_created_time":"20165-05-05 13:21:21",
			"purchase_time":"2016-05-05 13:24:21",
			"purchase_amount":18.5,
			"gender":"male",
			"customer_nick_name":"nick",
			"customer_country":"中国",
			"customer_province":"广东",
			"customer_city":"深圳",
			"transaction_id":"1001",
			"goods_list":[
				{
					"goods_id": 1,
					"goods_name": "鱼香茄子",
					"quantity": 1,
					"unit_price": 12.0
				},{
					"goods_id": 2,
					"goods_name": "肉末麻婆豆腐",
					"quantity": 2,
					"unit_price": 12.0
				}
			]
		},
		{...}
	]
 }
 注意：transaction_list 数组长度最大为1000
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
		<td>customer_created_time</th>
		<td>字符型</th>
		<td>用户创建时间 格式(yyyy-MM-dd HH:mm:ss)</th>
		<td>是</th>
	</tr>
	<tr>
		<td>purchase_time</th>
		<td>字符型</th>
		<td>用户消费时间 格式(yyyy-MM-dd HH:mm:ss)</th>
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
		<td>性别 male表示男，female表示女</th>
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
		<td>transaction_id</th>
		<td>字符型</th>
		<td>交易流水ID(不能重复)</th>
		<td>是</th>
	</tr>
	<tr>
            <td>goods_list</th>
            <td>数组</th>
            <td>消费商品列表</th>
            <td>否</th>
        </tr>
		<tr>
            <td>goods_id</th>
            <td>数字型</th>
            <td>商品id</th>
            <td>是</th>
        </tr>
		<tr>
            <td>goods_name</th>
            <td>字符型</th>
            <td>商品名称</th>
            <td>是</th>
        </tr>
		<tr>
            <td>quantity</th>
            <td>数字型</th>
            <td>购买数量</th>
            <td>是</th>
        </tr>
		<tr>
            <td>unit_price</th>
            <td>数字型</th>
            <td>商品单价</th>
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
	"result": {
		"total_count":1000,
		"success_count":998,
		"fail_identifier_list":['01800138000'],
		"message":"手机号码格式不正确，跳过该手机号码:01800138000 \n"
	}
}
```



 

 

