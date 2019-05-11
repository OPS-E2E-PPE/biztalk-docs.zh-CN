---
title: 单一登录：事件 10731 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 605e77f0-61f2-4a97-9ea0-bdc56344e8d9
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 630267c28a4db6b570be4c6efe73218e45f15b2f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267517"
---
# <a name="single-sign-on-event-10731"></a><span data-ttu-id="a40cf-102">单一登录：事件 10731</span><span class="sxs-lookup"><span data-stu-id="a40cf-102">Single Sign-On: Event 10731</span></span>
## <a name="details"></a><span data-ttu-id="a40cf-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="a40cf-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="a40cf-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="a40cf-104">Product Name</span></span>   |                                                                                                                         <span data-ttu-id="a40cf-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="a40cf-105">Enterprise Single Sign-On</span></span>                                                                                                                         |
| <span data-ttu-id="a40cf-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="a40cf-106">Product Version</span></span> |                                                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                         |
|    <span data-ttu-id="a40cf-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a40cf-107">Event ID</span></span>     |                                                                                                                                   <span data-ttu-id="a40cf-108">10731</span><span class="sxs-lookup"><span data-stu-id="a40cf-108">10731</span></span>                                                                                                                                   |
|  <span data-ttu-id="a40cf-109">事件源</span><span class="sxs-lookup"><span data-stu-id="a40cf-109">Event Source</span></span>   |                                                                                                                                  <span data-ttu-id="a40cf-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a40cf-110">ENTSSO</span></span>                                                                                                                                   |
|    <span data-ttu-id="a40cf-111">组件</span><span class="sxs-lookup"><span data-stu-id="a40cf-111">Component</span></span>    |                                                                                                                                    <span data-ttu-id="a40cf-112">N\A</span><span class="sxs-lookup"><span data-stu-id="a40cf-112">N\A</span></span>                                                                                                                                    |
|  <span data-ttu-id="a40cf-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="a40cf-113">Symbolic Name</span></span>  |                                                                                                                    <span data-ttu-id="a40cf-114">SSO_WARN_INVALID_USER_NOT_IN_GROUP</span><span class="sxs-lookup"><span data-stu-id="a40cf-114">SSO_WARN_INVALID_USER_NOT_IN_GROUP</span></span>                                                                                                                     |
|  <span data-ttu-id="a40cf-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="a40cf-115">Message Text</span></span>   | <span data-ttu-id="a40cf-116">无法创建映射，因为指定的用户不是应用程序用户 account.%r 的成员</span><span class="sxs-lookup"><span data-stu-id="a40cf-116">A mapping could not be created because the specified user is not a member of the Application Users account.%r</span></span><br /><br /> <span data-ttu-id="a40cf-117">域名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="a40cf-117">Domain Name: %1%r</span></span><br /><br /> <span data-ttu-id="a40cf-118">用户名: %2 %r</span><span class="sxs-lookup"><span data-stu-id="a40cf-118">User Name: %2%r</span></span><br /><br /> <span data-ttu-id="a40cf-119">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="a40cf-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="a40cf-120">应用程序用户: %4 %r</span><span class="sxs-lookup"><span data-stu-id="a40cf-120">Application Users: %4%r</span></span><br /><br /> <span data-ttu-id="a40cf-121">错误代码： %5</span><span class="sxs-lookup"><span data-stu-id="a40cf-121">Error Code: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="a40cf-122">解释</span><span class="sxs-lookup"><span data-stu-id="a40cf-122">Explanation</span></span>  
 <span data-ttu-id="a40cf-123">此警告事件表示，因为指定的用户不是应用程序用户帐户的成员可能不会创建一个映射。</span><span class="sxs-lookup"><span data-stu-id="a40cf-123">This Warning event indicates that a mapping could not be created because the specified user is not a member of the Application Users account.</span></span>  

 <span data-ttu-id="a40cf-124">为每个关联应用程序存在的应用程序用户组帐户。</span><span class="sxs-lookup"><span data-stu-id="a40cf-124">An application user's group account exists for each affiliate application.</span></span> <span data-ttu-id="a40cf-125">此帐户的成员可以验证其凭据的关联应用程序中，并且可以管理其凭据映射的关联应用程序中。</span><span class="sxs-lookup"><span data-stu-id="a40cf-125">Members of this account can verify their credentials in the affiliate application and can manage their credential mappings in the affiliate application.</span></span>  

## <a name="user-action"></a><span data-ttu-id="a40cf-126">用户操作</span><span class="sxs-lookup"><span data-stu-id="a40cf-126">User Action</span></span>  
 <span data-ttu-id="a40cf-127">若要解决此警告，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a40cf-127">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="a40cf-128">将指定的用户添加到指定的关联应用程序的应用程序用户的组。</span><span class="sxs-lookup"><span data-stu-id="a40cf-128">Add the specified user to the application user's group for the specified affiliate application.</span></span>  

  <span data-ttu-id="a40cf-129">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="a40cf-129">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="a40cf-130">SSO 用户组</span><span class="sxs-lookup"><span data-stu-id="a40cf-130">SSO User Groups</span></span>](../core/sso-user-groups.md)  

- [<span data-ttu-id="a40cf-131">SSO 关联应用程序</span><span class="sxs-lookup"><span data-stu-id="a40cf-131">SSO Affiliate Applications</span></span>](../core/sso-affiliate-applications.md)
