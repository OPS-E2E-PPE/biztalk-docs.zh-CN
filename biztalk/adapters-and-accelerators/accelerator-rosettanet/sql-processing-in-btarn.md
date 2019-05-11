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
ms.openlocfilehash: adbf3e0cfdc397b94383d7e0241eeddad045572d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281723"
---
# <a name="sql-processing-in-btarn"></a><span data-ttu-id="0e13c-102">BTARN 中的 SQL 处理</span><span class="sxs-lookup"><span data-stu-id="0e13c-102">SQL Processing in BTARN</span></span>
<span data-ttu-id="0e13c-103">Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]使用 SQL 适配器路由来自业务 (LOB) 应用程序的消息。</span><span class="sxs-lookup"><span data-stu-id="0e13c-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] uses a SQL adapter to route a message from the line-of-business (LOB) application.</span></span> <span data-ttu-id="0e13c-104">它使用 SQL 发送端口将消息路由到 LOB 应用程序。</span><span class="sxs-lookup"><span data-stu-id="0e13c-104">It uses a SQL send port to route a message to the LOB application.</span></span>  
  
## <a name="message-flow"></a><span data-ttu-id="0e13c-105">消息流</span><span class="sxs-lookup"><span data-stu-id="0e13c-105">Message Flow</span></span>  
 <span data-ttu-id="0e13c-106">在发起程序或响应方计算机中后, 端 LOB 应用程序将消息路由到 MessagesFromLOB 表中的[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]数据[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]数据库。</span><span class="sxs-lookup"><span data-stu-id="0e13c-106">On either the initiator or responder computer, the back-end LOB application routes a message to the MessagesFromLOB table of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="0e13c-107">使用 SQL 适配器将消息从 MessagesFromLOB 表移到专用流程。</span><span class="sxs-lookup"><span data-stu-id="0e13c-107">uses a SQL adapter to move the message from the MessagesFromLOB table to the private process.</span></span> <span data-ttu-id="0e13c-108">有关详细信息，请参阅 BizTalk Server 帮助中的"SQL 适配器"。</span><span class="sxs-lookup"><span data-stu-id="0e13c-108">For more information, see "SQL Adapter" in BizTalk Server Help.</span></span>  
  
 <span data-ttu-id="0e13c-109">您可以选择使用文件适配器将服务内容提交到[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]，而不是使用默认的 SQL 适配器。</span><span class="sxs-lookup"><span data-stu-id="0e13c-109">You can choose to use a File adapter to submit service content to [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], instead of using the default SQL adapter.</span></span> <span data-ttu-id="0e13c-110">如果您选择使用文件适配器[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]不支持附件。</span><span class="sxs-lookup"><span data-stu-id="0e13c-110">If you choose to use a File adapter, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] does not support attachments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e13c-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="0e13c-111">See Also</span></span>  
 [<span data-ttu-id="0e13c-112">BTARN 中的消息处理</span><span class="sxs-lookup"><span data-stu-id="0e13c-112">Message Processing in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)