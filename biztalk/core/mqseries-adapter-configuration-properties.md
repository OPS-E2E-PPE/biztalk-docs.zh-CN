---
title: "MQSeries 适配器配置属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, code sample
- receive locations, adapters
- MQSeries adapters, send ports
- MQSeries adapters, properties
- MQSeries adapters, receive location
- send ports, adapters
ms.assetid: 7517a8bf-aa65-4af9-aed0-7c74fb480328
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 332d8027a12e2d58a8b177d7b0c87eeec8996217
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="mqseries-adapter-configuration-properties"></a>MQSeries 适配器配置属性
下表列出了可为 MQSeries 适配器接收位置设置的配置属性：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|URI|VT_BSTR|指定到接收位置监视的位置的完整路径。|发送端口或接收位置的 URI 不能超过 256 个字符。|无|  
|queueDetails|VT_BSTR|指定与源 MQSeries 队列有关的信息，包括服务器、队列管理器和队列。|-无|此属性前如果放置 MQS://，可以创建 uri 属性。|  
|transactionSupported|VT_BSTR|指定 MQSeries 适配器是否在 BizTalk Server 和 MQSeries 服务器之间启动 Microsoft 分布式事务处理协调器 (DTC) 事务。|有效值为<br /><br /> -是<br />-没有|如果设置为“no”，则无法确保消息的送达。<br /><br /> 默认值为 yes。|  
|suspendAsNonResumable|VT_BSTR|指定是否将挂起的消息标记为可恢复。|有效值为<br /><br /> -是<br />-没有|默认值为“否”。|  
|dataOffsetForHeaders|VT_BSTR|适配器使用 MQSeries 标头（MQXQH、MQIIH 和 MQCIH 结构）中的值来填充 BizTalk Server 上下文属性中的相应值。 默认情况下，适配器将从消息正文中删除这些 MQSeries 属性。|有效值为<br /><br /> -是<br />-没有|将此属性设置为否以保留消息正文中的属性。<br /><br /> 默认值为 yes。|  
|pollingInterval|VT_BSTR|指定接收组件轮询 MQSeries 队列所采用的时间间隔。|有效值为从 1 到 10000。|pollingInterval 与适配器内置的 3 秒硬编码等待间隔结合使用。 如果 pollingInterval 值小于三 (3) 秒，则等待间隔将设置为 pollingInterval 的值。<br /><br /> 默认值为 3。|  
|pollingUnit|VT_BSTR|指定用于轮询间隔的时间单位。|有效值为<br /><br /> -小时数<br />-分钟<br />-秒|默认值是秒。|  
|maximumBatchSize|VT_BSTR|以千字节为单位指定消息批的最大大小 (KB)。|有效的值都是从 1 到 10485760|默认值为 100。|  
|maximumNumberOfMessages|VT_BSTR|指定一批中的最大消息数。|有效的值都是从 1 到 100000|默认值为 100。|  
|threadCount|VT_BSTR|指定每个接收位置使用的线程数。|有效值为从 1 到 64。|默认值为 2。|  
|fragmentationSize|VT_BSTR|指定在 MQSAgent 和适配器之间发送消息时消息块的大小（单位是千字节，即 KB）。|有效值为从 1 到 1048576。|默认值为 500。|  
|characterSet|VT_BSTR|指定字符集以及 MQSeries 向接收位置发送消息前是否转换字符。|有效值为<br /><br /> -none。 不会转换。<br />-Ucs-2 和 utf-16。 转换为这两个字符集。 MQSeries 不区分这两个字符集。<br />-UTF-8。 转换为 UTF-8 字符集。|默认值为 none。|  
|errorThreshold|VT_BSTR|指定可记录的最大错误数。 该适配器将继续工作，并且如果适配器恢复的话，还会在事件日志中记录事件。|有效值为 1 到 1000年。|默认值为 10。|  
|分段|VT_BSTR|指定 MQSeries 是组装已分段的消息还是按原样获取消息。|有效值为<br /><br /> -none<br />-完成|指定“无”将从 MQSeries 队列读取消息但不进行分段。<br /><br /> 指定“完整”，则 MQSeries 在将消息传递到适配器前会组装已分段的消息。<br /><br /> 默认值为 none。|  
|已排序|VT_BSTR|指定在从 MQSeries 队列接收消息时 MQSeries 是否保持消息的顺序。|有效值为<br /><br /> -没有<br />-noStop<br />-yesStop<br />-yesSuspend|指定“no”将忽略消息顺序。<br /><br /> 指定“noStop”将忽略消息顺序并在出现错误时禁用接收位置。<br /><br /> 指定“yesStop”将启用排序。 选择此选项将在出现错误时结束事务并禁用接收位置。<br /><br /> 指定“yesSuspend”将启用排序。 选择此选项会在出现错误时将消息移至挂起队列。 选择此值在出现错误时将不保留顺序，但允许接收位置继续接收消息。<br /><br /> 默认值为“否”。|  
  
 以下代码显示用于设置这些属性的字符串的格式：  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><uri>MQS://TESTMQServer/DQM1/RQ0</uri><queueDetails>TESTMQServer/DQM1/RQ0</queueDetails><transactionSupported>yes</transactionSupported><suspendAsNonResumable>no</suspendAsNonResumable><dataOffsetForHeaders>yes</dataOffsetForHeaders><pollingInterval>1</pollingInterval><pollingUnit>seconds</pollingUnit><maximumBatchSize>100</maximumBatchSize><maximumNumberOfMessages>100</maximumNumberOfMessages><threadCount>2</threadCount><fragmentationSize>500</fragmentationSize><characterSet>none</characterSet><errorThreshold>10</errorThreshold><segmentation>none</segmentation><ordered>no</ordered></Config></AdapterConfig></CustomProps>  
```  
  
 下表列出了可为 MQSeries 适配器发送端口设置的配置属性：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|URI|VT_BSTR|指定到数据发送目标位置的完整路径。|发送端口或接收位置的 URI 不能超过 256 个字符。|无|  
|queueDetails|VT_BSTR|指定与目标 MQSeries 队列有关的信息，包括服务器、队列管理器和队列。|发送端口或接收位置的 URI 不能超过 256 个字符。|此属性前如果放置 MQS://，可以创建 uri 属性。|  
|transactionSupported|VT_BSTR|指定 MQSeries 适配器是否在 BizTalk Server 和 MQSeries 服务器之间启动 Microsoft 分布式事务处理协调器 (DTC) 事务。|有效值为<br /><br /> -是<br />-没有|如果设置为“no”，则无法确保消息的送达。<br /><br /> 默认值为 yes。|  
|dataConversion|VT_BSTR|指定是否将消息转换为 MQSeries Server for Windows 服务器的 ANSI 代码页。|有效值为<br /><br /> -是<br />-没有|默认值为“否”。|  
|segmentationAllowed|VT_BSTR|指定在单个消息超出了 MQSeries 队列的最大消息长度的情况下，是否使用 MQSeries 队列管理器分段功能。|有效的值是：<br /><br /> -是<br />-没有|默认值为“否”。|  
|fragmentationSize|VT_BSTR|指定在适配器和 MQSAgent 之间发送消息时消息块的大小（单位是千字节，即 KB）。|有效值为从 1 到 1048576。|默认值为 500。|  
|已排序|VT_BSTR|指定在向 MQSeries 队列发送消息时 MQSeries 是否保持消息的顺序。|有效值为<br /><br /> -是<br />-没有|默认值为“否”。|  
  
 以下代码显示用于设置这些属性的字符串的格式：  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><uri>MQS://TESTMQServer/DQM1(QM1)/SQ0</uri><queueDetails>TESTMQServer/DQM1(QM1)/SQ0</queueDetails><transactionSupported>yes</transactionSupported><dataConversion>no</dataConversion><segmentationAllowed>no</segmentationAllowed><fragmentationSize>500</fragmentationSize><ordered>no</ordered></Config></AdapterConfig></CustomProps>  
```  
  
> [!NOTE]
>  在指定的适配器，使用适配器框架构建的 TransportTypeData 配置数据时，使用的名称/值对必须全部存储到\<AdapterConfig > 元素。 由于\<AdapterConfig > 元素指定 VT_BSTR (vt ="8") 数据类型则\<> 数据中的字符必须进行转义。