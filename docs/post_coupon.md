
# 接入流程说明 
 1. 登录后台设置好优惠券推送URL和优惠券明细推送URL;
 2. 给商户配置智能发券规则，保存后，会推送创建优惠券报文到惠券推送URL上面，开发者接收到请求后，对报文进行MD5签名对比，验证报文是否正常，处理并返回指定格式内容，如果不成功，智能发券规则创建失败;
 3. 智能发券触发时，会推送报文到优惠券明细推送URL,并返回指定格式内容,以便优惠券使用核销;
 
#MD5签名对比说明
以下提供了demo附件。
<a href='http://7xlef9.com1.z0.glb.clouddn.com/demo%2Fjava_demo1.0.zip'>下载<a>
```
把附件的Java类复制到代码中
使用示例:
	Boolean isValid = SignatureUtil.checkSignValid("developer_key", request);
	if(!isValid){
	    //签名验证失败。。
	}
	//业务处理
```


#推送优惠券报文
第三方在设置了营销规则并设置了优惠券内容，服务器会向其设置的"创建优惠券URL"，推送优惠券报文，第三方开发者收到报文后，进行业务处理，并返回指定报文。

##推送报文格式
```
	{
 		"campaign_start_time":"2016-05-01 00:00:00",
		"campaign_end_time":"2016-05-05 23:59:59",
		"coupon_name" :"现金券",
		"coupon_amount":10,
		"min_purchase_price":0,
		"coupon_type":0,
		"coupon_limit":0,
		"expiration_interval":1,
		"merchant_id":"88",
		"data_signature":"6F3FCD4608978BA4BDD9067AB2672F78"
	}
```
<table data-tablesaw-sortable>
    <thead>
        <tr>
            <th data-tablesaw-sortable-col data-tablesaw-sortable-default-col>字段名称</th>
            <th data-tablesaw-sortable-col>类型</th>
            <th data-tablesaw-sortable-col>是否必填</th>
            <th data-tablesaw-sortable-col>描述</th>
        </tr>
        	<tr>
				<td>campaign_start_time</td>
				<td>字符串</td>
				<td>活动开始时间, 格式yyyy-MM-dd HH:mm:ss</td>
		</tr>
		<tr>
				<td>campaign_end_time</td>
				<td>字符串</td>
				<td>活动结束时间, 格式yyyy-MM-dd HH:mm:ss</td>
		</tr>
		<tr>
				<td>coupon_name</td>
				<td>字符串</td>
				<td>优惠券名称</td>
		</tr>
		<tr>
				<td>coupon_type</td>
				<td>整型</td>
				<td>当前支持2种优惠券类型 0:现金券 1:折扣券</td>
		</tr>
		<tr>
				<td>coupon_amount</td>
				<td>Double</td>
				<td>优惠券金额，根据优惠券类型不同，例如：100元 或者 7.5折</td>
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
				<td>merchant_id</td>
				<td>字符串</td>
				<td>第三方商户ID(与创建商户接口的merchant_id字段相同)</td>
		</tr>
		<tr>
				<td>data_signature</td>
				<td>字符串</td>
				<td>除去data_signature字段外，其他字段按ASCII字典序排序加上developerKey生成的报文MD5签名</td>
		</tr>
    </thead>
<table>

##返回报文格式
```
	{
		"result" : {
			"campaign_id" : "111"
		}
	}
```


#推送优惠券明细报文
在触发了规则时，需要给用户，服务器会向其设置的"创建优惠券明细URL"，推送优惠券明细报文，第三方开发者收到报文后，进行业务处理，并返回指定报文。

##推送报文格式
```
	{
		"identifier":"18520869180",
		"merchant_id":"11",
		"campaign_id":"3",
		"expiration_time":"2016-07-30 00:00:00",
		"coupon_type":0,
		"coupon_amount":10,
		"min_purchase_price":0,
		"data_signature":"E42EB1F912BF43BEA69F0382FFF440D2"
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
			<td>campaign_id</th>
			<td>字符串</th>
			<td>第三方优惠券ID(推送创建优惠券返回的ID)</th>
		</tr>
		<tr>
		<tr>
			<td>merchant_id</th>
			<td>字符串</th>
			<td>第三方商户ID(与创建商户接口的merchant_id字段相同)</th>
		</tr>
		<tr>
				<td>coupon_amount</td>
				<td>数字型(Double)</td>
				<td>优惠券金额，折扣7.5折即是7.5</td>
		</tr>
		<tr>
				<td>min_purchase_price</td>
				<td>数字型(Double)</td>
				<td>最低消费金额</td>
		</tr>
		<tr>
				<td>coupon_type</td>
				<td>整型</td>
				<td>优惠券类型 0:现金券 1:折扣券</td>
		</tr>
		<tr>
				<td>data_signature</td>
				<td>字符串</td>
				<td>除去data_signature字段外，其他字段按ASCII字典序排序加上developerKey生成的报文MD5签名</td>
		</tr>
    </thead>
<table>

##返回报文格式
```
	{
		"result" : {
			"coupon_id" : "2222"
		}
	}
```
