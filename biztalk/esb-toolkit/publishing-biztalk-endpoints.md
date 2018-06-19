---
title: 发布 BizTalk 终结点 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c8e8cc81-c6c7-4269-81e3-8725082a0c98
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e33517f1261324ad01eb0d9cad0f51b74c280828
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294285"
---
# <a name="publishing-biztalk-endpoints"></a><span data-ttu-id="c964b-102">发布 BizTalk 终结点</span><span class="sxs-lookup"><span data-stu-id="c964b-102">Publishing BizTalk Endpoints</span></span>
<span data-ttu-id="c964b-103">ESB 管理门户可用于创建和发布到当前配置的通用、 描述、 发现和集成 (UDDI) 服务器的条目。</span><span class="sxs-lookup"><span data-stu-id="c964b-103">You can use the ESB Management Portal to create and publish entries into the currently configured Universal Description, Discovery, and Integration (UDDI) server.</span></span>  
  
### <a name="to-publish-a-microsoft-biztalk-server-endpoint-into-the-current-uddi-server"></a><span data-ttu-id="c964b-104">若要将 Microsoft BizTalk Server 终结点发布到当前的 UDDI 服务器</span><span class="sxs-lookup"><span data-stu-id="c964b-104">To publish a Microsoft BizTalk Server endpoint into the current UDDI server</span></span>  
  
1.  <span data-ttu-id="c964b-105">指向**注册表**在门户的主菜单上，选项卡，然后单击**新的注册表条目**以打开[新注册表条目页](../esb-toolkit/new-registry-entry-page.md)。</span><span class="sxs-lookup"><span data-stu-id="c964b-105">Point to the **Registry** tab on the portal main menu, and then click **New Registry Entry** to open the [New Registry Entry Page](../esb-toolkit/new-registry-entry-page.md).</span></span>  
  
2.  <span data-ttu-id="c964b-106">使用在页面上的下拉列表来筛选终结点类型、 状态和应用程序终结点所在的位置。</span><span class="sxs-lookup"><span data-stu-id="c964b-106">Use the drop-down lists on the page to filter on the endpoint type, the status, and the application where the endpoint resides.</span></span>  
  
3.  <span data-ttu-id="c964b-107">单击你想要发布创建 UDDI 注册请求的终结点旁边的箭头图标。</span><span class="sxs-lookup"><span data-stu-id="c964b-107">Click the arrow icon next to the endpoint you want to publish to create a UDDI registration request.</span></span>  
  
4.  <span data-ttu-id="c964b-108">如果管理员启用了自动发布的终结点，门户将自动发布到 UDDI 服务器的新条目。</span><span class="sxs-lookup"><span data-stu-id="c964b-108">If an administrator has enabled auto-publishing of endpoints, the portal automatically publishes the new entry into the UDDI server.</span></span>  
  
5.  <span data-ttu-id="c964b-109">如果管理员尚未启用自动发布的终结点，请求保留在队列中，直到管理员批准或拒绝请求。</span><span class="sxs-lookup"><span data-stu-id="c964b-109">If an administrator has not enabled auto-publishing of endpoints, the requests remains in the queue until an administrator approves or declines the request.</span></span>