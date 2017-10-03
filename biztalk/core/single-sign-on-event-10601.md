---
title: "单一登录： 事件 10601 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2624025e-b7a8-43b9-aa7e-6811a2fc3278
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c34711cf02711ec0ee2a259cc7d8f8fca9c87b7e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10601"></a><span data-ttu-id="ffd5d-102">单一登录： 事件 10601</span><span class="sxs-lookup"><span data-stu-id="ffd5d-102">Single Sign-On: Event 10601</span></span>
## <a name="details"></a><span data-ttu-id="ffd5d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ffd5d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ffd5d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ffd5d-104">Product Name</span></span>|<span data-ttu-id="ffd5d-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="ffd5d-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="ffd5d-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="ffd5d-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="ffd5d-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ffd5d-107">Event ID</span></span>|<span data-ttu-id="ffd5d-108">10601</span><span class="sxs-lookup"><span data-stu-id="ffd5d-108">10601</span></span>|  
|<span data-ttu-id="ffd5d-109">事件源</span><span class="sxs-lookup"><span data-stu-id="ffd5d-109">Event Source</span></span>|<span data-ttu-id="ffd5d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ffd5d-110">ENTSSO</span></span>|  
|<span data-ttu-id="ffd5d-111">组件</span><span class="sxs-lookup"><span data-stu-id="ffd5d-111">Component</span></span>|<span data-ttu-id="ffd5d-112">N/A</span><span class="sxs-lookup"><span data-stu-id="ffd5d-112">N/A</span></span>|  
|<span data-ttu-id="ffd5d-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="ffd5d-113">Symbolic Name</span></span>|<span data-ttu-id="ffd5d-114">SSO_WARN_INVALID_FLAGS</span><span class="sxs-lookup"><span data-stu-id="ffd5d-114">SSO_WARN_INVALID_FLAGS</span></span>|  
|<span data-ttu-id="ffd5d-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="ffd5d-115">Message Text</span></span>|<span data-ttu-id="ffd5d-116">指定的标志无法用于创建此类型的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ffd5d-116">The specified flags are not valid for creating this type of application.</span></span><br /><br /> <span data-ttu-id="ffd5d-117">有关详细信息，请参阅文档。%r</span><span class="sxs-lookup"><span data-stu-id="ffd5d-117">See documentation for details.%r</span></span><br /><br /> <span data-ttu-id="ffd5d-118">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="ffd5d-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="ffd5d-119">指定的标志: %2 %r</span><span class="sxs-lookup"><span data-stu-id="ffd5d-119">Specified Flags: %2%r</span></span><br /><br /> <span data-ttu-id="ffd5d-120">允许的标志: %3 %r</span><span class="sxs-lookup"><span data-stu-id="ffd5d-120">Allowed Flags: %3%r</span></span><br /><br /> <span data-ttu-id="ffd5d-121">不允许的标志： %4</span><span class="sxs-lookup"><span data-stu-id="ffd5d-121">Not Allowed Flags: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ffd5d-122">解释</span><span class="sxs-lookup"><span data-stu-id="ffd5d-122">Explanation</span></span>  
 <span data-ttu-id="ffd5d-123">指定的标志无法用于创建此类型的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ffd5d-123">The specified flags are not valid for creating this type of application.</span></span> <span data-ttu-id="ffd5d-124">警告中列出了相关的应用程序，以及允许和不允许的标志。</span><span class="sxs-lookup"><span data-stu-id="ffd5d-124">The warning lists the application concerned, as well as the flags that are allowed and those that are not.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ffd5d-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="ffd5d-125">User Action</span></span>  
 <span data-ttu-id="ffd5d-126">遵循警告消息中列出的准则来重新创建应用程序。</span><span class="sxs-lookup"><span data-stu-id="ffd5d-126">Recreate the application following the guidelines outlined in the warning message.</span></span>