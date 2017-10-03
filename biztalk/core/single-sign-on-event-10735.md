---
title: "单一登录： 事件 10735 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31c791c6-1901-4441-b329-ed75833cb83e
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94417860296cf01c2266a678832f8b02b9b51055
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10735"></a><span data-ttu-id="03548-102">单一登录： 事件 10735</span><span class="sxs-lookup"><span data-stu-id="03548-102">Single Sign-On: Event 10735</span></span>
## <a name="details"></a><span data-ttu-id="03548-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="03548-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="03548-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="03548-104">Product Name</span></span>|<span data-ttu-id="03548-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="03548-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="03548-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="03548-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="03548-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="03548-107">Event ID</span></span>|<span data-ttu-id="03548-108">10735</span><span class="sxs-lookup"><span data-stu-id="03548-108">10735</span></span>|  
|<span data-ttu-id="03548-109">事件源</span><span class="sxs-lookup"><span data-stu-id="03548-109">Event Source</span></span>|<span data-ttu-id="03548-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="03548-110">ENTSSO</span></span>|  
|<span data-ttu-id="03548-111">组件</span><span class="sxs-lookup"><span data-stu-id="03548-111">Component</span></span>|<span data-ttu-id="03548-112">N\A</span><span class="sxs-lookup"><span data-stu-id="03548-112">N\A</span></span>|  
|<span data-ttu-id="03548-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="03548-113">Symbolic Name</span></span>|<span data-ttu-id="03548-114">SSO_WARN_PS_APP_DISABLED</span><span class="sxs-lookup"><span data-stu-id="03548-114">SSO_WARN_PS_APP_DISABLED</span></span>|  
|<span data-ttu-id="03548-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="03548-115">Message Text</span></span>|<span data-ttu-id="03548-116">外部密码更改。</span><span class="sxs-lookup"><span data-stu-id="03548-116">External password change.</span></span> <span data-ttu-id="03548-117">由于禁用了应用程序，因此，未更改外部帐户的密码。%r</span><span class="sxs-lookup"><span data-stu-id="03548-117">The password was not changed for the external account because the application is disabled.%r</span></span><br /><br /> <span data-ttu-id="03548-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="03548-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="03548-119">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="03548-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="03548-120">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="03548-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="03548-121">外部帐户： %4</span><span class="sxs-lookup"><span data-stu-id="03548-121">External Account: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="03548-122">解释</span><span class="sxs-lookup"><span data-stu-id="03548-122">Explanation</span></span>  
 <span data-ttu-id="03548-123">此警告事件表示由于禁用了应用程序，因此，未更改外部帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="03548-123">This Warning event indicates that a password was not changed for the external account because the application is disabled.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="03548-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="03548-124">User Action</span></span>  
 <span data-ttu-id="03548-125">若要解决此警告问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="03548-125">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="03548-126">启用关联应用程序</span><span class="sxs-lookup"><span data-stu-id="03548-126">Enable the affiliate application</span></span>  
  
 <span data-ttu-id="03548-127">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="03548-127">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="03548-128">如何启用关联应用程序</span><span class="sxs-lookup"><span data-stu-id="03548-128">How to Enable an Affiliate Application</span></span>](../core/how-to-enable-an-affiliate-application.md)  
  
-   [<span data-ttu-id="03548-129">密码同步</span><span class="sxs-lookup"><span data-stu-id="03548-129">Password Synchronization</span></span>](../core/password-synchronization2.md)