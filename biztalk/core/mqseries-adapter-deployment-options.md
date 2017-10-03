---
title: "MQSeries 适配器部署选项 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, deploying
- deploying, MQSeries adapters
ms.assetid: d9380aff-40ea-419b-88e2-1e2ec3f023cb
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b88fa674c38df8b31c1954234846fd3939ed8568
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="mqseries-adapter-deployment-options"></a><span data-ttu-id="5d415-102">MQSeries 适配器部署选项</span><span class="sxs-lookup"><span data-stu-id="5d415-102">MQSeries Adapter Deployment Options</span></span>
<span data-ttu-id="5d415-103">使用 MQSeries 适配器可在配置硬件时提供很大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="5d415-103">The MQSeries adapter gives you great flexibility in configuring your hardware.</span></span> <span data-ttu-id="5d415-104">至少有三个主要使用模式：</span><span class="sxs-lookup"><span data-stu-id="5d415-104">There are at least three main patterns of use:</span></span>  
  
-   <span data-ttu-id="5d415-105">BizTalk Server、适配器和 MQSeries Server for Windows 位于同一计算机上。</span><span class="sxs-lookup"><span data-stu-id="5d415-105">BizTalk Server, the adapter, and MQSeries Server for Windows on the same computer.</span></span>  
  
-   <span data-ttu-id="5d415-106">BizTalk Server 和适配器位于同一计算机上，MQSeries Server for Windows（包括 MQSAgent）位于第二台计算机上，后者连接到一台或多台运行 MQSeries 服务的其他计算机。</span><span class="sxs-lookup"><span data-stu-id="5d415-106">BizTalk Server and the adapter on one computer, and MQSeries Server for Windows (including the MQSAgent) on a second computer, which connects to one or more additional computers that are running MQSeries Server.</span></span>  
  
-   <span data-ttu-id="5d415-107">一个组中的多个 BizTalk Server 安装和适配器，MQSeries 服务器（包括 MQSAgent）位于不同的计算机上。</span><span class="sxs-lookup"><span data-stu-id="5d415-107">Multiple BizTalk Server installations in a group and the adapter, and MQSeries Server (including MQSAgent) on a separate computer.</span></span>  
  
-   <span data-ttu-id="5d415-108">如果群集 MQSeries 服务器和 MQSeries 队列管理器，适配器能正常工作。</span><span class="sxs-lookup"><span data-stu-id="5d415-108">The adapter functions correctly if you cluster MQSeries Server and the MQSeries Queue Managers.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5d415-109">在这种情况下，不应对 MQSAgent COM+ 应用程序进行群集。</span><span class="sxs-lookup"><span data-stu-id="5d415-109">The MQSAgent COM+ application should not be clustered in this case.</span></span> <span data-ttu-id="5d415-110">而群集的两个节点都应安装并配置 MQSAgent COM+ 应用程序。</span><span class="sxs-lookup"><span data-stu-id="5d415-110">Instead, both nodes of the cluster should have the MQSAgent COM+ application installed and configured.</span></span> <span data-ttu-id="5d415-111">在此方案中，如果 MQSAgent COM+ 应用程序停止运行，则下一次从客户端中进行调用时将启动该程序。</span><span class="sxs-lookup"><span data-stu-id="5d415-111">In this scenario, if the MQSAgent COM+ application stops, the next call from the client will restart it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d415-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5d415-112">See Also</span></span>  
 [<span data-ttu-id="5d415-113">使用 MQSeries 适配器</span><span class="sxs-lookup"><span data-stu-id="5d415-113">Using the MQSeries Adapter</span></span>](../core/using-the-mqseries-adapter.md)