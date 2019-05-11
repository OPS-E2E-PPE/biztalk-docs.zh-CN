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
ms.openlocfilehash: 8910b5877e05d72e52707c93b0fb0bf99ae78cd9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398239"
---
# <a name="receive-location-for-metadata-not-found"></a><span data-ttu-id="9cc19-102">未找到元数据的接收位置</span><span class="sxs-lookup"><span data-stu-id="9cc19-102">Receive location for metadata not found</span></span>
## <a name="details"></a><span data-ttu-id="9cc19-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="9cc19-103">Details</span></span>  
  
|                 |                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="9cc19-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="9cc19-104">Product Name</span></span>   |                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                           |
| <span data-ttu-id="9cc19-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="9cc19-105">Product Version</span></span> |                                      [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                       |
|    <span data-ttu-id="9cc19-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="9cc19-106">Event ID</span></span>     |                                                                   <span data-ttu-id="9cc19-107">0</span><span class="sxs-lookup"><span data-stu-id="9cc19-107">0</span></span>                                                                   |
|  <span data-ttu-id="9cc19-108">事件源</span><span class="sxs-lookup"><span data-stu-id="9cc19-108">Event Source</span></span>   |                                                                   <span data-ttu-id="9cc19-109">0</span><span class="sxs-lookup"><span data-stu-id="9cc19-109">0</span></span>                                                                   |
|    <span data-ttu-id="9cc19-110">组件</span><span class="sxs-lookup"><span data-stu-id="9cc19-110">Component</span></span>    |                                                                   <span data-ttu-id="9cc19-111">0</span><span class="sxs-lookup"><span data-stu-id="9cc19-111">0</span></span>                                                                   |
|  <span data-ttu-id="9cc19-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="9cc19-112">Symbolic Name</span></span>  |                                                                   <span data-ttu-id="9cc19-113">0</span><span class="sxs-lookup"><span data-stu-id="9cc19-113">0</span></span>                                                                   |
|  <span data-ttu-id="9cc19-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="9cc19-114">Message Text</span></span>   | <span data-ttu-id="9cc19-115">接收位置"{0}"找不到元数据。</span><span class="sxs-lookup"><span data-stu-id="9cc19-115">Receive location "{0}" for metadata not found.</span></span> <span data-ttu-id="9cc19-116">（检查 Web.config 中的接收位置映射并验证该接收位置存在。）</span><span class="sxs-lookup"><span data-stu-id="9cc19-116">(Check receive location mapping in Web.config and verify the receive location exists.)</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="9cc19-117">解释</span><span class="sxs-lookup"><span data-stu-id="9cc19-117">Explanation</span></span>  
 <span data-ttu-id="9cc19-118">此错误表明发布的独立的 WCF 接收位置找不到相应的接收位置的元数据。</span><span class="sxs-lookup"><span data-stu-id="9cc19-118">This error indicates that a published isolated WCF receive location could not find the corresponding receive location for metadata.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9cc19-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="9cc19-119">User Action</span></span>  
 <span data-ttu-id="9cc19-120">若要解决此错误，请执行以下操作：在 BizTalk 管理控制台中，请确保 Web.config 文件中 receiveLocationName 属性指定的接收位置 BizTalk WCF 发布向导生成存在并且已启动。</span><span class="sxs-lookup"><span data-stu-id="9cc19-120">To resolve this error, do the following: In the BizTalk Administration console, make sure that the receive location specified by the receiveLocationName attribute in the Web.config file that the BizTalk WCF Publishing Wizard generated exists and is started.</span></span>  
  
 <span data-ttu-id="9cc19-121">有关其他信息接收位置，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="9cc19-121">For additional information on receive locations, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="9cc19-122">发布 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="9cc19-122">Publishing WCF Services</span></span>](../core/publishing-wcf-services.md)  
  
-   [<span data-ttu-id="9cc19-123">如何配置 Wcf-basichttp 接收位置</span><span class="sxs-lookup"><span data-stu-id="9cc19-123">How to Configure a WCF-BasicHttp Receive Location</span></span>](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [<span data-ttu-id="9cc19-124">如何配置 Wcf-wshttp 接收位置</span><span class="sxs-lookup"><span data-stu-id="9cc19-124">How to Configure a WCF-WSHttp Receive Location</span></span>](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [<span data-ttu-id="9cc19-125">如何配置 Wcf-customisolated 接收位置</span><span class="sxs-lookup"><span data-stu-id="9cc19-125">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="9cc19-126">演练：使用 Wcf-netmsmq 适配器发布 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="9cc19-126">Walkthrough: Publishing WCF Services with the WCF-NetMsmq Adapter</span></span>](../core/walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter.md)