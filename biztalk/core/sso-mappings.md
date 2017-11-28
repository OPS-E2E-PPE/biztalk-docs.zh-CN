---
title: "SSO 映射 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps [SSO]
- maps [SSO], creating
- SSO, maps
ms.assetid: b44f7a0c-595c-49dc-9d75-2e76f29dca88
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98b44a1a9e8be3b275a4dd328c70323d79eb8a54
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sso-mappings"></a><span data-ttu-id="75aeb-102">SSO 映射</span><span class="sxs-lookup"><span data-stu-id="75aeb-102">SSO Mappings</span></span>
<span data-ttu-id="75aeb-103">在企业单一登录 (SSO) 管理员或 SSO 关联管理员定义关联应用程序时，该管理员可以将其定义为具有单项映射的应用程序或具有组映射的应用程序。</span><span class="sxs-lookup"><span data-stu-id="75aeb-103">When an Enterprise Single Sign-On (SSO) administrator or an SSO affiliate administrator defines an affiliate application, the administrator can define it either as an application with individual mappings, or as an application with a group mapping.</span></span>  
  
## <a name="individual-mappings"></a><span data-ttu-id="75aeb-104">单项映射</span><span class="sxs-lookup"><span data-stu-id="75aeb-104">Individual Mappings</span></span>  
 <span data-ttu-id="75aeb-105">使用 SSO 单项映射，管理员和用户可以在 Windows 用户与他们对应的非 Windows 凭据之间创建一对一映射。</span><span class="sxs-lookup"><span data-stu-id="75aeb-105">SSO individual mappings enable administrators and users to create a one-to-one mapping between Windows users and their corresponding non-Windows credentials.</span></span> <span data-ttu-id="75aeb-106">在使用单项映射时，用户可以管理他们自己的映射。</span><span class="sxs-lookup"><span data-stu-id="75aeb-106">When using individual mappings, users can manage their own mappings.</span></span> <span data-ttu-id="75aeb-107">SSO 系统可维护用户的 Windows 帐户与该用户的非 Windows 帐户间的一对一关系。</span><span class="sxs-lookup"><span data-stu-id="75aeb-107">The SSO system maintains the one-to-one relation for the user's Windows account and the user's non-Windows account.</span></span>  
  
 <span data-ttu-id="75aeb-108">Windows 最终用户可以为单项类型的应用程序创建和管理他们自己的映射。</span><span class="sxs-lookup"><span data-stu-id="75aeb-108">Windows End-users can create and manage their own mappings for individual type applications.</span></span> <span data-ttu-id="75aeb-109">同一关联应用程序可以用作 Windows 启动的 SSO 类型应用程序和主机启动的 SSO 类型应用程序。</span><span class="sxs-lookup"><span data-stu-id="75aeb-109">The same affiliate application can act as a Windows Initiated SSO and a Host Initiated SSO type application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="75aeb-110">只能为 Windows 域帐户创建映射。</span><span class="sxs-lookup"><span data-stu-id="75aeb-110">Mappings can be created only for Windows domain accounts.</span></span> <span data-ttu-id="75aeb-111">无法映射本地帐户。</span><span class="sxs-lookup"><span data-stu-id="75aeb-111">Local accounts cannot be mapped.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="75aeb-112">在使用单项映射时，只有用户本人才可以获得其个人帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="75aeb-112">Only individual users can obtain the credentials to their individual accounts when using individual mappings.</span></span>  
  
## <a name="group-mapping"></a><span data-ttu-id="75aeb-113">组映射</span><span class="sxs-lookup"><span data-stu-id="75aeb-113">Group Mapping</span></span>  
 <span data-ttu-id="75aeb-114">SSO 组映射由从 Windows 组指向关联应用程序中的单个帐户的映射组成，该 Windows 组包含多个 Windows 用户。</span><span class="sxs-lookup"><span data-stu-id="75aeb-114">SSO group mapping consists of mapping a Windows group, which contains multiple Windows users, to a single account in the affiliate application.</span></span>  
  
 <span data-ttu-id="75aeb-115">也可以为 SSO 应用程序用户角色指定多个帐户。</span><span class="sxs-lookup"><span data-stu-id="75aeb-115">You can also specify multiple accounts for the SSO Application Users role.</span></span> <span data-ttu-id="75aeb-116">所指定的每个帐户均可与外部帐户关联。</span><span class="sxs-lookup"><span data-stu-id="75aeb-116">Each account you specify can be associated with an external account.</span></span> <span data-ttu-id="75aeb-117">例如，您可以将域组帐户映射到 EXTERNALUSER1，并将个人域帐户映射到 EXTERNALUSER2。</span><span class="sxs-lookup"><span data-stu-id="75aeb-117">For example, you can map a domain group account to EXTERNALUSER1 and an individual domain account to EXTERNALUSER2.</span></span> <span data-ttu-id="75aeb-118">如果同一用户具有多个映射，则使用 SSO 应用程序用户顺序中的第一个映射。</span><span class="sxs-lookup"><span data-stu-id="75aeb-118">If the same user has more than one mapping, the first mapping in the order of SSO Application Users is used.</span></span>  
  
 <span data-ttu-id="75aeb-119">只有应用程序管理员、SSO 关联管理员或 SSO 管理员才可以创建或管理组映射。</span><span class="sxs-lookup"><span data-stu-id="75aeb-119">Only an application administrator, SSO affiliate administrator, or SSO administrator can create or manage a group mapping.</span></span>  
  
 <span data-ttu-id="75aeb-120">不能为 Windows 启动的 SSO 和主机启动的 SSO 指定相同的组应用程序。</span><span class="sxs-lookup"><span data-stu-id="75aeb-120">You cannot specify the same group application for Windows initiated SSO and Host Initiated SSO.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="75aeb-121">只能为 Windows 域帐户创建映射。</span><span class="sxs-lookup"><span data-stu-id="75aeb-121">Mappings can be created only for Windows domain accounts.</span></span> <span data-ttu-id="75aeb-122">无法映射本地帐户。</span><span class="sxs-lookup"><span data-stu-id="75aeb-122">Local accounts cannot be mapped.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="75aeb-123">在使用组映射时，组成员可以获得组映射的凭据信息。</span><span class="sxs-lookup"><span data-stu-id="75aeb-123">When you use group mappings, the members of the group can obtain the credential information for the group mapping.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75aeb-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75aeb-124">See Also</span></span>  
 <span data-ttu-id="75aeb-125">[管理用户映射](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="75aeb-125">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="75aeb-126">SSO 关联应用程序</span><span class="sxs-lookup"><span data-stu-id="75aeb-126">SSO Affiliate Applications</span></span>](../core/sso-affiliate-applications.md)