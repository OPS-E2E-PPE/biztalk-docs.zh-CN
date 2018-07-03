---
title: 找不到地址接收位置 |Microsoft Docs
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
ms.openlocfilehash: 55b3744f6590ee706bcc3df4124f964306634ca5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994942"
---
# <a name="receive-location-for-address-not-found"></a><span data-ttu-id="eb3c2-102">找不到地址接收位置</span><span class="sxs-lookup"><span data-stu-id="eb3c2-102">Receive location for address not found</span></span>
## <a name="details"></a><span data-ttu-id="eb3c2-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="eb3c2-103">Details</span></span>  
  
|                 |                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------|
|  <span data-ttu-id="eb3c2-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="eb3c2-104">Product Name</span></span>   |      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]       |
| <span data-ttu-id="eb3c2-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="eb3c2-105">Product Version</span></span> |                  [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                   |
|    <span data-ttu-id="eb3c2-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="eb3c2-106">Event ID</span></span>     |                                               <span data-ttu-id="eb3c2-107">0</span><span class="sxs-lookup"><span data-stu-id="eb3c2-107">0</span></span>                                               |
|  <span data-ttu-id="eb3c2-108">事件源</span><span class="sxs-lookup"><span data-stu-id="eb3c2-108">Event Source</span></span>   |                                               <span data-ttu-id="eb3c2-109">0</span><span class="sxs-lookup"><span data-stu-id="eb3c2-109">0</span></span>                                               |
|    <span data-ttu-id="eb3c2-110">组件</span><span class="sxs-lookup"><span data-stu-id="eb3c2-110">Component</span></span>    |                                               <span data-ttu-id="eb3c2-111">0</span><span class="sxs-lookup"><span data-stu-id="eb3c2-111">0</span></span>                                               |
|  <span data-ttu-id="eb3c2-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="eb3c2-112">Symbolic Name</span></span>  |                                               <span data-ttu-id="eb3c2-113">0</span><span class="sxs-lookup"><span data-stu-id="eb3c2-113">0</span></span>                                               |
|  <span data-ttu-id="eb3c2-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="eb3c2-114">Message Text</span></span>   | <span data-ttu-id="eb3c2-115">地址的接收位置"{0}"找不到。</span><span class="sxs-lookup"><span data-stu-id="eb3c2-115">Receive location for address "{0}" not found.</span></span> <span data-ttu-id="eb3c2-116">（BizTalk 接收位置可能已被禁用。）</span><span class="sxs-lookup"><span data-stu-id="eb3c2-116">(The BizTalk receive location may be disabled.)</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="eb3c2-117">解释</span><span class="sxs-lookup"><span data-stu-id="eb3c2-117">Explanation</span></span>  
 <span data-ttu-id="eb3c2-118">此错误表明发布的独立 WCF 接收位置找不到相应的接收位置。</span><span class="sxs-lookup"><span data-stu-id="eb3c2-118">This error indicates that a published isolated WCF receive location could not find the corresponding receive location.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="eb3c2-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="eb3c2-119">User Action</span></span>  
 <span data-ttu-id="eb3c2-120">若要解决此错误，请执行以下： 在 BizTalk 管理控制台中，请确保 Web.config 文件中 receiveLocationName 属性指定的接收位置 BizTalk WCF 发布向导生成存在并且已启动。</span><span class="sxs-lookup"><span data-stu-id="eb3c2-120">To resolve this error, do the following: In the BizTalk Administration console, make sure that the receive location specified by the receiveLocationName attribute in the Web.config file that the BizTalk WCF Publishing Wizard generated exists and is started.</span></span>  
  
 <span data-ttu-id="eb3c2-121">有关创建接收位置的其他信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="eb3c2-121">For additional information on creating receive locations, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="eb3c2-122">通过独立 WCF 接收适配器发布 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="eb3c2-122">Publishing WCF Services with the Isolated WCF Receive Adapters</span></span>](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="eb3c2-123">如何配置 Wcf-basichttp 接收位置</span><span class="sxs-lookup"><span data-stu-id="eb3c2-123">How to Configure a WCF-BasicHttp Receive Location</span></span>](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [<span data-ttu-id="eb3c2-124">如何配置 Wcf-wshttp 接收位置</span><span class="sxs-lookup"><span data-stu-id="eb3c2-124">How to Configure a WCF-WSHttp Receive Location</span></span>](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [<span data-ttu-id="eb3c2-125">如何配置 Wcf-customisolated 接收位置</span><span class="sxs-lookup"><span data-stu-id="eb3c2-125">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="eb3c2-126">演练：通过 WCF-BasicHttp 适配器发布 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="eb3c2-126">Walkthrough: Publishing WCF Services with the WCF-BasicHttp Adapter</span></span>](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)