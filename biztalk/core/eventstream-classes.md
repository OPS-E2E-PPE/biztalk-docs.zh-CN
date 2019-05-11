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
ms.openlocfilehash: ba599c008c571af520dbc9b7919157371e32750f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388319"
---
# <a name="eventstream-classes"></a>EventStream 类
用于 BAM 的 EventStream Api 驻留在 Microsoft.BizTalk.BAM.EventObservation 命名空间。 若要针对 Api 进行编码，必须在开发计算机上安装以下 Dll:  
  
- Microsoft.BizTalk.BAM.EventObservation.dll  
  
- Microsoft.Biztalk.BAM.Xlangs.dll:业务流程事件流编码时需要此 DLL。  
  
- Microsoft.BizTalk.Pipeline.dll:将编码管道上下文用于消息传送事件流时需要此 DLL。  
  
  将 DLL 添加到项目引用和命名空间在代码中包含以下 using 语句：  
  
```  
using Microsoft.BizTalk.Bam.EventObservation;  
```  
  
 **类**  
  
|“属性”|Description|  
|----------|-----------------|  
|DirectEventStream (DES)|同步，无延迟|  
|BufferedEventStream (BES)|异步、 高吞吐量，一定程度的延迟|  
|OrchestrationEventStream (OES)|异步，参与 BizTalk 业务流程事务|  
|IPipelineContext 接口|异步，参与 BizTalk Server 管道事务。 用于创建消息传送事件流 (MES)。|  
  
 应选择 API 基于以下因素：  
  
- 如果您关注的问题的延迟，请选择的 DES，其中数据以同步方式保存到 BAM 主导入数据库。 除 DES 之外，所有其他 EventStream 类是异步的具有一些滞后时间。 数据首先将暂留到 MessageBox，并随后由 TDDS 将数据移到 BAMPrimaryImport 数据库的处理。  
  
- 如果您关注的问题的性能和事件插入的吞吐量，请选择异步 API。  
  
- 如果你正在编写不具有的计算机运行的应用程序安装 BizTalk Server，请使用 DES 和 BES。 （换句话说，这些 Api 可在非 BizTalk 应用程序。）  
  
- 如果你的应用程序在其安装 BizTalk Server 的计算机上运行，使用 MES 和 OES。 （这些都提供 Api 只能从 BizTalk 应用程序。）  
  
  -   如果您希望 BAM 事件持久化与管道事务保持同步，则应使用消息传送事件 Stream。  
  
  -   OES 等效于 MES，但对 BizTalk 业务流程。  
  
  有在其中你可能想要混合使用 EventStream 类型的方案。 例如，在管道处理中，你可能想要捕获特定数据在 BAM 中的，而不考虑是否管道正在回滚其事务。 具体而言，您可能希望捕获有关失败的消息数的数据或在管道处理过程中已有多少重试。 若要捕获的数据在此情况下应使用 BES。  
  
  所有异步 EventStreams （BES、 MES 和 OES） 首先在 BizTalk MessageBox 数据库中保留数据。 跟踪数据解码服务 (TDDS) 会定期处理这些数据，并将其持久化到 BAM 主导入数据库。  
  
> [!NOTE]
>  若要确保 EventStream 调用不执行操作的 BizTalk 应用程序中产生瓶颈，我们建议使用异步 Api。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [OrchestrationEventStream](../core/orchestrationeventstream.md)  
  
-   [消息传送事件流](../core/messaging-event-streams.md)