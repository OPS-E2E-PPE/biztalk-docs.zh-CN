---
title: 第 3 部分： Create-batch 方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, creating
- creating, batching
ms.assetid: 02247186-5b21-4738-9110-f0ca0304f0fd
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e487bfbe29ee2a34f2e50affa502d7f20592fe0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975950"
---
# <a name="part-3-create-batch-scenario"></a>第 3 部分： Create-batch 方案
在此方案的一部分，您收到两条传入消息、 将它们合并到批处理消息，和向目标发送一批。 BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 返回包含两个确认从目标到源的消息生成确认批处理。 下图显示了本教程的此部分的处理流程。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-create-batch-scenario.gif "hl7_create_batch_scenario")  
  
 **消息在创建 Batch 方案中的流动**  
  
 此方案包括以下工作流：  
  
- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 捕获与 MessageBox 数据库中的批次定义的所有消息。 输入此定义中的**批定义**选项卡[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。 在本教程中，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将捕获和批处理所有消息和 ADT 架构一起发送到 Tutorial_BatchDest ^ A03，和所有确认发送到由于 ADT Tutorial_BatchSource ^ A03 消息。  
  
- 计划的批发送时间时，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]发送批处理控制消息触发出站批处理事务。 在定义的计划**批处理计划**选项卡[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。 此外可以通过单击来触发进程**立即发送**同一选项卡。  
  
- 批处理业务流程窗体从 MessageBox 数据库中捕获的消息的消息批处理。 业务流程也会将文件标头和尾部和批处理标头和尾部中的批处理。 此业务流程是一个本机[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]业务流程添加[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]到集的 BizTalk 业务流程，因此它列在 BizTalk 浏览器或 BizTalk Server 管理控制台中的业务流程节点下的安装程序。  
  
- 如果确认都定义为源参与方 （因为在这种情况下，它们是用于 Tutorial_BatchSource），BizTalk 对确认进行批处理，并将它们在批处理中返回 （到 \Tutorial_BatchACKDrop 文件夹中）。 在本教程中，批处理的确认一小段延迟后发送。  
  
- 业务流程将消息路由到发送端口 (Tutorial_BatchDest)，可将批处理的消息发送到目标 （在此情况下，您的硬盘上的 \Tutorial_BatchMsgDrop 文件夹）。 在本教程中，在一小时后发送批处理的消息。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 1：配置和启用 BatchControlPort 接收端口](../../adapters-and-accelerators/accelerator-hl7/step-1-configure-and-enable-the-batchcontrolport-receive-port.md)  
  
-   [步骤 2：启用批处理业务流程](../../adapters-and-accelerators/accelerator-hl7/step-2-enable-the-batch-orchestration.md)  
  
-   [步骤 3：创建和配置目标参与方](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-configure-a-destination-party.md)  
  
-   [步骤 4：为 Create-Batch 方案配置源参与方](../../adapters-and-accelerators/accelerator-hl7/step-4-configure-the-source-party-for-the-create-batch-scenario.md)  
  
-   [步骤 5：为消息批处理创建发送端口](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-send-port-for-the-message-batch.md)  
  
-   [步骤 6：为确认批处理创建发送端口](../../adapters-and-accelerators/accelerator-hl7/step-6-create-the-send-port-for-the-acknowledgment-batch.md)  
  
-   [步骤 7：启动业务流程并重启 BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-7-start-the-orchestration-and-restart-biztalk-server.md)  
  
-   [步骤 8：测试 Create-Batch 方案](../../adapters-and-accelerators/accelerator-hl7/step-8-test-the-create-batch-scenario.md)