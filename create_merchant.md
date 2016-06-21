# 创建商户

本接口用于创建新的店铺.

## URL
   {BASE_URL}/tp/services/merchant

## Method
   POST

## Headers
```
   Content-type=application/json
```

## Request
```
  {
 	"merchant_id": "10086",
 	"merchant_name": "alipp测试",
 	"merchant_address": "深圳南山科技园",
 	"merchant_type": "餐饮",
 	"merchant_city": "深圳",
 	"create_time": "2016-03-24 17:21:40",
	"identifier_type" : 3,
	"password":"pdwdzzz",
	"login_name":"loginname",
	"developer_key":"asdfaefasd-asdfw3hrtgn-asfgrerawe124easd"
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
            <td>merchant_id</th>
            <td>字符型</th>
            <td>第三方商户ID</th>
            <td>是</th>
        </tr>
	<tr>
            <td>merchant_name</th>
            <td>字符型</th>
            <td>商户名称</th>
            <td>是</th>
        </tr>
	<tr>
            <td>merchant_address</th>
            <td>字符型</th>
            <td>商户地址</th>
            <td>是</th>
        </tr>
	<tr>
            <td>merchant_type</th>
            <td>字符型</th>
            <td>商户类型</th>
            <td>否</th>
    </tr>
	<tr>
            <td>merchant_city</th>
            <td>字符型</th>
            <td>商户所在城市</th>
            <td>否</th>
    </tr>
	<tr>
	<tr>
            <td>create_time</th>
            <td>字符型</th>
            <td>商户开店时间 格式为yyyy-MM-dd HH:mm:ss</th>
            <td>否</th>
        </tr>
	<tr>
		<td>identifier_type</th>
		<td>数字型</th>
		<td>用户类型：1表示微信；2表示支付宝；3表示电话号码；</th>
		<td>是</th>
	</tr>
	<tr>
		<td>password</th>
		<td>字符型</th>
		<td>商户登录密码</th>
		<td>否</th>
	</tr>
	<tr>
		<td>login_name</th>
		<td>字符型</th>
		<td>用户登录名称</th>
		<td>否</th>
	</tr>
	<tr>
		<td>developer_key</th>
		<td>字符型</th>
		<td>开发者key,由一满乐提供</th>
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
	"result": {
		"login_name":"maxfun",
		"app_id":"app_id",
		"app_secret":"app_secret"
	}
}
```



 

 

