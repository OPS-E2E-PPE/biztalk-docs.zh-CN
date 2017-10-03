---
title: "World Wide Web 服务不可用的主机上 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b14eaae-2158-4aef-9561-610d033998be
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ff3196501fe4192b7b7826a0611be9cf7644098
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="world-wide-web-service-on-host-not-available"></a><span data-ttu-id="92a68-102">主机上的 World Wide Web 服务不可用</span><span class="sxs-lookup"><span data-stu-id="92a68-102">World Wide Web service on host not available</span></span>
## <a name="details"></a><span data-ttu-id="92a68-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="92a68-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="92a68-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="92a68-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="92a68-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="92a68-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="92a68-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="92a68-106">Event ID</span></span>|<span data-ttu-id="92a68-107">0</span><span class="sxs-lookup"><span data-stu-id="92a68-107">0</span></span>|  
|<span data-ttu-id="92a68-108">事件源</span><span class="sxs-lookup"><span data-stu-id="92a68-108">Event Source</span></span>|<span data-ttu-id="92a68-109">0</span><span class="sxs-lookup"><span data-stu-id="92a68-109">0</span></span>|  
|<span data-ttu-id="92a68-110">组件</span><span class="sxs-lookup"><span data-stu-id="92a68-110">Component</span></span>|<span data-ttu-id="92a68-111">0</span><span class="sxs-lookup"><span data-stu-id="92a68-111">0</span></span>|  
|<span data-ttu-id="92a68-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="92a68-112">Symbolic Name</span></span>|<span data-ttu-id="92a68-113">0</span><span class="sxs-lookup"><span data-stu-id="92a68-113">0</span></span>|  
|<span data-ttu-id="92a68-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="92a68-114">Message Text</span></span>|<span data-ttu-id="92a68-115">主机“{0}”上的“万维网服务 (W3SVC)”不可用</span><span class="sxs-lookup"><span data-stu-id="92a68-115">World Wide Web service (W3SVC) on host "{0}" not available</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="92a68-116">解释</span><span class="sxs-lookup"><span data-stu-id="92a68-116">Explanation</span></span>  
 <span data-ttu-id="92a68-117">此错误表示“万维网服务”未运行。</span><span class="sxs-lookup"><span data-stu-id="92a68-117">This error indicates the World Wide Web service is not running.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="92a68-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="92a68-118">User Action</span></span>  
 <span data-ttu-id="92a68-119">使用以下过程启动“万维网服务”。</span><span class="sxs-lookup"><span data-stu-id="92a68-119">Use the following procedure to start the World Wide Web service.</span></span>  
  
#### <a name="to-start-the-world-wide-web-service"></a><span data-ttu-id="92a68-120">启动“万维网服务”的步骤</span><span class="sxs-lookup"><span data-stu-id="92a68-120">To start the World Wide Web service</span></span>  
  
1.  <span data-ttu-id="92a68-121">单击**启动**，单击**控制面板**，双击**管理工具**，双击**服务**。</span><span class="sxs-lookup"><span data-stu-id="92a68-121">Click **Start**, click **Control Panel**, double-click **Administrative Tools**, and double-click **Services**.</span></span>  
  
2.  <span data-ttu-id="92a68-122">在名称列中，找到**World Wide Web Publishing**。</span><span class="sxs-lookup"><span data-stu-id="92a68-122">In the Name column, locate **World Wide Web Publishing**.</span></span> <span data-ttu-id="92a68-123">确保状态是**已启动**。</span><span class="sxs-lookup"><span data-stu-id="92a68-123">Ensure that the status is **Started**.</span></span>