---
title: 单一登录： 事件 10532 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae2112bc-b53c-4d99-9dc1-a2f55dda4665
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7a9d477ec54a3c959f2afdf4c687c65b88523ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269749"
---
# <a name="single-sign-on-event-10532"></a><span data-ttu-id="4848a-102">单一登录： 事件 10532</span><span class="sxs-lookup"><span data-stu-id="4848a-102">Single Sign-On: Event 10532</span></span>
## <a name="details"></a><span data-ttu-id="4848a-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="4848a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4848a-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="4848a-104">Product Name</span></span>|<span data-ttu-id="4848a-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="4848a-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="4848a-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="4848a-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="4848a-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="4848a-107">Event ID</span></span>|<span data-ttu-id="4848a-108">10532</span><span class="sxs-lookup"><span data-stu-id="4848a-108">10532</span></span>|  
|<span data-ttu-id="4848a-109">事件源</span><span class="sxs-lookup"><span data-stu-id="4848a-109">Event Source</span></span>|<span data-ttu-id="4848a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="4848a-110">ENTSSO</span></span>|  
|<span data-ttu-id="4848a-111">组件</span><span class="sxs-lookup"><span data-stu-id="4848a-111">Component</span></span>|<span data-ttu-id="4848a-112">CO</span><span class="sxs-lookup"><span data-stu-id="4848a-112">CO</span></span>|  
|<span data-ttu-id="4848a-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="4848a-113">Symbolic Name</span></span>|<span data-ttu-id="4848a-114">SSO_WARN_LOST_SECRET_SERVER</span><span class="sxs-lookup"><span data-stu-id="4848a-114">SSO_WARN_LOST_SECRET_SERVER</span></span>|  
|<span data-ttu-id="4848a-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="4848a-115">Message Text</span></span>|<span data-ttu-id="4848a-116">检索主密钥失败。</span><span class="sxs-lookup"><span data-stu-id="4848a-116">Failed to retrieve master secrets.</span></span> <span data-ttu-id="4848a-117">请确保主密钥服务器名称正确且该服务器可用。%r</span><span class="sxs-lookup"><span data-stu-id="4848a-117">Verify that the master secret server name is correct and that it is available.%r</span></span><br /><br /> <span data-ttu-id="4848a-118">机密的服务器名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="4848a-118">Secret Server Name: %1%r</span></span><br /><br /> <span data-ttu-id="4848a-119">错误代码： %2</span><span class="sxs-lookup"><span data-stu-id="4848a-119">Error Code: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4848a-120">解释</span><span class="sxs-lookup"><span data-stu-id="4848a-120">Explanation</span></span>  
 <span data-ttu-id="4848a-121">此警告事件表示，获得主密钥的请求失败。</span><span class="sxs-lookup"><span data-stu-id="4848a-121">This Warning event indicates that a request to get the master secret has failed.</span></span> <span data-ttu-id="4848a-122">这可能是因为企业单一登录服务未在服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="4848a-122">This might be because the Enterprise Single Sign-On service is not running on the server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4848a-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="4848a-123">User Action</span></span>  
 <span data-ttu-id="4848a-124">若要解决此警告问题，请执行以下一项或多项操作：</span><span class="sxs-lookup"><span data-stu-id="4848a-124">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="4848a-125">请检查关联的事件或错误的应用程序事件日志。</span><span class="sxs-lookup"><span data-stu-id="4848a-125">Check the Application event log for associated events or errors.</span></span>  
  
-   <span data-ttu-id="4848a-126">验证主密钥服务器名称是否正确。</span><span class="sxs-lookup"><span data-stu-id="4848a-126">Verify the master secret server name is correct.</span></span>  
  
-   <span data-ttu-id="4848a-127">验证主密钥服务器是否联机，以及企业单一登录服务是否正在运行。</span><span class="sxs-lookup"><span data-stu-id="4848a-127">Verify the master secret server is online and that the Enterprise Single Sign-On service is running.</span></span>  
  
 <span data-ttu-id="4848a-128">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="4848a-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="4848a-129">如何生成主密钥</span><span class="sxs-lookup"><span data-stu-id="4848a-129">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  
  
-   [<span data-ttu-id="4848a-130">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="4848a-130">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)