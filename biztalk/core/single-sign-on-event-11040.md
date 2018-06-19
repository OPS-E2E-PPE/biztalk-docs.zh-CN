---
title: 单一登录： 事件 11040 |Microsoft 文档
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
ms.openlocfilehash: b9eafbbe1c0cbcb0db96c94d072ed511e69b2d6e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276909"
---
# <a name="single-sign-on-event-11040"></a><span data-ttu-id="d6c62-102">单一登录： 事件 11040</span><span class="sxs-lookup"><span data-stu-id="d6c62-102">Single Sign-On: Event 11040</span></span>
## <a name="details"></a><span data-ttu-id="d6c62-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="d6c62-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d6c62-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="d6c62-104">Product Name</span></span>|<span data-ttu-id="d6c62-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="d6c62-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="d6c62-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="d6c62-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="d6c62-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d6c62-107">Event ID</span></span>|<span data-ttu-id="d6c62-108">11040</span><span class="sxs-lookup"><span data-stu-id="d6c62-108">11040</span></span>|  
|<span data-ttu-id="d6c62-109">事件源</span><span class="sxs-lookup"><span data-stu-id="d6c62-109">Event Source</span></span>|<span data-ttu-id="d6c62-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d6c62-110">ENTSSO</span></span>|  
|<span data-ttu-id="d6c62-111">组件</span><span class="sxs-lookup"><span data-stu-id="d6c62-111">Component</span></span>|<span data-ttu-id="d6c62-112">N/A</span><span class="sxs-lookup"><span data-stu-id="d6c62-112">N/A</span></span>|  
|<span data-ttu-id="d6c62-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="d6c62-113">Symbolic Name</span></span>|<span data-ttu-id="d6c62-114">SSO_WARN_NETWORK_SERVICE</span><span class="sxs-lookup"><span data-stu-id="d6c62-114">SSO_WARN_NETWORK_SERVICE</span></span>|  
|<span data-ttu-id="d6c62-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="d6c62-115">Message Text</span></span>|<span data-ttu-id="d6c62-116">SSO 服务在网络服务帐户下运行。</span><span class="sxs-lookup"><span data-stu-id="d6c62-116">The SSO service is running under the Network Service account.</span></span> <span data-ttu-id="d6c62-117">此帐户有一些特殊的注意事项。</span><span class="sxs-lookup"><span data-stu-id="d6c62-117">There are some special considerations for this account.</span></span> <span data-ttu-id="d6c62-118">有关详细信息，请参阅您的文档。%r</span><span class="sxs-lookup"><span data-stu-id="d6c62-118">See your documentation for details.%r</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d6c62-119">解释</span><span class="sxs-lookup"><span data-stu-id="d6c62-119">Explanation</span></span>  
 <span data-ttu-id="d6c62-120">SSO 服务在网络服务帐户下运行。</span><span class="sxs-lookup"><span data-stu-id="d6c62-120">The SSO service is running under the Network Service account.</span></span> <span data-ttu-id="d6c62-121">此帐户有一些特殊的注意事项。</span><span class="sxs-lookup"><span data-stu-id="d6c62-121">There are some special considerations for this account.</span></span> <span data-ttu-id="d6c62-122">例如，添加网络服务帐户后需要重新启动。</span><span class="sxs-lookup"><span data-stu-id="d6c62-122">For example, a reboot is required after adding a Network Service account.</span></span> <span data-ttu-id="d6c62-123">同时，在网络服务帐户下运行会限制您只能在非常有限的情况下运行。</span><span class="sxs-lookup"><span data-stu-id="d6c62-123">Also, running under a Network Service account restricts you to running in very limited scenarios.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d6c62-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="d6c62-124">User Action</span></span>  
 <span data-ttu-id="d6c62-125">有关详细信息，请参阅[SSO 安全建议](../core/sso-security-recommendations.md)。</span><span class="sxs-lookup"><span data-stu-id="d6c62-125">For more information, see [SSO Security Recommendations](../core/sso-security-recommendations.md).</span></span>