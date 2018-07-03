---
title: 找不到元数据的接收位置 |Microsoft Docs
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
ms.openlocfilehash: d4ae137cc48d5df142c2917b0d40fd2bc95e36dd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011590"
---
# <a name="receive-location-for-metadata-not-found"></a><span data-ttu-id="67d31-102">未找到元数据的接收位置</span><span class="sxs-lookup"><span data-stu-id="67d31-102">Receive location for metadata not found</span></span>
## <a name="details"></a><span data-ttu-id="67d31-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="67d31-103">Details</span></span>  
  
|                 |                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="67d31-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="67d31-104">Product Name</span></span>   |                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                           |
| <span data-ttu-id="67d31-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="67d31-105">Product Version</span></span> |                                      [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                       |
|    <span data-ttu-id="67d31-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="67d31-106">Event ID</span></span>     |                                                                   <span data-ttu-id="67d31-107">0</span><span class="sxs-lookup"><span data-stu-id="67d31-107">0</span></span>                                                                   |
|  <span data-ttu-id="67d31-108">事件源</span><span class="sxs-lookup"><span data-stu-id="67d31-108">Event Source</span></span>   |                                                                   <span data-ttu-id="67d31-109">0</span><span class="sxs-lookup"><span data-stu-id="67d31-109">0</span></span>                                                                   |
|    <span data-ttu-id="67d31-110">组件</span><span class="sxs-lookup"><span data-stu-id="67d31-110">Component</span></span>    |                                                                   <span data-ttu-id="67d31-111">0</span><span class="sxs-lookup"><span data-stu-id="67d31-111">0</span></span>                                                                   |
|  <span data-ttu-id="67d31-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="67d31-112">Symbolic Name</span></span>  |                                                                   <span data-ttu-id="67d31-113">0</span><span class="sxs-lookup"><span data-stu-id="67d31-113">0</span></span>                                                                   |
|  <span data-ttu-id="67d31-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="67d31-114">Message Text</span></span>   | <span data-ttu-id="67d31-115">接收位置"{0}"找不到元数据。</span><span class="sxs-lookup"><span data-stu-id="67d31-115">Receive location "{0}" for metadata not found.</span></span> <span data-ttu-id="67d31-116">（检查 Web.config 中的接收位置映射并验证该接收位置存在。）</span><span class="sxs-lookup"><span data-stu-id="67d31-116">(Check receive location mapping in Web.config and verify the receive location exists.)</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="67d31-117">解释</span><span class="sxs-lookup"><span data-stu-id="67d31-117">Explanation</span></span>  
 <span data-ttu-id="67d31-118">此错误表明发布的独立 WCF 接收位置找不到元数据的相应接收位置。</span><span class="sxs-lookup"><span data-stu-id="67d31-118">This error indicates that a published isolated WCF receive location could not find the corresponding receive location for metadata.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="67d31-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="67d31-119">User Action</span></span>  
 <span data-ttu-id="67d31-120">若要解决此错误，请执行以下： 在 BizTalk 管理控制台中，请确保 Web.config 文件中 receiveLocationName 属性指定的接收位置 BizTalk WCF 发布向导生成存在并且已启动。</span><span class="sxs-lookup"><span data-stu-id="67d31-120">To resolve this error, do the following: In the BizTalk Administration console, make sure that the receive location specified by the receiveLocationName attribute in the Web.config file that the BizTalk WCF Publishing Wizard generated exists and is started.</span></span>  
  
 <span data-ttu-id="67d31-121">有关接收位置的其他信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="67d31-121">For additional information on receive locations, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="67d31-122">发布 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="67d31-122">Publishing WCF Services</span></span>](../core/publishing-wcf-services.md)  
  
-   [<span data-ttu-id="67d31-123">如何配置 Wcf-basichttp 接收位置</span><span class="sxs-lookup"><span data-stu-id="67d31-123">How to Configure a WCF-BasicHttp Receive Location</span></span>](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [<span data-ttu-id="67d31-124">如何配置 Wcf-wshttp 接收位置</span><span class="sxs-lookup"><span data-stu-id="67d31-124">How to Configure a WCF-WSHttp Receive Location</span></span>](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [<span data-ttu-id="67d31-125">如何配置 Wcf-customisolated 接收位置</span><span class="sxs-lookup"><span data-stu-id="67d31-125">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="67d31-126">演练：通过 WCF-NetMsmq 适配器发布 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="67d31-126">Walkthrough: Publishing WCF Services with the WCF-NetMsmq Adapter</span></span>](../core/walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter.md)