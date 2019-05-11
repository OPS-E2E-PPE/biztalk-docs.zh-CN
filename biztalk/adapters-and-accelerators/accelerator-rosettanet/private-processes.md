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
ms.openlocfilehash: 549c7cd01472345ab8449b35d2de6b5ef32ca0e7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282589"
---
# <a name="private-processes"></a>专用流程
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]业务流程作为专用流程将组织内部的实现。 公用流程处理涉及与贸易合作伙伴集成的业务流程。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将服务内容处理及后端集成 （在专用流程中） 从 RosettaNet 实现框架 (RNIF) 处理 （在公用流程） 中隔离出来。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 专用流程作为长期 BizTalk 业务流程来实现。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 在发起方和响应方各使用一个专用业务流程。 每个专用流程解释并处理服务内容消息部分，传入或传出。 专用流程将发送到服务内容，或从公用流程接收。 专用流程不处理标头，并且不执行 RNIF 处理。 则将保留的公用流程。  
  
 在企业方案中，通常会为每个 PIP 消息架构的一个专用流程。 但是， [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 包括两个专用业务流程可以处理任何 PIP 消息。 一个业务流程是发起方流程 (PrivateInitiator.odx，请参阅[PrivateInitiator 示例&#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md))，一个用于响应方流程 (PrivateResponder.odx，请参阅[PrivateResponder示例&#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md))。 您将必须自定义专用流程，使[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]到您的特定业务流程。  
  
 SDK 还包括一个过程，实现特定于 PIP 的专用响应方流程以并入业务规则 (PIP3A4PrivateResponder.odx，请参阅[3A4 专用响应方业务流程使用业务规则](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md))。  
  
 专用流程将服务内容的格式从后端--业务线 (LOB) 格式设为 XML。 立即采用 XML 格式[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]处理服务内容和公用流程将符合 RNIF 的头添加到服务内容中进行传输。  
  
 专用流程连接到后端业务线应用程序中的 messagetolob 表和 MessagesFromLOB 表[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]数据[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]数据库。 此数据库处理之间的通信[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]和 LOB 应用程序。 LOB 应用程序使用接口来访问数据库表。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [发起方专用流程](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md)  
  
-   [响应方专用流程](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md)