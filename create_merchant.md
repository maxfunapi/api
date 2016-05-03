# 创建商户

本接口用于创建新的店铺.

## URL
   {BASE_URL}/qf/services/tp/merchant

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
            <!-- Default column -->
            <th data-tablesaw-sortable-col data-tablesaw-sortable-default-col>Rank</th>
            <th data-tablesaw-sortable-col>Movie Title</th>
            <th data-tablesaw-sortable-col data-sortable-numeric>Year</th>
            <th data-tablesaw-sortable-col data-sortable-numeric><abbr title="Rotten Tomato Rating">Rating</abbr></th>
            <!-- Unsortable column -->
            <th>Reviews</th>
        </tr>
    </thead>
<table>
## Request字段描述
字段名称	类型	描述
status		请求返回的状态，所以得返回值都会有这个字段。如果有错误，code将是非200
code	数字型	Code为200表示成功，其他为错误
debug		调试信息
result	对象	返回的实际内容
login_name		登录名,登录后台时使用
app_id		appId,获取token的凭证
app_secret		appSecret,获取token的凭证


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
