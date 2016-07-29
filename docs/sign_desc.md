### 签名详情 

 签名是为了确保合作方都到的报文来源合法，报文里都包含了data_signature和signature_time两个字段，校验步骤：  
 *  Step1: 请使用一满乐提供的developer_key加上signature_time进行MD5加密，生成一个字符串；
 *  Step2: 用和生成的内容和报文里的data_signature进行比较，一致说明合法，否者为非法；
 

 Pseudocode示例:
 ```
     String newsign = MD5(developer_key + signature_timep);  //根据收到的signature_time和原有的developer_key生成新的字符串
     Boolean isValid = newsign.equals(data_signature)；  //用和生成的内容和报文里的data_signature进行比较
```

<a href=''>Java demo下载</a>
