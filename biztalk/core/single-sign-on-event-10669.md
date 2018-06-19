---
title: 单一登录： 事件 10669 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e88a583d-7385-42dd-841e-aa2d2215dd69
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 334180225d47cb9a86577cab75490ea0b6f2225a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271621"
---
# <a name="single-sign-on-event-10669"></a><span data-ttu-id="b77d9-102">单一登录： 事件 10669</span><span class="sxs-lookup"><span data-stu-id="b77d9-102">Single Sign-On: Event 10669</span></span>
## <a name="details"></a><span data-ttu-id="b77d9-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="b77d9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b77d9-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="b77d9-104">Product Name</span></span>|<span data-ttu-id="b77d9-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="b77d9-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="b77d9-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="b77d9-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="b77d9-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="b77d9-107">Event ID</span></span>|<span data-ttu-id="b77d9-108">10669</span><span class="sxs-lookup"><span data-stu-id="b77d9-108">10669</span></span>|  
|<span data-ttu-id="b77d9-109">事件源</span><span class="sxs-lookup"><span data-stu-id="b77d9-109">Event Source</span></span>|<span data-ttu-id="b77d9-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b77d9-110">ENTSSO</span></span>|  
|<span data-ttu-id="b77d9-111">组件</span><span class="sxs-lookup"><span data-stu-id="b77d9-111">Component</span></span>|<span data-ttu-id="b77d9-112">N\A</span><span class="sxs-lookup"><span data-stu-id="b77d9-112">N\A</span></span>|  
|<span data-ttu-id="b77d9-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="b77d9-113">Symbolic Name</span></span>|<span data-ttu-id="b77d9-114">SSO_WARN_CHANGE_WINDOWS_PASSWORD_FAILED</span><span class="sxs-lookup"><span data-stu-id="b77d9-114">SSO_WARN_CHANGE_WINDOWS_PASSWORD_FAILED</span></span>|  
|<span data-ttu-id="b77d9-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="b77d9-115">Message Text</span></span>|<span data-ttu-id="b77d9-116">无法更改 Windows 密码。%r</span><span class="sxs-lookup"><span data-stu-id="b77d9-116">Failed to change the Windows password.%r</span></span><br /><br /> <span data-ttu-id="b77d9-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="b77d9-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="b77d9-118">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="b77d9-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="b77d9-119">Windows 帐户: %3 %r</span><span class="sxs-lookup"><span data-stu-id="b77d9-119">Windows Account: %3%r</span></span><br /><br /> <span data-ttu-id="b77d9-120">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="b77d9-120">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b77d9-121">解释</span><span class="sxs-lookup"><span data-stu-id="b77d9-121">Explanation</span></span>  
 <span data-ttu-id="b77d9-122">此警告事件表示 SSO 无法更改 Windows 密码。</span><span class="sxs-lookup"><span data-stu-id="b77d9-122">This Warning event indicates that SSO failed to change a Windows password.</span></span> <span data-ttu-id="b77d9-123">SSO 调用 Win32 函数 NetUserChangePassword 函数来更改与映射关联的 Windows 密码。</span><span class="sxs-lookup"><span data-stu-id="b77d9-123">SSO calls the Win32 function NetUserChangePassword function to change the Windows password associated with the mapping.</span></span> <span data-ttu-id="b77d9-124">如果调用此函数失败，则系统会发出此错误消息。</span><span class="sxs-lookup"><span data-stu-id="b77d9-124">If this function fails this error message is issued.</span></span> <span data-ttu-id="b77d9-125">错误代码将是从 NetUserChangePassword 中返回的代码。</span><span class="sxs-lookup"><span data-stu-id="b77d9-125">The error code will be the one returned from NetUserChangePassword.</span></span> <span data-ttu-id="b77d9-126">有关详细信息，请参阅 MSDN 中此函数的文档。</span><span class="sxs-lookup"><span data-stu-id="b77d9-126">See the documentation for this function in MSDN for details.</span></span> <span data-ttu-id="b77d9-127">失败的最可能原因是旧密码不正确，或者是新密码不满足 Windows 密码策略的要求。</span><span class="sxs-lookup"><span data-stu-id="b77d9-127">Most likely causes of failure are that the old password was incorrect, or that the new password does not meet the required Windows password policy.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b77d9-128">用户操作</span><span class="sxs-lookup"><span data-stu-id="b77d9-128">User Action</span></span>  
 <span data-ttu-id="b77d9-129">若要解决此警告问题，请执行以下一项或多项操作：</span><span class="sxs-lookup"><span data-stu-id="b77d9-129">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="b77d9-130">验证旧密码。</span><span class="sxs-lookup"><span data-stu-id="b77d9-130">Verify the old password.</span></span> <span data-ttu-id="b77d9-131">如果旧密码不正确，则可以使用命令行工具或 Admin MMC 在 SSO 数据库中手动进行设置。</span><span class="sxs-lookup"><span data-stu-id="b77d9-131">If the old password is incorrect then it can be set manually in the SSO database using the command line tools or Admin MMC.</span></span>  
  
-   <span data-ttu-id="b77d9-132">验证新密码满足 Windows 密码策略的要求。</span><span class="sxs-lookup"><span data-stu-id="b77d9-132">Verify the new password meets the required Windows password policy.</span></span> <span data-ttu-id="b77d9-133">如果密码不符合 Windows 密码策略，则考虑使用密码筛选器。</span><span class="sxs-lookup"><span data-stu-id="b77d9-133">If the password does not meet the Windows password policy then consider using password filters.</span></span>  
  
 <span data-ttu-id="b77d9-134">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="b77d9-134">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="b77d9-135">密码同步</span><span class="sxs-lookup"><span data-stu-id="b77d9-135">Password Synchronization</span></span>](../core/password-synchronization2.md)