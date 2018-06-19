---
title: 接收位置找不到地址 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 637f3925-06ff-47b2-99db-f85e829ee318
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1242ffc77976fb2ffcc469752d13a6f6366d7a1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268765"
---
# <a name="receive-location-for-address-not-found"></a><span data-ttu-id="4defa-102">找不到地址接收位置</span><span class="sxs-lookup"><span data-stu-id="4defa-102">Receive location for address not found</span></span>
## <a name="details"></a><span data-ttu-id="4defa-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="4defa-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4defa-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="4defa-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="4defa-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="4defa-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="4defa-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="4defa-106">Event ID</span></span>|<span data-ttu-id="4defa-107">0</span><span class="sxs-lookup"><span data-stu-id="4defa-107">0</span></span>|  
|<span data-ttu-id="4defa-108">事件源</span><span class="sxs-lookup"><span data-stu-id="4defa-108">Event Source</span></span>|<span data-ttu-id="4defa-109">0</span><span class="sxs-lookup"><span data-stu-id="4defa-109">0</span></span>|  
|<span data-ttu-id="4defa-110">组件</span><span class="sxs-lookup"><span data-stu-id="4defa-110">Component</span></span>|<span data-ttu-id="4defa-111">0</span><span class="sxs-lookup"><span data-stu-id="4defa-111">0</span></span>|  
|<span data-ttu-id="4defa-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="4defa-112">Symbolic Name</span></span>|<span data-ttu-id="4defa-113">0</span><span class="sxs-lookup"><span data-stu-id="4defa-113">0</span></span>|  
|<span data-ttu-id="4defa-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="4defa-114">Message Text</span></span>|<span data-ttu-id="4defa-115">找不到地址“{0}”的接收位置。</span><span class="sxs-lookup"><span data-stu-id="4defa-115">Receive location for address "{0}" not found.</span></span> <span data-ttu-id="4defa-116">（BizTalk 接收位置可能已被禁用。）</span><span class="sxs-lookup"><span data-stu-id="4defa-116">(The BizTalk receive location may be disabled.)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4defa-117">解释</span><span class="sxs-lookup"><span data-stu-id="4defa-117">Explanation</span></span>  
 <span data-ttu-id="4defa-118">此错误表明发布的独立 WCF 接收位置找不到相应的接收位置。</span><span class="sxs-lookup"><span data-stu-id="4defa-118">This error indicates that a published isolated WCF receive location could not find the corresponding receive location.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4defa-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="4defa-119">User Action</span></span>  
 <span data-ttu-id="4defa-120">若要解决此错误，请执行以下操作： 在 BizTalk 管理控制台中，请确保由 receiveLocationName 特性的 Web.config 文件中指定接收位置 BizTalk WCF 发布向导生成存在，并且已启动。</span><span class="sxs-lookup"><span data-stu-id="4defa-120">To resolve this error, do the following: In the BizTalk Administration console, make sure that the receive location specified by the receiveLocationName attribute in the Web.config file that the BizTalk WCF Publishing Wizard generated exists and is started.</span></span>  
  
 <span data-ttu-id="4defa-121">有关创建接收位置的其他信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="4defa-121">For additional information on creating receive locations, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="4defa-122">使用独立的 WCF 发布 WCF 服务接收适配器</span><span class="sxs-lookup"><span data-stu-id="4defa-122">Publishing WCF Services with the Isolated WCF Receive Adapters</span></span>](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="4defa-123">如何配置 WCF BasicHttp 接收位置</span><span class="sxs-lookup"><span data-stu-id="4defa-123">How to Configure a WCF-BasicHttp Receive Location</span></span>](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [<span data-ttu-id="4defa-124">如何配置 WCF WSHttp 接收位置</span><span class="sxs-lookup"><span data-stu-id="4defa-124">How to Configure a WCF-WSHttp Receive Location</span></span>](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [<span data-ttu-id="4defa-125">如何配置 WCF CustomIsolated 接收位置</span><span class="sxs-lookup"><span data-stu-id="4defa-125">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="4defa-126">演练： 使用 WCF BasicHttp 适配器的 WCF 服务发布</span><span class="sxs-lookup"><span data-stu-id="4defa-126">Walkthrough: Publishing WCF Services with the WCF-BasicHttp Adapter</span></span>](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)