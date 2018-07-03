---
title: BizTalk 设计时工具 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Adapter Framework
- schemas, tools
- BizTalk Orchestration Designer
- schemas, BTARN schemas
- BizTalk Editor
- BizTalk Mapper
- tools, schemas
- BTARN, schemas
- BizTalk Pipeline Designer
ms.assetid: a981e167-f178-4fef-be0e-02fa15feffc2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c50c96934a36af89db442e1f2fae49535d4645b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013342"
---
# <a name="biztalk-design-time-tools"></a>BizTalk 设计时工具
在 Microsoft 工作的开发人员[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]可以使用 BizTalk Server 中内置的设计时工具的集合。 这些工具已集成到 Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]。 有关详细信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]工具，请参阅 MicrosoftBizTalk Server 帮助。  
  
## <a name="biztalk-editor"></a>BizTalk 编辑器  
 使用 BizTalk 编辑器来管理[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]基于 RosettaNet 合作伙伴接口流程 (Pip) 的 XSD 架构。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 安装你的解决方案开发的以下架构：  
  
- 0A1_FailureNotificationPropertySchema.xsd  
  
- 0A1_MS_V02_00_FailureNotification.xsd  
  
- 0A1_V1_FailureNotificationMessageGuideline.xsd  
  
- 0C1_MS_R01_02_AsynchronousTestNotification.xsd  
  
- 0C2_MS_R01_02_AsynchronousTestConfirmation.xsd  
  
- 0C2_MS_R01_02_AsynchronousTestRequest.xsd  
  
- 0C3_MS_R01_02_SynchronousTestNotification.xsd  
  
- 0C4_MS_R01_02_SynchronousTestQuery.xsd  
  
- 0C4_MS_R01_02_SynchronousTestResponse.xsd  
  
- 2A12_MS_V01_03_ProductMasterNotification.xsd  
  
- 3A2PriceAndAvailabilityQueryMessageGuideline_v1_3.xsd  
  
- 3A2PriceAndAvailabilityResponseMessageGuideline_v1_3.xsd  
  
- 3A4_MS_V02_02_PurchaseOrderConfirmation.xsd  
  
- 3A4_MS_V02_02_PurchaseOrderRequest.xsd  
  
  这些架构包括网址\<*驱动器*\>: \Program Files\\Microsoft BizTalk\<版本\>Accelerator for rosettanet\sdk\schemas 中找到。  
  
  可以通过从 RosettaNet 网站下载 Pip 来添加多个架构[ http://go.microsoft.com/fwlink/?linkid=33859 ](http://go.microsoft.com/fwlink/?linkid=33859)。 有关详细信息，请参阅[并入新的合作伙伴接口流程](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md)。  
  
## <a name="biztalk-mapper"></a>BizTalk 映射器  
 你可以使用 BizTalk 映射器来创建并自定义用以定义数据转换的映射。 还可以使用 BizTalk 映射器来映射入站和出站 RosettaNet 消息类型的转换。  
  
## <a name="biztalk-orchestration-designer"></a>BizTalk 业务流程设计器  
 你可以使用 BizTalk 业务流程设计器来设计和实现业务流程。 还可以自定义 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 中提供的专用流程。 有关详细信息，请参阅[专用流程&#91;RN3&#93; ](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)并[自定义专用流程&#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/customizing-private-processes.md)。 你不能自定义公用流程，否则将破坏公用流程的 RosettaNet 兼容性。  
  
## <a name="biztalk-pipeline-designer"></a>BizTalk 管道设计器  
 你可以使用 BizTalk 管道设计器来创建和配置用以定义和链接消息处理步骤的管道。 管道将消息处理分为不同的阶段，并确定执行每类工作的顺序。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 包括接收 RosettaNet 实现框架 (RNIF) 管道和传输 RosettaNet 实现框架 (RNIF) 管道。 有关详细信息，请参阅[RNIF 管道](../../adapters-and-accelerators/accelerator-rosettanet/rnif-pipelines.md)。  
  
## <a name="biztalk-adapter-framework"></a>BizTalk 适配器框架  
 你可以使用带有终结点适配器的 BizTalk 适配器框架与合作伙伴及应用程序集成。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 和 BTARN 的工具和功能](../../adapters-and-accelerators/accelerator-rosettanet/tools-and-features-of-biztalk-server-and-btarn.md)   
 [管理和运行时工具](../../adapters-and-accelerators/accelerator-rosettanet/administration-and-run-time-tools.md)   
 [分析工具](../../adapters-and-accelerators/accelerator-rosettanet/analysis-tools1.md)   
 [并入新的合作伙伴接口流程](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md)