---
title: "单一登录： 事件 10742 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba62f878-ed12-421f-81ea-9285b2624fe9
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abb3acb03e60d1d7a7e705ac8b36aa5157616f6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10742"></a><span data-ttu-id="1e04b-102">单一登录： 事件 10742</span><span class="sxs-lookup"><span data-stu-id="1e04b-102">Single Sign-On: Event 10742</span></span>
## <a name="details"></a><span data-ttu-id="1e04b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="1e04b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1e04b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="1e04b-104">Product Name</span></span>|<span data-ttu-id="1e04b-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="1e04b-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="1e04b-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="1e04b-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="1e04b-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1e04b-107">Event ID</span></span>|<span data-ttu-id="1e04b-108">10742</span><span class="sxs-lookup"><span data-stu-id="1e04b-108">10742</span></span>|  
|<span data-ttu-id="1e04b-109">事件源</span><span class="sxs-lookup"><span data-stu-id="1e04b-109">Event Source</span></span>|<span data-ttu-id="1e04b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1e04b-110">ENTSSO</span></span>|  
|<span data-ttu-id="1e04b-111">组件</span><span class="sxs-lookup"><span data-stu-id="1e04b-111">Component</span></span>|<span data-ttu-id="1e04b-112">N\A</span><span class="sxs-lookup"><span data-stu-id="1e04b-112">N\A</span></span>|  
|<span data-ttu-id="1e04b-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="1e04b-113">Symbolic Name</span></span>|<span data-ttu-id="1e04b-114">SSO_WARN_NO_UPDATE_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="1e04b-114">SSO_WARN_NO_UPDATE_ADAPTER</span></span>|  
|<span data-ttu-id="1e04b-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="1e04b-115">Message Text</span></span>|<span data-ttu-id="1e04b-116">若要更新适配器，客户端用户必须是 SSO 管理员帐户或应用程序管理员帐户的成员。%r</span><span class="sxs-lookup"><span data-stu-id="1e04b-116">The client user must be a member of the SSO Administrators account or the Application Administrators account to update the adapter.%r</span></span><br /><br /> <span data-ttu-id="1e04b-117">客户端用户: %1 %r</span><span class="sxs-lookup"><span data-stu-id="1e04b-117">Client User: %1%r</span></span><br /><br /> <span data-ttu-id="1e04b-118">SSO Administrators: %2 %r</span><span class="sxs-lookup"><span data-stu-id="1e04b-118">SSO Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="1e04b-119">Application Administrators: %3 %r</span><span class="sxs-lookup"><span data-stu-id="1e04b-119">Application Administrators: %3%r</span></span><br /><br /> <span data-ttu-id="1e04b-120">适配器: %4 %r</span><span class="sxs-lookup"><span data-stu-id="1e04b-120">Adapter: %4%r</span></span><br /><br /> <span data-ttu-id="1e04b-121">错误代码： %5</span><span class="sxs-lookup"><span data-stu-id="1e04b-121">Error Code: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1e04b-122">解释</span><span class="sxs-lookup"><span data-stu-id="1e04b-122">Explanation</span></span>  
 <span data-ttu-id="1e04b-123">此警告事件表示进行了更新指定适配器的尝试，但是无法完成，因为所使用的用户帐户不是 SSO 管理员帐户或应用程序管理员帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="1e04b-123">This Warning event indicates that an attempt to update the specified adapter was made, but could not be completed because the user account used is not a member of the SSO Administrators account or the Application Administrators account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1e04b-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="1e04b-124">User Action</span></span>  
 <span data-ttu-id="1e04b-125">若要解决此警告问题，请执行以下一项或多项操作：</span><span class="sxs-lookup"><span data-stu-id="1e04b-125">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="1e04b-126">将用户帐户添加到 SSO 管理员帐户或应用程序管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="1e04b-126">Add user account to the SSO Administrators account or the Application Administrators account.</span></span>  
  
-   <span data-ttu-id="1e04b-127">重试更新。</span><span class="sxs-lookup"><span data-stu-id="1e04b-127">Retry update.</span></span>  
  
 <span data-ttu-id="1e04b-128">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="1e04b-128">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="1e04b-129">如何管理密码同步</span><span class="sxs-lookup"><span data-stu-id="1e04b-129">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)