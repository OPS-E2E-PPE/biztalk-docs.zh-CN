---
title: 自定义发送和接收组件在 BizTalk Server 中使用 RosettaNet 加速器 |Microsoft Docs
description: 创建、 自定义，或设置属性的 RosettaNet acclerator (BTARN) 上的发送和接收端口的 BizTalk Server
ms.custom: ''
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send components
- developing, send components
- developing, receive components
- receive components
ms.assetid: 78224a31-4eff-4a48-bcb9-deed388299f1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1127eed100389f548c7a4b579a44ee84120529e2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283774"
---
# <a name="customizing-send-and-receive-components"></a><span data-ttu-id="84a7b-103">自定义发送和接收组件</span><span class="sxs-lookup"><span data-stu-id="84a7b-103">Customizing Send and Receive Components</span></span>
<span data-ttu-id="84a7b-104">在本部分中的主题介绍如何创建、 自定义，或设置属性的 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]发送和接收组件。</span><span class="sxs-lookup"><span data-stu-id="84a7b-104">The topics in this section describe how to create, customize, or set the properties of Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] send and receive components.</span></span> <span data-ttu-id="84a7b-105">这些组件包括 ASPX 页、 发送和接收端口和适配器。</span><span class="sxs-lookup"><span data-stu-id="84a7b-105">These components include ASPX pages, send and receive ports, and adapters.</span></span>  
  
 <span data-ttu-id="84a7b-106">有关详细信息[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]，然后[阅读有关 RosettaNet 加速器](learn-the-rosettanet-accelerator-and-the-biztalk-tools-available.md)。</span><span class="sxs-lookup"><span data-stu-id="84a7b-106">For more information about [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], then [read about the RosettaNet accelerator](learn-the-rosettanet-accelerator-and-the-biztalk-tools-available.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="84a7b-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="84a7b-107">In This Section</span></span>  
  
-   [<span data-ttu-id="84a7b-108">设置 ASPX 页的连接超时</span><span class="sxs-lookup"><span data-stu-id="84a7b-108">Setting the Connection Time-Out for an ASPX Page</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/setting-the-connection-time-out-for-an-aspx-page.md)  
  
-   [<span data-ttu-id="84a7b-109">创建处理孤立或重复消息的发送端口</span><span class="sxs-lookup"><span data-stu-id="84a7b-109">Creating a Send Port to Handle Orphan or Duplicate Messages</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-a-send-port-to-handle-orphan-or-duplicate-messages.md)  
  
-   [<span data-ttu-id="84a7b-110">设置公用业务流程和 HTTP 适配器的超时值</span><span class="sxs-lookup"><span data-stu-id="84a7b-110">Setting Time-Outs for a Public-Process Orchestration and an HTTP Adapter</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/setting-time-outs-for-a-public-process-orchestration-and-an-http-adapter.md)