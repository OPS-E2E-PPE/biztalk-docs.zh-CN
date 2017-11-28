---
title: "单一登录： 事件 10567 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f29c8d9-3da2-4de7-b61f-8c586382b68f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb6f57bed2f386363d3ae4d92b4e300061056826
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10567"></a><span data-ttu-id="e3cb4-102">单一登录： 事件 10567</span><span class="sxs-lookup"><span data-stu-id="e3cb4-102">Single Sign-On: Event 10567</span></span>
## <a name="details"></a><span data-ttu-id="e3cb4-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e3cb4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e3cb4-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e3cb4-104">Product Name</span></span>|<span data-ttu-id="e3cb4-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="e3cb4-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="e3cb4-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="e3cb4-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="e3cb4-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e3cb4-107">Event ID</span></span>|<span data-ttu-id="e3cb4-108">10567</span><span class="sxs-lookup"><span data-stu-id="e3cb4-108">10567</span></span>|  
|<span data-ttu-id="e3cb4-109">事件源</span><span class="sxs-lookup"><span data-stu-id="e3cb4-109">Event Source</span></span>|<span data-ttu-id="e3cb4-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e3cb4-110">ENTSSO</span></span>|  
|<span data-ttu-id="e3cb4-111">组件</span><span class="sxs-lookup"><span data-stu-id="e3cb4-111">Component</span></span>|<span data-ttu-id="e3cb4-112">N/A</span><span class="sxs-lookup"><span data-stu-id="e3cb4-112">N/A</span></span>|  
|<span data-ttu-id="e3cb4-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="e3cb4-113">Symbolic Name</span></span>|<span data-ttu-id="e3cb4-114">SSO_WARN_INVALID_APP_USER_GROUP</span><span class="sxs-lookup"><span data-stu-id="e3cb4-114">SSO_WARN_INVALID_APP_USER_GROUP</span></span>|  
|<span data-ttu-id="e3cb4-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="e3cb4-115">Message Text</span></span>|<span data-ttu-id="e3cb4-116">该 Application Users 帐户对于应用程序 update.%r 无效</span><span class="sxs-lookup"><span data-stu-id="e3cb4-116">The Application Users account is not valid for application update.%r</span></span><br /><br /> <span data-ttu-id="e3cb4-117">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="e3cb4-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="e3cb4-118">Application Users: %2 %r</span><span class="sxs-lookup"><span data-stu-id="e3cb4-118">Application Users: %2%r</span></span><br /><br /> <span data-ttu-id="e3cb4-119">无效帐户: %3 %r</span><span class="sxs-lookup"><span data-stu-id="e3cb4-119">Invalid accounts: %3%r</span></span><br /><br /> <span data-ttu-id="e3cb4-120">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="e3cb4-120">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e3cb4-121">解释</span><span class="sxs-lookup"><span data-stu-id="e3cb4-121">Explanation</span></span>  
 <span data-ttu-id="e3cb4-122">您尝试更新的应用程序用户帐户无效或不存在。</span><span class="sxs-lookup"><span data-stu-id="e3cb4-122">You have attempted to update an Application Users account which is either invalid or does not exist.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e3cb4-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="e3cb4-123">User Action</span></span>  
 <span data-ttu-id="e3cb4-124">检查帐户的名称是否正确。</span><span class="sxs-lookup"><span data-stu-id="e3cb4-124">Check that the name of the account is correct.</span></span>