---
title: 单一登录： 事件 10669 |Microsoft Docs
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
ms.openlocfilehash: d3006b8c861ac56effa504480f2645f22f9deae8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019257"
---
# <a name="single-sign-on-event-10669"></a><span data-ttu-id="573cc-102">单一登录： 事件 10669</span><span class="sxs-lookup"><span data-stu-id="573cc-102">Single Sign-On: Event 10669</span></span>
## <a name="details"></a><span data-ttu-id="573cc-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="573cc-103">Details</span></span>  

|                 |                                                                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="573cc-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="573cc-104">Product Name</span></span>   |                                                                   <span data-ttu-id="573cc-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="573cc-105">Enterprise Single Sign-On</span></span>                                                                   |
| <span data-ttu-id="573cc-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="573cc-106">Product Version</span></span> |                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                   |
|    <span data-ttu-id="573cc-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="573cc-107">Event ID</span></span>     |                                                                             <span data-ttu-id="573cc-108">10669</span><span class="sxs-lookup"><span data-stu-id="573cc-108">10669</span></span>                                                                             |
|  <span data-ttu-id="573cc-109">事件源</span><span class="sxs-lookup"><span data-stu-id="573cc-109">Event Source</span></span>   |                                                                            <span data-ttu-id="573cc-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="573cc-110">ENTSSO</span></span>                                                                             |
|    <span data-ttu-id="573cc-111">组件</span><span class="sxs-lookup"><span data-stu-id="573cc-111">Component</span></span>    |                                                                              <span data-ttu-id="573cc-112">N\A</span><span class="sxs-lookup"><span data-stu-id="573cc-112">N\A</span></span>                                                                              |
|  <span data-ttu-id="573cc-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="573cc-113">Symbolic Name</span></span>  |                                                            <span data-ttu-id="573cc-114">SSO_WARN_CHANGE_WINDOWS_PASSWORD_FAILED</span><span class="sxs-lookup"><span data-stu-id="573cc-114">SSO_WARN_CHANGE_WINDOWS_PASSWORD_FAILED</span></span>                                                            |
|  <span data-ttu-id="573cc-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="573cc-115">Message Text</span></span>   | <span data-ttu-id="573cc-116">无法更改 Windows 密码。%r</span><span class="sxs-lookup"><span data-stu-id="573cc-116">Failed to change the Windows password.%r</span></span><br /><br /> <span data-ttu-id="573cc-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="573cc-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="573cc-118">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="573cc-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="573cc-119">Windows 帐户: %3 %r</span><span class="sxs-lookup"><span data-stu-id="573cc-119">Windows Account: %3%r</span></span><br /><br /> <span data-ttu-id="573cc-120">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="573cc-120">Error Code: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="573cc-121">解释</span><span class="sxs-lookup"><span data-stu-id="573cc-121">Explanation</span></span>  
 <span data-ttu-id="573cc-122">此警告事件表示 SSO 无法更改 Windows 密码。</span><span class="sxs-lookup"><span data-stu-id="573cc-122">This Warning event indicates that SSO failed to change a Windows password.</span></span> <span data-ttu-id="573cc-123">SSO 将调用 Win32 函数 NetUserChangePassword 函数来更改与映射关联的 Windows 密码。</span><span class="sxs-lookup"><span data-stu-id="573cc-123">SSO calls the Win32 function NetUserChangePassword function to change the Windows password associated with the mapping.</span></span> <span data-ttu-id="573cc-124">如果调用此函数失败，则系统会发出此错误消息。</span><span class="sxs-lookup"><span data-stu-id="573cc-124">If this function fails this error message is issued.</span></span> <span data-ttu-id="573cc-125">错误代码将是从 NetUserChangePassword 中返回的代码。</span><span class="sxs-lookup"><span data-stu-id="573cc-125">The error code will be the one returned from NetUserChangePassword.</span></span> <span data-ttu-id="573cc-126">有关详细信息，请参阅 MSDN 中此函数的文档。</span><span class="sxs-lookup"><span data-stu-id="573cc-126">See the documentation for this function in MSDN for details.</span></span> <span data-ttu-id="573cc-127">失败的最可能原因是旧密码不正确，或者是新密码不满足 Windows 密码策略的要求。</span><span class="sxs-lookup"><span data-stu-id="573cc-127">Most likely causes of failure are that the old password was incorrect, or that the new password does not meet the required Windows password policy.</span></span>  

## <a name="user-action"></a><span data-ttu-id="573cc-128">用户操作</span><span class="sxs-lookup"><span data-stu-id="573cc-128">User Action</span></span>  
 <span data-ttu-id="573cc-129">若要解决此警告问题，请执行以下一项或多项操作：</span><span class="sxs-lookup"><span data-stu-id="573cc-129">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="573cc-130">验证旧密码。</span><span class="sxs-lookup"><span data-stu-id="573cc-130">Verify the old password.</span></span> <span data-ttu-id="573cc-131">如果旧密码不正确，则可以使用命令行工具或 Admin MMC 在 SSO 数据库中手动进行设置。</span><span class="sxs-lookup"><span data-stu-id="573cc-131">If the old password is incorrect then it can be set manually in the SSO database using the command line tools or Admin MMC.</span></span>  

- <span data-ttu-id="573cc-132">验证新密码满足 Windows 密码策略的要求。</span><span class="sxs-lookup"><span data-stu-id="573cc-132">Verify the new password meets the required Windows password policy.</span></span> <span data-ttu-id="573cc-133">如果密码不符合 Windows 密码策略，则考虑使用密码筛选器。</span><span class="sxs-lookup"><span data-stu-id="573cc-133">If the password does not meet the Windows password policy then consider using password filters.</span></span>  

  <span data-ttu-id="573cc-134">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="573cc-134">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="573cc-135">密码同步</span><span class="sxs-lookup"><span data-stu-id="573cc-135">Password Synchronization</span></span>](../core/password-synchronization2.md)
