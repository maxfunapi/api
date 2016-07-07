# 一满乐API文档


## API访问URL
   
  * 测试环境： https://demo.maxfun.co/
  * 正式环境： https://openapi.maxfun.co/


##  Header token格式
  * Authorization: bearer {access_token}

## 接入流程
  我们推荐一般按照下面的步骤进行数据的对接：  
  1.创建一个商户（先要联系一满乐公司获取developer_key）,成功后返回值里面会有appid和appsecret，第三方想要保存起来；  
  2.通过上一步过去的appid和appscret获取访问下面接口用的token（token是这家店的安全标示，该token不会过期，如果调用多次会返回不同的token值）；  
  3.历史消费数据同步（通过上一步获取的token）；  
  4.历史数据同步完成后，需要调用报表计算接口，会立即生成报表（如果不手动调用接口，报表不会立即生成，每天凌晨后台有任务定时   计算生成报表）；  
  5.实时交易数据的同步；
  6.报表页面的嵌入；

## 接口说明
  * [创建商户](https://github.com/maxfunapi/api/blob/master/create_merchant.md)
  * [获取访问token](https://github.com/maxfunapi/api/blob/master/get_access_token.md)
  * [实时交易同步](https://github.com/maxfunapi/api/blob/master/syn_transaction.md)
  * [取消交易](https://github.com/maxfunapi/api/blob/master/cancel_transaction.md)
  * [历史消费数据导入](https://github.com/maxfunapi/api/blob/master/import_history.md)
  * [页面嵌入](https://github.com/maxfunapi/api/blob/master/page_embed.md)
  * [报表计算](https://github.com/maxfunapi/api/blob/master/calculate_data.md)
  * [错误码说明](https://github.com/maxfunapi/api/blob/master/error_code.md)
