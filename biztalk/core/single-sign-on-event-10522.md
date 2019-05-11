---
title: 单一登录：Event 10522 | Microsoft Docs
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
ms.openlocfilehash: ac9347492793170faed39be91f2925e0ffdc1cdc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393024"
---
# <a name="single-sign-on-event-10522"></a><span data-ttu-id="288bf-102">单一登录：事件 10522</span><span class="sxs-lookup"><span data-stu-id="288bf-102">Single Sign-On: Event 10522</span></span>
## <a name="details"></a><span data-ttu-id="288bf-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="288bf-103">Details</span></span>  

|                 |                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------|
|  <span data-ttu-id="288bf-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="288bf-104">Product Name</span></span>   |                                   <span data-ttu-id="288bf-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="288bf-105">Enterprise Single Sign-On</span></span>                                   |
| <span data-ttu-id="288bf-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="288bf-106">Product Version</span></span> |                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                   |
|    <span data-ttu-id="288bf-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="288bf-107">Event ID</span></span>     |                                             <span data-ttu-id="288bf-108">10522</span><span class="sxs-lookup"><span data-stu-id="288bf-108">10522</span></span>                                             |
|  <span data-ttu-id="288bf-109">事件源</span><span class="sxs-lookup"><span data-stu-id="288bf-109">Event Source</span></span>   |                                            <span data-ttu-id="288bf-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="288bf-110">ENTSSO</span></span>                                             |
|    <span data-ttu-id="288bf-111">组件</span><span class="sxs-lookup"><span data-stu-id="288bf-111">Component</span></span>    |                                              <span data-ttu-id="288bf-112">N\A</span><span class="sxs-lookup"><span data-stu-id="288bf-112">N\A</span></span>                                              |
|  <span data-ttu-id="288bf-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="288bf-113">Symbolic Name</span></span>  |                                      <span data-ttu-id="288bf-114">SSO_ERROR_REENCRYPT</span><span class="sxs-lookup"><span data-stu-id="288bf-114">SSO_ERROR_REENCRYPT</span></span>                                      |
|  <span data-ttu-id="288bf-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="288bf-115">Message Text</span></span>   | <span data-ttu-id="288bf-116">SSO 数据库重新加密失败。</span><span class="sxs-lookup"><span data-stu-id="288bf-116">SSO database re-encryption failed.</span></span> <span data-ttu-id="288bf-117">将在重试 %1 minutes.%r</span><span class="sxs-lookup"><span data-stu-id="288bf-117">Will try again in %1 minutes.%r</span></span><br /><br /> <span data-ttu-id="288bf-118">错误代码： %2</span><span class="sxs-lookup"><span data-stu-id="288bf-118">Error Code: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="288bf-119">解释</span><span class="sxs-lookup"><span data-stu-id="288bf-119">Explanation</span></span>  
 <span data-ttu-id="288bf-120">此错误事件表示 SSO 数据库重新加密失败。</span><span class="sxs-lookup"><span data-stu-id="288bf-120">This Error event indicates that the SSO database re-encryption failed.</span></span> <span data-ttu-id="288bf-121">SSO 服务启动时在主服务器上，的首先就是检查是否有任何内容仍使用之前的主密钥加密的 SSO 数据库中。</span><span class="sxs-lookup"><span data-stu-id="288bf-121">When the SSO service starts on the master secret server, the first thing it does is to check if there is anything in the SSO database still encrypted with the previous master secret.</span></span> <span data-ttu-id="288bf-122">如果找到任何内容，它会解密 （使用上一个密钥） 此信息并重新对它使用当前的主密钥进行加密。</span><span class="sxs-lookup"><span data-stu-id="288bf-122">If it finds anything, it decrypts that information (using the previous secret) and re-encrypts it using the current master secret.</span></span> <span data-ttu-id="288bf-123">如果出于任何原因，此过程失败，会发出此事件消息。</span><span class="sxs-lookup"><span data-stu-id="288bf-123">If for any reason this process fails, then this event message is issued.</span></span>  

## <a name="user-action"></a><span data-ttu-id="288bf-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="288bf-124">User Action</span></span>  
 <span data-ttu-id="288bf-125">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="288bf-125">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="288bf-126">检查错误代码，以确定错误的根本原因可能是什么。</span><span class="sxs-lookup"><span data-stu-id="288bf-126">Check the error code to determine what the underlying cause of the error might be.</span></span> <span data-ttu-id="288bf-127">这可能是网络或数据库问题。</span><span class="sxs-lookup"><span data-stu-id="288bf-127">This could be a network or database issue.</span></span> <span data-ttu-id="288bf-128">如果它是间歇性的则不需要操作，因为将一小段延迟后再次尝试重新加密。</span><span class="sxs-lookup"><span data-stu-id="288bf-128">If it is intermittent, then no action is required because re-encryption will be attempted again after a short delay.</span></span> <span data-ttu-id="288bf-129">如果此问题不是间歇性的停止 SSO 服务，并尝试解决此问题。</span><span class="sxs-lookup"><span data-stu-id="288bf-129">If the issue is not intermittent, stop the SSO service and attempt to resolve the issue.</span></span> <span data-ttu-id="288bf-130">一旦问题解决后，然后重启 SSO 服务，则重新启动 SSO 服务将自动执行重新加密。</span><span class="sxs-lookup"><span data-stu-id="288bf-130">Once the issue is resolved then restart the SSO service, Restarting the SSO service will automatically perform the re-encryption.</span></span>  

  <span data-ttu-id="288bf-131">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="288bf-131">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="288bf-132">如何显示 SSO 数据库信息</span><span class="sxs-lookup"><span data-stu-id="288bf-132">How to Display the SSO Database Information</span></span>](../core/how-to-display-the-sso-database-information.md)  

- [<span data-ttu-id="288bf-133">主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="288bf-133">Master Secret Server</span></span>](../core/master-secret-server.md)
