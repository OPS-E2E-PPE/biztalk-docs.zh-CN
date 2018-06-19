---
title: 接收位置找不到的元数据 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c397fb5-f400-4cff-85b9-5bf0d2069557
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3eb45272f7d3ef4491b59d5b019eb4499bcf5dff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268973"
---
# <a name="receive-location-for-metadata-not-found"></a><span data-ttu-id="68188-102">未找到元数据的接收位置</span><span class="sxs-lookup"><span data-stu-id="68188-102">Receive location for metadata not found</span></span>
## <a name="details"></a><span data-ttu-id="68188-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="68188-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="68188-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="68188-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="68188-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="68188-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="68188-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="68188-106">Event ID</span></span>|<span data-ttu-id="68188-107">0</span><span class="sxs-lookup"><span data-stu-id="68188-107">0</span></span>|  
|<span data-ttu-id="68188-108">事件源</span><span class="sxs-lookup"><span data-stu-id="68188-108">Event Source</span></span>|<span data-ttu-id="68188-109">0</span><span class="sxs-lookup"><span data-stu-id="68188-109">0</span></span>|  
|<span data-ttu-id="68188-110">组件</span><span class="sxs-lookup"><span data-stu-id="68188-110">Component</span></span>|<span data-ttu-id="68188-111">0</span><span class="sxs-lookup"><span data-stu-id="68188-111">0</span></span>|  
|<span data-ttu-id="68188-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="68188-112">Symbolic Name</span></span>|<span data-ttu-id="68188-113">0</span><span class="sxs-lookup"><span data-stu-id="68188-113">0</span></span>|  
|<span data-ttu-id="68188-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="68188-114">Message Text</span></span>|<span data-ttu-id="68188-115">找不到元数据的接收位置“{0}”。</span><span class="sxs-lookup"><span data-stu-id="68188-115">Receive location "{0}" for metadata not found.</span></span> <span data-ttu-id="68188-116">（检查在 Web.config 中的接收位置映射，并验证接收位置存在）。</span><span class="sxs-lookup"><span data-stu-id="68188-116">(Check receive location mapping in Web.config and verify the receive location exists.)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="68188-117">解释</span><span class="sxs-lookup"><span data-stu-id="68188-117">Explanation</span></span>  
 <span data-ttu-id="68188-118">此错误表明发布的独立 WCF 接收位置找不到元数据的相应接收位置。</span><span class="sxs-lookup"><span data-stu-id="68188-118">This error indicates that a published isolated WCF receive location could not find the corresponding receive location for metadata.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="68188-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="68188-119">User Action</span></span>  
 <span data-ttu-id="68188-120">若要解决此错误，请执行以下操作： 在 BizTalk 管理控制台中，请确保由 receiveLocationName 特性的 Web.config 文件中指定接收位置 BizTalk WCF 发布向导生成存在，并且已启动。</span><span class="sxs-lookup"><span data-stu-id="68188-120">To resolve this error, do the following: In the BizTalk Administration console, make sure that the receive location specified by the receiveLocationName attribute in the Web.config file that the BizTalk WCF Publishing Wizard generated exists and is started.</span></span>  
  
 <span data-ttu-id="68188-121">有关接收位置的其他信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="68188-121">For additional information on receive locations, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="68188-122">发布的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="68188-122">Publishing WCF Services</span></span>](../core/publishing-wcf-services.md)  
  
-   [<span data-ttu-id="68188-123">如何配置 WCF BasicHttp 接收位置</span><span class="sxs-lookup"><span data-stu-id="68188-123">How to Configure a WCF-BasicHttp Receive Location</span></span>](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [<span data-ttu-id="68188-124">如何配置 WCF WSHttp 接收位置</span><span class="sxs-lookup"><span data-stu-id="68188-124">How to Configure a WCF-WSHttp Receive Location</span></span>](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [<span data-ttu-id="68188-125">如何配置 WCF CustomIsolated 接收位置</span><span class="sxs-lookup"><span data-stu-id="68188-125">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="68188-126">演练： 使用 WCF NetMsmq 适配器的 WCF 服务发布</span><span class="sxs-lookup"><span data-stu-id="68188-126">Walkthrough: Publishing WCF Services with the WCF-NetMsmq Adapter</span></span>](../core/walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter.md)