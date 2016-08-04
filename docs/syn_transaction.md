# 实时交易同步

消费记录实时插入，如果传入的用户不存在会创建新用户.

## URL
   {BASE_URL}/tp/services/transaction

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
    "transaction_id": "12345wefr23r",
    "customer_identifier": "13592619028",
    "purchase_time": "2016-03-24 10:10:00",
    "purchase_amount": 14.1,
    "coupon_detail_id": 123456,
    "coupon_amount": 0.8,
    "wx_coupon_amount": 0,
    "gender": 1,
    "customer_nick_name": "ethan",
    "customer_country": " 中国",
    "customer_province": "广东",
    "customer_city": "深圳",
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
     ],
     "coupon_id_list":["abc","12a"]
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
            <td>transaction_id</th>
            <td>字符型</th>
            <td>第三方消费记录的唯一标识</th>
            <td>是</th>
        </tr>
	<tr>
            <td>customer_identifier</th>
            <td>字符型</th>
            <td>用户的唯一标识，如微信的openid</th>
            <td>是</th>
        </tr>
	<tr>
            <td>purchase_time</th>
            <td>字符型</th>
            <td>购买时间，格式为yyyy-mm-dd HH:mm:ss</th>
            <td>是</th>
        </tr>
	<tr>
            <td>purchase_amount</th>
            <td>double</th>
            <td>购买金额</th>
            <td>是</th>
        </tr>
	<tr>
            <td>coupon_amount</th>
            <td>double</th>
            <td>使用优惠券金额</th>
            <td>否</th>
        </tr>
        <tr>
            <td>wx_coupon_amount</th>
            <td>double</th>
            <td>微信优惠券金额</th>
            <td>否</th>
        </tr>
	<tr>
            <td>coupon_detail_id</th>
            <td>数字型</th>
            <td>满乐卡优惠券记录ID</th>
            <td>否</th>
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
        <tr>
            <td>coupon_id_list</td>
            <td>数组</td>
            <td>使用优惠券ID列表</td>
            <td>否</td>
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
	"result": 123456
}
```
