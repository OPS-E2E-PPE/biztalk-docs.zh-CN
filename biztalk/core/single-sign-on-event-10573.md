---
title: 单一登录： 事件 10573 |Microsoft 文档
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
ms.openlocfilehash: 39c07ba359c93c4a98211216af1c795340b5801b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270397"
---
# <a name="single-sign-on-event-10573"></a><span data-ttu-id="f6c4a-102">单一登录： 事件 10573</span><span class="sxs-lookup"><span data-stu-id="f6c4a-102">Single Sign-On: Event 10573</span></span>
## <a name="details"></a><span data-ttu-id="f6c4a-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f6c4a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f6c4a-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f6c4a-104">Product Name</span></span>|<span data-ttu-id="f6c4a-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="f6c4a-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="f6c4a-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="f6c4a-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="f6c4a-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f6c4a-107">Event ID</span></span>|<span data-ttu-id="f6c4a-108">10573</span><span class="sxs-lookup"><span data-stu-id="f6c4a-108">10573</span></span>|  
|<span data-ttu-id="f6c4a-109">事件源</span><span class="sxs-lookup"><span data-stu-id="f6c4a-109">Event Source</span></span>|<span data-ttu-id="f6c4a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f6c4a-110">ENTSSO</span></span>|  
|<span data-ttu-id="f6c4a-111">组件</span><span class="sxs-lookup"><span data-stu-id="f6c4a-111">Component</span></span>|<span data-ttu-id="f6c4a-112">N/A</span><span class="sxs-lookup"><span data-stu-id="f6c4a-112">N/A</span></span>|  
|<span data-ttu-id="f6c4a-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="f6c4a-113">Symbolic Name</span></span>|<span data-ttu-id="f6c4a-114">SSO_WARN_INVALID_SSO_APP_ADMIN_GROUP</span><span class="sxs-lookup"><span data-stu-id="f6c4a-114">SSO_WARN_INVALID_SSO_APP_ADMIN_GROUP</span></span>|  
|<span data-ttu-id="f6c4a-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="f6c4a-115">Message Text</span></span>|<span data-ttu-id="f6c4a-116">此 SSO 关联管理员帐户无法用于全局信息更新。%r</span><span class="sxs-lookup"><span data-stu-id="f6c4a-116">The SSO Affiliate Administrators account is not valid for global info update.%r</span></span><br /><br /> <span data-ttu-id="f6c4a-117">SSO 关联管理员: %1 %r</span><span class="sxs-lookup"><span data-stu-id="f6c4a-117">SSO Affiliate Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="f6c4a-118">无效帐户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="f6c4a-118">Invalid accounts: %2%r</span></span><br /><br /> <span data-ttu-id="f6c4a-119">错误代码： %3</span><span class="sxs-lookup"><span data-stu-id="f6c4a-119">Error Code: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f6c4a-120">解释</span><span class="sxs-lookup"><span data-stu-id="f6c4a-120">Explanation</span></span>  
 <span data-ttu-id="f6c4a-121">此 SSO 关联管理员帐户无法用于全局信息更新。</span><span class="sxs-lookup"><span data-stu-id="f6c4a-121">The SSO Affiliate Administrators account is not valid for global info update.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f6c4a-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="f6c4a-122">User Action</span></span>  
 <span data-ttu-id="f6c4a-123">此警告消息包含 SSO 关联管理员帐户和无效帐户的相关信息。</span><span class="sxs-lookup"><span data-stu-id="f6c4a-123">The warning message contains information regarding the SSO Affiliate Administrators account and the invalid accounts.</span></span> <span data-ttu-id="f6c4a-124">查看此信息，进行任何必要的更正，然后重试更新。</span><span class="sxs-lookup"><span data-stu-id="f6c4a-124">Review this information, make any necessary corrections, and try the update again.</span></span>