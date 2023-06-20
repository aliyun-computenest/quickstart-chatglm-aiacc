# 快速构建中英文AI对话机器人

>**免责声明：**本服务由第三方提供，我们尽力确保其安全性、准确性和可靠性，但无法保证其完全免于故障、中断、错误或攻击。因此，本公司在此声明：对于本服务的内容、准确性、完整性、可靠性、适用性以及及时性不作任何陈述、保证或承诺，不对您使用本服务所产生的任何直接或间接的损失或损害承担任何责任；对于您通过本服务访问的第三方网站、应用程序、产品和服务，不对其内容、准确性、完整性、可靠性、适用性以及及时性承担任何责任，您应自行承担使用后果产生的风险和责任；对于因您使用本服务而产生的任何损失、损害，包括但不限于直接损失、间接损失、利润损失、商誉损失、数据损失或其他经济损失，不承担任何责任，即使本公司事先已被告知可能存在此类损失或损害的可能性；我们保留不时修改本声明的权利，因此请您在使用本服务前定期检查本声明。如果您对本声明或本服务存在任何问题或疑问，请联系我们。


## 概述

**ChatGLM-6B** 由清华大学团队开发的是一个开源的、支持中英双语的对话语言模型，基于 **General** **Language** **Model** **(GLM)** 架构，具有 62 亿参数。结合模型量化技术，用户可以在**单GPU卡(A10或者V100)上进行部署**。ChatGLM-6B 使用了和 ChatGPT 相似的技术，针对中文问答和对话进行了优化。经过约 1T 标识符的中英双语训练，辅以监督微调、反馈自助、人类反馈强化学习等技术的加持，62 亿参数的 ChatGLM-6B 已经能生成相当符合人类偏好的回答。
# 计算巢实例创建
## 创建实例
访问[计算巢实例](https://computenest.console.aliyun.com/user/cn-hangzhou/recommendService)，点击创建**ChatGLM 中英文对话机器人社区版。**
![image.png](https://intranetproxy.alipay.com/skylark/lark/0/2023/png/125679/1687250427454-3ac327af-8d0b-4022-a5a3-6778092f87fe.png#clientId=u6d8ed4f9-232c-4&from=paste&height=408&id=ua4303fcb&originHeight=815&originWidth=968&originalType=binary&ratio=2&rotation=0&showTitle=false&size=685031&status=done&style=none&taskId=ua129f29e-b06d-41f7-84fa-36135a7aa52&title=&width=484)
## 选择所需地域:
![image.png](https://intranetproxy.alipay.com/skylark/lark/0/2023/png/125679/1685066681428-c9ad983f-eba7-4705-a508-1e7e79d5809f.png#clientId=u98f890e2-bf6b-4&from=paste&height=632&id=uc1466379&originHeight=632&originWidth=2022&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1060858&status=done&style=none&taskId=u1222a295-5b65-4e09-b52c-35be36b94f7&title=&width=2022)
勾选实例类型，并填写实例密码：
![image.png](https://intranetproxy.alipay.com/skylark/lark/0/2023/png/125679/1685066734916-f5216e58-a314-4bb4-a4c6-3c07efe15ca1.png#clientId=u98f890e2-bf6b-4&from=paste&height=986&id=u4cfcc128&originHeight=986&originWidth=2168&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1877143&status=done&style=none&taskId=u641f88d6-6a62-4d88-ba0f-224238d2460&title=&width=2168)
填写登录用户名和密码，用户名和密码在后续登录webui时使用:
![image.png](https://intranetproxy.alipay.com/skylark/lark/0/2023/png/125679/1685066772866-82dbbcfd-a808-4800-84aa-a43596df8239.png#clientId=u98f890e2-bf6b-4&from=paste&height=414&id=ua326f875&originHeight=414&originWidth=2158&originalType=binary&ratio=1&rotation=0&showTitle=false&size=748549&status=done&style=none&taskId=uc9af6f1e-5916-4100-8449-ef9f6361b69&title=&width=2158)
选择网络配置，如果希望在已有vpc中使用，则选择不新建VPC，同时选择VPC的实例ID和交换机ID。否则，可以选择新建VPC如下图所示:
![image.png](https://intranetproxy.alipay.com/skylark/lark/0/2023/png/125679/1687250587569-7947651f-67f0-4741-af48-448aea57fac7.png#clientId=u6d8ed4f9-232c-4&from=paste&height=258&id=uc4fc051d&originHeight=371&originWidth=814&originalType=binary&ratio=2&rotation=0&showTitle=false&size=191675&status=done&style=none&taskId=u87fb6094-fac6-40ee-8366-85c04091a8d&title=&width=566)
设置模型配置，请将ChatGLM-6B模型权重地址填入PluginGitUrl字段中，例如[https://huggingface.co/THUDM/chatglm-6b](https://huggingface.co/THUDM/chatglm-6b)，如下图所示：
![image.png](https://intranetproxy.alipay.com/skylark/lark/0/2023/png/125679/1687250670062-a6cb4297-764a-4bfa-bc4c-b2c65af612fd.png#clientId=u6d8ed4f9-232c-4&from=paste&height=191&id=ud10ef6a9&originHeight=277&originWidth=820&originalType=binary&ratio=2&rotation=0&showTitle=false&size=148713&status=done&style=none&taskId=ud0c7cdb9-bb1a-4ea3-86b0-7bc24db7f92&title=&width=566)
点击下一步:确认订单，并勾选服务条款，点击创建：
![image.png](https://intranetproxy.alipay.com/skylark/lark/0/2023/png/125679/1685066899702-b24b6a24-32f4-49be-a797-47961dd02202.png#clientId=u98f890e2-bf6b-4&from=paste&height=217&id=ub402146f&originHeight=448&originWidth=970&originalType=binary&ratio=1&rotation=0&showTitle=false&size=409082&status=done&style=none&taskId=u93db4c88-6d08-4357-8d40-1aac1c578f7&title=&width=470)
由于我们需要下载模型，因此需等待20分钟左右，等待部署完成。
# 执行测试
## 登录页面
点击计算巢控制台中的实例:
![image.png](https://intranetproxy.alipay.com/skylark/lark/0/2023/png/125679/1687254805477-f54c93a7-3177-4b4e-9ba6-ec2250092f6b.png#clientId=u7a73b449-7a4c-4&from=paste&height=346&id=u0f6975ff&originHeight=692&originWidth=1078&originalType=binary&ratio=2&rotation=0&showTitle=false&size=505125&status=done&style=none&taskId=ue136bf40-021e-407f-974f-65279a5dee0&title=&width=539)
点击其中的endpoint网址：
![image.png](https://intranetproxy.alipay.com/skylark/lark/0/2023/png/125679/1685067348654-6ef6bc5e-b291-4a37-98d0-fc2e40c30b2a.png#clientId=u98f890e2-bf6b-4&from=paste&height=1190&id=u76383091&originHeight=1190&originWidth=2588&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2541533&status=done&style=none&taskId=udaf1cb4b-4017-454a-ba32-218624e9c6f&title=&width=2588)
## 测试
输入登录信息中的用户名和密码登录:
![image.png](https://intranetproxy.alipay.com/skylark/lark/0/2023/png/125679/1685067431628-1f7b4b83-eda3-4d7b-9522-6959a7c69047.png#clientId=u98f890e2-bf6b-4&from=paste&height=1710&id=u9571d219&originHeight=1710&originWidth=3128&originalType=binary&ratio=1&rotation=0&showTitle=false&size=3856733&status=done&style=none&taskId=u49d8db20-a82b-458d-8843-e0c0a5bc6ce&title=&width=3128)
进入测试页面:
![image.png](https://intranetproxy.alipay.com/skylark/lark/0/2023/png/140360/1681704084081-283c4e07-fe8d-4f97-9026-45b42e8c4683.png#clientId=u8ac9958f-c728-4&from=paste&height=687&id=u8b313080&originHeight=945&originWidth=1920&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=158934&status=done&style=none&taskId=uad9ffe18-959a-4b01-ae5f-d827336df06&title=&width=1396.3636363636363)
输入中文对话内容，例如:
```bash
中国有多少个少数民族?
```
点击"发送"，即可开始AI对话：
![image.png](https://intranetproxy.alipay.com/skylark/lark/0/2023/png/140360/1681704214021-bfe8a798-99da-464c-ab07-bd9318ead398.png#clientId=u8ac9958f-c728-4&from=paste&height=687&id=u5fa60210&originHeight=945&originWidth=1920&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=203603&status=done&style=none&taskId=u942b73bd-f0a3-4b2e-81db-7a97f649daf&title=&width=1396.3636363636363)


