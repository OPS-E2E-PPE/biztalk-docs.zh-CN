---
title: 无法注册独立的接收器地址 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 313b436a-d7c5-4b46-bfe3-bbad0d8efe42
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e33aa3e48cd92b3d190289c1d65bf3a3bb7c7907
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986614"
---
# <a name="failed-to-register-isolated-receiver-for-address"></a><span data-ttu-id="fbbde-102">无法为地址注册独立的接收器</span><span class="sxs-lookup"><span data-stu-id="fbbde-102">Failed to register isolated receiver for address</span></span>
## <a name="details"></a><span data-ttu-id="fbbde-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="fbbde-103">Details</span></span>  
  
|                 |                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="fbbde-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="fbbde-104">Product Name</span></span>   |           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]            |
| <span data-ttu-id="fbbde-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="fbbde-105">Product Version</span></span> |                       [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                        |
|    <span data-ttu-id="fbbde-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="fbbde-106">Event ID</span></span>     |                                                    <span data-ttu-id="fbbde-107">0</span><span class="sxs-lookup"><span data-stu-id="fbbde-107">0</span></span>                                                    |
|  <span data-ttu-id="fbbde-108">事件源</span><span class="sxs-lookup"><span data-stu-id="fbbde-108">Event Source</span></span>   |                                                    <span data-ttu-id="fbbde-109">0</span><span class="sxs-lookup"><span data-stu-id="fbbde-109">0</span></span>                                                    |
|    <span data-ttu-id="fbbde-110">组件</span><span class="sxs-lookup"><span data-stu-id="fbbde-110">Component</span></span>    |                                                    <span data-ttu-id="fbbde-111">0</span><span class="sxs-lookup"><span data-stu-id="fbbde-111">0</span></span>                                                    |
|  <span data-ttu-id="fbbde-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="fbbde-112">Symbolic Name</span></span>  |                                                    <span data-ttu-id="fbbde-113">0</span><span class="sxs-lookup"><span data-stu-id="fbbde-113">0</span></span>                                                    |
|  <span data-ttu-id="fbbde-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="fbbde-114">Message Text</span></span>   | <span data-ttu-id="fbbde-115">未能注册独立的接收器，地址为"{0}"; 接收位置不存在或已禁用。</span><span class="sxs-lookup"><span data-stu-id="fbbde-115">Failed to register isolated receiver for address "{0}"; receive location does not exist or is disabled.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="fbbde-116">解释</span><span class="sxs-lookup"><span data-stu-id="fbbde-116">Explanation</span></span>  
 <span data-ttu-id="fbbde-117">此错误表明发布的独立 WCF 接收位置找不到相应的接收位置。</span><span class="sxs-lookup"><span data-stu-id="fbbde-117">This error indicates that a published isolated WCF receive location could not find the corresponding receive location.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fbbde-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="fbbde-118">User Action</span></span>  
 <span data-ttu-id="fbbde-119">若要解决此错误，请执行以下： 在 BizTalk 管理控制台中，请确保 Web.config 文件中 receiveLocationName 属性指定的接收位置 BizTalk WCF 服务发布向导生成存在并且已启动。</span><span class="sxs-lookup"><span data-stu-id="fbbde-119">To resolve this error, do the following: In the BizTalk Administration console, make sure that the receive location specified by the receiveLocationName attribute in the Web.config file that the BizTalk WCF Services Publishing Wizard generated exists and is started.</span></span>  
  
 <span data-ttu-id="fbbde-120">有关创建接收位置的其他信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="fbbde-120">For additional information on creating receive locations, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="fbbde-121">通过独立 WCF 接收适配器发布 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="fbbde-121">Publishing WCF Services with the Isolated WCF Receive Adapters</span></span>](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="fbbde-122">如何配置 Wcf-basichttp 接收位置</span><span class="sxs-lookup"><span data-stu-id="fbbde-122">How to Configure a WCF-BasicHttp Receive Location</span></span>](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [<span data-ttu-id="fbbde-123">如何配置 Wcf-wshttp 接收位置</span><span class="sxs-lookup"><span data-stu-id="fbbde-123">How to Configure a WCF-WSHttp Receive Location</span></span>](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [<span data-ttu-id="fbbde-124">如何配置 Wcf-customisolated 接收位置</span><span class="sxs-lookup"><span data-stu-id="fbbde-124">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="fbbde-125">演练：通过 WCF-BasicHttp 适配器发布 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="fbbde-125">Walkthrough: Publishing WCF Services with the WCF-BasicHttp Adapter</span></span>](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)