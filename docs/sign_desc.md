### 签名详情 

 签名是为了确保合作方收到的报文来源合法，报文里都包含了data_signature和signature_time两个字段，校验步骤：  
 *  Step1: 用一满乐提供的developer_key加上signature_time进行MD5加密，生成一个签名字符串，再对签名字符串转换成全英文大写；
 *  Step2: 比较新生成的字符串和报文里的data_signature，两者一致说明合法，不一致为非法；
 
---

 Pseudocode示例:
 ```
     String newsign = MD5(developer_key + signature_time);  //生成新的签名字符串
     newsSign = newsSign.toUpperCase(); //转换成全大写英文 
     Boolean isValid = newsign.equals(data_signature);      //比较生成的内容和报文里的data_signature
```

---

<a href='http://7xlef9.com1.z0.glb.clouddn.com/demo/java_demo.zip'>Java demo下载</a>
