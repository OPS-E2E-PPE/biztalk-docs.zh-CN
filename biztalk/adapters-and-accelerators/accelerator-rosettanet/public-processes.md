---
title: 公用流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- public processes, orchestrations
- business processes, public processes
- public processes, trading partners
- BTARN, public processes
- orchestrations, public-process orchestrations
- public processes
- trading partners, public processes
- public processes, about public processes
ms.assetid: 5ccc7449-5741-4d49-beb6-567bcd93f679
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f9d0288defa0705c7e12f102011edbf9ee7e90d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984718"
---
# <a name="public-processes"></a>公用流程
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]涉及与贸易合作伙伴作为公用过程集成的业务流程来实现。 而将组织内部的业务流程作为专用流程来实现。 使用专用流程和公用流程可将 RosettaNet 实现框架 (RNIF) 处理（在公用流程中）与服务内容处理及后端集成（在专用流程中）分隔开来。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 公用流程作为长期 BizTalk 业务流程来实现。 在发起方和响应方各会运行一个公用业务流程。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序提供了版本的发起方和响应方公用业务流程的 RNIF 1.1 和 RNIF 2.01。  
  
 这些公用业务流程实现了所有的 RNIF 流程。 公用流程使 RNIF 对于其他组件来说变得相对简单了。 除了执行与 RNIF 兼容的消息流之外，公用流程还确定默认跟踪设置并在运行时提供流程状态信息。 它并不处理消息的服务内容。 这由专用流程来处理。  
  
 每个贸易合作伙伴协议都引用一个单一的公用流程，以便发起或响应合作伙伴接口流程 (PIP) 操作。 然而，公用流程是 PIP 不可知的。  
  
 RosettaNet 规范对公用流程的设计进行了规定。 建议您不要修改公用流程。 公用业务流程是版本化的，且经过签名。 如果您修改了公用流程，它将不再兼容 RNIF。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [发起方公用流程](../../adapters-and-accelerators/accelerator-rosettanet/initiator-public-process.md)  
  
-   [响应方公用流程](../../adapters-and-accelerators/accelerator-rosettanet/responder-public-process.md)