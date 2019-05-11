---
title: 单一登录：事件 11017 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a4f7264-18aa-4eca-97c9-d5fd7e90e2cc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41b28506409bb68190f7dfe07f025d19c99dc47c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267145"
---
# <a name="single-sign-on-event-11017"></a><span data-ttu-id="7652b-102">单一登录：事件 11017</span><span class="sxs-lookup"><span data-stu-id="7652b-102">Single Sign-On: Event 11017</span></span>
## <a name="details"></a><span data-ttu-id="7652b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="7652b-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="7652b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="7652b-104">Product Name</span></span>   |                                                                                                                               <span data-ttu-id="7652b-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="7652b-105">Enterprise Single Sign-On</span></span>                                                                                                                                |
| <span data-ttu-id="7652b-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="7652b-106">Product Version</span></span> |                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                               |
|    <span data-ttu-id="7652b-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7652b-107">Event ID</span></span>     |                                                                                                                                         <span data-ttu-id="7652b-108">11017</span><span class="sxs-lookup"><span data-stu-id="7652b-108">11017</span></span>                                                                                                                                          |
|  <span data-ttu-id="7652b-109">事件源</span><span class="sxs-lookup"><span data-stu-id="7652b-109">Event Source</span></span>   |                                                                                                                                         <span data-ttu-id="7652b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="7652b-110">ENTSSO</span></span>                                                                                                                                         |
|    <span data-ttu-id="7652b-111">组件</span><span class="sxs-lookup"><span data-stu-id="7652b-111">Component</span></span>    |                                                                                                                                          <span data-ttu-id="7652b-112">不可用</span><span class="sxs-lookup"><span data-stu-id="7652b-112">N/A</span></span>                                                                                                                                           |
|  <span data-ttu-id="7652b-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="7652b-113">Symbolic Name</span></span>  |                                                                                                                           <span data-ttu-id="7652b-114">SSO_PS_WARN_NOT_IN_GROUP_DELETE_OK</span><span class="sxs-lookup"><span data-stu-id="7652b-114">SSO_PS_WARN_NOT_IN_GROUP_DELETE_OK</span></span>                                                                                                                           |
|  <span data-ttu-id="7652b-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="7652b-115">Message Text</span></span>   | <span data-ttu-id="7652b-116">映射无效，因为 Windows 帐户不在应用程序的应用程序用户帐户。</span><span class="sxs-lookup"><span data-stu-id="7652b-116">The mapping is not valid because the Windows account is not in the Application Users account for the application.</span></span> <span data-ttu-id="7652b-117">映射已被 deleted.%r</span><span class="sxs-lookup"><span data-stu-id="7652b-117">The mapping has been deleted.%r</span></span><br /><br /> <span data-ttu-id="7652b-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="7652b-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="7652b-119">Windows 帐户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="7652b-119">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="7652b-120">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="7652b-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="7652b-121">应用程序用户： %4</span><span class="sxs-lookup"><span data-stu-id="7652b-121">Application Users: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="7652b-122">解释</span><span class="sxs-lookup"><span data-stu-id="7652b-122">Explanation</span></span>  
 <span data-ttu-id="7652b-123">指定的 Windows 帐户从来都不属于此应用程序的应用程序用户帐户或它是一次，但已更改或删除。</span><span class="sxs-lookup"><span data-stu-id="7652b-123">Either the Windows account specified was never a part of the Application Users account for this application, or it was at one time, but has been changed or removed.</span></span> <span data-ttu-id="7652b-124">已删除该映射。</span><span class="sxs-lookup"><span data-stu-id="7652b-124">The mapping has been deleted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7652b-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="7652b-125">User Action</span></span>  
 <span data-ttu-id="7652b-126">检查您的系统，密码同步帐户信息，请确保你的信息有效。</span><span class="sxs-lookup"><span data-stu-id="7652b-126">Check the password sync account information for your system, and make sure your information is valid.</span></span> <span data-ttu-id="7652b-127">然后重新创建映射。</span><span class="sxs-lookup"><span data-stu-id="7652b-127">Then recreate the mapping.</span></span> <span data-ttu-id="7652b-128">请注意，使用创建映射向导可降低无效映射信息的风险。</span><span class="sxs-lookup"><span data-stu-id="7652b-128">Note that using the Create Mapping Wizard reduces the risk of invalid mapping information.</span></span>