---
title: "单一登录： 事件 11035 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d551083c-a897-4a76-a40c-2254d3a3e52e
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e104d28517eab153880e3c922f3fd1f174a6170a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11035"></a><span data-ttu-id="5074e-102">单一登录： 事件 11035</span><span class="sxs-lookup"><span data-stu-id="5074e-102">Single Sign-On: Event 11035</span></span>
## <a name="details"></a><span data-ttu-id="5074e-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="5074e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5074e-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="5074e-104">Product Name</span></span>|<span data-ttu-id="5074e-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="5074e-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="5074e-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="5074e-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="5074e-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="5074e-107">Event ID</span></span>|<span data-ttu-id="5074e-108">11035</span><span class="sxs-lookup"><span data-stu-id="5074e-108">11035</span></span>|  
|<span data-ttu-id="5074e-109">事件源</span><span class="sxs-lookup"><span data-stu-id="5074e-109">Event Source</span></span>|<span data-ttu-id="5074e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5074e-110">ENTSSO</span></span>|  
|<span data-ttu-id="5074e-111">组件</span><span class="sxs-lookup"><span data-stu-id="5074e-111">Component</span></span>|<span data-ttu-id="5074e-112">N/A</span><span class="sxs-lookup"><span data-stu-id="5074e-112">N/A</span></span>|  
|<span data-ttu-id="5074e-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="5074e-113">Symbolic Name</span></span>|<span data-ttu-id="5074e-114">SSO_INFO_PS_WIN_CHANGE_NO_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="5074e-114">SSO_INFO_PS_WIN_CHANGE_NO_ADAPTER</span></span>|  
|<span data-ttu-id="5074e-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="5074e-115">Message Text</span></span>|<span data-ttu-id="5074e-116">Windows 密码更改。</span><span class="sxs-lookup"><span data-stu-id="5074e-116">Windows password change.</span></span> <span data-ttu-id="5074e-117">已检测到此 Windows 帐户的映射，但忽略该映射，因为尚未为此应用程序配置密码同步。%r</span><span class="sxs-lookup"><span data-stu-id="5074e-117">A mapping for this Windows account has been detected but ignored because password sync is not configured for this application.%r</span></span><br /><br /> <span data-ttu-id="5074e-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="5074e-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="5074e-119">Windows 帐户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="5074e-119">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="5074e-120">应用程序: %3 %r</span><span class="sxs-lookup"><span data-stu-id="5074e-120">Application: %3%r</span></span><br /><br /> <span data-ttu-id="5074e-121">外部帐户: %4 %r</span><span class="sxs-lookup"><span data-stu-id="5074e-121">External Account: %4%r</span></span><br /><br /> <span data-ttu-id="5074e-122">客户端用户： %5</span><span class="sxs-lookup"><span data-stu-id="5074e-122">Client User: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5074e-123">解释</span><span class="sxs-lookup"><span data-stu-id="5074e-123">Explanation</span></span>  
 <span data-ttu-id="5074e-124">已检测到此 Windows 帐户的映射，但忽略该映射，因为尚未为此应用程序配置密码同步。</span><span class="sxs-lookup"><span data-stu-id="5074e-124">A mapping for this Windows account has been detected but ignored because password sync is not configured for this application.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5074e-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="5074e-125">User Action</span></span>  
 <span data-ttu-id="5074e-126">有关配置密码同步的信息，请参阅[密码同步](../core/password-synchronization2.md)。</span><span class="sxs-lookup"><span data-stu-id="5074e-126">For information on configuring Password Sync, see [Password Synchronization](../core/password-synchronization2.md).</span></span>