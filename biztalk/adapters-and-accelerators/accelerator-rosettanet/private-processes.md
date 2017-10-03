---
title: "私有进程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b28bf49af1305220d96f129080b274b5391495eb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="private-processes"></a>私有进程
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]实现都是作为私有进程组织内部的业务流程。 公共进程处理涉及与贸易合作伙伴集成的业务流程。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]隔离服务内容处理中的和后端集成 （专用的过程中） 从 RosettaNet 实现框架 (RNIF) （公共在进程中） 处理。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]实现私有进程作为长时间运行 BizTalk 业务流程。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]在发起方端，另一个在响应方端使用一个私有进程业务流程。 每个专用流程解释并处理服务内容的消息部分，包括传入消息和传出消息。 专用流程将服务内容发送给公用流程，或从公用流程接收服务内容。 专用流程不处理头，也不执行 RNIF 处理。 这两种处理均由公用流程执行。  
  
 在企业方案中，每个 PIP 消息架构通常只有一个专用流程。 但是，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 包括两个专用业务流程，可以处理任何 PIP 消息。 为发起程序的进程是一个业务流程 (PrivateInitiator.odx，请参阅[PrivateInitiator 示例 &#91;RN3 &#93;](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md)) 和响应方过程有一个是 (PrivateResponder.odx，请参阅[PrivateResponder 示例 &#91;RN3 &#93;](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md)). 您必须自定义专用流程，使 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 适合您的特定业务流程。  
  
 SDK 还包括实现合并业务规则的 PIP 特定私有响应方进程的进程 (PIP3A4PrivateResponder.odx，请参阅[3A4 私有响应方业务流程使用业务规则](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md))。  
  
 专用流程将服务内容的格式由后端业务线 (LOB) 格式更改为 XML 格式。 一旦服务内容更改为 XML 格式，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 就对其进行处理，而公用流程会将符合 RNIF 的头添加到服务内容中进行传输。  
  
 专用流程通过 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] 数据库中的 MessageToLOB 表和 MessagesFromLOB 表连接到后端业务线应用程序。 此数据库处理 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 和 LOB 应用程序之间的通信。 LOB 应用程序使用接口来访问数据库表。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [发起方私有过程](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md)  
  
-   [响应方私有过程](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md)