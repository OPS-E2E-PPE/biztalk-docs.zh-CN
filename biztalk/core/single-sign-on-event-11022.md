---
title: "单一登录： 事件 11022 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c65ca12b-dda8-408b-9512-39df6f8e035b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccae36e9beef672e6c5fb7917c88341ce4bb3c08
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11022"></a><span data-ttu-id="586b4-102">单一登录： 事件 11022</span><span class="sxs-lookup"><span data-stu-id="586b4-102">Single Sign-On: Event 11022</span></span>
## <a name="details"></a><span data-ttu-id="586b4-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="586b4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="586b4-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="586b4-104">Product Name</span></span>|<span data-ttu-id="586b4-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="586b4-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="586b4-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="586b4-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="586b4-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="586b4-107">Event ID</span></span>|<span data-ttu-id="586b4-108">11022</span><span class="sxs-lookup"><span data-stu-id="586b4-108">11022</span></span>|  
|<span data-ttu-id="586b4-109">事件源</span><span class="sxs-lookup"><span data-stu-id="586b4-109">Event Source</span></span>|<span data-ttu-id="586b4-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="586b4-110">ENTSSO</span></span>|  
|<span data-ttu-id="586b4-111">组件</span><span class="sxs-lookup"><span data-stu-id="586b4-111">Component</span></span>|<span data-ttu-id="586b4-112">N/A</span><span class="sxs-lookup"><span data-stu-id="586b4-112">N/A</span></span>|  
|<span data-ttu-id="586b4-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="586b4-113">Symbolic Name</span></span>|<span data-ttu-id="586b4-114">SSO_WARN_EXTERNAL_TO_EXTERNAL_MAPPING_CONFLICT_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="586b4-114">SSO_WARN_EXTERNAL_TO_EXTERNAL_MAPPING_CONFLICT_NOT_ALLOWED</span></span>|  
|<span data-ttu-id="586b4-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="586b4-115">Message Text</span></span>|<span data-ttu-id="586b4-116">外部密码更改将导致不同外部帐户的更改。%r</span><span class="sxs-lookup"><span data-stu-id="586b4-116">An external password change would have caused a different external account to be changed.%r</span></span><br /><br /> <span data-ttu-id="586b4-117">此操作已被阻止，因为此外部系统的适配器配置为不允许映射冲突。%r</span><span class="sxs-lookup"><span data-stu-id="586b4-117">This has been prevented because the adapter for this external system is configured to not allow mapping conflicts.%r</span></span><br /><br /> <span data-ttu-id="586b4-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="586b4-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="586b4-119">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="586b4-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="586b4-120">Windows 帐户: %3 %r</span><span class="sxs-lookup"><span data-stu-id="586b4-120">Windows Account: %3%r</span></span><br /><br /> <span data-ttu-id="586b4-121">外部帐户 1: %4 %r</span><span class="sxs-lookup"><span data-stu-id="586b4-121">External Account 1: %4%r</span></span><br /><br /> <span data-ttu-id="586b4-122">外部帐户 2: %5</span><span class="sxs-lookup"><span data-stu-id="586b4-122">External Account 2: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="586b4-123">解释</span><span class="sxs-lookup"><span data-stu-id="586b4-123">Explanation</span></span>  
 <span data-ttu-id="586b4-124">此信息消息表示，外部密码更改（可能导致不同的外部帐户更改）失败。</span><span class="sxs-lookup"><span data-stu-id="586b4-124">This is an informational message reporting the failure of an external password change which would have caused a different external account to be changed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="586b4-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="586b4-125">User Action</span></span>  
 <span data-ttu-id="586b4-126">尽管没有做出任何更改（因为此系统配置为不允许映射冲突），您仍然应该立即确认这是利用您的信息和授权做出的更改。</span><span class="sxs-lookup"><span data-stu-id="586b4-126">Although no change was made (because this system is configured to not allow mapping conflicts) you should confirm immediately that this attempt was made with your knowledge and authorization.</span></span> <span data-ttu-id="586b4-127">如果是这样，无需进行任何操作。</span><span class="sxs-lookup"><span data-stu-id="586b4-127">If so, no action is required.</span></span> <span data-ttu-id="586b4-128">如果不是，请查明进行更改的位置，并确认此更改位于系统中的安全位置。</span><span class="sxs-lookup"><span data-stu-id="586b4-128">If not, find out where the change initiated, and confirm that it was a location safely within the system.</span></span>