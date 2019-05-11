---
title: 业务规则框架安全性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, code samples
- security, business rules
- artifacts, security
- security, artifacts
- business rules, security
ms.assetid: 86582d3a-259e-47f2-9f72-8dbbe0051503
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 078c4671fbc587b56ce1dafed0e9676ddadbd7d0
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530423"
---
# <a name="business-rules-framework-security"></a><span data-ttu-id="19797-102">业务规则框架安全性</span><span class="sxs-lookup"><span data-stu-id="19797-102">Business Rules Framework Security</span></span>
<span data-ttu-id="19797-103">业务规则引擎会在宿主应用程序的安全上下文运行。</span><span class="sxs-lookup"><span data-stu-id="19797-103">The Business Rule Engine operates in the security context of the hosting application.</span></span> <span data-ttu-id="19797-104">在执行过程的规则引擎实例的标识是，线程上下文的调用**Policy.Execute**方法。</span><span class="sxs-lookup"><span data-stu-id="19797-104">The identity of the rule engine instance during execution is that of the thread context that invokes the **Policy.Execute** method.</span></span>  
  
## <a name="default-security-configuration"></a><span data-ttu-id="19797-105">默认的安全配置</span><span class="sxs-lookup"><span data-stu-id="19797-105">Default security configuration</span></span>  
 <span data-ttu-id="19797-106">当你安装 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、 两个默认情况下，管理员和用户创建 Microsoft Windows 组："BizTalk Server 管理员"和"BizTalk 应用程序用户"。</span><span class="sxs-lookup"><span data-stu-id="19797-106">When you install Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], two Microsoft Windows groups are created by default, one for administrators and one for users: "BizTalk Server Administrators" and "BizTalk Application Users."</span></span> <span data-ttu-id="19797-107">这两个 Windows 组是 BTS_ADMIN_USERS 和 BTS_HOST_USERS SQL 角色分别为 RE_ADMIN_USERS 和 RE_HOST_USERS SQL 角色的成员的成员。</span><span class="sxs-lookup"><span data-stu-id="19797-107">These two Windows groups are members of BTS_ADMIN_USERS and BTS_HOST_USERS SQL Roles which are members of RE_ADMIN_USERS and RE_HOST_USERS SQL Roles respectively.</span></span>  
  
 <span data-ttu-id="19797-108">每当创建规则存储时，会创建默认 SQL 角色：BTS_ADMIN_USERS、 BTS_HOST_USERS、 RE_ADMIN_USERS 和 RE_HOST_USERS。</span><span class="sxs-lookup"><span data-stu-id="19797-108">The default SQL roles are created whenever a rule store is created: BTS_ADMIN_USERS, BTS_HOST_USERS, RE_ADMIN_USERS and RE_HOST_USERS.</span></span>  
  
|<span data-ttu-id="19797-109">默认 Windows 组</span><span class="sxs-lookup"><span data-stu-id="19797-109">Default Windows groups</span></span>|<span data-ttu-id="19797-110">SQL 角色</span><span class="sxs-lookup"><span data-stu-id="19797-110">SQL roles</span></span>|  
|----------------------------|---------------|  
|<span data-ttu-id="19797-111">BizTalk Server Administrators</span><span class="sxs-lookup"><span data-stu-id="19797-111">BizTalk Server Administrators</span></span>|<span data-ttu-id="19797-112">RE_ADMIN_USERS</span><span class="sxs-lookup"><span data-stu-id="19797-112">RE_ADMIN_USERS</span></span>|  
|<span data-ttu-id="19797-113">BizTalk Application Users</span><span class="sxs-lookup"><span data-stu-id="19797-113">BizTalk Application Users</span></span>|<span data-ttu-id="19797-114">RE_HOST_USERS</span><span class="sxs-lookup"><span data-stu-id="19797-114">RE_HOST_USERS</span></span>|  
  
 <span data-ttu-id="19797-115">只有 RE_ADMIN_USERS 角色中的用户可以执行更新部署表和实体访问保护配置表的存储的过程。</span><span class="sxs-lookup"><span data-stu-id="19797-115">Only users in the RE_ADMIN_USERS role can execute the stored procedures that update the deployment and entity access protection configuration tables.</span></span> <span data-ttu-id="19797-116">这意味着，部署、 取消部署和保护配置所有这样的是仅由规则引擎管理员。</span><span class="sxs-lookup"><span data-stu-id="19797-116">This means that the deployment, undeployment, and protection configuration are all done only by rule engine administrators.</span></span> <span data-ttu-id="19797-117">RE_HOST_USERS 角色中的用户可以在 SQL 规则存储中执行的其他存储的过程。</span><span class="sxs-lookup"><span data-stu-id="19797-117">Users in the RE_HOST_USERS role can execute the other stored procedures in the SQL rule store.</span></span>  
  
 <span data-ttu-id="19797-118">而不考虑的规则引擎的安装顺序，规则引擎配置进程授予规则引擎更新服务帐户成员身份为 RE_HOST_USERS SQL 角色中，如果它尚不包含数据库访问权限。</span><span class="sxs-lookup"><span data-stu-id="19797-118">Regardless of the order of installation of the rule engine, the rule engine configuration process grants the Rule Engine Update Service account membership to the RE_HOST_USERS SQL role, if it does not already have database access.</span></span> <span data-ttu-id="19797-119">但是，如果安装规则引擎后初始 BizTalk 安装 BizTalk，特定于宿主的用户组未添加到规则引擎数据库中的 BTS_HOST_USERS SQL 角色由于主机创建已完成。</span><span class="sxs-lookup"><span data-stu-id="19797-119">However, if the rule engine is installed after the initial BizTalk installation the BizTalk, host-specific users group is not added to the BTS_HOST_USERS SQL role in the Rule Engine database because host creation has already been completed.</span></span> <span data-ttu-id="19797-120">您需要手动执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="19797-120">You need to perform this step manually.</span></span>  
  
## <a name="artifact-level-security"></a><span data-ttu-id="19797-121">项目级别安全性</span><span class="sxs-lookup"><span data-stu-id="19797-121">Artifact level security</span></span>  
 <span data-ttu-id="19797-122">除了默认的安全配置，业务规则引擎还可以提供该项目的安全性，策略和词汇级别。</span><span class="sxs-lookup"><span data-stu-id="19797-122">In addition to the default security configuration, the Business Rule Engine can also provide security at the artifact—policy and vocabulary level.</span></span>  
  
 <span data-ttu-id="19797-123">每个策略或词汇版本都具有一个或多个与之关联的授权组。</span><span class="sxs-lookup"><span data-stu-id="19797-123">Each policy or vocabulary version has one or more authorization groups associated with it.</span></span> <span data-ttu-id="19797-124">授权组是 Microsoft Windows 用户、 SQL 用户、 SQL 角色和具有特定访问级别对每种类型的 Windows 组的一个命名的列表。</span><span class="sxs-lookup"><span data-stu-id="19797-124">An Authorization group is a named list of Microsoft Windows users, SQL users, SQL roles, and Windows groups, with a particular access level on each type.</span></span>  
  
 <span data-ttu-id="19797-125">规则存储中创建新策略或词汇后，只有创建了它以及规则引擎管理员的用户具有读取/执行和默认情况下修改/删除访问权限。</span><span class="sxs-lookup"><span data-stu-id="19797-125">When a new policy or vocabulary is created in the rule store, only the user who created it and the rule engine administrator have both read/execute and modify/delete access by default.</span></span> <span data-ttu-id="19797-126">规则引擎管理员可以配置哪些用户 （根据用户凭据运行进程） 具有的访问级别或权限，以执行不同的操作-读取/执行、 修改/删除、 完全权限或没有权限。</span><span class="sxs-lookup"><span data-stu-id="19797-126">The rule engine administrator can configure which users (processes operate under user credentials) have the access level, or rights, to perform different operations—read/execute, modify/delete, full permission, or no permission.</span></span>  
  
 <span data-ttu-id="19797-127">默认情况下不启用项目特定安全性。</span><span class="sxs-lookup"><span data-stu-id="19797-127">Artifact specific security is not enabled by default.</span></span> <span data-ttu-id="19797-128">设置项目级别安全性不是当前可通过用户界面。</span><span class="sxs-lookup"><span data-stu-id="19797-128">Setting artifact level security is not currently available through the user interface.</span></span> <span data-ttu-id="19797-129">但是，它可以设置以编程方式使用业务规则引擎管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="19797-129">However, it can be set programmatically with the Business Rule Engine administrator credential.</span></span> <span data-ttu-id="19797-130">下面的代码段演示如何创建新的授权并将关联到规则集的组。</span><span class="sxs-lookup"><span data-stu-id="19797-130">The following code fragment shows how to create a new authorization and associate the group to a rule set.</span></span>  
  
```  
RuleSet rs;  
string RSName;     
  
// Create new user  
AuthorizationGroupEntry newuser = new AuthorizationGroupEntry(UserName, UID);  
AuthorizationGroupEntryCollection AGEC = new AuthorizationGroupEntryCollection();  
AGEC.Add(newuser);  
  
// Define new authorization group collection  
AuthorizationGroupCollection AGC = new AuthorizationGroupCollection();  
  
// Create new authorization group  
AuthorizationGroup AG = new AuthorizationGroup(GroupName, AccessPermit, AGEC);  
  
//add the authorization group to the authorization group collection  
AGC.Add(AG);  
  
//saving the authorization group collection to the rule store  
m_sqlRS.SaveAuthorizationGroups(AGC);  
  
rs = m_sqlRS.GetRuleSet(rsInfo[0]);                 
RSName = rs.Name;  
  
// Associate authorization group to the ruleset  
m_sqlRS.SetRuleSetAuthorizations(RSName, AGC);  
  
// Get ruleset by name from SQL rule store  
RuleSetInfoCollection rsInfo = m_sqlRS.GetRuleSets("myRuleSet", RuleStore.Filter.All);  
```  
  
> [!NOTE]
>  <span data-ttu-id="19797-131">使用项目级别 l 安全性会降低性能，因为该策略将只需每次执行返回的规则引擎实例前评估应用程序的访问级别上进行的数据库查找。</span><span class="sxs-lookup"><span data-stu-id="19797-131">The use of artifact level l security can diminish performance, because the policy will have to do a database lookup on each execution to evaluate the application's access level before returning an instance of the rule engine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19797-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="19797-132">See Also</span></span>  
 [<span data-ttu-id="19797-133">业务规则引擎的重要安全说明</span><span class="sxs-lookup"><span data-stu-id="19797-133">Important Security Notes for the Business Rule Engine</span></span>](../core/important-security-notes-for-the-business-rule-engine.md)