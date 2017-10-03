---
title: "第 3 部分： 创建批处理方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching, creating
- creating, batching
ms.assetid: 02247186-5b21-4738-9110-f0ca0304f0fd
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0949d45fc70ead14338e30b554e0cb4b9694b5d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="part-3-create-batch-scenario"></a>第 3 部分： 创建批处理方案
在此方案的一部分，你将接收两个传入消息、 将它们合并到消息的批处理，和批处理发送到目标。 BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 返回包含生成从目标到源的消息的两个确认的确认批次。 下图显示在本教程的此部分的处理流程。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-create-batch-scenario.gif "hl7_create_batch_scenario")  
  
 **如何将消息流中创建批处理方案**  
  
 此方案包括以下工作流：  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]捕获符合 MessageBox 数据库中的批处理定义的所有消息。 输入在此定义**批定义**选项卡[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。 在本教程中，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将捕获和批处理所有消息的架构的 ADT 与发送到 Tutorial_BatchDest ^ A03，和所有确认发送到由于 ADT Tutorial_BatchSource ^ A03 消息。  
  
-   当计划的批发送时间发生时，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]发送批处理控件消息触发的出站批处理事务。 在定义计划**批处理计划**选项卡[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。 你也可以通过单击来触发进程**立即发送**同一选项卡上。  
  
-   批处理业务流程窗体消息批处理外困在 MessageBox 数据库的消息。 业务流程也会将在文件标头和尾部，以及批处理标头和预告片批处理。 此业务流程是一个本机[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]业务流程通过添加[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]到您的 BizTalk 业务流程，以便该设备将在 BizTalk 资源管理器或 BizTalk Server 管理控制台中的业务流程节点集的安装程序。  
  
-   如果确认为源方 （如在这种情况下，它们是为 Tutorial_BatchSource） 定义，BizTalk 批处理确认并将它们返回批处理中 （到 \Tutorial_BatchACKDrop 文件夹中）。 在本教程中，批处理的确认会发送一小段延迟后。  
  
-   业务流程将消息路由到发送端口 (Tutorial_BatchDest)，它将批处理的消息发送到目标 （在此情况下，在硬盘上的 \Tutorial_BatchMsgDrop 文件夹）。 在本教程中，批处理的消息会发送一小时之后。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 1： 配置和启用 BatchControlPort 接收端口](../../adapters-and-accelerators/accelerator-hl7/step-1-configure-and-enable-the-batchcontrolport-receive-port.md)  
  
-   [步骤 2： 启用批处理业务流程](../../adapters-and-accelerators/accelerator-hl7/step-2-enable-the-batch-orchestration.md)  
  
-   [步骤 3： 创建并配置目标方](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-configure-a-destination-party.md)  
  
-   [步骤 4： 配置创建批处理方案的源方](../../adapters-and-accelerators/accelerator-hl7/step-4-configure-the-source-party-for-the-create-batch-scenario.md)  
  
-   [步骤 5： 为消息批创建发送端口](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-send-port-for-the-message-batch.md)  
  
-   [步骤 6： 为确认批处理创建发送端口](../../adapters-and-accelerators/accelerator-hl7/step-6-create-the-send-port-for-the-acknowledgment-batch.md)  
  
-   [步骤 7： 启动业务流程和重新启动 BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-7-start-the-orchestration-and-restart-biztalk-server.md)  
  
-   [步骤 8： 测试创建批处理方案](../../adapters-and-accelerators/accelerator-hl7/step-8-test-the-create-batch-scenario.md)