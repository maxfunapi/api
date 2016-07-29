### 签名详情 

 本签名是为了确保合作方收到的报文来源合法，报文里都包含了data_signature和signature_time两个字段，校验步骤：  
 *  Step1: 用一满乐提供的developer_key加上signature_time进行MD5加密，生成一个签名字符串；
 *  Step2: 比较生成的字符串和报文里的data_signature，一致说明合法，否者为非法；
 
---

 Pseudocode示例:
 ```
     String newsign = MD5(developer_key + signature_time);  //生成新的签名字符串
     Boolean isValid = newsign.equals(data_signature);      //比较生成的内容和报文里的data_signature
```

---

<a href=''>Java demo下载</a>
