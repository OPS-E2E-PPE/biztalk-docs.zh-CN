---
title: MSMQ 适配器配置属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, receive locations
- MSMQ adapters, send ports
- receive locations, adapters
- MSMQ adapters, properties
- MSMQ adapters, code sample
- send ports, adapters
ms.assetid: d660d0ce-bff9-4bc5-be1d-38954c2fdbe2
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66c6e2345044b9fbd43bbb3fce4e0c8cf265ce72
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531156"
---
# <a name="msmq-adapter-configuration-properties"></a>MSMQ 适配器配置属性
下表列出了可以设置为 MSMQ 适配器的配置属性接收位置：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|queue|VT_BSTR|指定接收位置所监视的位置的有效的队列路径。|URI 发送端口或接收位置不能超过 256 个字符。|None|  
|batchSize|VT_BSTR|指定 MSMQ 适配器将使用提交到 MessageBox 数据库的消息批时批处理大小。|有效值为从 1 到 4294967295。|默认值为 20。|  
|事务|VT_BSTR|指定是否从下的 Microsoft 分布式事务 (MSDTC) 的上下文的源队列读取消息。|有效值为<br /><br /> -true<br />-false<br /><br /> 适配器不支持对远程队列事务性读取。|默认值是 False。|  
|serialProcessing|VT_BSTR|指定是否按顺序处理消息。|有效值为<br /><br /> -true<br />-false|默认值是 False。|  
|onFailure|VT_BSTR|指定适配器应如何响应错误。|有效值为<br /><br /> -   stopOnFailure<br />-   suspendNonResumable<br />-   suspendResumable|默认值为 suspendresumable。|  
|uri|VT_BSTR|指定接收位置所监视的队列的完整路径。|URI 发送端口或接收位置不能超过 256 个字符。|None|  
  
 下面的代码显示了使用设置的属性的字符串的格式：  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><queue>FORMATNAME:DIRECT=OS:.\PRIVATE$\QUEUE</queue><batchSize>20</batchSize><transactional>false</transactional><serialProcessing>false</serialProcessing><onFailure>suspendResumable</onFailure><uri>FORMATNAME:DIRECT=OS:.\PRIVATE$\QUEUE</uri></Config></AdapterConfig></CustomProps>  
```  
  
 下表列出了发送端口可以设置为 MSMQ 适配器的配置属性：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|队列|VT_BSTR|指定目标队列。|URI 发送端口或接收位置不能超过 256 个字符。|None|  
|maximumMessageSiz|VT_BSTR|为发送到指定的队列的消息中指定的最大消息大小以千字节 (KB)。|有效值为从 1 到 4294967295 之间如果将 segmentationSupport 和 transactional 设置为 true。 否则，有效值为从 1 到 4095。|默认值为 1024年。|  
|acknowledgeType|VT_BSTR|指定一个或多个确认类型。|有效值为.NET 成员**System.Messaging.AcknowledgeTypes**枚举。|默认值为 None。|  
|administrationQueue|VT_BSTR|指定 MSMQ 管理队列。|None|None|  
|timeOut|VT_BSTR|指定等待消息到达目标队列的最长时间。|此属性仅适用于事务性属性设置为 true。<br /><br /> 有效值为 1 到 10675199 时指定的天数将 timeOutUnits 的值。<br />-指定的小时数将 timeOutUnits 值时，有效值为 1 到 596523。<br />-指定分钟的 timeOutUnits 值时，有效值为 1 到 35791394。<br />有效值为 1 到 2147483647 时指定的秒将 timeOutUnits 的值。|None|  
|priority|VT_BSTR|指定消息优先级。|有效值为.NET 成员**System.Messaging.MessagePriority**枚举。|None|  
|可恢复|VT_BSTR|指定是否保证消息的可恢复性。|有效值为<br /><br /> -true<br />-false|默认值是 False。|  
|encryptionAlgorithm|VT_BSTR|指定要使用的加密算法。|有效值为.NET 成员**System.Messaging.EncryptionAlgorithm**枚举。|默认值为 None。|  
|useAuthentication|VT_BSTR|指定是否使用身份验证。|使用与证书属性结合使用此属性对消息进行验证。 使用 userName 和 password 属性来访问队列。|None|  
|证书 (certificate)|VT_BSTR|指定用于验证消息的证书。|输入 40 个字符的证书指纹。|None|  
|segmentationSupport|VT_BSTR|指定是否支持分段。|有效值为<br /><br /> -true<br />-false|默认值是 False。|  
|事务|VT_BSTR|指定是否支持发送消息的上下文的 Microsoft 分布式事务 (MSDTC)|有效值为<br /><br /> -true<br />-false|默认值是 False。|  
|useJournalQueue|VT_BSTR|指定是否处理消息时保存消息的副本。|有效值为<br /><br /> -true<br />-false|默认值是 False。|  
|useDeadLetterQueue|VT_BSTR|指定是否将消息发送到死信队列，如果故障发生。|有效值为<br /><br /> -true<br />-false|默认值为 true。|  
|ackTypeEnumsValue|VT_BSTR|指定与指定的 acknowledgeType 值相关联的值的按位 OR。|None|默认值为 0。|  
|timeOutUnits|VT_BSTR|指定要为 timeOut 属性指定的值与一起使用的单位。|有效值为<br /><br /> -天<br />小时数<br />-分钟<br />/ 字节秒|默认值为天。|  
|userName|VT_BSTR|指定远程队列的用户名。|默认值为空。|  
|password|VT_BSTR|指定要与指定远程队列的访问权限的用户名属性的值结合使用的密码。|导出绑定文件时，此值始终会被屏蔽。 此字段前，必须手动填充密码与绑定文件导入目标 BizTalk Server 配置。|默认值为空。|  
|bodyType|VT_BSTR|指定 MSMQ 中的消息正文类型。|有效值为.NET 成员**VarEnum**枚举。|默认值为 8209。|  
|uri|VT_BSTR|指定目标队列的完整路径。|URI 发送端口或接收位置不能超过 256 个字符。|None|  
  
 下面的代码显示了使用设置的属性的字符串的格式：  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><queue>FORMATNAME:DIRECT=OS:TESTSERVER\PRIVATE$\DESTQUEUE</queue><maximumMessageSize>1024</maximumMessageSize><acknowledgeType>None</acknowledgeType><administrationQueue>Direct=OS:TestServer\Private$\AdminQueue</administrationQueue><timeOut>4</timeOut><priority>Normal</priority><recoverable>false</recoverable><encryptionAlgorithm>None</encryptionAlgorithm><useAuthentication>false</useAuthentication><segmentationSupport>false</segmentationSupport><transactional>false</transactional><useJournalQueue>false</useJournalQueue><useDeadLetterQueue>true</useDeadLetterQueue><ackTypeEnumsValue>0</ackTypeEnumsValue><timeOutUnits>Days</timeOutUnits><userName>TestUser</userName><password>******</password><bodyType>8209</bodyType><uri>FORMATNAME:DIRECT=OS:TESTSERVER\PRIVATE$\DESTQUEUE</uri></Config></AdapterConfig>  
```  
  
> [!NOTE]
>  当指定为使用适配器框架生成的适配器的 TransportTypeData 配置数据，使用的名称/值对必须全部存储到\<AdapterConfig\>元素。 由于\<AdapterConfig\>元素指定 VT_BSTR (vt ="8") 数据类型则\<\>必须对数据中的字符进行转义。