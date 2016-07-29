### 签名详情 

 签名是为了确保合作方都到的报文来源合法，报文里都包含了data_signature和signature_time两个字段，校验步骤：  
 *  Step1: 请使用一满乐提供的developer_key加上signature_time进行MD5加密，生成一个字符串；
 *  Step2: 用和生成的内容和报文里的data_signature进行比较，一致说明合法，否者为非法；
 

 Pseudocode示例:
 ```
   //根据收到的signature_time和原有的developer_key生成新的字符串
     String newsign = MD5(developer_key + signature_timep);
   
   //用和生成的内容和报文里的data_signature进行比较
     Boolean isValid = newsign.equals(data_signature)
   
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
