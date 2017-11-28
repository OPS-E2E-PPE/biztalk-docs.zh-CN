---
title: "SSO 用户组 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- administrator accounts, SSO
- groups, SSO
- user accounts, administrators
- service accounts, SSO
- SSO, user groups
- SSO, service accounts
- SSO, administrator accounts
ms.assetid: e279001e-c724-4a2d-8939-0ba9dd08a19c
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 949f3aa72771982321abf6904c43352b8821fc0c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sso-user-groups"></a><span data-ttu-id="55c39-102">SSO 用户组</span><span class="sxs-lookup"><span data-stu-id="55c39-102">SSO User Groups</span></span>
<span data-ttu-id="55c39-103">若要配置和管理企业单一登录 (SSO) 系统，必须为其中每个角色创建某些 Windows 组和帐户。</span><span class="sxs-lookup"><span data-stu-id="55c39-103">To configure and manage the Enterprise Single Sign-On (SSO) system, you must create certain Windows groups and accounts for each of these roles.</span></span> <span data-ttu-id="55c39-104">在企业 sso 配置的访问帐户，你可以为每个这些角色指定多个帐户。</span><span class="sxs-lookup"><span data-stu-id="55c39-104">When configuring the access accounts in Enterprise SSO, you can specify more than one account for each of these roles.</span></span> <span data-ttu-id="55c39-105">本部分介绍这些角色。</span><span class="sxs-lookup"><span data-stu-id="55c39-105">This section describes these roles.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="55c39-106">强烈建议你配置 SSO 时使用域组。</span><span class="sxs-lookup"><span data-stu-id="55c39-106">It is strongly recommended that you use domain groups when configuring SSO.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="55c39-107">出于安全考虑，SSO 系统不允许内置帐户。</span><span class="sxs-lookup"><span data-stu-id="55c39-107">For security purposes, the SSO system does not allow built-in accounts.</span></span>  
  
## <a name="single-sign-on-administrators"></a><span data-ttu-id="55c39-108">单一登录管理员</span><span class="sxs-lookup"><span data-stu-id="55c39-108">Single Sign-On Administrators</span></span>  
 <span data-ttu-id="55c39-109">SSO 管理员 SSO 系统中具有最高的级别的用户权限。</span><span class="sxs-lookup"><span data-stu-id="55c39-109">SSO administrators have the highest level user rights in the SSO system.</span></span> <span data-ttu-id="55c39-110">用户可以：</span><span class="sxs-lookup"><span data-stu-id="55c39-110">They can:</span></span>  
  
-   <span data-ttu-id="55c39-111">创建和管理 SSO 数据库</span><span class="sxs-lookup"><span data-stu-id="55c39-111">Create and manage the SSO database</span></span>  
  
-   <span data-ttu-id="55c39-112">创建和管理主密钥</span><span class="sxs-lookup"><span data-stu-id="55c39-112">Create and manage the master secret</span></span>  
  
-   <span data-ttu-id="55c39-113">启用和禁用 SSO 系统</span><span class="sxs-lookup"><span data-stu-id="55c39-113">Enable and disable the SSO system</span></span>  
  
-   <span data-ttu-id="55c39-114">创建密码同步适配器</span><span class="sxs-lookup"><span data-stu-id="55c39-114">Create password synchronization adapters</span></span>  
  
-   <span data-ttu-id="55c39-115">启用和禁用 SSO 系统中的密码同步</span><span class="sxs-lookup"><span data-stu-id="55c39-115">Enable and disable password synchronization in the SSO system</span></span>  
  
-   <span data-ttu-id="55c39-116">启用和禁用主机启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="55c39-116">Enable and disable host initiated SSO</span></span>  
  
-   <span data-ttu-id="55c39-117">执行所有管理任务</span><span class="sxs-lookup"><span data-stu-id="55c39-117">Perform all administration tasks</span></span>  
  
 <span data-ttu-id="55c39-118">SSO administrators 帐户可以是 Windows 组帐户或个人帐户。</span><span class="sxs-lookup"><span data-stu-id="55c39-118">The SSO administrators account can be either a Windows group account or an individual account.</span></span> <span data-ttu-id="55c39-119">域或本地组或个人帐户，也可以是 SSO administrators 帐户。</span><span class="sxs-lookup"><span data-stu-id="55c39-119">The SSO administrators account can also be either a domain or local group or individual account.</span></span> <span data-ttu-id="55c39-120">时使用个人帐户，不能为其他个人帐户更改此帐户。</span><span class="sxs-lookup"><span data-stu-id="55c39-120">When using an individual account, you cannot change this account to another individual account.</span></span> <span data-ttu-id="55c39-121">因此，建议不使用个人帐户。</span><span class="sxs-lookup"><span data-stu-id="55c39-121">Therefore, it is recommended that you do not use an individual account.</span></span> <span data-ttu-id="55c39-122">只要原始帐户是新帐户的成员，可以更改此帐户为组帐户。</span><span class="sxs-lookup"><span data-stu-id="55c39-122">You can change this account to a group account as long as the original account is a member of the new account.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="55c39-123">运行企业单一登录服务的服务帐户必须是此帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="55c39-123">The service account running the Enterprise Single Sign-On service must be a member of this account.</span></span> <span data-ttu-id="55c39-124">若要保护你的环境，请确保没有其他服务正在使用的相同服务帐户。</span><span class="sxs-lookup"><span data-stu-id="55c39-124">To secure your environment, ensure that no other service is using the same service account.</span></span>  
  
## <a name="single-sign-on-affiliate-administrators"></a><span data-ttu-id="55c39-125">单一登录在分支机构管理员</span><span class="sxs-lookup"><span data-stu-id="55c39-125">Single Sign-On Affiliate Administrators</span></span>  
 <span data-ttu-id="55c39-126">SSO 关联管理员将定义 SSO 系统包含关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="55c39-126">The SSO affiliate administrator defines the affiliate applications that the SSO system contains.</span></span> <span data-ttu-id="55c39-127">关联应用程序是表示使用 SSO 连接后端系统的逻辑实体。</span><span class="sxs-lookup"><span data-stu-id="55c39-127">Affiliate applications are a logical entity that represents the back-end system to which you are connecting using SSO.</span></span> <span data-ttu-id="55c39-128">SSO affiliate 管理员可以：</span><span class="sxs-lookup"><span data-stu-id="55c39-128">SSO affiliate administrators can:</span></span>  
  
-   <span data-ttu-id="55c39-129">创建、 管理和删除关联应用程序</span><span class="sxs-lookup"><span data-stu-id="55c39-129">Create, manage, and delete affiliate applications</span></span>  
  
-   <span data-ttu-id="55c39-130">指定每个关联应用程序的应用程序管理员帐户</span><span class="sxs-lookup"><span data-stu-id="55c39-130">Specify the application administrators account for each affiliate application</span></span>  
  
-   <span data-ttu-id="55c39-131">执行应用程序管理员和应用程序用户可以的所有管理任务</span><span class="sxs-lookup"><span data-stu-id="55c39-131">Perform all the administration tasks that the application administrators and application users can</span></span>  
  
 <span data-ttu-id="55c39-132">SSO Affiliate Administrator 帐户可以是 Windows 组帐户或个人帐户。</span><span class="sxs-lookup"><span data-stu-id="55c39-132">The SSO Affiliate Administrator account can be either a Windows group account or an individual account.</span></span> <span data-ttu-id="55c39-133">域或本地组或帐户，也可以是 SSO Affiliate Administrator 帐户。</span><span class="sxs-lookup"><span data-stu-id="55c39-133">The SSO Affiliate Administrator account can also be either a domain or local group or account.</span></span>  
  
## <a name="application-administrators"></a><span data-ttu-id="55c39-134">应用程序管理员</span><span class="sxs-lookup"><span data-stu-id="55c39-134">Application Administrators</span></span>  
 <span data-ttu-id="55c39-135">没有每个关联应用程序的一个应用程序管理员组。</span><span class="sxs-lookup"><span data-stu-id="55c39-135">There is one application administrators group per affiliate application.</span></span>  
  
 <span data-ttu-id="55c39-136">此组的成员可以：</span><span class="sxs-lookup"><span data-stu-id="55c39-136">Members of this group can:</span></span>  
  
-   <span data-ttu-id="55c39-137">更改应用程序用户组帐户</span><span class="sxs-lookup"><span data-stu-id="55c39-137">Change the application users group account</span></span>  
  
-   <span data-ttu-id="55c39-138">创建、 删除和管理特定的关联应用程序的所有用户的凭据映射</span><span class="sxs-lookup"><span data-stu-id="55c39-138">Create, delete, and manage credential mappings for all users of the specific affiliate application</span></span>  
  
-   <span data-ttu-id="55c39-139">设置的任何用户的凭据，在于特定关联应用程序用户组帐户</span><span class="sxs-lookup"><span data-stu-id="55c39-139">Set credentials for any user in that specific affiliate application users group account</span></span>  
  
-   <span data-ttu-id="55c39-140">执行应用程序用户可以的所有管理任务</span><span class="sxs-lookup"><span data-stu-id="55c39-140">Perform all the administration tasks that the application users can</span></span>  
  
## <a name="application-users"></a><span data-ttu-id="55c39-141">应用程序用户</span><span class="sxs-lookup"><span data-stu-id="55c39-141">Application Users</span></span>  
 <span data-ttu-id="55c39-142">没有为每个关联应用程序的一个应用程序用户组帐户。</span><span class="sxs-lookup"><span data-stu-id="55c39-142">There is one application users group account for each affiliate application.</span></span> <span data-ttu-id="55c39-143">此帐户包含一个企业单一登录的环境中的最终用户的列表。</span><span class="sxs-lookup"><span data-stu-id="55c39-143">This account contains the list of end users in an Enterprise Single Sign-On environment.</span></span> <span data-ttu-id="55c39-144">此帐户的成员可以：</span><span class="sxs-lookup"><span data-stu-id="55c39-144">Members of this account can:</span></span>  
  
-   <span data-ttu-id="55c39-145">查找关联应用程序在其凭据</span><span class="sxs-lookup"><span data-stu-id="55c39-145">Look up their credentials in the affiliate application</span></span>  
  
-   <span data-ttu-id="55c39-146">管理关联应用程序在其凭据映射</span><span class="sxs-lookup"><span data-stu-id="55c39-146">Manage their credential mappings in the affiliate application</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="55c39-147">请记住要警惕，当将组分配。</span><span class="sxs-lookup"><span data-stu-id="55c39-147">Remember to be vigilant when assigning groups.</span></span> <span data-ttu-id="55c39-148">它是有可能，例如，使用 BizTalk Server 安全用户组为 SSO 应用程序用户组。</span><span class="sxs-lookup"><span data-stu-id="55c39-148">It is possible, for example, to use a BizTalk Server security user group for the SSO application users group.</span></span> <span data-ttu-id="55c39-149">执行此操作之前，请确保所有用户都需要将会提供给他们的所有访问。</span><span class="sxs-lookup"><span data-stu-id="55c39-149">Before you do this, be certain that all users need all access that will then be available to them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55c39-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55c39-150">See Also</span></span>  
 <span data-ttu-id="55c39-151">[如何更新关联应用程序的属性](../core/how-to-update-the-properties-of-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="55c39-151">[How to Update the Properties of an Affiliate Application](../core/how-to-update-the-properties-of-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="55c39-152">[如何更新 SSO 数据库](../core/how-to-update-the-sso-database.md) </span><span class="sxs-lookup"><span data-stu-id="55c39-152">[How to Update the SSO Database](../core/how-to-update-the-sso-database.md) </span></span>  
 <span data-ttu-id="55c39-153">[管理用户映射](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="55c39-153">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="55c39-154">了解 SSO</span><span class="sxs-lookup"><span data-stu-id="55c39-154">Understanding SSO</span></span>](../core/understanding-sso.md)