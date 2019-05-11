---
title: 单一登录：事件 11040 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e6ccdc06-9677-4454-ae2c-8dde78d6f3f8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a071aa4959aaf8668a0713221904a1a612d0a417
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401010"
---
# <a name="single-sign-on-event-11040"></a><span data-ttu-id="b1316-102">单一登录：事件 11040</span><span class="sxs-lookup"><span data-stu-id="b1316-102">Single Sign-On: Event 11040</span></span>
## <a name="details"></a><span data-ttu-id="b1316-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="b1316-103">Details</span></span>  
  
|                 |                                                                                                                                                             |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b1316-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="b1316-104">Product Name</span></span>   |                                                                  <span data-ttu-id="b1316-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="b1316-105">Enterprise Single Sign-On</span></span>                                                                  |
| <span data-ttu-id="b1316-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="b1316-106">Product Version</span></span> |                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                  |
|    <span data-ttu-id="b1316-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="b1316-107">Event ID</span></span>     |                                                                            <span data-ttu-id="b1316-108">11040</span><span class="sxs-lookup"><span data-stu-id="b1316-108">11040</span></span>                                                                            |
|  <span data-ttu-id="b1316-109">事件源</span><span class="sxs-lookup"><span data-stu-id="b1316-109">Event Source</span></span>   |                                                                           <span data-ttu-id="b1316-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b1316-110">ENTSSO</span></span>                                                                            |
|    <span data-ttu-id="b1316-111">组件</span><span class="sxs-lookup"><span data-stu-id="b1316-111">Component</span></span>    |                                                                             <span data-ttu-id="b1316-112">不可用</span><span class="sxs-lookup"><span data-stu-id="b1316-112">N/A</span></span>                                                                             |
|  <span data-ttu-id="b1316-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="b1316-113">Symbolic Name</span></span>  |                                                                  <span data-ttu-id="b1316-114">SSO_WARN_NETWORK_SERVICE</span><span class="sxs-lookup"><span data-stu-id="b1316-114">SSO_WARN_NETWORK_SERVICE</span></span>                                                                   |
|  <span data-ttu-id="b1316-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="b1316-115">Message Text</span></span>   | <span data-ttu-id="b1316-116">SSO 服务正在网络服务帐户。</span><span class="sxs-lookup"><span data-stu-id="b1316-116">The SSO service is running under the Network Service account.</span></span> <span data-ttu-id="b1316-117">有一些特殊注意事项为此帐户。</span><span class="sxs-lookup"><span data-stu-id="b1316-117">There are some special considerations for this account.</span></span> <span data-ttu-id="b1316-118">请参阅有关 details.%r 文档</span><span class="sxs-lookup"><span data-stu-id="b1316-118">See your documentation for details.%r</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="b1316-119">解释</span><span class="sxs-lookup"><span data-stu-id="b1316-119">Explanation</span></span>  
 <span data-ttu-id="b1316-120">SSO 服务正在网络服务帐户。</span><span class="sxs-lookup"><span data-stu-id="b1316-120">The SSO service is running under the Network Service account.</span></span> <span data-ttu-id="b1316-121">有一些特殊注意事项为此帐户。</span><span class="sxs-lookup"><span data-stu-id="b1316-121">There are some special considerations for this account.</span></span> <span data-ttu-id="b1316-122">例如，重新启动后需要，则添加网络服务帐户。</span><span class="sxs-lookup"><span data-stu-id="b1316-122">For example, a reboot is required after adding a Network Service account.</span></span> <span data-ttu-id="b1316-123">此外下一项网络服务, 运行帐户会限制您只能在非常有限的情况中运行。</span><span class="sxs-lookup"><span data-stu-id="b1316-123">Also, running under a Network Service account restricts you to running in very limited scenarios.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b1316-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="b1316-124">User Action</span></span>  
 <span data-ttu-id="b1316-125">有关详细信息，请参阅[SSO 安全建议](../core/sso-security-recommendations.md)。</span><span class="sxs-lookup"><span data-stu-id="b1316-125">For more information, see [SSO Security Recommendations](../core/sso-security-recommendations.md).</span></span>