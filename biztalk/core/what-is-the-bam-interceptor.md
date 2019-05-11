---
title: 什么是 BAM 侦听器？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM Interceptor object
- BAM, collecting data
- BAM, Interceptor object
- data, collecting [BAM]
ms.assetid: e0213c4e-e2f4-4bb0-bd27-e5810f7e39d9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2dbd9b3a2bff2d6a858de372de5e06b1ff6cbbde
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243061"
---
# <a name="what-is-the-bam-interceptor"></a>什么是 BAM 侦听器？
## <a name="overview"></a>概述 

BAM 侦听器是一个对象，它可以装备应用程序以捕获感兴趣的数据。 下图显示了 BAM 侦听器和及其与其他 BAM 组件的交互的角色：  
  
 ![](../core/media/bam-config-api.gif "bam_config_api")  
BAM 侦听器  
  
 在应用程序可能有感兴趣的数据的位置的每个步骤中，调用侦听器 OnStep、 步骤中，提供标识符和提供某些数据或使用应用程序中的任意对象。  
  
 必须实现一个回调函数，当回调发生时，回调过程获取当前步骤 ID 和数据对象。 从根本上讲，BAM 侦听器只需将传播到回调的数据对象。 提取数据的实际逻辑驻留在你的应用程序中。 例如，如果数据采用 XML 消息形式，回调将使用的 Xpath。 有关 Xpath 的详细信息，请参阅[在消息赋值中使用 Xpath](../core/using-xpaths-in-message-assignments.md)。  
  
 BAM 侦听器决定要在每一步，基于可以以编程方式创建的配置数据。 BAM 侦听器使用获得的数据来调用 DirectEventStream 或 BufferedEventStream 需要作为自变量的每次传递给 OnStep 的。  
  
 为每个步骤调用侦听器不占用大量资源的操作。 如果您调用并注册任何关于此步骤的信息，则侦听器立即返回。 这意味着有没有磁盘操作，没有事务，甚至没有内存分配，因此性能几乎没有影响。 同时，您将有机会为 BAM 提取的任何数据，如有必要。 涉及数据提取和数据的可用性的步骤对性能的影响取决于您的实现的`IBAMDataExtractor Interface`。  
  
 下面的代码示例演示使用侦听器配置期间和运行时。  
  
## <a name="configuration-time"></a>配置时间  
 下面的代码演示如何配置侦听器，以便该应用程序的 recvPO 步骤处停止，并请求客户名称和客户 SSN:  
  
```  
ActivityInterceptorConfiguration cfg= new ActivityInterceptorConfiguration ("PurchaseOrder");  
...  
cfg.RegisterDataExtraction("CustomerName",recvPO,XpathName);  
cfg.RegisterDataExtraction("CustomerSSN",recvPO,XpathSSN);  
...  
BAMInterceptor interceptor=new BAMInterceptor();  
cfg.UpdateInterceptor(interceptor);  
...  
// The interceptor instance is ready.  
```  
  
 创建某个侦听器实例后，可以将其存储在运行时的更高版本使用。  
  
 您可以保存代表不同数据首选项和 BAM 里程碑的不同预创建的侦听器。 为了获得最佳性能，序列化侦听器实例使用 BinaryFormatter 类。  
  
## <a name="run-time"></a>运行的时  
 使用以下代码在生产环境中运行时使用的侦听器：  
  
```  
// Deserialize the Interceptor that was prepared before  
...  
es=new DirectEventStream(...)  
...  
Interceptor.OnStep(recvPO, data1, es, callback)  
...  
Interceptor.OnStep(approvePO, data2, es, callback)  
...  
```  
  
 其中：  
  
- *recvPO*并*approvePO*是用于标识你的应用程序中的步骤的任意对象。  
  
- *data1*并*data2*是任意对象已存在的可能包含感兴趣的数据 – 例如采购订单的 XML 文档。  
  
- *es*是 DirectEventStream 或 BufferedEvent 流，具体取决于你的性能要求。  
  
- *回调*是的实现`IBAMDataExtractor Interface`。  
  
  SDK 示例中， [BAM API （BizTalk Server 示例）](../core/bam-api-biztalk-server-sample.md)，演示了如何使用侦听器，其中包含这两种配置工具和示例运行时应用程序。  
  
  BizTalk 业务流程引擎允许进行侦听，这样就能够更改在运行时使用跟踪配置文件编辑器为 BAM 收集哪些数据。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何确定和设置活动的事件写入者角色](../core/how-to-determine-and-set-event-writer-roles-for-activities.md)  
  
## <a name="see-also"></a>请参阅  
 [BAM API（BizTalk Server 示例）](../core/bam-api-biztalk-server-sample.md)