---
title: MQSeries 适配器部署选项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, deploying
- deploying, MQSeries adapters
ms.assetid: d9380aff-40ea-419b-88e2-1e2ec3f023cb
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18d2791b62478b1927772149f3f5d54f3cb5f618
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65264420"
---
# <a name="mqseries-adapter-deployment-options"></a><span data-ttu-id="d9c93-102">MQSeries 适配器部署选项</span><span class="sxs-lookup"><span data-stu-id="d9c93-102">MQSeries Adapter Deployment Options</span></span>
<span data-ttu-id="d9c93-103">MQSeries 适配器为您提供了极其灵活地配置硬件。</span><span class="sxs-lookup"><span data-stu-id="d9c93-103">The MQSeries adapter gives you great flexibility in configuring your hardware.</span></span> <span data-ttu-id="d9c93-104">有三个主要模式的使用：</span><span class="sxs-lookup"><span data-stu-id="d9c93-104">There are at least three main patterns of use:</span></span>  
  
-   <span data-ttu-id="d9c93-105">BizTalk Server、 适配器和 MQSeries Server for Windows 在同一计算机上。</span><span class="sxs-lookup"><span data-stu-id="d9c93-105">BizTalk Server, the adapter, and MQSeries Server for Windows on the same computer.</span></span>  
  
-   <span data-ttu-id="d9c93-106">BizTalk Server 和上一台计算机和 MQSeries Server for Windows （包括 MQSAgent） 连接到一个或多个运行 MQSeries 服务器的其他计算机的第二个计算机上的适配器。</span><span class="sxs-lookup"><span data-stu-id="d9c93-106">BizTalk Server and the adapter on one computer, and MQSeries Server for Windows (including the MQSAgent) on a second computer, which connects to one or more additional computers that are running MQSeries Server.</span></span>  
  
-   <span data-ttu-id="d9c93-107">多个不同的计算机上组的适配器和 MQSeries 服务器 （包括 MQSAgent） 中的 BizTalk Server 安装。</span><span class="sxs-lookup"><span data-stu-id="d9c93-107">Multiple BizTalk Server installations in a group and the adapter, and MQSeries Server (including MQSAgent) on a separate computer.</span></span>  
  
-   <span data-ttu-id="d9c93-108">如果群集 MQSeries Server 和 MQSeries 队列管理器，该适配器的功能正确。</span><span class="sxs-lookup"><span data-stu-id="d9c93-108">The adapter functions correctly if you cluster MQSeries Server and the MQSeries Queue Managers.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d9c93-109">MQSAgent COM + 应用程序不应在这种情况下群集。</span><span class="sxs-lookup"><span data-stu-id="d9c93-109">The MQSAgent COM+ application should not be clustered in this case.</span></span> <span data-ttu-id="d9c93-110">相反，在群集的两个节点应具有的 MQSAgent COM + 应用程序安装和配置。</span><span class="sxs-lookup"><span data-stu-id="d9c93-110">Instead, both nodes of the cluster should have the MQSAgent COM+ application installed and configured.</span></span> <span data-ttu-id="d9c93-111">在此方案中，如果 MQSAgent COM + 应用程序停止时，从客户端的下一个调用将重新启动它。</span><span class="sxs-lookup"><span data-stu-id="d9c93-111">In this scenario, if the MQSAgent COM+ application stops, the next call from the client will restart it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9c93-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="d9c93-112">See Also</span></span>  
 [<span data-ttu-id="d9c93-113">使用 MQSeries 适配器</span><span class="sxs-lookup"><span data-stu-id="d9c93-113">Using the MQSeries Adapter</span></span>](../core/using-the-mqseries-adapter.md)