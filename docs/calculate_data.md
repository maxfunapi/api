# 报表计算

导入数据后需要进行数据计算统计，全部数据导入完毕后调用一次即可，多次调用无效。
该接口是异步执行

## URL
   {BASE_URL}/tp/services/calculate_data

## Method
   GET

## Headers
```
   Authorization: bearer {token}
```

## Request


## Response
```
{
	"status": {
		"code": "200",
		"message": "success"
	},
	"result": "success"
}
```
