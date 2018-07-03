---
title: BTARN 中的 SQL 处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- line-of-business applications (LOBs)
- LOBs
- SQL processing
- messages, message flow
- BTARN, SQL processing
ms.assetid: cfaf804f-3803-438e-a22e-50f487fe21c3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21255c03a9a9c1f2a30eb7f716c5e1bf285a3c5b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000710"
---
# <a name="sql-processing-in-btarn"></a><span data-ttu-id="1eb69-102">BTARN 中的 SQL 处理</span><span class="sxs-lookup"><span data-stu-id="1eb69-102">SQL Processing in BTARN</span></span>
<span data-ttu-id="1eb69-103">Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]使用 SQL 适配器路由来自业务 (LOB) 应用程序的消息。</span><span class="sxs-lookup"><span data-stu-id="1eb69-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] uses a SQL adapter to route a message from the line-of-business (LOB) application.</span></span> <span data-ttu-id="1eb69-104">它使用 SQL 发送端口将消息路由至 LOB 应用程序。</span><span class="sxs-lookup"><span data-stu-id="1eb69-104">It uses a SQL send port to route a message to the LOB application.</span></span>  
  
## <a name="message-flow"></a><span data-ttu-id="1eb69-105">消息流</span><span class="sxs-lookup"><span data-stu-id="1eb69-105">Message Flow</span></span>  
 <span data-ttu-id="1eb69-106">在发起程序或响应方计算机中后, 端 LOB 应用程序将消息路由到 MessagesFromLOB 表中的[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]数据[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]数据库。</span><span class="sxs-lookup"><span data-stu-id="1eb69-106">On either the initiator or responder computer, the back-end LOB application routes a message to the MessagesFromLOB table of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="1eb69-107"> 使用 SQL 适配器将消息从 MessagesFromLOB 表移到专用流程。</span><span class="sxs-lookup"><span data-stu-id="1eb69-107"> uses a SQL adapter to move the message from the MessagesFromLOB table to the private process.</span></span> <span data-ttu-id="1eb69-108">有关详细信息，请参阅 BizTalk Server 帮助中的"SQL 适配器"。</span><span class="sxs-lookup"><span data-stu-id="1eb69-108">For more information, see "SQL Adapter" in BizTalk Server Help.</span></span>  
  
 <span data-ttu-id="1eb69-109">您可以选择使用 FILE 适配器（而不是使用默认的 SQL 适配器）将服务内容提交给 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1eb69-109">You can choose to use a File adapter to submit service content to [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], instead of using the default SQL adapter.</span></span> <span data-ttu-id="1eb69-110">如果您选择使用文件适配器[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]不支持附件。</span><span class="sxs-lookup"><span data-stu-id="1eb69-110">If you choose to use a File adapter, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] does not support attachments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eb69-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="1eb69-111">See Also</span></span>  
 [<span data-ttu-id="1eb69-112">BTARN 中的消息处理</span><span class="sxs-lookup"><span data-stu-id="1eb69-112">Message Processing in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)