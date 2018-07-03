---
title: 单一登录： 事件 10573 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de1ea4e3-5d5f-4d50-8f9a-eff270ac0edb
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf7b2dffb5bd78a3257a400cf2d3cb93978e1d72
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980180"
---
# <a name="single-sign-on-event-10573"></a><span data-ttu-id="45259-102">单一登录： 事件 10573</span><span class="sxs-lookup"><span data-stu-id="45259-102">Single Sign-On: Event 10573</span></span>
## <a name="details"></a><span data-ttu-id="45259-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="45259-103">Details</span></span>  
  
|                 |                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="45259-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="45259-104">Product Name</span></span>   |                                                                                  <span data-ttu-id="45259-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="45259-105">Enterprise Single Sign-On</span></span>                                                                                   |
| <span data-ttu-id="45259-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="45259-106">Product Version</span></span> |                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    <span data-ttu-id="45259-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="45259-107">Event ID</span></span>     |                                                                                            <span data-ttu-id="45259-108">10573</span><span class="sxs-lookup"><span data-stu-id="45259-108">10573</span></span>                                                                                             |
|  <span data-ttu-id="45259-109">事件源</span><span class="sxs-lookup"><span data-stu-id="45259-109">Event Source</span></span>   |                                                                                            <span data-ttu-id="45259-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="45259-110">ENTSSO</span></span>                                                                                            |
|    <span data-ttu-id="45259-111">组件</span><span class="sxs-lookup"><span data-stu-id="45259-111">Component</span></span>    |                                                                                             <span data-ttu-id="45259-112">N/A</span><span class="sxs-lookup"><span data-stu-id="45259-112">N/A</span></span>                                                                                              |
|  <span data-ttu-id="45259-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="45259-113">Symbolic Name</span></span>  |                                                                             <span data-ttu-id="45259-114">SSO_WARN_INVALID_SSO_APP_ADMIN_GROUP</span><span class="sxs-lookup"><span data-stu-id="45259-114">SSO_WARN_INVALID_SSO_APP_ADMIN_GROUP</span></span>                                                                             |
|  <span data-ttu-id="45259-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="45259-115">Message Text</span></span>   | <span data-ttu-id="45259-116">此 SSO 关联管理员帐户无法用于全局信息更新。%r</span><span class="sxs-lookup"><span data-stu-id="45259-116">The SSO Affiliate Administrators account is not valid for global info update.%r</span></span><br /><br /> <span data-ttu-id="45259-117">SSO 关联管理员: %1 %r</span><span class="sxs-lookup"><span data-stu-id="45259-117">SSO Affiliate Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="45259-118">无效帐户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="45259-118">Invalid accounts: %2%r</span></span><br /><br /> <span data-ttu-id="45259-119">错误代码： %3</span><span class="sxs-lookup"><span data-stu-id="45259-119">Error Code: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="45259-120">解释</span><span class="sxs-lookup"><span data-stu-id="45259-120">Explanation</span></span>  
 <span data-ttu-id="45259-121">此 SSO 关联管理员帐户无法用于全局信息更新。</span><span class="sxs-lookup"><span data-stu-id="45259-121">The SSO Affiliate Administrators account is not valid for global info update.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="45259-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="45259-122">User Action</span></span>  
 <span data-ttu-id="45259-123">此警告消息包含 SSO 关联管理员帐户和无效帐户的相关信息。</span><span class="sxs-lookup"><span data-stu-id="45259-123">The warning message contains information regarding the SSO Affiliate Administrators account and the invalid accounts.</span></span> <span data-ttu-id="45259-124">查看此信息，进行任何必要的更正，然后重试更新。</span><span class="sxs-lookup"><span data-stu-id="45259-124">Review this information, make any necessary corrections, and try the update again.</span></span>