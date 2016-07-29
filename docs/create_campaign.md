## 创建营销活动

本接口由合作方提供，下面是为了说明合作方将收到的报文内容.

### URL
```
   回调url，由合作方在一满了合作方后台配置，在创建营销活动的时候，活动报文会通过该url推送给合作方。
   
   * 测试环境配置地址： http://qa.maxfun.co/ 
   * 正式环境配置地址： https://tp.maxfun.co/
```

### Method
   POST

### Headers
```
   Content-type=application/json
```

### Request
```
  	{
		"merchant_id":"88ydr",
		"campaign_name" :"流失顾客将流失挽留",
 		"campaign_start_time":"2016-05-01 00:00:00",
		"campaign_end_time":"2016-05-05 23:59:59",
		"coupon_type":0,
		"coupon_amount":10,
		"min_purchase_price":100,
		"expiration_interval":15,
		"coupon_limit":0,
		"data_signature":"6F3FCD4608978BA4BDD9067AB2672F78",
		"signature_time":"1469707218373"
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
				<td>merchant_id</td>
				<td>字符串</td>
				<td>第三方商户ID(与创建商户接口的merchant_id字段相同)</td>
		</tr>
		<tr>
				<td>campaign_name</td>
				<td>字符串</td>
				<td>营销活动名称，如流失顾客将流失挽留</td>
		</tr>
        	<tr>
				<td>campaign_start_time</td>
				<td>字符串</td>
				<td>营销活动开始时间, 格式yyyy-MM-dd HH:mm:ss</td>
		</tr>
		<tr>
				<td>campaign_end_time</td>
				<td>字符串</td>
				<td>营销活动结束时间, 格式yyyy-MM-dd HH:mm:ss</td>
		</tr>
		<tr>
				<td>coupon_type</td>
				<td>整型</td>
				<td>当前支持2种优惠券类型 0:现金券 1:折扣券</td>
		</tr>
		<tr>
				<td>coupon_amount</td>
				<td>Double</td>
				<td>优惠券金额，根据优惠券类型不同，例如：折扣券7.5折即是7.5，现金券100元即是100</td>
		</tr>
		<tr>
				<td>min_purchase_price</td>
				<td>Double</td>
				<td>最低消费金额，在发满减券时使用，无最低消费金额限制的此处为0</td>
		</tr>
		<tr>
				<td>expiration_interval</td>
				<td>整型</td>
				<td>优惠劵过期时间间隔天数，比如此处为15表示优惠券在发送后15日内有效</td>
		</tr>
		<tr>
				<td>coupon_limit</td>
				<td>整型</td>
				<td>优惠券发送限额，在有优惠券张数预算时使用，比如某个活动商家最多只想发100张券</td>
		</tr>
		<tr>
		<tr>
				<td>data_signature</td>
				<td>字符串</td>	<td>除去data_signature字段外，developerKey加上signature_time生成的报文MD5签名</td>
		</tr>
		<tr>
				<td>signature_time</td>
				<td>字符串</td>	<td>签名时间戳</td>
		</tr>
    </thead>
<table>


### Response
```
	{
		"result" : {
			"campaign_id" : "111"
		}
	}
```
