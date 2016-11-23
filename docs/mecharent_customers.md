# 查询商户用户列表

 查询商户用户列表

## URL
   {BASE_URL}/tp/services/mecharent_customers

## Method
   GET

## Headers
```
   Authorization=bearer {access_token}
```

## Request
```
{BASE_URL}/tp/services/mecharent_customers?search_param=xx&register_date=2016-11-01&rfm_group_id=-1&limit=10&current_page=1&sorting=1
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
            <td>search_param</th>
            <td>字符型</th>
            <td>模糊搜索标识符和手机号码</th>
            <td>否</th>
        </tr>
		<tr>
            <td>register_date</th>
            <td>字符型</th>
            <td>注册时间:格式yyyy-MM-dd</th>
            <td>否</th>
        </tr>
		<tr>
            <td>limit</th>
            <td>整型</th>
            <td>每页数量，默认10</th>
            <td>否</th>
        </tr>
		<tr>
            <td>current_page</th>
            <td>整型</th>
            <td>当前第几页,默认1</th>
            <td>否</th>
        </tr>
		<tr>
            <td>rfm_group_id</th>
            <td>整型</th>
            <td>分组id</th>
            <td>否</th>
        </tr>
		<tr>
            <td>sorting</th>
            <td>整型</th>
            <td>排序 1 消费金额排序 2 最后消费时间排序</th>
			<td>否</th>
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
    "list": [
      {
        "gender": "男",
        "customer_nick_name": "162925",
        "customer_identifier": "13126993329",
        "last_purchase_time": "2016-02-23 11:40:46",
        "total_purchase_amount": 37595,
        "rfm_display": "流失顾客"
	  }
    ],
    "pagination": {
      "limit": 10,
      "total_count": 1,
      "total_page": 1,
      "current_page": 1
    }
  }
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
            <td>customer_identifier</th>
            <td>字符型</th>
            <td>用户的唯一标识</th>
        </tr>
		<tr>
            <td>gender</th>
            <td>字符型</th>
            <td>性别 male表示男，female表示女</th>
        </tr>
		<tr>
            <td>last_purchase_time</th>
            <td>字符型</th>
            <td>最后消费时间， 格式:yyyy-MM-dd HH:ss:mm</th>
        </tr>
		<tr>
            <td>total_purchase_amount</th>
            <td>数字型</th>
            <td>总消费金额</th>
        </tr>
		<tr>
            <td>rfm_display</th>
            <td>字符型</th>
            <td>分组名称</th>
        </tr>
    </thead>
<table>
