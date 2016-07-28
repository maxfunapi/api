### 一满乐API文档

---   
  * 测试环境： https://demo.maxfun.co/
  * 正式环境： https://openapi.maxfun.co/
  
---
### 数据接入流程说明
  我们推荐一般按照下面的步骤进行数据对接：  
  1. 创建一个商户（先要联系一满乐获取developer_key）,成功后返回值里面会有app_id和app_secret，第三方需要保存起来,每个商户会对应一个app_id和app_secret;  
  2. 通过上一步得到的app_id和app_secret获取访问其他接口用的token(token是一家店的标识，该token不会过期，如果调用多次会返回不同的token值);
  3. 历史消费数据同步（通过之前获取的token），我们通过transaction_id来判断该纪录是否导入过，如果有发现重复的纪录，会跳过； 
  4. 历史数据同步完成后，为了立即生成报表，需要手动调用报表计算接口(如果不手动调用该接口，报表不会立即生成，每天凌晨后台有任务定时生成); 
  5. 实时交易数据的同步(如果transaction_id重复会报错)，实时交易数据的同步需要考虑的问题比较多，比如撤销、冲正等情况，所以此步骤不是必须的;
  6. 如果跳过第5步，替代方案是定时调用历史数据导入接口，把每天的增量数据导入（推荐每天凌晨导前一天的数据）。这样做的优势是对第三方本身代码的倾入性较小，方便接入；劣势是有些数据不能实时显示，不能做后续的实时营销的操作（如消费后发券）；
  7. 报表页面的嵌入;

---
### 数据接入接口说明
  * [创建商户](https://github.com/maxfunapi/api/blob/master/docs/create_merchant.md)
  * [获取访问token](https://github.com/maxfunapi/api/blob/master/docs/get_access_token.md)
  * [历史消费数据导入](https://github.com/maxfunapi/api/blob/master/docs/import_history.md)
  * [实时交易同步](https://github.com/maxfunapi/api/blob/master/docs/syn_transaction.md)
  * [取消交易](https://github.com/maxfunapi/api/blob/master/docs/cancel_transaction.md)
  * [页面嵌入](https://github.com/maxfunapi/api/blob/master/docs/page_embed.md)
  * [报表计算](https://github.com/maxfunapi/api/blob/master/docs/calculate_data.md)
  * [错误码说明](https://github.com/maxfunapi/api/blob/master/docs/error_code.md)
  

---
### 优惠券接入说明 
 1. 合作方本身已经有发送优惠券和核销优惠券的相关功能；
 2. 提供发券接口：合作方需要按照指定格式提供创建营销活动和发券2个接口，接口接收的内容要和下面接口说明的一致；
 3. 配置回调url：合作方需要把上述2个接口的接入url配置到一满乐合作方后台中，在建活动和发券的时候，相应的报文会推送到配置的url接口中；
 4. 关于报文签名：每个报文都包括有个签名，合作方需要根据签名检验报文的合法性，点击查看<a href=''>签名详情</a>；
 
---
### 回调url配置地址

 测试环境： http://qa.maxfun.co/   
 正式环境： https://tp.maxfun.co/

---
### 接口说明
  * [创建营销活动](https://github.com/maxfunapi/api/blob/master/docs/create_campaign.md)
  * [发券](https://github.com/maxfunapi/api/blob/master/docs/send_coupon.md)
