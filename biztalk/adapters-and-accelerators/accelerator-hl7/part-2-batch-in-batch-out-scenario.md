---
title: 第 2 部分： 批处理中的批处理方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, outbound batches
- batching, inbound batches
ms.assetid: 36b9d927-f5b7-4c1a-9163-9e79d17c3e9e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 593f1e57b12eb30f47db65bfacd34a988f701f07
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975414"
---
# <a name="part-2-batch-inbatch-out-scenario"></a>第 2 部分： 中的批处理 / 出站批处理方案
在本教程的此部分中，接收 HL7 编码的批文件，将通过其传递[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]而无需碎片，并发送到目标不变的批处理文件。 下图显示了此过程中，流和以下子节介绍了工作流。  
  
> [!NOTE]
>  开始本教程的此部分之前，请关闭您的关闭该命令会提示使用第 1 部分，MllpReceive 和 MllpSend 工具。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-batch-in-batch-out-scenario.gif "hl7_batch_in_batch_out_scenario")  
  
 **在 Batch 中的消息流的方式在 / 出站批处理方案**  
  
 此方案包括以下工作流：  
  
1. 在工作流开始时的业务线应用程序中将消息批发送到 Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 集成引擎使用 FILE 协议。 批处理包含两个版本的 ADT ^ A03 消息。 源应用程序属于 Tutorial_BatchSource 参与方。  
  
2. 集成引擎接收的批处理文件中的接收端口，并验证消息批。 (的验证级别取决于选择中的源参与方设置[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。)  
  
3. 根据中的设置[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器，以禁用批处理碎片的参与方，接口引擎未分析为单个消息批，但保留作为批处理的批处理。 它会验证各条消息，根据在源参与方选择的设置重新[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。  
  
4. 接口引擎生成批消息，根据中的确认定义设置确认[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]的参与方的配置编辑器。 在这种情况下，选择原始确认模式，因此接口引擎在验证消息标头和正文后会生成消息批的单个应用程序接受确认。 引擎生成确认基于 ACK_024_GLO_DEF 架构、 在确认 MSA2 字段中输入"AA"、 在 MSH3，输入目标参与方和 MSH5 中输入的源参与方。  
  
5. 确认批处理到源参与方通过文件的接口引擎路由发送适配器设置来处理确认。 在这种情况下，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将批处理路由到 \Tutorial_BatchACKDrop 文件夹。  
  
6. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 将发送到目标消息批次为指定目标参与方，在此情况下文件夹 \Tutorial_BTAHL7Drop。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 1：为入站批处理/出站批处理配置参与方信息](../../adapters-and-accelerators/accelerator-hl7/step-1-configure-party-information-for-batch-in-batch-out.md)  
  
-   [步骤 2：修改或创建发送端口和接收端口](../../adapters-and-accelerators/accelerator-hl7/step-2-modify-or-create-the-send-and-receive-ports.md)  
  
-   [步骤 3：测试入站批处理/出站批处理方案](../../adapters-and-accelerators/accelerator-hl7/step-3-test-the-batch-in-batch-out-scenario.md)