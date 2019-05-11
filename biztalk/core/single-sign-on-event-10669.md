---
title: 单一登录：Event 10669 | Microsoft Docs
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
ms.openlocfilehash: 1d0a9ab77f528060be25616eb8d80072402957a4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397531"
---
# <a name="single-sign-on-event-10669"></a><span data-ttu-id="a2af8-102">单一登录：事件 10669</span><span class="sxs-lookup"><span data-stu-id="a2af8-102">Single Sign-On: Event 10669</span></span>
## <a name="details"></a><span data-ttu-id="a2af8-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="a2af8-103">Details</span></span>  

|                 |                                                                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="a2af8-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="a2af8-104">Product Name</span></span>   |                                                                   <span data-ttu-id="a2af8-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="a2af8-105">Enterprise Single Sign-On</span></span>                                                                   |
| <span data-ttu-id="a2af8-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="a2af8-106">Product Version</span></span> |                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                   |
|    <span data-ttu-id="a2af8-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a2af8-107">Event ID</span></span>     |                                                                             <span data-ttu-id="a2af8-108">10669</span><span class="sxs-lookup"><span data-stu-id="a2af8-108">10669</span></span>                                                                             |
|  <span data-ttu-id="a2af8-109">事件源</span><span class="sxs-lookup"><span data-stu-id="a2af8-109">Event Source</span></span>   |                                                                            <span data-ttu-id="a2af8-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a2af8-110">ENTSSO</span></span>                                                                             |
|    <span data-ttu-id="a2af8-111">组件</span><span class="sxs-lookup"><span data-stu-id="a2af8-111">Component</span></span>    |                                                                              <span data-ttu-id="a2af8-112">N\A</span><span class="sxs-lookup"><span data-stu-id="a2af8-112">N\A</span></span>                                                                              |
|  <span data-ttu-id="a2af8-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="a2af8-113">Symbolic Name</span></span>  |                                                            <span data-ttu-id="a2af8-114">SSO_WARN_CHANGE_WINDOWS_PASSWORD_FAILED</span><span class="sxs-lookup"><span data-stu-id="a2af8-114">SSO_WARN_CHANGE_WINDOWS_PASSWORD_FAILED</span></span>                                                            |
|  <span data-ttu-id="a2af8-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="a2af8-115">Message Text</span></span>   | <span data-ttu-id="a2af8-116">更改 Windows password.%r 失败</span><span class="sxs-lookup"><span data-stu-id="a2af8-116">Failed to change the Windows password.%r</span></span><br /><br /> <span data-ttu-id="a2af8-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="a2af8-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="a2af8-118">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="a2af8-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="a2af8-119">Windows 帐户: %3 %r</span><span class="sxs-lookup"><span data-stu-id="a2af8-119">Windows Account: %3%r</span></span><br /><br /> <span data-ttu-id="a2af8-120">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="a2af8-120">Error Code: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="a2af8-121">解释</span><span class="sxs-lookup"><span data-stu-id="a2af8-121">Explanation</span></span>  
 <span data-ttu-id="a2af8-122">此警告事件表示 SSO 无法更改 Windows 密码。</span><span class="sxs-lookup"><span data-stu-id="a2af8-122">This Warning event indicates that SSO failed to change a Windows password.</span></span> <span data-ttu-id="a2af8-123">SSO 将调用 Win32 函数 NetUserChangePassword 函数来更改与映射关联的 Windows 密码。</span><span class="sxs-lookup"><span data-stu-id="a2af8-123">SSO calls the Win32 function NetUserChangePassword function to change the Windows password associated with the mapping.</span></span> <span data-ttu-id="a2af8-124">如果该函数会此错误消息发出。</span><span class="sxs-lookup"><span data-stu-id="a2af8-124">If this function fails this error message is issued.</span></span> <span data-ttu-id="a2af8-125">错误代码将是从 NetUserChangePassword 中返回。</span><span class="sxs-lookup"><span data-stu-id="a2af8-125">The error code will be the one returned from NetUserChangePassword.</span></span> <span data-ttu-id="a2af8-126">请参阅 MSDN 中此函数的详细信息的文档。</span><span class="sxs-lookup"><span data-stu-id="a2af8-126">See the documentation for this function in MSDN for details.</span></span> <span data-ttu-id="a2af8-127">最有可能导致失败的原因是旧密码不正确，或新的密码不满足 Windows 密码策略要求。</span><span class="sxs-lookup"><span data-stu-id="a2af8-127">Most likely causes of failure are that the old password was incorrect, or that the new password does not meet the required Windows password policy.</span></span>  

## <a name="user-action"></a><span data-ttu-id="a2af8-128">用户操作</span><span class="sxs-lookup"><span data-stu-id="a2af8-128">User Action</span></span>  
 <span data-ttu-id="a2af8-129">若要解决此警告，请执行一个或多个以下操作：</span><span class="sxs-lookup"><span data-stu-id="a2af8-129">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="a2af8-130">验证旧密码。</span><span class="sxs-lookup"><span data-stu-id="a2af8-130">Verify the old password.</span></span> <span data-ttu-id="a2af8-131">如果旧密码不正确，则可以使用命令行工具或 Admin MMC 在 SSO 数据库中手动设置。</span><span class="sxs-lookup"><span data-stu-id="a2af8-131">If the old password is incorrect then it can be set manually in the SSO database using the command line tools or Admin MMC.</span></span>  

- <span data-ttu-id="a2af8-132">验证新的密码符合 Windows 密码策略要求。</span><span class="sxs-lookup"><span data-stu-id="a2af8-132">Verify the new password meets the required Windows password policy.</span></span> <span data-ttu-id="a2af8-133">如果密码不符合 Windows 密码策略，则请考虑使用密码筛选器。</span><span class="sxs-lookup"><span data-stu-id="a2af8-133">If the password does not meet the Windows password policy then consider using password filters.</span></span>  

  <span data-ttu-id="a2af8-134">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="a2af8-134">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="a2af8-135">密码同步</span><span class="sxs-lookup"><span data-stu-id="a2af8-135">Password Synchronization</span></span>](../core/password-synchronization2.md)
