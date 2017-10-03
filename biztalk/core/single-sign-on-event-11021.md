---
title: "单一登录： 事件 11021 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 70b987aa-8097-4243-a25b-f1cc12c5bc6a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1e246ac3d0bbab4e991b17c091567b4b59131b4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11021"></a><span data-ttu-id="c2f6b-102">单一登录： 事件 11021</span><span class="sxs-lookup"><span data-stu-id="c2f6b-102">Single Sign-On: Event 11021</span></span>
## <a name="details"></a><span data-ttu-id="c2f6b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="c2f6b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c2f6b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="c2f6b-104">Product Name</span></span>|<span data-ttu-id="c2f6b-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="c2f6b-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="c2f6b-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="c2f6b-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="c2f6b-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c2f6b-107">Event ID</span></span>|<span data-ttu-id="c2f6b-108">11021</span><span class="sxs-lookup"><span data-stu-id="c2f6b-108">11021</span></span>|  
|<span data-ttu-id="c2f6b-109">事件源</span><span class="sxs-lookup"><span data-stu-id="c2f6b-109">Event Source</span></span>|<span data-ttu-id="c2f6b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c2f6b-110">ENTSSO</span></span>|  
|<span data-ttu-id="c2f6b-111">组件</span><span class="sxs-lookup"><span data-stu-id="c2f6b-111">Component</span></span>|<span data-ttu-id="c2f6b-112">N/A</span><span class="sxs-lookup"><span data-stu-id="c2f6b-112">N/A</span></span>|  
|<span data-ttu-id="c2f6b-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="c2f6b-113">Symbolic Name</span></span>|<span data-ttu-id="c2f6b-114">SSO_INFO_EXTERNAL_TO_EXTERNAL_MAPPING_CONFLICT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="c2f6b-114">SSO_INFO_EXTERNAL_TO_EXTERNAL_MAPPING_CONFLICT_ALLOWED</span></span>|  
|<span data-ttu-id="c2f6b-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="c2f6b-115">Message Text</span></span>|<span data-ttu-id="c2f6b-116">外部密码更改将导致另一外部帐户被更改。%r</span><span class="sxs-lookup"><span data-stu-id="c2f6b-116">An external password change will cause a different external account to be changed.%r</span></span><br /><br /> <span data-ttu-id="c2f6b-117">这是允许的，因为此外部系统的适配器配置为允许映射冲突。%r</span><span class="sxs-lookup"><span data-stu-id="c2f6b-117">This is allowed because the adapter for this external system is configured to allow mapping conflicts.%r</span></span><br /><br /> <span data-ttu-id="c2f6b-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="c2f6b-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="c2f6b-119">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="c2f6b-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="c2f6b-120">Windows 帐户: %3 %r</span><span class="sxs-lookup"><span data-stu-id="c2f6b-120">Windows Account: %3%r</span></span><br /><br /> <span data-ttu-id="c2f6b-121">外部帐户 1: %4 %r</span><span class="sxs-lookup"><span data-stu-id="c2f6b-121">External Account 1: %4%r</span></span><br /><br /> <span data-ttu-id="c2f6b-122">外部帐户 2: %5</span><span class="sxs-lookup"><span data-stu-id="c2f6b-122">External Account 2: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c2f6b-123">解释</span><span class="sxs-lookup"><span data-stu-id="c2f6b-123">Explanation</span></span>  
 <span data-ttu-id="c2f6b-124">这是一条信息性消息，指示外部密码更改将导致另一外部帐户被更改。</span><span class="sxs-lookup"><span data-stu-id="c2f6b-124">This is an informational message stating that an external password change will cause a different external account to be changed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c2f6b-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="c2f6b-125">User Action</span></span>  
 <span data-ttu-id="c2f6b-126">您应该立即确认是利用您的信息和授权做出的更改。</span><span class="sxs-lookup"><span data-stu-id="c2f6b-126">You should confirm immediately that this change was made with your knowledge and authorization.</span></span> <span data-ttu-id="c2f6b-127">如果是这样，无需进行任何操作。</span><span class="sxs-lookup"><span data-stu-id="c2f6b-127">If so, no action is required.</span></span> <span data-ttu-id="c2f6b-128">如果不是，请查明进行更改的位置，并确认此更改位于系统中的安全位置。</span><span class="sxs-lookup"><span data-stu-id="c2f6b-128">If not, find out where the change initiated, and confirm that it was a location safely within the system.</span></span>