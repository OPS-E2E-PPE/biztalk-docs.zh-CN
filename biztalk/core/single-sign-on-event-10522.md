---
title: 单一登录： 事件 10522 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd634a57-01dc-44bd-bcf9-668689db7b77
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b56999d7898af01d0009a7722d78aed0dbf5dbf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271877"
---
# <a name="single-sign-on-event-10522"></a><span data-ttu-id="7069a-102">单一登录： 事件 10522</span><span class="sxs-lookup"><span data-stu-id="7069a-102">Single Sign-On: Event 10522</span></span>
## <a name="details"></a><span data-ttu-id="7069a-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="7069a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7069a-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="7069a-104">Product Name</span></span>|<span data-ttu-id="7069a-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="7069a-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="7069a-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="7069a-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="7069a-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7069a-107">Event ID</span></span>|<span data-ttu-id="7069a-108">10522</span><span class="sxs-lookup"><span data-stu-id="7069a-108">10522</span></span>|  
|<span data-ttu-id="7069a-109">事件源</span><span class="sxs-lookup"><span data-stu-id="7069a-109">Event Source</span></span>|<span data-ttu-id="7069a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="7069a-110">ENTSSO</span></span>|  
|<span data-ttu-id="7069a-111">组件</span><span class="sxs-lookup"><span data-stu-id="7069a-111">Component</span></span>|<span data-ttu-id="7069a-112">N\A</span><span class="sxs-lookup"><span data-stu-id="7069a-112">N\A</span></span>|  
|<span data-ttu-id="7069a-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="7069a-113">Symbolic Name</span></span>|<span data-ttu-id="7069a-114">SSO_ERROR_REENCRYPT</span><span class="sxs-lookup"><span data-stu-id="7069a-114">SSO_ERROR_REENCRYPT</span></span>|  
|<span data-ttu-id="7069a-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="7069a-115">Message Text</span></span>|<span data-ttu-id="7069a-116">SSO 数据库重新加密失败。</span><span class="sxs-lookup"><span data-stu-id="7069a-116">SSO database re-encryption failed.</span></span> <span data-ttu-id="7069a-117">将在 %1%minutes.%r 试</span><span class="sxs-lookup"><span data-stu-id="7069a-117">Will try again in %1 minutes.%r</span></span><br /><br /> <span data-ttu-id="7069a-118">错误代码： %2</span><span class="sxs-lookup"><span data-stu-id="7069a-118">Error Code: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7069a-119">解释</span><span class="sxs-lookup"><span data-stu-id="7069a-119">Explanation</span></span>  
 <span data-ttu-id="7069a-120">此错误事件指示 SSO 数据库重新加密失败。</span><span class="sxs-lookup"><span data-stu-id="7069a-120">This Error event indicates that the SSO database re-encryption failed.</span></span> <span data-ttu-id="7069a-121">SSO 服务启动时在主密钥服务器，它执行的第一个操作是检查是否有任何内容仍使用以前的主密钥加密的 SSO 数据库中。</span><span class="sxs-lookup"><span data-stu-id="7069a-121">When the SSO service starts on the master secret server, the first thing it does is to check if there is anything in the SSO database still encrypted with the previous master secret.</span></span> <span data-ttu-id="7069a-122">如果找到任何内容，则系统会解密此信息（使用上一个密钥）并使用当前主密钥对其重新加密。</span><span class="sxs-lookup"><span data-stu-id="7069a-122">If it finds anything, it decrypts that information (using the previous secret) and re-encrypts it using the current master secret.</span></span> <span data-ttu-id="7069a-123">如果由于某种原因这一过程失败，则系统会发出此事件消息。</span><span class="sxs-lookup"><span data-stu-id="7069a-123">If for any reason this process fails, then this event message is issued.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7069a-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="7069a-124">User Action</span></span>  
 <span data-ttu-id="7069a-125">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7069a-125">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="7069a-126">检查错误代码，以确定错误的根本原因可能是什么。</span><span class="sxs-lookup"><span data-stu-id="7069a-126">Check the error code to determine what the underlying cause of the error might be.</span></span> <span data-ttu-id="7069a-127">这可能是网络或数据库的问题。</span><span class="sxs-lookup"><span data-stu-id="7069a-127">This could be a network or database issue.</span></span> <span data-ttu-id="7069a-128">如果它是间歇性的然后不不需要任何操作因为将一小段延迟后再次尝试重新加密。</span><span class="sxs-lookup"><span data-stu-id="7069a-128">If it is intermittent, then no action is required because re-encryption will be attempted again after a short delay.</span></span> <span data-ttu-id="7069a-129">如果此问题不是间歇性，停止 SSO 服务，然后尝试解决此问题。</span><span class="sxs-lookup"><span data-stu-id="7069a-129">If the issue is not intermittent, stop the SSO service and attempt to resolve the issue.</span></span> <span data-ttu-id="7069a-130">问题解决后重新启动 SSO 服务。重新启动 SSO 服务将自动执行重新加密。</span><span class="sxs-lookup"><span data-stu-id="7069a-130">Once the issue is resolved then restart the SSO service, Restarting the SSO service will automatically perform the re-encryption.</span></span>  
  
 <span data-ttu-id="7069a-131">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="7069a-131">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="7069a-132">如何显示的 SSO 数据库信息</span><span class="sxs-lookup"><span data-stu-id="7069a-132">How to Display the SSO Database Information</span></span>](../core/how-to-display-the-sso-database-information.md)  
  
-   [<span data-ttu-id="7069a-133">主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="7069a-133">Master Secret Server</span></span>](../core/master-secret-server.md)