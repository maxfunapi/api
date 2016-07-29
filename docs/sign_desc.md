### 签名详情 
 1. 一满乐服务器推送的报文，都包含了data_signature,signature_time。收到报文后，请使用一满乐提供的developer_key加上signature_time进行MD5加密
 ```
  示例:
   String sign = MD5(developer_key + signature_timep);
```
 
 2. 用data_signature与新生成的MD5值进行比较，如果值不一致。报文是非法的。
 ```
  示例：
   Boolean isValid = sign.equals(data_signature);
   也可以使用demo内提供的Java的签名验证工具
   Boolean isValid = SignatureUtil.checkSignValid("developer_key", signature_time, data_signature);
   isValid返回true表示MD5值对比一致，相反则报文非法。
 ```
 ---
