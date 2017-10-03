---
title: "重要的安全注意事项业务规则引擎 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- business rules, store administrator
- Business Rule Composer, security
- business rules, security
- Denial of Service attacks
ms.assetid: 8972127a-5569-4b32-bc09-e9265efe9514
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a90090c55dcbb0f8e55296d2711d5e4b36cd346
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="important-security-notes-for-the-business-rule-engine"></a><span data-ttu-id="1efeb-102">业务规则引擎的重要的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="1efeb-102">Important Security Notes for the Business Rule Engine</span></span>
<span data-ttu-id="1efeb-103">本主题概括介绍了 Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 中已知的安全问题以及缓解这些安全风险所必须采取的步骤。</span><span class="sxs-lookup"><span data-stu-id="1efeb-103">This topic summarizes known security issues in Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] and the steps you must take to mitigate the security risks.</span></span>  
  
## <a name="malicious-schema-input-causing-denial-of-service-attack"></a><span data-ttu-id="1efeb-104">导致拒绝服务攻击的恶意架构输入</span><span class="sxs-lookup"><span data-stu-id="1efeb-104">Malicious schema input causing Denial of Service attack</span></span>  
 <span data-ttu-id="1efeb-105">在添加事实时，将根据与策略内所支持类型匹配的每个对象来验证每条规则。</span><span class="sxs-lookup"><span data-stu-id="1efeb-105">While asserting facts, each rule is verified against every object that matches the supported types within a policy.</span></span> <span data-ttu-id="1efeb-106">假定策略中有一条规则根据一个选择器使用所传递架构中的某个元素。</span><span class="sxs-lookup"><span data-stu-id="1efeb-106">Suppose there is a rule in a policy that uses one of the elements in a schema passed by using a selector.</span></span> <span data-ttu-id="1efeb-107">在此情形下，如果与该选择器匹配的元素/属性的实例出现数千次，则会添加所有此类实例，这将导致性能下降，随后可能导致拒绝服务 (DoS)。</span><span class="sxs-lookup"><span data-stu-id="1efeb-107">Now if the instance if this element/attribute that matches the selector is repeated thousands of times, every such instance is asserted, causing performance degradation and subsequent possible Denial of Service (DoS).</span></span>  
  
 <span data-ttu-id="1efeb-108">若要缓解这种潜在问题，则需要对执行策略时传递的所有不明确的输入进行验证。</span><span class="sxs-lookup"><span data-stu-id="1efeb-108">To mitigate this potential issue, you need to validate all ambiguous input that is passed while executing a policy.</span></span>  
  
## <a name="ruleset-not-validating-objects-before-asserting-the-facts"></a><span data-ttu-id="1efeb-109">规则集在添加事实前不验证对象</span><span class="sxs-lookup"><span data-stu-id="1efeb-109">RuleSet not validating objects before asserting the facts</span></span>  
 <span data-ttu-id="1efeb-110">任何架构实例传递与的事实数据到**RuleSet**然后再判断使用选择器的所有规则不针对架构验证。</span><span class="sxs-lookup"><span data-stu-id="1efeb-110">Any schema instance passed as a fact to the **RuleSet** is not validated against the schema before asserting any rules using selectors.</span></span> <span data-ttu-id="1efeb-111">您应在执行策略时验证传递的所有输入。</span><span class="sxs-lookup"><span data-stu-id="1efeb-111">You should validate all input that is passed while executing a policy.</span></span>  
  
## <a name="expected-behaviors-of-the-business-rule-composer-when-rulestore-security-is-on"></a><span data-ttu-id="1efeb-112">当 RuleStore 安全性为启用状态时业务规则编辑器的工作方式</span><span class="sxs-lookup"><span data-stu-id="1efeb-112">Expected behaviors of the Business Rule Composer when RuleStore security is on</span></span>  
 <span data-ttu-id="1efeb-113">你可以通过调用启用规则存储的基于角色的安全性功能**EnableAuthorization**方法**RuleStore**类。</span><span class="sxs-lookup"><span data-stu-id="1efeb-113">You can enable the role-based security feature for the rule store by calling the **EnableAuthorization** method of the **RuleStore** class.</span></span> <span data-ttu-id="1efeb-114">当此安全功能为启用状态时，业务规则编辑器的工作方式如下所述：</span><span class="sxs-lookup"><span data-stu-id="1efeb-114">When this security feature is enabled, the expected behaviors in the Business Rule Composer are as follows:</span></span>  
  
-   <span data-ttu-id="1efeb-115">对象模型将筛选出用户不具备读取权限的规则集和词汇。</span><span class="sxs-lookup"><span data-stu-id="1efeb-115">The object model filters out rule sets and vocabularies to which the user does not have read access.</span></span> <span data-ttu-id="1efeb-116">因此，这些规则集和词汇将不显示在业务规则编辑器中。</span><span class="sxs-lookup"><span data-stu-id="1efeb-116">Therefore, they do not appear in the Business Rule Composer.</span></span>  
  
-   <span data-ttu-id="1efeb-117">如果用户对策略或词汇不具备写权限，则任何保存尝试都将引发异常。</span><span class="sxs-lookup"><span data-stu-id="1efeb-117">If the user does not have write access to a policy or a vocabulary, any save attempt causes an exception to be thrown.</span></span>  
  
## <a name="user-types-for-rule-store-administrator"></a><span data-ttu-id="1efeb-118">规则存储管理员的用户类型</span><span class="sxs-lookup"><span data-stu-id="1efeb-118">User types for rule store administrator</span></span>  
 <span data-ttu-id="1efeb-119">规则存储管理员有权为规则存储中保存的项目定义授权组。</span><span class="sxs-lookup"><span data-stu-id="1efeb-119">The rule store administrator has the privilege to define an authorization group for artifacts saved in the rule store.</span></span> <span data-ttu-id="1efeb-120">但是，请注意规则存储管理员可以属于的两种用户类型之间存在以下区别：</span><span class="sxs-lookup"><span data-stu-id="1efeb-120">However, note the following differences between two types of user to which the rule store administrator can belong:</span></span>  
  
-   <span data-ttu-id="1efeb-121">如果规则存储管理员是 Windows 用户（即，使用 Windows 身份验证连接规则存储），则规则存储管理员定义的授权组的用户可以是 Windows 组或 Windows 用户。</span><span class="sxs-lookup"><span data-stu-id="1efeb-121">When the rule store administrator is a Windows user, which means using Windows authentication to connect the rule store, the rule store administrator can define an authorization group whose user is a Windows group or a Windows user.</span></span>  
  
-   <span data-ttu-id="1efeb-122">如果规则存储管理员是 SQL 用户（即，使用 SQL 验证连接规则存储），则规则存储管理员定义的授权组的用户不能是 Windows 组，但授权组的用户可以是 Windows 用户。</span><span class="sxs-lookup"><span data-stu-id="1efeb-122">When the rule store administrator is a SQL user, which means using SQL authentication to connect the rule store, the rule store administrator cannot define an authorization group whose user is a Windows group, but can define an authorization group whose user is a Windows user.</span></span>  
  
## <a name="user-cannot-associate-an-authorization-group-with-an-artifact-without-sufficient-rights"></a><span data-ttu-id="1efeb-123">用户无法将授权组与没有足够权限的项目关联。</span><span class="sxs-lookup"><span data-stu-id="1efeb-123">User cannot associate an authorization group with an artifact without sufficient rights</span></span>  
 <span data-ttu-id="1efeb-124">如果项目创建者既非 SQL dbo 用户，也非 RE_ADMIN_USERS 的成员，而且不具备对项目的 MODIFY_DELETE 权限，则无法为该项目关联新的授权组。</span><span class="sxs-lookup"><span data-stu-id="1efeb-124">An artifact creator that is neither a SQL dbo user nor a member of RE_ADMIN_USERS, and does not have MODIFY_DELETE permission to an artifact, cannot associate a new authorization group with the artifact.</span></span> <span data-ttu-id="1efeb-125">下面举例说明了这种情况：</span><span class="sxs-lookup"><span data-stu-id="1efeb-125">The following scenario is an example of this behavior:</span></span>  
  
1.  <span data-ttu-id="1efeb-126">规则集创建者不是 dbo，也不在 RE_ADMIN_USERS 组中，并且在创建该规则集后不具备 MODIFY_DELETE 权限。</span><span class="sxs-lookup"><span data-stu-id="1efeb-126">Rule set creator is not dbo, is not in the RE_ADMIN_USERS group, and does not have MODIFY_DELETE permission after the rule set is created.</span></span>  
  
2.  <span data-ttu-id="1efeb-127">创建者创建一个规则集。</span><span class="sxs-lookup"><span data-stu-id="1efeb-127">Creator creates a rule set.</span></span>  
  
3.  <span data-ttu-id="1efeb-128">RE_ADMIN_USERS 组的成员创建授权 AG1，为 User2 授予 MODIFY_DELETE 权限。</span><span class="sxs-lookup"><span data-stu-id="1efeb-128">Member of the RE_ADMIN_USERS group creates authorization AG1 with MODIFY_DELETE permission to User2.</span></span>  
  
4.  <span data-ttu-id="1efeb-129">创建者将 AG1 与该规则集关联。</span><span class="sxs-lookup"><span data-stu-id="1efeb-129">Creator associates AG1 with the rule set.</span></span>  
  
5.  <span data-ttu-id="1efeb-130">启用规则存储授权。</span><span class="sxs-lookup"><span data-stu-id="1efeb-130">Enable the rule store authorization.</span></span>  
  
6.  <span data-ttu-id="1efeb-131">RE_ADMIN_USERS 组的成员创建授权 AG2，为 User2 授予 READ_EXECUTE 权限。</span><span class="sxs-lookup"><span data-stu-id="1efeb-131">Member of the RE_ADMIN_USERS group creates authorization AG2 with READ_EXECUTE permission to User2.</span></span>  
  
7.  <span data-ttu-id="1efeb-132">创建者将 AG2 与该规则集关联。</span><span class="sxs-lookup"><span data-stu-id="1efeb-132">Creator associates AG2 with the rule set.</span></span> <span data-ttu-id="1efeb-133">尽管创建者没有足够的权限执行此操作，但不会显示错误消息。</span><span class="sxs-lookup"><span data-stu-id="1efeb-133">Although the creator does not have sufficient right to do so, no error message appears.</span></span>  
  
8.  <span data-ttu-id="1efeb-134">User2 尝试读取该规则集时将失败。</span><span class="sxs-lookup"><span data-stu-id="1efeb-134">Attempt to read the rule set by User2 fails.</span></span>