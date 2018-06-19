---
title: 单一登录： 事件 11019 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ec07b00-d567-4518-89eb-340e4f92429b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb4b2d2494a404566c7350a9e9988d429a3e335c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276373"
---
# <a name="single-sign-on-event-11019"></a><span data-ttu-id="423ff-102">单一登录： 事件 11019</span><span class="sxs-lookup"><span data-stu-id="423ff-102">Single Sign-On: Event 11019</span></span>
## <a name="details"></a><span data-ttu-id="423ff-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="423ff-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="423ff-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="423ff-104">Product Name</span></span>|<span data-ttu-id="423ff-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="423ff-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="423ff-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="423ff-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="423ff-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="423ff-107">Event ID</span></span>|<span data-ttu-id="423ff-108">11019</span><span class="sxs-lookup"><span data-stu-id="423ff-108">11019</span></span>|  
|<span data-ttu-id="423ff-109">事件源</span><span class="sxs-lookup"><span data-stu-id="423ff-109">Event Source</span></span>|<span data-ttu-id="423ff-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="423ff-110">ENTSSO</span></span>|  
|<span data-ttu-id="423ff-111">组件</span><span class="sxs-lookup"><span data-stu-id="423ff-111">Component</span></span>|<span data-ttu-id="423ff-112">N/A</span><span class="sxs-lookup"><span data-stu-id="423ff-112">N/A</span></span>|  
|<span data-ttu-id="423ff-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="423ff-113">Symbolic Name</span></span>|<span data-ttu-id="423ff-114">SSO_PS_WARN_NOT_IN_GROUP_DELETE_FAILED</span><span class="sxs-lookup"><span data-stu-id="423ff-114">SSO_PS_WARN_NOT_IN_GROUP_DELETE_FAILED</span></span>|  
|<span data-ttu-id="423ff-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="423ff-115">Message Text</span></span>|<span data-ttu-id="423ff-116">由于 Windows 帐户不属于应用程序的应用程序用户帐户而导致映射无效。</span><span class="sxs-lookup"><span data-stu-id="423ff-116">The mapping is not valid because the Windows account is not in the Application Users account for the application.</span></span> <span data-ttu-id="423ff-117">无法删除映射。</span><span class="sxs-lookup"><span data-stu-id="423ff-117">Failed to delete the mapping.</span></span> <span data-ttu-id="423ff-118">将忽略此映射。%r</span><span class="sxs-lookup"><span data-stu-id="423ff-118">The mapping will be ignored.%r</span></span><br /><br /> <span data-ttu-id="423ff-119">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="423ff-119">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="423ff-120">Windows 帐户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="423ff-120">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="423ff-121">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="423ff-121">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="423ff-122">Application Users: %4 %r</span><span class="sxs-lookup"><span data-stu-id="423ff-122">Application Users: %4%r</span></span><br /><br /> <span data-ttu-id="423ff-123">错误代码： %5</span><span class="sxs-lookup"><span data-stu-id="423ff-123">Error Code: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="423ff-124">解释</span><span class="sxs-lookup"><span data-stu-id="423ff-124">Explanation</span></span>  
 <span data-ttu-id="423ff-125">指定的 Windows 帐户不是此应用程序的应用程序用户帐户的一部分，或者曾经是应用程序用户帐户的一部分，但已更改或删除。</span><span class="sxs-lookup"><span data-stu-id="423ff-125">Either the Windows account specified was never a part of the Application Users account for this application, or it was at one time, but has been changed or removed.</span></span> <span data-ttu-id="423ff-126">尚未映射中删除。</span><span class="sxs-lookup"><span data-stu-id="423ff-126">The mapping has not been deleted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="423ff-127">用户操作</span><span class="sxs-lookup"><span data-stu-id="423ff-127">User Action</span></span>  
 <span data-ttu-id="423ff-128">检查系统的密码同步帐户信息，并确保您的信息有效。</span><span class="sxs-lookup"><span data-stu-id="423ff-128">Check the password sync account information for your system, and make sure your information is valid.</span></span> <span data-ttu-id="423ff-129">然后重新创建映射。</span><span class="sxs-lookup"><span data-stu-id="423ff-129">Then recreate the mapping.</span></span> <span data-ttu-id="423ff-130">请注意，使用创建映射向导可降低无效映射信息的风险。</span><span class="sxs-lookup"><span data-stu-id="423ff-130">Note that using the Create Mapping Wizard reduces the risk of invalid mapping information.</span></span> <span data-ttu-id="423ff-131">您可以删除失败的映射。</span><span class="sxs-lookup"><span data-stu-id="423ff-131">You can delete the failed mapping.</span></span> <span data-ttu-id="423ff-132">否则，将忽略失败的映射。</span><span class="sxs-lookup"><span data-stu-id="423ff-132">If you do not delete it, it will be ignored.</span></span>