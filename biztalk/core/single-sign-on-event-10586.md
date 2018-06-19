---
title: 单一登录： 事件 10586 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7d480e9-dc34-44ac-9272-0caf80237bd9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 124ed0a722d0da0f21722f3b337c8bb938068b24
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270709"
---
# <a name="single-sign-on-event-10586"></a><span data-ttu-id="6111e-102">单一登录： 事件 10586</span><span class="sxs-lookup"><span data-stu-id="6111e-102">Single Sign-On: Event 10586</span></span>
## <a name="details"></a><span data-ttu-id="6111e-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="6111e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6111e-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="6111e-104">Product Name</span></span>|<span data-ttu-id="6111e-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="6111e-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="6111e-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="6111e-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="6111e-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="6111e-107">Event ID</span></span>|<span data-ttu-id="6111e-108">10586</span><span class="sxs-lookup"><span data-stu-id="6111e-108">10586</span></span>|  
|<span data-ttu-id="6111e-109">事件源</span><span class="sxs-lookup"><span data-stu-id="6111e-109">Event Source</span></span>|<span data-ttu-id="6111e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="6111e-110">ENTSSO</span></span>|  
|<span data-ttu-id="6111e-111">组件</span><span class="sxs-lookup"><span data-stu-id="6111e-111">Component</span></span>|<span data-ttu-id="6111e-112">N/A</span><span class="sxs-lookup"><span data-stu-id="6111e-112">N/A</span></span>|  
|<span data-ttu-id="6111e-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="6111e-113">Symbolic Name</span></span>|<span data-ttu-id="6111e-114">SSO_WARN_CRED_CACHE_OFF</span><span class="sxs-lookup"><span data-stu-id="6111e-114">SSO_WARN_CRED_CACHE_OFF</span></span>|  
|<span data-ttu-id="6111e-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="6111e-115">Message Text</span></span>|<span data-ttu-id="6111e-116">此 SSO 服务器已禁用凭据缓存。</span><span class="sxs-lookup"><span data-stu-id="6111e-116">The credential cache has been disabled for this SSO server.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6111e-117">解释</span><span class="sxs-lookup"><span data-stu-id="6111e-117">Explanation</span></span>  
 <span data-ttu-id="6111e-118">已禁用凭据缓存；而通常情况下是启用凭据缓存的。</span><span class="sxs-lookup"><span data-stu-id="6111e-118">The credential cache, which is generally enabled, has been disabled.</span></span> <span data-ttu-id="6111e-119">只有系统管理员可以启用或禁用凭据缓存。</span><span class="sxs-lookup"><span data-stu-id="6111e-119">Only a system administrator can enable or disable the credential cache.</span></span> <span data-ttu-id="6111e-120">禁用凭据缓存有时将导致 ENTSSO 系统出现更多当前凭据，虽然这会降低性能。</span><span class="sxs-lookup"><span data-stu-id="6111e-120">Disabling the credential cache will sometimes result in more current credentials from the ENTSSO system, although it could slow down peformance.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6111e-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="6111e-121">User Action</span></span>  
 <span data-ttu-id="6111e-122">若要重新启用凭据缓存，请参阅中的 Afflilate 应用程序属性表[SSO Affiliate 应用程序](../core/sso-affiliate-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="6111e-122">To re-enable the credential cache, see the Afflilate Application Properties table in [SSO Affiliate Applications](../core/sso-affiliate-applications.md).</span></span>