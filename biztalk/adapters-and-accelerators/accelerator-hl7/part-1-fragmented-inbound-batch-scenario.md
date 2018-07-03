---
title: 第 1 部分： 零碎的入站的批处理方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, fragmenting messages
- batching tutorial, fragmenting messages
- fragmenting messages
ms.assetid: 8adf2c17-5f66-408d-b30b-51b22d8e71fa
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c5cf6f38daca7b1773798e4bc8ed2e40ad143bd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970502"
---
# <a name="part-1-fragmented-inbound-batch-scenario"></a>第 1 部分： 零碎的入站的批处理方案
在本教程的此部分中，接收 HL7 编码的批、 为单个消息片段和各个消息发送到目标。 下图显示了此过程的流。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-fragmented-inbound-batching-scenario.gif "hl7_fragmented_inbound_batching_scenario")  
  
 此方案包括以下工作流：  
  
1. 在工作流开始时的业务线应用程序向 Microsoft 发送一个消息批次[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]集成引擎使用最少的较低层协议 (MLLP) 协议。 批处理包含两个版本的 ADT ^ A03 消息。 源应用程序属于 Tutorial_BatchSource 参与方。  
  
2. 接口引擎接收批处理上 MLLP 接收端口，并验证消息批。 （的验证级别取决于选择 BTAHL7 配置资源管理器中的源参与方设置。）  
  
3. 基于 BTAHL7 配置资源管理器，使批处理碎片中的设置，接口引擎将分析批处理为两个单独 ADT ^ A03 消息。 它会验证各条消息，再次基于 BTAHL7 配置资源管理器中的源参与方选择的设置。  
  
4. 接口引擎生成基于 BTAHL7 配置资源管理器中的确认定义设置的每个消息的确认。 在本教程中，您将选择原始确认模式，因此接口引擎在验证消息标头和正文后生成的每个消息的单个应用程序接受确认。 引擎生成确认基于 ACK_024_GLO_DEF 架构、 在确认 MSA2 字段中输入"AA"、 在 MSH3，输入目标参与方和 MSH5 中输入的源参与方。  
  
5. 接口引擎会将 MLLP 包装每个确认，并路由到源确认的参与方通过 MLLP 发送适配器将设置为处理确认。  
  
6. 接口引擎会将 MLLP 包装每个消息，并分别为 MLLP 的每条消息的发送端口设置来处理非确认消息的路由。  
  
7. BTAHL7 将通过另一处的 MLLP 发送端口的每条消息发送到其 MSH5 字段中指定的目标。  
  
8. 目标参与方将发送到 BTAHL7 应用程序接受为每个收到的消息的确认。  
  
9. 接口收到的每个确认。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 1：添加标头和确认架构](../../adapters-and-accelerators/accelerator-hl7/step-1-add-header-and-acknowledgment-schemas.md)  
  
-   [步骤 2：添加适用于 v2.3.1 的通用架构](../../adapters-and-accelerators/accelerator-hl7/step-2-add-common-schemas-for-v2-3-1.md)  
  
-   [步骤 3：添加触发器事件（消息）架构](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md)  
  
-   [步骤 4：创建用于接受批处理消息的接收端口](../../adapters-and-accelerators/accelerator-hl7/step-4-create-a-receive-port-for-accepting-the-batch-message.md)  
  
-   [步骤 5：创建用于传递消息的发送端口](../../adapters-and-accelerators/accelerator-hl7/step-5-create-a-send-port-to-deliver-messages.md)  
  
-   [步骤 6：创建用于传递确认消息的发送端口](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-acknowledgments.md)  
  
-   [步骤 7：创建和配置源参与方](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md)  
  
-   [步骤 8：重启 BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-8-restart-biztalk-server.md)  
  
-   [步骤 9：验证零碎的入站批处理方案](../../adapters-and-accelerators/accelerator-hl7/step-9-verify-the-fragmented-inbound-batch-scenario.md)