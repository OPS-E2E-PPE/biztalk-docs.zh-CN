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
ms.openlocfilehash: 426884dd700ad5b7862b5c191339b8ca49388232
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282608"
---
# <a name="public-processes"></a>公用流程
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]涉及与贸易合作伙伴作为公用过程集成的业务流程来实现。 它实现作为专用流程将组织内部的业务流程。 使用公共和专用流程将服务内容处理及后端集成 （在专用流程中） 与隔离开来 RosettaNet 实现框架 (RNIF) 处理 （在公用流程）。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 公用流程作为长期 BizTalk 业务流程来实现。 一个公用业务流程在发起方和响应方各上运行。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序提供了版本的发起方和响应方公用业务流程的 RNIF 1.1 和 RNIF 2.01。  
  
 这些公用业务流程实现所有的 RNIF 流程。 公用流程使 RNIF 从其他组件的复杂性。 除了强制实施符合 RNIF 消息流，则公用流程还确定默认跟踪设置，并提供在运行时进程状态信息。 它不会处理一条消息的服务内容。 专用流程执行此操作。  
  
 每个贸易合作伙伴协议引用单个公用流程，以便发起或响应合作伙伴接口流程 (PIP) 操作。 但是，公用流程是 PIP 不可知。  
  
 RosettaNet 规范对公用流程的设计进行了规定。 建议您不要修改公用流程。 公用业务流程是版本控制和签名。 如果您修改公用流程，它将不再符合 RNIF 的。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [发起方公用流程](../../adapters-and-accelerators/accelerator-rosettanet/initiator-public-process.md)  
  
-   [响应方公用流程](../../adapters-and-accelerators/accelerator-rosettanet/responder-public-process.md)