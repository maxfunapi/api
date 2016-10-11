## 优惠券发送

本接口由合作方提供，下面是为了说明合作方将收到的报文内容.

### URL
```
 回调url，由合作方在一满了合作方后台配置，在发送优惠券的时候，相关报文会通过该url推送给合作方。
 * 测试环境配置地址： http://qa.maxfun.co
 * 正式环境配置地址： https://tp.maxfun.co
```

### Method
```
   POST
   ```

### Headers
```
   Content-type=application/json
```

### Request
```
  		{
		"merchant_id":"11",
		"campaign_id":"3",
		"customer_identifier":"7uy3hasdf929-1ertg238824",
		"coupon_type":0,
		"coupon_amount":10,
		"min_purchase_price":100,
		"expiration_time":"2016-07-30 00:00:00",
		"data_signature":"E42EB1F912BF43BEA69F0382FFF440D2",
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
				<td>campaign_id</th>
				<td>字符串</th>
				<td>合作方营销活动ID(推送创建营销活动时返回的ID)</th>
		</tr>
		<tr>
		<tr>
				<td>merchant_id</th>
				<td>字符串</th>
				<td>合作方商户ID(与创建商户接口的merchant_id字段相同)</th>
		</tr>
		<tr>
				<td>customer_identifier</th>
				<td>字符串</th>
				<td>用户唯一标识符</th>
		</tr>
		<tr>
				<td>coupon_amount</td>
				<td>Double</td>
				<td>优惠券金额，折扣7.5折即是7.5，现金券100元即是100</td>
		</tr>
		<tr>
				<td>min_purchase_price</td>
				<td>Double</td>
				<td>最低消费金额</td>
		</tr>
		<tr>
				<td>coupon_type</td>
				<td>整型</td>
				<td>优惠券类型 0:现金券 1:折扣券</td>
		</tr>
		<tr>
				<td>expiration_time</th>
				<td>字符串</th>
				<td>优惠券过期时间 格式:yyyy-MM-dd HH:mm:ss</th>
		</tr>
		<tr>
				<td>data_signature</td>
				<td>字符串</td>
				<td>除去data_signature字段外，developer_key加上signature_time生成的报文MD5签名</td>
		</tr>
		<tr>
				<td>signature_time</td>
				<td>字符串</td>
				<td>签名时间戳</td>
		</tr>
    </thead>
<table>


### Response
```
	{
		"return_code":"success/fail",
        	"return_msg":"错误信息",
		"coupon_id" : "2222"
	}
```
