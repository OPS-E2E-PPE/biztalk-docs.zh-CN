---
title: SSO 映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps [SSO]
- maps [SSO], creating
- SSO, maps
ms.assetid: b44f7a0c-595c-49dc-9d75-2e76f29dca88
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5debd3e1dcf1ee0e45d421e777006d247a6da84f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258613"
---
# <a name="sso-mappings"></a><span data-ttu-id="26ca1-102">SSO 映射</span><span class="sxs-lookup"><span data-stu-id="26ca1-102">SSO Mappings</span></span>
<span data-ttu-id="26ca1-103">当企业单一登录 (SSO) 管理员或 SSO 关联管理员定义关联应用程序时，管理员可以将其定义为具有单项映射的应用程序或使用组映射的应用程序。</span><span class="sxs-lookup"><span data-stu-id="26ca1-103">When an Enterprise Single Sign-On (SSO) administrator or an SSO affiliate administrator defines an affiliate application, the administrator can define it either as an application with individual mappings, or as an application with a group mapping.</span></span>  
  
## <a name="individual-mappings"></a><span data-ttu-id="26ca1-104">单项映射</span><span class="sxs-lookup"><span data-stu-id="26ca1-104">Individual Mappings</span></span>  
 <span data-ttu-id="26ca1-105">SSO 单项映射，管理员和用户可创建 Windows 用户和其相应的非 Windows 凭据之间的一对一映射。</span><span class="sxs-lookup"><span data-stu-id="26ca1-105">SSO individual mappings enable administrators and users to create a one-to-one mapping between Windows users and their corresponding non-Windows credentials.</span></span> <span data-ttu-id="26ca1-106">在使用单项映射时，用户可以管理他们自己的映射。</span><span class="sxs-lookup"><span data-stu-id="26ca1-106">When using individual mappings, users can manage their own mappings.</span></span> <span data-ttu-id="26ca1-107">SSO 系统会维护有关用户的 Windows 帐户和用户的非 Windows 帐户的一对一关系。</span><span class="sxs-lookup"><span data-stu-id="26ca1-107">The SSO system maintains the one-to-one relation for the user's Windows account and the user's non-Windows account.</span></span>  
  
 <span data-ttu-id="26ca1-108">Windows 最终用户可以创建和管理他们自己的映射的各个类型的应用程序。</span><span class="sxs-lookup"><span data-stu-id="26ca1-108">Windows End-users can create and manage their own mappings for individual type applications.</span></span> <span data-ttu-id="26ca1-109">同一关联应用程序可充当 Windows 启动的 SSO 和主机启动的 SSO 类型应用程序。</span><span class="sxs-lookup"><span data-stu-id="26ca1-109">The same affiliate application can act as a Windows Initiated SSO and a Host Initiated SSO type application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="26ca1-110">可以仅为 Windows 域帐户创建映射。</span><span class="sxs-lookup"><span data-stu-id="26ca1-110">Mappings can be created only for Windows domain accounts.</span></span> <span data-ttu-id="26ca1-111">无法映射本地帐户。</span><span class="sxs-lookup"><span data-stu-id="26ca1-111">Local accounts cannot be mapped.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="26ca1-112">使用单项映射时，只有用户可以获取其个人帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="26ca1-112">Only individual users can obtain the credentials to their individual accounts when using individual mappings.</span></span>  
  
## <a name="group-mapping"></a><span data-ttu-id="26ca1-113">组映射</span><span class="sxs-lookup"><span data-stu-id="26ca1-113">Group Mapping</span></span>  
 <span data-ttu-id="26ca1-114">将 Windows 组，其中包含多个 Windows 用户，映射到关联应用程序中的单个帐户包含 SSO 组映射。</span><span class="sxs-lookup"><span data-stu-id="26ca1-114">SSO group mapping consists of mapping a Windows group, which contains multiple Windows users, to a single account in the affiliate application.</span></span>  
  
 <span data-ttu-id="26ca1-115">此外可以指定为 SSO 应用程序用户角色的多个帐户。</span><span class="sxs-lookup"><span data-stu-id="26ca1-115">You can also specify multiple accounts for the SSO Application Users role.</span></span> <span data-ttu-id="26ca1-116">指定每个帐户可以与外部帐户相关联。</span><span class="sxs-lookup"><span data-stu-id="26ca1-116">Each account you specify can be associated with an external account.</span></span> <span data-ttu-id="26ca1-117">例如，可以将域组帐户映射到 EXTERNALUSER1，并将个人域帐户到 EXTERNALUSER2。</span><span class="sxs-lookup"><span data-stu-id="26ca1-117">For example, you can map a domain group account to EXTERNALUSER1 and an individual domain account to EXTERNALUSER2.</span></span> <span data-ttu-id="26ca1-118">如果同一用户具有多个映射，则使用 SSO 应用程序用户顺序的第一个映射。</span><span class="sxs-lookup"><span data-stu-id="26ca1-118">If the same user has more than one mapping, the first mapping in the order of SSO Application Users is used.</span></span>  
  
 <span data-ttu-id="26ca1-119">只有应用程序管理员、 SSO 关联管理员或 SSO 管理员可以创建或管理组映射。</span><span class="sxs-lookup"><span data-stu-id="26ca1-119">Only an application administrator, SSO affiliate administrator, or SSO administrator can create or manage a group mapping.</span></span>  
  
 <span data-ttu-id="26ca1-120">不能指定同一组应用程序的 Windows 启动的 SSO 和主机启动的 SSO。</span><span class="sxs-lookup"><span data-stu-id="26ca1-120">You cannot specify the same group application for Windows initiated SSO and Host Initiated SSO.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="26ca1-121">可以仅为 Windows 域帐户创建映射。</span><span class="sxs-lookup"><span data-stu-id="26ca1-121">Mappings can be created only for Windows domain accounts.</span></span> <span data-ttu-id="26ca1-122">无法映射本地帐户。</span><span class="sxs-lookup"><span data-stu-id="26ca1-122">Local accounts cannot be mapped.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="26ca1-123">当你使用组映射时，组的成员可以获得组映射的凭据信息。</span><span class="sxs-lookup"><span data-stu-id="26ca1-123">When you use group mappings, the members of the group can obtain the credential information for the group mapping.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26ca1-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="26ca1-124">See Also</span></span>  
 <span data-ttu-id="26ca1-125">[管理用户映射](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="26ca1-125">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="26ca1-126">SSO 关联应用程序</span><span class="sxs-lookup"><span data-stu-id="26ca1-126">SSO Affiliate Applications</span></span>](../core/sso-affiliate-applications.md)