---
title: 无法创建一个或多个 BizTalk 接收位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b564f87b-34ba-400e-9a71-bd66081fc1b8
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0dfc81876cba51b4dad03a01c2feb935b4fc959
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986398"
---
# <a name="unable-to-create-one-or-more-biztalk-receive-locations"></a><span data-ttu-id="31498-102">无法创建一个或多个 BizTalk 接收位置</span><span class="sxs-lookup"><span data-stu-id="31498-102">Unable to create one or more BizTalk receive locations</span></span>
## <a name="details"></a><span data-ttu-id="31498-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="31498-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="31498-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="31498-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="31498-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="31498-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="31498-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="31498-106">Event ID</span></span>     |                                         <span data-ttu-id="31498-107">0</span><span class="sxs-lookup"><span data-stu-id="31498-107">0</span></span>                                          |
|  <span data-ttu-id="31498-108">事件源</span><span class="sxs-lookup"><span data-stu-id="31498-108">Event Source</span></span>   |                                         <span data-ttu-id="31498-109">0</span><span class="sxs-lookup"><span data-stu-id="31498-109">0</span></span>                                          |
|    <span data-ttu-id="31498-110">组件</span><span class="sxs-lookup"><span data-stu-id="31498-110">Component</span></span>    |                                         <span data-ttu-id="31498-111">0</span><span class="sxs-lookup"><span data-stu-id="31498-111">0</span></span>                                          |
|  <span data-ttu-id="31498-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="31498-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="31498-113">0</span><span class="sxs-lookup"><span data-stu-id="31498-113">0</span></span>                                          |
|  <span data-ttu-id="31498-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="31498-114">Message Text</span></span>   |              <span data-ttu-id="31498-115">无法创建一个或多个 BizTalk 接收位置。</span><span class="sxs-lookup"><span data-stu-id="31498-115">Unable to create one or more BizTalk receive locations.</span></span>               |
  
## <a name="explanation"></a><span data-ttu-id="31498-116">解释</span><span class="sxs-lookup"><span data-stu-id="31498-116">Explanation</span></span>  
 <span data-ttu-id="31498-117">此错误表示 BizTalk WCF 发布向导创建宿主独立 WCF 适配器的接收位置时失败。</span><span class="sxs-lookup"><span data-stu-id="31498-117">This error indicates that the BizTalk WCF Publishing Wizard failed to create receive locations hosting an isolated WCF adapter.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="31498-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="31498-118">User Action</span></span>  
 <span data-ttu-id="31498-119">确保已启动 BizTalk 实例。</span><span class="sxs-lookup"><span data-stu-id="31498-119">Make sure that BizTalk instance is started.</span></span>  
  
 <span data-ttu-id="31498-120">有关创建接收位置的其他信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 文档中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="31498-120">For additional information on creating receive locations, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentation:</span></span>  
  
-   [<span data-ttu-id="31498-121">通过独立 WCF 接收适配器发布 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="31498-121">Publishing WCF Services with the Isolated WCF Receive Adapters</span></span>](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="31498-122">如何配置 Wcf-basichttp 接收位置</span><span class="sxs-lookup"><span data-stu-id="31498-122">How to Configure a WCF-BasicHttp Receive Location</span></span>](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [<span data-ttu-id="31498-123">如何配置 Wcf-wshttp 接收位置</span><span class="sxs-lookup"><span data-stu-id="31498-123">How to Configure a WCF-WSHttp Receive Location</span></span>](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [<span data-ttu-id="31498-124">如何配置 Wcf-customisolated 接收位置</span><span class="sxs-lookup"><span data-stu-id="31498-124">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="31498-125">演练：通过 WCF-BasicHttp 适配器发布 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="31498-125">Walkthrough: Publishing WCF Services with the WCF-BasicHttp Adapter</span></span>](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)