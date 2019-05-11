---
title: 单一登录：Event 10573 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de1ea4e3-5d5f-4d50-8f9a-eff270ac0edb
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37199e0b619f6d9f9d5a37ef1a6b4eb53c6f5712
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398724"
---
# <a name="single-sign-on-event-10573"></a><span data-ttu-id="8924d-102">单一登录：事件 10573</span><span class="sxs-lookup"><span data-stu-id="8924d-102">Single Sign-On: Event 10573</span></span>
## <a name="details"></a><span data-ttu-id="8924d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="8924d-103">Details</span></span>  
  
|                 |                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="8924d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="8924d-104">Product Name</span></span>   |                                                                                  <span data-ttu-id="8924d-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="8924d-105">Enterprise Single Sign-On</span></span>                                                                                   |
| <span data-ttu-id="8924d-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="8924d-106">Product Version</span></span> |                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    <span data-ttu-id="8924d-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8924d-107">Event ID</span></span>     |                                                                                            <span data-ttu-id="8924d-108">10573</span><span class="sxs-lookup"><span data-stu-id="8924d-108">10573</span></span>                                                                                             |
|  <span data-ttu-id="8924d-109">事件源</span><span class="sxs-lookup"><span data-stu-id="8924d-109">Event Source</span></span>   |                                                                                            <span data-ttu-id="8924d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="8924d-110">ENTSSO</span></span>                                                                                            |
|    <span data-ttu-id="8924d-111">组件</span><span class="sxs-lookup"><span data-stu-id="8924d-111">Component</span></span>    |                                                                                             <span data-ttu-id="8924d-112">不可用</span><span class="sxs-lookup"><span data-stu-id="8924d-112">N/A</span></span>                                                                                              |
|  <span data-ttu-id="8924d-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="8924d-113">Symbolic Name</span></span>  |                                                                             <span data-ttu-id="8924d-114">SSO_WARN_INVALID_SSO_APP_ADMIN_GROUP</span><span class="sxs-lookup"><span data-stu-id="8924d-114">SSO_WARN_INVALID_SSO_APP_ADMIN_GROUP</span></span>                                                                             |
|  <span data-ttu-id="8924d-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="8924d-115">Message Text</span></span>   | <span data-ttu-id="8924d-116">SSO Affiliate Administrators 帐户对于全局信息 update.%r 无效</span><span class="sxs-lookup"><span data-stu-id="8924d-116">The SSO Affiliate Administrators account is not valid for global info update.%r</span></span><br /><br /> <span data-ttu-id="8924d-117">SSO 关联管理员: %1 %r</span><span class="sxs-lookup"><span data-stu-id="8924d-117">SSO Affiliate Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="8924d-118">无效帐户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="8924d-118">Invalid accounts: %2%r</span></span><br /><br /> <span data-ttu-id="8924d-119">错误代码： %3</span><span class="sxs-lookup"><span data-stu-id="8924d-119">Error Code: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="8924d-120">解释</span><span class="sxs-lookup"><span data-stu-id="8924d-120">Explanation</span></span>  
 <span data-ttu-id="8924d-121">SSO Affiliate Administrators 帐户无效，不能用于全局信息更新。</span><span class="sxs-lookup"><span data-stu-id="8924d-121">The SSO Affiliate Administrators account is not valid for global info update.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8924d-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="8924d-122">User Action</span></span>  
 <span data-ttu-id="8924d-123">此警告消息包含有关 SSO 关联管理员帐户和无效帐户的信息。</span><span class="sxs-lookup"><span data-stu-id="8924d-123">The warning message contains information regarding the SSO Affiliate Administrators account and the invalid accounts.</span></span> <span data-ttu-id="8924d-124">查看此信息，进行任何必要的更正，并重试该更新。</span><span class="sxs-lookup"><span data-stu-id="8924d-124">Review this information, make any necessary corrections, and try the update again.</span></span>