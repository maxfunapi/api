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
 	"merchant_id": 8888889,
 	"merchant_name": "满乐测试",
 	"merchant_address": "深圳南山科技园",
 	"merchant_type": "餐饮",
 	"business_district": "科技园",
 	"merchant_city": "深圳",
 	"create_time": "2016-03-24 17:21:40",
	"indentifier_type" : 1
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
            <td>数字型</th>
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
            <td>business_district</th>
            <td>字符型</th>
            <td>商圈</th>
            <td>否</th>
        </tr>
	<tr>
            <td>create_time</th>
            <td>字符型</th>
            <td>商户开店时间</th>
            <td>否</th>
        </tr>
	<tr>
            <td>indentifier_type</th>
            <td>数字型</th>
            <td>用户类型：1表示微信；2表示支付宝；3表示电话号码；</th>
            <td>是</th>
        </tr>
    </thead>
<table>



## Response
```
{
	"status": {
		"code": "200",
		"message": "success",
		"errors": [],
		"debug": {
			"build": "1.0",
			"serverName": "ethan-PC",
			"duration": 20332
		}
	},
	"result": {
		  "login_name":"maxfun",
		  "app_id":"9e9e4e8394904c16a6c14e39ba406724",
		  "app_secret":"f2cd22d42c134252b874fbc01cf39a7f"
	}
}
```
<table>
    <thead>
        <tr>
            <th data-tablesaw-sortable-col data-tablesaw-sortable-default-col>字段名称</th>
            <th data-tablesaw-sortable-col>类型</th>
            <th data-tablesaw-sortable-col>描述</th>
        </tr>
      </thead>   
</table>

## Response
 

 

