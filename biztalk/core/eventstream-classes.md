---
title: EventStream 类 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3e7a6b3-69cc-4312-9074-acccd1175d37
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c4cb000d479a51d2215bda6349adfa6df39338a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973558"
---
# <a name="eventstream-classes"></a>EventStream 类
用于 BAM 的 EventStream API 驻留在 Microsoft.BizTalk.BAM.EventObservation 命名空间中。 要针对该 API 进行编码，必须在用于开发的计算机上安装以下 DLL：  
  
- Microsoft.BizTalk.BAM.EventObservation.dll  
  
- Microsoft.biztalk.bam.xlangs.dll 添加： 业务流程事件流编码时，此 DLL 是必需。  
  
- Microsoft.BizTalk.Pipeline.dll： 使用编码管道上下文用于消息传送事件流时需要此 DLL。  
  
  将该 DLL 添加到您的项目引用，并使用下面的 using 语句在编码中包括命名空间：  
  
```  
using Microsoft.BizTalk.Bam.EventObservation;  
```  
  
 **类**  
  
|“属性”|Description|  
|----------|-----------------|  
|DirectEventStream (DES)|同步，无延迟|  
|BufferedEventStream (BES)|异步，高吞吐量，有一定的延迟|  
|OrchestrationEventStream (OES)|异步，参与 BizTalk 业务流程事务|  
|IPipelineContext 接口|异步，参与 BizTalk Server 管道事务。 用于创建消息传送事件流 (MES)。|  
  
 您应该基于以下因素选择 API：  
  
- 如果关心延迟问题，请选择 DES，可使数据同步地保留到 BAM 主导入数据库。 除 DES 之外，所有其他 EventStream 类是异步的，并具有一些滞后时间。 数据首先将暂留到 MessageBox，随后由 TDDS 处理，从而可以将数据移动到 BAMPrimaryImport 数据库中。  
  
- 如果关心事件插入的性能和吞吐量，请选择异步 API。  
  
- 如果您要编写的应用程序运行在没有安装 BizTalk Server 的计算机上，请使用 DES 和 BES。 （也就是说，这些 API 可以在非 BizTalk 应用程序中使用。）  
  
- 如果您的应用程序运行在安装了 BizTalk Server 的计算机上，请使用 MES 和 OES。 （这些 API 只在 BizTalk 应用程序中可用。）  
  
  -   如果您希望 BAM 事件持久化与管道事务保持同步，应使用消息传送事件流。  
  
  -   OES 等效于 MES，但对 BizTalk 业务流程除外。  
  
  在有些情况下，您可能需要混合使用 EventStream 类型。 例如，在管道处理中，可能需要在 BAM 中捕获特定数据，而不考虑管道是否回滚其事务。 特别是，您可能需要捕获有关管道处理期间多少消息失败或有多少重试的数据。 若要在这种情况下捕获数据，应使用 BES。  
  
  所有异步 EventStreams（BES、MES 和 OES）都首先在 BizTalk MessageBox 数据库中保留数据。 跟踪数据解码服务 (TDDS) 会定期处理这些数据，并将其持久化到 BAM 主导入数据库。  
  
> [!NOTE]
>  若要确保 EventStream 调用不会在 BizTalk 应用程序中产生瓶颈，建议您使用异步 API。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [OrchestrationEventStream](../core/orchestrationeventstream.md)  
  
-   [消息传送事件流](../core/messaging-event-streams.md)