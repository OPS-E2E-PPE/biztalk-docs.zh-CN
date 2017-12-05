---
title: "MSMQ 适配器配置属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, receive locations
- MSMQ adapters, send ports
- receive locations, adapters
- MSMQ adapters, properties
- MSMQ adapters, code sample
- send ports, adapters
ms.assetid: d660d0ce-bff9-4bc5-be1d-38954c2fdbe2
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 060d6fbfb75c97e4fa4bc6bbfc3f160972c437ff
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="msmq-adapter-configuration-properties"></a>MSMQ 适配器配置属性
下表列出了可为 MSMQ 适配器接收位置设置的配置属性：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|queue|VT_BSTR|指定接收位置所监视的位置的有效队列路径。|发送端口或接收位置的 URI 不能超过 256 个字符。|无|  
|batchSize|VT_BSTR|指定 MSMQ 适配器向 MessageBox 数据库提交消息批时所用的批大小。|有效值为从 1 到 4294967295。|默认值为 20。|  
|transactional|VT_BSTR|指定是否从 Microsoft 分布式事务处理 (MSDTC) 的上下文下的源队列读取消息。|有效值为<br /><br /> -true<br />-false<br /><br /> 该适配器不支持对远程队列进行事务性读取。|默认值为 false。|  
|serialProcessing|VT_BSTR|指定是否按顺序处理信息。|有效值为<br /><br /> -true<br />-false|默认值为 false。|  
|onFailure|VT_BSTR|指定适配器响应错误的方式。|有效值为<br /><br /> -stopOnFailure<br />-suspendNonResumable<br />-suspendResumable|默认值为“suspendResumable”。|  
|URI|VT_BSTR|指定接收位置所监视的队列的完整路径。|发送端口或接收位置的 URI 不能超过 256 个字符。|无|  
  
 以下代码显示用于设置这些属性的字符串的格式：  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><queue>FORMATNAME:DIRECT=OS:.\PRIVATE$\QUEUE</queue><batchSize>20</batchSize><transactional>false</transactional><serialProcessing>false</serialProcessing><onFailure>suspendResumable</onFailure><uri>FORMATNAME:DIRECT=OS:.\PRIVATE$\QUEUE</uri></Config></AdapterConfig></CustomProps>  
```  
  
 下表列出了可为 MSMQ 适配器发送端口设置的配置属性：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|队列|VT_BSTR|指定目标队列。|发送端口或接收位置的 URI 不能超过 256 个字符。|无|  
|maximumMessageSiz|VT_BSTR|指定发送给指定队列的消息的最大大小 (KB)。|如果将 segmentationSupport 和 transactional 设置为“true”，则有效值为 1 到 4294967295。 否则，有效值为 1 到 4095。|默认值为 1024年。|  
|acknowledgeType|VT_BSTR|指定一个或多个确认类型。|有效值为的.NET 成员**System.Messaging.AcknowledgeTypes**枚举。|默认值为 None。|  
|administrationQueue|VT_BSTR|指定 MSMQ 管理队列。|无|无|  
|timeOut|VT_BSTR|指定等待消息到达目标队列的最长时间。|仅当将 transactional 属性设置为“true”时，才应用此属性。<br /><br /> -有效值为 1 到 10675199 时指定的天数 timeOutUnits 值。<br />-有效值为 1 到 596523 时指定的小时 timeOutUnits 值。<br />-有效值为 1 到 35791394 指定分钟的 timeOutUnits 值时。<br />-指定的秒 timeOutUnits 值时，有效值为 1 到 2147483647。|无|  
|priority|VT_BSTR|指定消息优先级。|有效值为的.NET 成员**System.Messaging.MessagePriority**枚举。|无|  
|recoverable|VT_BSTR|指定是否确保消息的可恢复性。|有效值为<br /><br /> -true<br />-false|默认值为 false。|  
|encryptionAlgorithm|VT_BSTR|指定要使用的加密算法。|有效值为的.NET 成员**System.Messaging.EncryptionAlgorithm**枚举。|默认值为 None。|  
|useAuthentication|VT_BSTR|指定是否使用验证。|此属性与 certificate 属性合用来验证消息。 使用 userName 属性和 password 属性来访问队列。|无|  
|证书 (certificate)|VT_BSTR|指定用于验证消息的证书。|输入 40 个字符的证书指纹。|无|  
|segmentationSupport|VT_BSTR|指定是否支持分段。|有效值为<br /><br /> -true<br />-false|默认值为 false。|  
|transactional|VT_BSTR|指定是否支持 Microsoft 分布式事务处理 (MSDTC) 的上下文下的消息发送。|有效值为<br /><br /> -true<br />-false|默认值为 false。|  
|useJournalQueue|VT_BSTR|指定是否在处理消息时，保存该消息的副本。|有效值为<br /><br /> -true<br />-false|默认值为 false。|  
|useDeadLetterQueue|VT_BSTR|指定在出错时，是否向死信队列发送消息。|有效值为<br /><br /> -true<br />-false|默认值为 true。|  
|ackTypeEnumsValue|VT_BSTR|指定对与给定的 acknowledgeType 值相关的值进行位或运算。|无|默认值为 0。|  
|timeOutUnits|VT_BSTR|指定为 timeOut 属性指定的值的单位。|有效值为<br /><br /> -天数<br />-小时数<br />-分钟<br />-秒|默认值为“天”。|  
|userName|VT_BSTR|指定远程队列的用户名。|默认值为空。|  
|password|VT_BSTR|指定与 userName 属性的指定值一起使用的密码，以访问远程队列。|在导出绑定文件时此值始终会被屏蔽。 在将绑定文件导入目标 BizTalk Server 配置前，必须手动在此字段中填充密码。|默认值为空。|  
|bodyType|VT_BSTR|指定 MSMQ 中的消息正文类型。|有效值为.NET 成员**VarEnum**枚举。|默认值为 8209。|  
|URI|VT_BSTR|指定目标队列的完整路径。|发送端口或接收位置的 URI 不能超过 256 个字符。|无|  
  
 以下代码显示用于设置这些属性的字符串的格式：  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><queue>FORMATNAME:DIRECT=OS:TESTSERVER\PRIVATE$\DESTQUEUE</queue><maximumMessageSize>1024</maximumMessageSize><acknowledgeType>None</acknowledgeType><administrationQueue>Direct=OS:TestServer\Private$\AdminQueue</administrationQueue><timeOut>4</timeOut><priority>Normal</priority><recoverable>false</recoverable><encryptionAlgorithm>None</encryptionAlgorithm><useAuthentication>false</useAuthentication><segmentationSupport>false</segmentationSupport><transactional>false</transactional><useJournalQueue>false</useJournalQueue><useDeadLetterQueue>true</useDeadLetterQueue><ackTypeEnumsValue>0</ackTypeEnumsValue><timeOutUnits>Days</timeOutUnits><userName>TestUser</userName><password>******</password><bodyType>8209</bodyType><uri>FORMATNAME:DIRECT=OS:TESTSERVER\PRIVATE$\DESTQUEUE</uri></Config></AdapterConfig>  
```  
  
> [!NOTE]
>  在指定的适配器，使用适配器框架构建的 TransportTypeData 配置数据时，使用的名称/值对必须全部存储到\<AdapterConfig\>元素。 由于\<AdapterConfig\>元素指定 VT_BSTR (vt ="8") 数据类型则\<\>数据中的字符必须进行转义。