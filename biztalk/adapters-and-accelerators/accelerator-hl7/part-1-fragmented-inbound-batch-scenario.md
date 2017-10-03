---
title: "第 1 部分： 零碎的入站的批处理方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching, fragmenting messages
- batching tutorial, fragmenting messages
- fragmenting messages
ms.assetid: 8adf2c17-5f66-408d-b30b-51b22d8e71fa
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8891bd09c803c77e1878b304f5db5b71a26ab9d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="part-1-fragmented-inbound-batch-scenario"></a>第 1 部分： 零碎的入站的批处理方案
在本教程的此部分中，你将接收 HL7 编码批、 片段转换为单个消息，和各条消息发送到目标。 下图显示在此过程中的流。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-fragmented-inbound-batching-scenario.gif "hl7_fragmented_inbound_batching_scenario")  
  
 此方案包括以下工作流：  
  
1.  工作流一开始时的业务线应用程序发送消息批为[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]集成引擎使用的最小较低层协议 (MLLP) 协议。 批处理包含两个版本的 ADT ^ A03 消息。 源应用程序所属 Tutorial_BatchSource 方。  
  
2.  接口引擎接收上 MLLP 批处理接收端口，并验证消息批处理。 （的验证级别取决于为源方 BTAHL7 配置资源管理器中选择的设置。）  
  
3.  根据 BTAHL7 配置资源管理器，使批处理碎片中的设置，接口引擎将分析批处理为两个单独 ADT ^ A03 消息。 它会验证各条消息，根据为 BTAHL7 配置资源管理器中的源方选择设置。  
  
4.  接口引擎生成基于 BTAHL7 配置资源管理器中的确认定义设置的每个消息的确认。 在本教程中，将选择原始确认模式，因此接口引擎在验证的消息标头和正文之后生成每条消息将单个应用程序接受确认。 引擎生成基于 ACK_024_GLO_DEF 架构该确认，该确认 MSA2 字段中输入"AA"，在 MSH3，输入目标方并在 MSH5 输入源方。  
  
5.  接口引擎将放 MLLP 包装每个确认并路由到源确认方通过 MLLP 发送适配器将设置为处理确认。  
  
6.  接口引擎将放 MLLP 包装每个消息，并单独到 MLLP 每条消息发送端口设置来处理非确认消息的路由。  
  
7.  BTAHL7 将通过另一个 MLLP 发送端口的每条消息发送到其 MSH5 字段中指定的目标。  
  
8.  目标方将发送到 BTAHL7 应用程序接受它接收每条消息的确认。  
  
9. 接口引擎接收每个确认。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 1： 添加标头和确认架构](../../adapters-and-accelerators/accelerator-hl7/step-1-add-header-and-acknowledgment-schemas.md)  
  
-   [步骤 2： 添加常见 v2.3.1 架构](../../adapters-and-accelerators/accelerator-hl7/step-2-add-common-schemas-for-v2-3-1.md)  
  
-   [步骤 3： 添加触发器事件 （消息） 架构](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md)  
  
-   [步骤 4： 创建用于接受批处理消息接收端口](../../adapters-and-accelerators/accelerator-hl7/step-4-create-a-receive-port-for-accepting-the-batch-message.md)  
  
-   [步骤 5： 创建发送端口将消息传递](../../adapters-and-accelerators/accelerator-hl7/step-5-create-a-send-port-to-deliver-messages.md)  
  
-   [步骤 6： 创建发送端口，以提供确认](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-acknowledgments.md)  
  
-   [步骤 7： 创建并配置源方](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md)  
  
-   [步骤 8： 重新启动 BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-8-restart-biztalk-server.md)  
  
-   [步骤 9： 验证零碎的入站的批处理方案](../../adapters-and-accelerators/accelerator-hl7/step-9-verify-the-fragmented-inbound-batch-scenario.md)