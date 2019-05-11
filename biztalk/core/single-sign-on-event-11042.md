---
title: 单一登录：事件 11042 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1927bb5-a400-4e3a-8f80-95ef5693216c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bef9cdffc7e1b11409491ad27bb195d40c639518
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400986"
---
# <a name="single-sign-on-event-11042"></a><span data-ttu-id="0f064-102">单一登录：事件 11042</span><span class="sxs-lookup"><span data-stu-id="0f064-102">Single Sign-On: Event 11042</span></span>
## <a name="details"></a><span data-ttu-id="0f064-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="0f064-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="0f064-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="0f064-104">Product Name</span></span>   |                                                                                                                                                   <span data-ttu-id="0f064-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="0f064-105">Enterprise Single Sign-On</span></span>                                                                                                                                                   |
| <span data-ttu-id="0f064-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="0f064-106">Product Version</span></span> |                                                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                   |
|    <span data-ttu-id="0f064-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0f064-107">Event ID</span></span>     |                                                                                                                                                             <span data-ttu-id="0f064-108">11042</span><span class="sxs-lookup"><span data-stu-id="0f064-108">11042</span></span>                                                                                                                                                             |
|  <span data-ttu-id="0f064-109">事件源</span><span class="sxs-lookup"><span data-stu-id="0f064-109">Event Source</span></span>   |                                                                                                                                                            <span data-ttu-id="0f064-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0f064-110">ENTSSO</span></span>                                                                                                                                                             |
|    <span data-ttu-id="0f064-111">组件</span><span class="sxs-lookup"><span data-stu-id="0f064-111">Component</span></span>    |                                                                                                                                                              <span data-ttu-id="0f064-112">不可用</span><span class="sxs-lookup"><span data-stu-id="0f064-112">N/A</span></span>                                                                                                                                                              |
|  <span data-ttu-id="0f064-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="0f064-113">Symbolic Name</span></span>  |                                                                                                                                                <span data-ttu-id="0f064-114">SSO_WARN_ACCESS_DENIED_ACCOUNTS</span><span class="sxs-lookup"><span data-stu-id="0f064-114">SSO_WARN_ACCESS_DENIED_ACCOUNTS</span></span>                                                                                                                                                |
|  <span data-ttu-id="0f064-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="0f064-115">Message Text</span></span>   | <span data-ttu-id="0f064-116">访问被拒绝。</span><span class="sxs-lookup"><span data-stu-id="0f064-116">Access denied.</span></span><br /><br /> <span data-ttu-id="0f064-117">客户端用户必须是以下帐户之一的成员才能执行此 function.%r</span><span class="sxs-lookup"><span data-stu-id="0f064-117">The client user must be a member of one of the following accounts to perform this function.%r</span></span><br /><br /> <span data-ttu-id="0f064-118">SSO Administrators: %1 %r</span><span class="sxs-lookup"><span data-stu-id="0f064-118">SSO Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="0f064-119">SSO 关联管理员: %2 %r</span><span class="sxs-lookup"><span data-stu-id="0f064-119">SSO Affiliate Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="0f064-120">应用程序管理员: %3 %r</span><span class="sxs-lookup"><span data-stu-id="0f064-120">Application Administrators: %3%r</span></span><br /><br /> <span data-ttu-id="0f064-121">应用程序用户: %4 %r</span><span class="sxs-lookup"><span data-stu-id="0f064-121">Application Users: %4%r</span></span><br /><br /> <span data-ttu-id="0f064-122">其他数据： %5</span><span class="sxs-lookup"><span data-stu-id="0f064-122">Additional Data: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="0f064-123">解释</span><span class="sxs-lookup"><span data-stu-id="0f064-123">Explanation</span></span>  
 <span data-ttu-id="0f064-124">客户端用户必须是一个警告来执行此功能中列出的帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="0f064-124">The client user must be a member of one of the accounts listed in the warning to perform this function.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0f064-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="0f064-125">User Action</span></span>  
 <span data-ttu-id="0f064-126">您必须加入一个帐户来执行此功能。</span><span class="sxs-lookup"><span data-stu-id="0f064-126">You must join one of the accounts to perform this function.</span></span>