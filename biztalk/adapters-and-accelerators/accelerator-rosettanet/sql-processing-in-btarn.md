---
title: "SQL 中 BTARN 处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- line-of-business applications (LOBs)
- LOBs
- SQL processing
- messages, message flow
- BTARN, SQL processing
ms.assetid: cfaf804f-3803-438e-a22e-50f487fe21c3
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9cf1aba9f2d4d2ea77f369e76c277160739f7f17
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sql-processing-in-btarn"></a><span data-ttu-id="3432c-102">SQL 中 BTARN 处理</span><span class="sxs-lookup"><span data-stu-id="3432c-102">SQL Processing in BTARN</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="3432c-103">[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]使用 SQL 适配器路由中的业务线 (LOB) 应用程序的消息。</span><span class="sxs-lookup"><span data-stu-id="3432c-103"> [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] uses a SQL adapter to route a message from the line-of-business (LOB) application.</span></span> <span data-ttu-id="3432c-104">它使用 SQL 发送端口将消息路由至 LOB 应用程序。</span><span class="sxs-lookup"><span data-stu-id="3432c-104">It uses a SQL send port to route a message to the LOB application.</span></span>  
  
## <a name="message-flow"></a><span data-ttu-id="3432c-105">消息流</span><span class="sxs-lookup"><span data-stu-id="3432c-105">Message Flow</span></span>  
 <span data-ttu-id="3432c-106">发起方还是响应方计算机，在后端 LOB 应用程序将消息路由到的 MessagesFromLOB 表[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]数据[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]数据库。</span><span class="sxs-lookup"><span data-stu-id="3432c-106">On either the initiator or responder computer, the back-end LOB application routes a message to the MessagesFromLOB table of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="3432c-107">使用 SQL 适配器将消息从 MessagesFromLOB 表移动到专用的流程。</span><span class="sxs-lookup"><span data-stu-id="3432c-107"> uses a SQL adapter to move the message from the MessagesFromLOB table to the private process.</span></span> <span data-ttu-id="3432c-108">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] 帮助中的“SQL 适配器”。</span><span class="sxs-lookup"><span data-stu-id="3432c-108">For more information, see "SQL Adapter" in [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span>  
  
 <span data-ttu-id="3432c-109">您可以选择使用 FILE 适配器（而不是使用默认的 SQL 适配器）将服务内容提交给 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3432c-109">You can choose to use a File adapter to submit service content to [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], instead of using the default SQL adapter.</span></span> <span data-ttu-id="3432c-110">如果你选择使用一个文件适配器，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]不支持附件。</span><span class="sxs-lookup"><span data-stu-id="3432c-110">If you choose to use a File adapter, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] does not support attachments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3432c-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3432c-111">See Also</span></span>  
 [<span data-ttu-id="3432c-112">消息处理在 BTARN</span><span class="sxs-lookup"><span data-stu-id="3432c-112">Message Processing in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)