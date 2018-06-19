---
title: 第 2 部分： 批处理中的批处理方案出 |Microsoft 文档
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
ms.openlocfilehash: 56ffac38676fe6b163a39ff06be5fe0538800d2c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206181"
---
# <a name="part-2-batch-inbatch-out-scenario"></a>第 2 部分： 中的批处理 / 批处理出方案
在本教程的此部分中，你会收到 HL7 编码批处理文件，将其传递[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]碎片，而发送到目标的不变的批处理文件。 下图显示了此过程中，流和以下子节介绍工作流。  
  
> [!NOTE]
>  在开始之前在本教程的此部分，请关闭 MllpReceive 和 MllpSend 的工具，可通过关闭命令提示符的第 1 部分中使用。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-batch-in-batch-out-scenario.gif "hl7_batch_in_batch_out_scenario")  
  
 **消息在批处理作业中的流动方式在 / 批处理出方案**  
  
 此方案包括以下工作流：  
  
1.  工作流一开始时的业务线应用程序发送消息批为[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 集成引擎使用 FILE 协议。 批处理包含两个版本的 ADT ^ A03 消息。 源应用程序所属 Tutorial_BatchSource 方。  
  
2.  集成引擎接收文件上的批处理接收端口，并验证消息批处理。 (的验证级别取决于为中的源方选择设置[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。)  
  
3.  基于中的设置[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]禁用批处理碎片当事方，接口引擎的配置资源管理器不会转换为单个消息，分析批处理，但会作为批处理批处理。 它会验证各条消息，根据为中的源方选择设置重新[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。  
  
4.  接口引擎生成基于中的确认定义设置批处理消息的确认[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]方的配置编辑器。 在这种情况下，选择原始确认模式，以便接口引擎生成在验证的消息标头和正文之后消息批处理的单个应用程序接受确认。 引擎生成基于 ACK_024_GLO_DEF 架构该确认，该确认 MSA2 字段中输入"AA"，在 MSH3，输入目标方并在 MSH5 输入源方。  
  
5.  确认批处理到源方通过文件的接口引擎路由发送适配器设置来处理确认。 在这种情况下，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将批处理路由到 \Tutorial_BatchACKDrop 文件夹。  
  
6.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将发送到目标消息批处理为指定目标方中，在此情况下文件夹 \Tutorial_BTAHL7Drop。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 1： 配置对批次中的当事方信息/批处理出](../../adapters-and-accelerators/accelerator-hl7/step-1-configure-party-information-for-batch-in-batch-out.md)  
  
-   [步骤 2： 修改或创建发送方和接收端口](../../adapters-and-accelerators/accelerator-hl7/step-2-modify-or-create-the-send-and-receive-ports.md)  
  
-   [步骤 3： 测试中的批处理/批处理出方案](../../adapters-and-accelerators/accelerator-hl7/step-3-test-the-batch-in-batch-out-scenario.md)