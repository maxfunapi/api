
# 接入流程说明 
 1. 登录后台设置好优惠券推送URL和优惠券明细推送URL;
 2. 给商户配置智能发券规则，保存后，会推送创建优惠券报文到惠券推送URL上面，开发者接收到请求后处理后，并返回指定格式内容，如果不成功，智能发券规则创建失败;
 3. 智能发券触发时，会推送报文到优惠券明细推送URL,并返回指定格式内容,以便优惠券使用核销;
 
#推送优惠券报文
第三方在设置了营销规则并设置了优惠券内容，服务器会向其设置的"创建优惠券URL"，推送优惠券报文，第三方开发者收到报文后，进行业务处理，并返回指定报文。

##推送报文格式
```
	{
		"coupon_name" :"现金券",
		"coupon_amount":10,
		"min_buy_price":0,
		"coupon_type":0,
		"expiration_type":1,
		"expiration_time":"2016-05-01 23:59:59",
		"expiration_interval":1,
		"merchant_id":"88"
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
				<td>coupon_name</th>
				<td>字符串</th>
				<td>优惠券名称</th>
			</tr>
		<tr>
				<td>coupon_amount</th>
				<td>数字型(Double)</th>
				<td>优惠券金额</th>
			</tr>
		<tr>
				<td>coupon_type</th>
				<td>整型</th>
				<td>优惠券类型 0:现金券 1:折扣券</th>
			</tr>
		<tr>
				<td>expiration_type</th>
				<td>整型</th>
				<td>优惠券过期类型<br> 1:是指该优惠劵有统一的过期时间，根据expiration_time的值设定<br>2:是指该优惠劵的过期时间是动态的，根据expiration_interval的值设定</th>
		</tr>
		<tr>
				<td>expiration_interval</th>
				<td>整型</th>
				<td>动态设置优惠劵的时间间隔天数</th>
		</tr>
		<tr>
		<tr>
				<td>merchant_id</th>
				<td>字符串</th>
				<td>第三方商户ID(与创建商户接口的merchant_id字段相同)</th>
		</tr>
    </thead>
<table>

##返回报文格式
```
	{
		"result" : {
			"coupon_id" : "111"
		}
	}
```


#推送优惠券明细报文
在触发了规则时，需要给用户，服务器会向其设置的"创建优惠券明细URL"，推送优惠券明细报文，第三方开发者收到报文后，进行业务处理，并返回指定报文。

##推送报文格式
```
	{
		"identifier" :"13800138000",
		"expiration_time":"2016-05-01 23:59:59",
		"coupon_id":"111",
		"merchant_id":"88"
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
			<td>identifier</th>
			<td>字符串</th>
			<td>用户唯一标识符</th>
		</tr>
		<tr>
			<td>expiration_time</th>
			<td>字符串</th>
			<td>优惠券过期时间 格式:yyyy-MM-dd HH:mm:ss</th>
		</tr>
		<tr>
			<td>coupon_id</th>
			<td>字符串</th>
			<td>第三方优惠券ID(推送创建优惠券返回的优惠券ID)</th>
		</tr>
		<tr>
		<tr>
			<td>merchant_id</th>
			<td>字符串</th>
			<td>第三方商户ID(与创建商户接口的merchant_id字段相同)</th>
		</tr>
    </thead>
<table>

##返回报文格式
```
	{
		"result" : {
			"coupon_detail_id" : "2222"
		}
	}
```
