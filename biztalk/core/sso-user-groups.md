---
title: SSO 用户组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd38c0417c84f7130a40f54fb684b01b6b853623
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398952"
---
# <a name="sso-user-groups"></a><span data-ttu-id="0b9e0-102">SSO 用户组</span><span class="sxs-lookup"><span data-stu-id="0b9e0-102">SSO User Groups</span></span>
<span data-ttu-id="0b9e0-103">若要配置和管理企业单一登录 (SSO) 系统，必须为每个角色创建特定的 Windows 组和帐户。</span><span class="sxs-lookup"><span data-stu-id="0b9e0-103">To configure and manage the Enterprise Single Sign-On (SSO) system, you must create certain Windows groups and accounts for each of these roles.</span></span> <span data-ttu-id="0b9e0-104">在企业 SSO 中配置访问帐户，可以为每个角色指定多个帐户。</span><span class="sxs-lookup"><span data-stu-id="0b9e0-104">When configuring the access accounts in Enterprise SSO, you can specify more than one account for each of these roles.</span></span> <span data-ttu-id="0b9e0-105">本部分介绍这些角色。</span><span class="sxs-lookup"><span data-stu-id="0b9e0-105">This section describes these roles.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0b9e0-106">强烈建议配置 SSO 时使用域组。</span><span class="sxs-lookup"><span data-stu-id="0b9e0-106">It is strongly recommended that you use domain groups when configuring SSO.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b9e0-107">出于安全目的，SSO 系统不允许内置帐户。</span><span class="sxs-lookup"><span data-stu-id="0b9e0-107">For security purposes, the SSO system does not allow built-in accounts.</span></span>  
  
## <a name="single-sign-on-administrators"></a><span data-ttu-id="0b9e0-108">单一登录管理员</span><span class="sxs-lookup"><span data-stu-id="0b9e0-108">Single Sign-On Administrators</span></span>  
 <span data-ttu-id="0b9e0-109">SSO 管理员在 SSO 系统中具有最高的级别的用户权限。</span><span class="sxs-lookup"><span data-stu-id="0b9e0-109">SSO administrators have the highest level user rights in the SSO system.</span></span> <span data-ttu-id="0b9e0-110">他们可以：</span><span class="sxs-lookup"><span data-stu-id="0b9e0-110">They can:</span></span>  
  
- <span data-ttu-id="0b9e0-111">创建和管理 SSO 数据库</span><span class="sxs-lookup"><span data-stu-id="0b9e0-111">Create and manage the SSO database</span></span>  
  
- <span data-ttu-id="0b9e0-112">创建和管理主密钥</span><span class="sxs-lookup"><span data-stu-id="0b9e0-112">Create and manage the master secret</span></span>  
  
- <span data-ttu-id="0b9e0-113">启用和禁用 SSO 系统</span><span class="sxs-lookup"><span data-stu-id="0b9e0-113">Enable and disable the SSO system</span></span>  
  
- <span data-ttu-id="0b9e0-114">创建密码同步适配器</span><span class="sxs-lookup"><span data-stu-id="0b9e0-114">Create password synchronization adapters</span></span>  
  
- <span data-ttu-id="0b9e0-115">启用和禁用 SSO 系统中的密码同步</span><span class="sxs-lookup"><span data-stu-id="0b9e0-115">Enable and disable password synchronization in the SSO system</span></span>  
  
- <span data-ttu-id="0b9e0-116">启用和禁用主机启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="0b9e0-116">Enable and disable host initiated SSO</span></span>  
  
- <span data-ttu-id="0b9e0-117">执行所有管理任务</span><span class="sxs-lookup"><span data-stu-id="0b9e0-117">Perform all administration tasks</span></span>  
  
  <span data-ttu-id="0b9e0-118">SSO 管理员帐户可以是 Windows 组帐户或个人帐户。</span><span class="sxs-lookup"><span data-stu-id="0b9e0-118">The SSO administrators account can be either a Windows group account or an individual account.</span></span> <span data-ttu-id="0b9e0-119">域或本地组或个人帐户，也可以是 SSO 管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="0b9e0-119">The SSO administrators account can also be either a domain or local group or individual account.</span></span> <span data-ttu-id="0b9e0-120">如果使用个人帐户，则无法更改此帐户到另一个个人帐户。</span><span class="sxs-lookup"><span data-stu-id="0b9e0-120">When using an individual account, you cannot change this account to another individual account.</span></span> <span data-ttu-id="0b9e0-121">因此，建议不使用个人帐户。</span><span class="sxs-lookup"><span data-stu-id="0b9e0-121">Therefore, it is recommended that you do not use an individual account.</span></span> <span data-ttu-id="0b9e0-122">只要原始帐户是新帐户的成员，您可以更改此帐户为组帐户。</span><span class="sxs-lookup"><span data-stu-id="0b9e0-122">You can change this account to a group account as long as the original account is a member of the new account.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0b9e0-123">运行企业单一登录服务的服务帐户必须是此帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="0b9e0-123">The service account running the Enterprise Single Sign-On service must be a member of this account.</span></span> <span data-ttu-id="0b9e0-124">若要保护你的环境，请确保没有其他服务使用相同的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="0b9e0-124">To secure your environment, ensure that no other service is using the same service account.</span></span>  
  
## <a name="single-sign-on-affiliate-administrators"></a><span data-ttu-id="0b9e0-125">单一登录关联管理员</span><span class="sxs-lookup"><span data-stu-id="0b9e0-125">Single Sign-On Affiliate Administrators</span></span>  
 <span data-ttu-id="0b9e0-126">SSO 关联管理员定义 SSO 系统包含的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="0b9e0-126">The SSO affiliate administrator defines the affiliate applications that the SSO system contains.</span></span> <span data-ttu-id="0b9e0-127">关联应用程序是表示使用 SSO 连接在后端系统的逻辑实体。</span><span class="sxs-lookup"><span data-stu-id="0b9e0-127">Affiliate applications are a logical entity that represents the back-end system to which you are connecting using SSO.</span></span> <span data-ttu-id="0b9e0-128">SSO 关联管理员可以：</span><span class="sxs-lookup"><span data-stu-id="0b9e0-128">SSO affiliate administrators can:</span></span>  
  
- <span data-ttu-id="0b9e0-129">创建、 管理和删除关联应用程序</span><span class="sxs-lookup"><span data-stu-id="0b9e0-129">Create, manage, and delete affiliate applications</span></span>  
  
- <span data-ttu-id="0b9e0-130">指定每个关联应用程序的应用程序管理员帐户</span><span class="sxs-lookup"><span data-stu-id="0b9e0-130">Specify the application administrators account for each affiliate application</span></span>  
  
- <span data-ttu-id="0b9e0-131">执行所有的应用程序管理员和应用程序用户可以管理任务</span><span class="sxs-lookup"><span data-stu-id="0b9e0-131">Perform all the administration tasks that the application administrators and application users can</span></span>  
  
  <span data-ttu-id="0b9e0-132">SSO 关联管理员帐户可以是 Windows 组帐户或个人帐户。</span><span class="sxs-lookup"><span data-stu-id="0b9e0-132">The SSO Affiliate Administrator account can be either a Windows group account or an individual account.</span></span> <span data-ttu-id="0b9e0-133">SSO 关联管理员帐户也可以是域或本地组或帐户。</span><span class="sxs-lookup"><span data-stu-id="0b9e0-133">The SSO Affiliate Administrator account can also be either a domain or local group or account.</span></span>  
  
## <a name="application-administrators"></a><span data-ttu-id="0b9e0-134">应用程序管理员</span><span class="sxs-lookup"><span data-stu-id="0b9e0-134">Application Administrators</span></span>  
 <span data-ttu-id="0b9e0-135">没有每个关联应用程序的一个应用程序管理员组。</span><span class="sxs-lookup"><span data-stu-id="0b9e0-135">There is one application administrators group per affiliate application.</span></span>  
  
 <span data-ttu-id="0b9e0-136">此组的成员可以：</span><span class="sxs-lookup"><span data-stu-id="0b9e0-136">Members of this group can:</span></span>  
  
-   <span data-ttu-id="0b9e0-137">更改应用程序用户组帐户</span><span class="sxs-lookup"><span data-stu-id="0b9e0-137">Change the application users group account</span></span>  
  
-   <span data-ttu-id="0b9e0-138">创建、 删除和管理的特定关联应用程序的所有用户的凭据映射</span><span class="sxs-lookup"><span data-stu-id="0b9e0-138">Create, delete, and manage credential mappings for all users of the specific affiliate application</span></span>  
  
-   <span data-ttu-id="0b9e0-139">为任何用户设置凭据，特定关联应用程序用户组帐户</span><span class="sxs-lookup"><span data-stu-id="0b9e0-139">Set credentials for any user in that specific affiliate application users group account</span></span>  
  
-   <span data-ttu-id="0b9e0-140">执行应用程序用户的所有管理任务</span><span class="sxs-lookup"><span data-stu-id="0b9e0-140">Perform all the administration tasks that the application users can</span></span>  
  
## <a name="application-users"></a><span data-ttu-id="0b9e0-141">应用程序用户</span><span class="sxs-lookup"><span data-stu-id="0b9e0-141">Application Users</span></span>  
 <span data-ttu-id="0b9e0-142">有了一个应用程序用户组帐户的每个关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="0b9e0-142">There is one application users group account for each affiliate application.</span></span> <span data-ttu-id="0b9e0-143">此帐户包含企业单一登录的环境中的最终用户的列表。</span><span class="sxs-lookup"><span data-stu-id="0b9e0-143">This account contains the list of end users in an Enterprise Single Sign-On environment.</span></span> <span data-ttu-id="0b9e0-144">此帐户的成员可以：</span><span class="sxs-lookup"><span data-stu-id="0b9e0-144">Members of this account can:</span></span>  
  
-   <span data-ttu-id="0b9e0-145">查找凭据，关联应用程序</span><span class="sxs-lookup"><span data-stu-id="0b9e0-145">Look up their credentials in the affiliate application</span></span>  
  
-   <span data-ttu-id="0b9e0-146">管理关联应用程序中的其凭据映射</span><span class="sxs-lookup"><span data-stu-id="0b9e0-146">Manage their credential mappings in the affiliate application</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b9e0-147">请记住将组分配时要警惕。</span><span class="sxs-lookup"><span data-stu-id="0b9e0-147">Remember to be vigilant when assigning groups.</span></span> <span data-ttu-id="0b9e0-148">它是有可能，例如，使用 BizTalk Server 安全用户组为 SSO 应用程序用户组。</span><span class="sxs-lookup"><span data-stu-id="0b9e0-148">It is possible, for example, to use a BizTalk Server security user group for the SSO application users group.</span></span> <span data-ttu-id="0b9e0-149">执行此操作之前，请确保所有用户都需要然后将提供给他们的所有访问。</span><span class="sxs-lookup"><span data-stu-id="0b9e0-149">Before you do this, be certain that all users need all access that will then be available to them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b9e0-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b9e0-150">See Also</span></span>  
 <span data-ttu-id="0b9e0-151">[如何更新关联应用程序的属性](../core/how-to-update-the-properties-of-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="0b9e0-151">[How to Update the Properties of an Affiliate Application](../core/how-to-update-the-properties-of-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="0b9e0-152">[如何更新 SSO 数据库](../core/how-to-update-the-sso-database.md) </span><span class="sxs-lookup"><span data-stu-id="0b9e0-152">[How to Update the SSO Database](../core/how-to-update-the-sso-database.md) </span></span>  
 <span data-ttu-id="0b9e0-153">[管理用户映射](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="0b9e0-153">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="0b9e0-154">了解 SSO</span><span class="sxs-lookup"><span data-stu-id="0b9e0-154">Understanding SSO</span></span>](../core/understanding-sso.md)