---
title: "BAM 侦听器是什么？ | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM Interceptor object
- BAM, collecting data
- BAM, Interceptor object
- data, collecting [BAM]
ms.assetid: e0213c4e-e2f4-4bb0-bd27-e5810f7e39d9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9400e80a2f8e8acfdeb12e3d6e61a046151d1e7e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-bam-interceptor"></a>BAM 侦听器是什么？
## <a name="overview"></a>概述 

BAM 侦听器是一种对象，使用它可以装备应用程序来捕获目标数据。 以下关系图显示 BAM 侦听器的角色以及它与其他 BAM 组件的交互过程：  
  
 ![](../core/media/bam-config-api.gif "bam_config_api")  
BAM 拦截器  
  
 在可能具有目标数据应用程序的每一步中，调用侦听器 OnStep，为每一步提供标识符，并提供应用程序中正使用的某个数据对象或任意对象。  
  
 然后必须实现一个回调函数，当回调发生时，回调过程获取当前的步骤 ID 和数据对象。 实际上，BAM 侦听器只是将数据对象传播到回调中。 而提取数据的实际逻辑驻留在应用程序中。 例如，如果数据采用 XML 消息形式，则回调将使用 XPath。 有关 Xpath 的详细信息，请参阅[消息分配中使用 Xpath](../core/using-xpaths-in-message-assignments.md)。  
  
 BAM 侦听器基于可编程创建的配置在每一步中判断是否有需要的数据。 然后，BAM 侦听器使用获得的数据来调用需要使用的、每次作为参数传递给 OnStep 的 DirectEventStream 或 BufferedEventStream。  
  
 为每一步调用侦听器不会占用大量资源。 如果为此步骤调用侦听器但没有注册任何内容，则侦听器立即返回。 这意味着没有磁盘操作，没有事务，甚至没有内存分配；因此，对性能几乎没有影响。 同时，还有机会在必要时为 BAM 提取数据。 对数据提取和数据的可用性所涉及的步骤的性能影响将取决于你的实现`IBAMDataExtractor Interface`。  
  
 以下代码示例演示在配置和运行时期间如何使用侦听器。  
  
## <a name="configuration-time"></a>配置时  
 以下代码显示如何配置侦听器，以便在应用程序的 recvPO 步骤处停止，然后要求输入 客户名称和客户 SSN：  
  
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
  
 创建某个侦听器实例后，可以将其存储起来，以便将来在运行时使用。  
  
 您可以保存代表不同数据首选项和 BAM 里程碑的、预先创建的不同侦听器。 为了获得最佳性能，请使用 BinaryFormatter 类序列化侦听器实例。  
  
## <a name="run-time"></a>运行的时  
 在生产环境中使用以下代码，以便在运行时使用侦听器：  
  
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
  
-   *recvPO*和*approvePO*是用于标识你的应用程序中的步骤的任意对象。  
  
-   *data1*和*data2*是你已在该点，并可能包含有趣的数据 – 例如采购订单的 XML 文档的任意对象。  
  
-   *es*是 DirectEventStream 或 BufferedEvent 流，具体取决于您的性能要求。  
  
-   *回调*是你实现`IBAMDataExtractor Interface`。  
  
 SDK 示例中， [BAM API （BizTalk Server 示例）](../core/bam-api-biztalk-server-sample.md)，演示如何使用侦听器，其中包含两个配置工具和示例运行时应用程序。  
  
 BizTalk 业务流程引擎允许进行侦听，这样就能够在运行时使用跟踪配置文件编辑器更改为 BAM 收集的数据。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何确定并设置为活动的事件写入者角色](../core/how-to-determine-and-set-event-writer-roles-for-activities.md)  
  
## <a name="see-also"></a>另请参阅  
 [BAM API （BizTalk Server 示例）](../core/bam-api-biztalk-server-sample.md)