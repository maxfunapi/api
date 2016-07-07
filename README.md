### 一满乐API文档

---   
  * 测试环境： https://demo.maxfun.co/
  * 正式环境： https://openapi.maxfun.co/

---
####  Header token格式
  * Authorization: bearer {access_token}
  
---
#### 接入流程
  我们推荐一般按照下面的步骤进行数据的对接：  
  1. 创建一个商户（先要联系一满乐获取developer_key）,成功后返回值里面会有app_id和app_secret，第三方需要保存起来,每个商户会定义一个app_id和app_secret；  
  2. 通过上一步得到的appid和appscret获取访问其他接口用的token（token是一家店的标识，该token不会过期，如果调用多次会返回不同的token值）；  
  3. 历史消费数据同步（通过之前获取的token），我们通过transaction_id来判断该纪录是否导入过，如果有发现重复的纪录，会跳过； 
  4. 历史数据同步完成后，需要调用报表计算接口，会立即生成报表（如果不手动调用接口，报表不会立即生成，每天凌晨后台有任务定时   计算生成报表）；  
  5. 实时交易数据的同步（如果transaction_id重复的纪录会报相应错误）；  
  6. 报表页面的嵌入；

---
#### 接口说明
  * [创建商户](https://github.com/maxfunapi/api/blob/master/docs/create_merchant.md)
  * [获取访问token](https://github.com/maxfunapi/api/blob/master/docs/get_access_token.md)
  * [实时交易同步](https://github.com/maxfunapi/api/blob/master/docs/syn_transaction.md)
  * [取消交易](https://github.com/maxfunapi/api/blob/master/docs/cancel_transaction.md)
  * [历史消费数据导入](https://github.com/maxfunapi/api/blob/master/docs/import_history.md)
  * [页面嵌入](https://github.com/maxfunapi/api/blob/master/docs/page_embed.md)
  * [报表计算](https://github.com/maxfunapi/api/blob/master/docs/calculate_data.md)
  * [错误码说明](https://github.com/maxfunapi/api/blob/master/docs/error_code.md)
