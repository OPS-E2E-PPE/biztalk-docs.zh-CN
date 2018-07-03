---
title: 专用流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private processes, trading partners
- private processes, about private processes
- private processes, orchestrations
- private processes
- orchestrations, private-process orchestrations
- trading partners, private processes
- BTARN, private processes
- business processes, private processes
ms.assetid: 0c5895eb-22c1-431f-a769-ae6ca05d1e45
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ff99f03b3a38ff9d8c1c33ec16b108e5bd58ca7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967479"
---
# <a name="private-processes"></a>专用流程
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]业务流程作为专用流程将组织内部的实现。 公用流程处理涉及与贸易合作伙伴集成的业务流程。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将服务内容处理及后端集成 （在专用流程中） 从 RosettaNet 实现框架 (RNIF) 处理 （在公用流程） 中隔离出来。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 专用流程作为长期 BizTalk 业务流程来实现。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 在发起方和响应方各使用一个专用业务流程。 每个专用流程解释并处理服务内容的消息部分，包括传入消息和传出消息。 专用流程将服务内容发送给公用流程，或从公用流程接收服务内容。 专用流程不处理头，也不执行 RNIF 处理。 这两种处理均由公用流程执行。  
  
 在企业方案中，每个 PIP 消息架构通常只有一个专用流程。 但是，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 包括两个专用业务流程，可以处理任何 PIP 消息。 一个业务流程是发起方流程 (PrivateInitiator.odx，请参阅[PrivateInitiator 示例&#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md))，一个用于响应方流程 (PrivateResponder.odx，请参阅[PrivateResponder示例&#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md))。 您必须自定义专用流程，使 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 适合您的特定业务流程。  
  
 SDK 还包括一个过程，实现特定于 PIP 的专用响应方流程以并入业务规则 (PIP3A4PrivateResponder.odx，请参阅[3A4 专用响应方业务流程使用业务规则](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md))。  
  
 专用流程将服务内容的格式由后端业务线 (LOB) 格式更改为 XML 格式。 一旦服务内容更改为 XML 格式，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 就对其进行处理，而公用流程会将符合 RNIF 的头添加到服务内容中进行传输。  
  
 专用流程通过 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] 数据库中的 MessageToLOB 表和 MessagesFromLOB 表连接到后端业务线应用程序。 此数据库处理 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 和 LOB 应用程序之间的通信。 LOB 应用程序使用接口来访问数据库表。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [发起方专用流程](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md)  
  
-   [响应方专用流程](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md)