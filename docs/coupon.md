### 优惠券接入说明 
 1. 合作方本身已经有发送优惠券和核销优惠券的相关功能；
 2. 提供发券接口：合作方需要按照指定格式提供创建营销活动和发券2个接口，接口接收的内容要和下面接口说明的一致；
 3. 配置回调url：合作方需要把上述2个接口的接入url配置到一满乐合作方后台中，在建活动和发券的时候，相应的报文会推送到配置的url接口中；
 4. 关于报文签名：每个报文都包括有个签名，合作方需要根据签名检验报文的合法性，点击查看<a href=''>签名详情</a>；
 
---
### 回调url配置地址

 * 测试环境： http://qa.maxfun.co/ 
 * 正式环境： https://tp.maxfun.co/

---
### 接口说明
  * [创建营销活动](https://github.com/maxfunapi/api/blob/master/docs/create_campaign.md)
  * [发券](https://github.com/maxfunapi/api/blob/master/docs/send_coupon.md)