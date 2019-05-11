---
title: MQSeries 适配器配置属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, code sample
- receive locations, adapters
- MQSeries adapters, send ports
- MQSeries adapters, properties
- MQSeries adapters, receive location
- send ports, adapters
ms.assetid: 7517a8bf-aa65-4af9-aed0-7c74fb480328
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9840b7018bf334d93076aaa0a9e20d697ab355c5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65264546"
---
# <a name="mqseries-adapter-configuration-properties"></a>MQSeries 适配器配置属性
下表列出了可以设置为 MQSeries 适配器的配置属性接收位置：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|uri|VT_BSTR|指定接收位置所监视的位置的完整路径。|URI 发送端口或接收位置不能超过 256 个字符。|None|  
|queueDetails|VT_BSTR|指定包括服务器、 队列管理器和队列源 MQSeries 队列有关的信息。|-None|此属性前如果放置 mqs: / /，可以创建 uri 属性。|  
|transactionSupported|VT_BSTR|指定 MQSeries 适配器是启动 BizTalk Server 和 MQSeries 服务器之间的 Microsoft 分布式事务处理协调器 (DTC) 事务。|有效值为<br /><br /> -是<br />-   no|当设置为 no，则无法保证消息传递。<br /><br /> 默认值为是。|  
|suspendAsNonResumable|VT_BSTR|指定是否挂起的消息标记为可恢复或不。|有效值为<br /><br /> -是<br />-   no|默认值是没有。|  
|dataOffsetForHeaders|VT_BSTR|适配器使用 MQSeries 标头 （MQXQH、 MQIIH 和 MQCIH 结构） 中的值来填充 BizTalk Server 上下文属性中的相应值。 默认情况下，适配器从消息正文中删除这些 MQSeries 属性。|有效值为<br /><br /> -是<br />-   no|将此属性设置为否保留消息正文中的属性。<br /><br /> 默认值为是。|  
|pollingInterval|VT_BSTR|指定接收组件用于轮询 MQSeries 队列的时间间隔。|有效值为从 1 到 10000。|PollingInterval 结合使用硬编码等待间隔与适配器内置的 3 秒。 如果 pollingInterval 值小于三 （3） 秒，则等待间隔设置为 pollingInterval 的值。<br /><br /> 默认值为 3。|  
|pollingUnit|VT_BSTR|指定轮询间隔的时间单位。|有效值为<br /><br /> -小时<br />-分钟<br />-秒|默认值为秒。|  
|maximumBatchSize|VT_BSTR|指定一批消息的最大大小 (kb)。|有效值为从 1 到 10485760|默认值为 100。|  
|maximumNumberOfMessages|VT_BSTR|在批处理中指定的最大消息数。|有效值为从 1 到 100000|默认值为 100。|  
|threadCount|VT_BSTR|指定接收位置的每个使用的线程数。|有效值为从 1 到 64。|默认值为 2。|  
|fragmentationSize|VT_BSTR|在 MQSAgent 和适配器之间发送的消息的千字节 (KB) 中指定消息块的大小。|有效值为从 1 到 1048576。|默认值为 500。|  
|characterSet|VT_BSTR|指定的字符集以及 MQSeries 是否将消息发送到接收位置之前转换字符。|有效值为<br /><br /> -none。 不会转换。<br />-Ucs-2 和 utf-16。 将转换为这两个字符集。 MQSeries 不区分它们。<br />-   UTF-8. 将转换为 utf-8 字符集。|默认值为 none。|  
|errorThreshold|VT_BSTR|指定要记录的错误的最大数量。 适配器将继续工作，并且如果适配器恢复的话，它在事件日志中记录事件。|有效值为 1 到 1000年。|默认值为 10。|  
|分段|VT_BSTR|指定 MQSeries 是组装已分段的消息还是原样获取消息。|有效值为<br /><br /> -none<br />-完成|指定 none，以从 MQSeries 队列读取消息，但不进行分段。<br /><br /> 指定完成可使 MQSeries 传递到适配器前会组装已分段的消息。<br /><br /> 默认值为 none。|  
|排序|VT_BSTR|指定在从 MQSeries 队列接收时 MQSeries 是否保持消息的顺序。|有效值为<br /><br /> -   no<br />-   noStop<br />-   yesStop<br />-yessuspend|指定 no 将忽略消息顺序。<br /><br /> 指定 nostop 将忽略消息顺序并出现错误时禁用接收位置。<br /><br /> 指定 yesstop 将启用排序。 此选项结束事务并禁用接收位置，如果出现错误。<br /><br /> 指定 yessuspend 将启用排序。 错误时，此选项会将消息移至挂起队列。 此值不会保留顺序时出现错误，但允许接收位置继续接收消息。<br /><br /> 默认值是没有。|  
  
 下面的代码显示了使用设置的属性的字符串的格式：  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><uri>MQS://TESTMQServer/DQM1/RQ0</uri><queueDetails>TESTMQServer/DQM1/RQ0</queueDetails><transactionSupported>yes</transactionSupported><suspendAsNonResumable>no</suspendAsNonResumable><dataOffsetForHeaders>yes</dataOffsetForHeaders><pollingInterval>1</pollingInterval><pollingUnit>seconds</pollingUnit><maximumBatchSize>100</maximumBatchSize><maximumNumberOfMessages>100</maximumNumberOfMessages><threadCount>2</threadCount><fragmentationSize>500</fragmentationSize><characterSet>none</characterSet><errorThreshold>10</errorThreshold><segmentation>none</segmentation><ordered>no</ordered></Config></AdapterConfig></CustomProps>  
```  
  
 下表列出了发送端口可以设置为 MQSeries 适配器的配置属性：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|uri|VT_BSTR|指定要将数据发送到的位置的完整路径。|URI 发送端口或接收位置不能超过 256 个字符。|None|  
|queueDetails|VT_BSTR|指定包括服务器、 队列管理器和队列目标 MQSeries 队列有关的信息。|URI 发送端口或接收位置不能超过 256 个字符。|此属性前如果放置 mqs: / /，可以创建 uri 属性。|  
|transactionSupported|VT_BSTR|指定 MQSeries 适配器是启动 BizTalk Server 和 MQSeries 服务器之间的 Microsoft 分布式事务处理协调器 (DTC) 事务。|有效值为<br /><br /> -是<br />-   no|当设置为 no，则无法保证消息传递。<br /><br /> 默认值为是。|  
|dataConversion|VT_BSTR|指定是否将消息转换为 Windows MQSeries 服务器的 ANSI 代码页。|有效值为<br /><br /> -是<br />-   no|默认值是没有。|  
|segmentationAllowed|VT_BSTR|指定是否要使用 MQSeries 队列管理器分段功能，单个消息超出了 MQSeries 队列的最大消息长度。|有效的值是：<br /><br /> -是<br />-   no|默认值是没有。|  
|fragmentationSize|VT_BSTR|在适配器和 MQSAgent 之间发送的消息的千字节 (KB) 中指定消息块的大小。|有效值为从 1 到 1048576。|默认值为 500。|  
|排序|VT_BSTR|指定与将它们发送到 MQSeries 队列时 MQSeries 是否保持消息的顺序。|有效值为<br /><br /> -是<br />-   no|默认值是没有。|  
  
 下面的代码显示了使用设置的属性的字符串的格式：  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><uri>MQS://TESTMQServer/DQM1(QM1)/SQ0</uri><queueDetails>TESTMQServer/DQM1(QM1)/SQ0</queueDetails><transactionSupported>yes</transactionSupported><dataConversion>no</dataConversion><segmentationAllowed>no</segmentationAllowed><fragmentationSize>500</fragmentationSize><ordered>no</ordered></Config></AdapterConfig></CustomProps>  
```  
  
> [!NOTE]
>  当指定为使用适配器框架生成的适配器的 TransportTypeData 配置数据，使用的名称/值对必须全部存储到\<AdapterConfig\>元素。 由于\<AdapterConfig\>元素指定 VT_BSTR (vt ="8") 数据类型则\<\>必须对数据中的字符进行转义。