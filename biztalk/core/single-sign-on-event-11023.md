---
title: "单一登录： 事件 11023 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: feeb4ede-6045-46bf-9f2b-65062c583faa
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd65ac5cab5b49f43e0c3649cf205f7f6dc2ceaf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11023"></a><span data-ttu-id="54958-102">单一登录： 事件 11023</span><span class="sxs-lookup"><span data-stu-id="54958-102">Single Sign-On: Event 11023</span></span>
## <a name="details"></a><span data-ttu-id="54958-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="54958-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="54958-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="54958-104">Product Name</span></span>|<span data-ttu-id="54958-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="54958-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="54958-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="54958-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="54958-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="54958-107">Event ID</span></span>|<span data-ttu-id="54958-108">11023</span><span class="sxs-lookup"><span data-stu-id="54958-108">11023</span></span>|  
|<span data-ttu-id="54958-109">事件源</span><span class="sxs-lookup"><span data-stu-id="54958-109">Event Source</span></span>|<span data-ttu-id="54958-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="54958-110">ENTSSO</span></span>|  
|<span data-ttu-id="54958-111">组件</span><span class="sxs-lookup"><span data-stu-id="54958-111">Component</span></span>|<span data-ttu-id="54958-112">N/A</span><span class="sxs-lookup"><span data-stu-id="54958-112">N/A</span></span>|  
|<span data-ttu-id="54958-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="54958-113">Symbolic Name</span></span>|<span data-ttu-id="54958-114">SSO_WARN_WINDOWS_PASSWORD_DELETED</span><span class="sxs-lookup"><span data-stu-id="54958-114">SSO_WARN_WINDOWS_PASSWORD_DELETED</span></span>|  
|<span data-ttu-id="54958-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="54958-115">Message Text</span></span>|<span data-ttu-id="54958-116">已删除 SSO 数据库中无效的 Windows 密码以阻止帐户锁定。%r</span><span class="sxs-lookup"><span data-stu-id="54958-116">An invalid Windows password in the SSO database was deleted to prevent account lockout.%r</span></span><br /><br /> <span data-ttu-id="54958-117">请使用 SSO 管理工具为此 Windows 帐户设置外部凭据。%r</span><span class="sxs-lookup"><span data-stu-id="54958-117">Use the SSO administration tools to set the external credentials for this Windows account.%r</span></span><br /><br /> <span data-ttu-id="54958-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="54958-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="54958-119">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="54958-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="54958-120">Windows 帐户： %3</span><span class="sxs-lookup"><span data-stu-id="54958-120">Windows Account: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="54958-121">解释</span><span class="sxs-lookup"><span data-stu-id="54958-121">Explanation</span></span>  
 <span data-ttu-id="54958-122">已删除无效的 Windows 密码。</span><span class="sxs-lookup"><span data-stu-id="54958-122">An invalid Windows password has been deleted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="54958-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="54958-123">User Action</span></span>  
 <span data-ttu-id="54958-124">使用 SSO 管理工具为此 Windows 帐户设置外部凭据。</span><span class="sxs-lookup"><span data-stu-id="54958-124">Use the SSO administration tools to set the external credentials for this Windows account.</span></span> <span data-ttu-id="54958-125">有关详细信息，请参阅[使用 SSO](../core/using-sso.md)。</span><span class="sxs-lookup"><span data-stu-id="54958-125">For more information, see [Using SSO](../core/using-sso.md).</span></span>