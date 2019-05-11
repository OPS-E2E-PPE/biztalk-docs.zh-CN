---
title: 重要的安全注意事项业务规则引擎 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, store administrator
- Business Rule Composer, security
- business rules, security
- Denial of Service attacks
ms.assetid: 8972127a-5569-4b32-bc09-e9265efe9514
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d369299dc767a24eb636f495c91f4278fe544e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332194"
---
# <a name="important-security-notes-for-the-business-rule-engine"></a><span data-ttu-id="fe9e7-102">业务规则引擎的重要安全说明</span><span class="sxs-lookup"><span data-stu-id="fe9e7-102">Important Security Notes for the Business Rule Engine</span></span>
<span data-ttu-id="fe9e7-103">本主题概述了 Microsoft BizTalk Server 和缓解安全风险所必须采取的步骤中的已知的安全问题。</span><span class="sxs-lookup"><span data-stu-id="fe9e7-103">This topic summarizes known security issues in Microsoft BizTalk Server and the steps you must take to mitigate the security risks.</span></span>  
  
## <a name="malicious-schema-input-causing-denial-of-service-attack"></a><span data-ttu-id="fe9e7-104">导致拒绝服务攻击的恶意架构输入</span><span class="sxs-lookup"><span data-stu-id="fe9e7-104">Malicious schema input causing Denial of Service attack</span></span>  
 <span data-ttu-id="fe9e7-105">在添加事实，时根据每个对象都与匹配策略中受支持的类型验证每个规则。</span><span class="sxs-lookup"><span data-stu-id="fe9e7-105">While asserting facts, each rule is verified against every object that matches the supported types within a policy.</span></span> <span data-ttu-id="fe9e7-106">假定有一个规则的策略中，通过使用一个选择器，传递架构中使用的一个元素。</span><span class="sxs-lookup"><span data-stu-id="fe9e7-106">Suppose there is a rule in a policy that uses one of the elements in a schema passed by using a selector.</span></span> <span data-ttu-id="fe9e7-107">现在，如果与选择器匹配此元素/属性的实例出现数千次，如果添加每个此类实例，从而导致性能下降和后续可能拒绝服务 (DoS)。</span><span class="sxs-lookup"><span data-stu-id="fe9e7-107">Now if the instance if this element/attribute that matches the selector is repeated thousands of times, every such instance is asserted, causing performance degradation and subsequent possible Denial of Service (DoS).</span></span>  
  
 <span data-ttu-id="fe9e7-108">若要缓解这种潜在问题，你需要验证所有执行策略时传递的不明确的输入。</span><span class="sxs-lookup"><span data-stu-id="fe9e7-108">To mitigate this potential issue, you need to validate all ambiguous input that is passed while executing a policy.</span></span>  
  
## <a name="ruleset-not-validating-objects-before-asserting-the-facts"></a><span data-ttu-id="fe9e7-109">添加事实前不验证对象的规则集</span><span class="sxs-lookup"><span data-stu-id="fe9e7-109">RuleSet not validating objects before asserting the facts</span></span>  
 <span data-ttu-id="fe9e7-110">任何架构实例作为事实传递**RuleSet**添加任何规则使用选择器前不根据架构验证。</span><span class="sxs-lookup"><span data-stu-id="fe9e7-110">Any schema instance passed as a fact to the **RuleSet** is not validated against the schema before asserting any rules using selectors.</span></span> <span data-ttu-id="fe9e7-111">你应验证所有执行策略时传递的输入。</span><span class="sxs-lookup"><span data-stu-id="fe9e7-111">You should validate all input that is passed while executing a policy.</span></span>  
  
## <a name="expected-behaviors-of-the-business-rule-composer-when-rulestore-security-is-on"></a><span data-ttu-id="fe9e7-112">当 RuleStore 安全性为业务规则编辑器的工作方式</span><span class="sxs-lookup"><span data-stu-id="fe9e7-112">Expected behaviors of the Business Rule Composer when RuleStore security is on</span></span>  
 <span data-ttu-id="fe9e7-113">可以通过调用启用规则存储的基于角色的安全性功能**EnableAuthorization**方法**RuleStore**类。</span><span class="sxs-lookup"><span data-stu-id="fe9e7-113">You can enable the role-based security feature for the rule store by calling the **EnableAuthorization** method of the **RuleStore** class.</span></span> <span data-ttu-id="fe9e7-114">启用此安全功能后，业务规则编辑器中的预期的行为如下所示：</span><span class="sxs-lookup"><span data-stu-id="fe9e7-114">When this security feature is enabled, the expected behaviors in the Business Rule Composer are as follows:</span></span>  
  
-   <span data-ttu-id="fe9e7-115">对象模型筛选出规则集和词汇到的用户不具有读取访问权限。</span><span class="sxs-lookup"><span data-stu-id="fe9e7-115">The object model filters out rule sets and vocabularies to which the user does not have read access.</span></span> <span data-ttu-id="fe9e7-116">因此，它们不显示在业务规则编辑器中。</span><span class="sxs-lookup"><span data-stu-id="fe9e7-116">Therefore, they do not appear in the Business Rule Composer.</span></span>  
  
-   <span data-ttu-id="fe9e7-117">如果用户没有对策略或词汇的写访问权限，任何保存尝试会引发异常。</span><span class="sxs-lookup"><span data-stu-id="fe9e7-117">If the user does not have write access to a policy or a vocabulary, any save attempt causes an exception to be thrown.</span></span>  
  
## <a name="user-types-for-rule-store-administrator"></a><span data-ttu-id="fe9e7-118">规则存储管理员的用户类型</span><span class="sxs-lookup"><span data-stu-id="fe9e7-118">User types for rule store administrator</span></span>  
 <span data-ttu-id="fe9e7-119">规则存储管理员有权定义在规则存储中保存的项目的授权组。</span><span class="sxs-lookup"><span data-stu-id="fe9e7-119">The rule store administrator has the privilege to define an authorization group for artifacts saved in the rule store.</span></span> <span data-ttu-id="fe9e7-120">但请注意两种类型的规则存储管理员可以为属于的用户的以下区别：</span><span class="sxs-lookup"><span data-stu-id="fe9e7-120">However, note the following differences between two types of user to which the rule store administrator can belong:</span></span>  
  
-   <span data-ttu-id="fe9e7-121">如果规则存储管理员是 Windows 用户，即使用 Windows 身份验证连接规则存储，则规则存储管理员可以定义的用户可以是 Windows 组或 Windows 用户的授权组。</span><span class="sxs-lookup"><span data-stu-id="fe9e7-121">When the rule store administrator is a Windows user, which means using Windows authentication to connect the rule store, the rule store administrator can define an authorization group whose user is a Windows group or a Windows user.</span></span>  
  
-   <span data-ttu-id="fe9e7-122">如果规则存储管理员是 SQL 用户，这意味着使用 SQL 身份验证连接规则存储，则规则存储管理员不能定义授权组的用户可以是 Windows 组，但可以定义授权组的用户可以是Windows 用户。</span><span class="sxs-lookup"><span data-stu-id="fe9e7-122">When the rule store administrator is a SQL user, which means using SQL authentication to connect the rule store, the rule store administrator cannot define an authorization group whose user is a Windows group, but can define an authorization group whose user is a Windows user.</span></span>  
  
## <a name="user-cannot-associate-an-authorization-group-with-an-artifact-without-sufficient-rights"></a><span data-ttu-id="fe9e7-123">用户无法将授权组与没有足够权限的项目关联</span><span class="sxs-lookup"><span data-stu-id="fe9e7-123">User cannot associate an authorization group with an artifact without sufficient rights</span></span>  
 <span data-ttu-id="fe9e7-124">如果项目创建者既不 SQL dbo 用户，也不属于 RE_ADMIN_USERS，且不安装到的项目的 MODIFY_DELETE 权限不能将新的授权组与项目相关联。</span><span class="sxs-lookup"><span data-stu-id="fe9e7-124">An artifact creator that is neither a SQL dbo user nor a member of RE_ADMIN_USERS, and does not have MODIFY_DELETE permission to an artifact, cannot associate a new authorization group with the artifact.</span></span> <span data-ttu-id="fe9e7-125">下面的方案是此行为的示例：</span><span class="sxs-lookup"><span data-stu-id="fe9e7-125">The following scenario is an example of this behavior:</span></span>  
  
1.  <span data-ttu-id="fe9e7-126">规则集创建者不是 dbo，是不在 RE_ADMIN_USERS 组中，创建规则集后不具备 MODIFY_DELETE 权限。</span><span class="sxs-lookup"><span data-stu-id="fe9e7-126">Rule set creator is not dbo, is not in the RE_ADMIN_USERS group, and does not have MODIFY_DELETE permission after the rule set is created.</span></span>  
  
2.  <span data-ttu-id="fe9e7-127">创建者创建一个规则集。</span><span class="sxs-lookup"><span data-stu-id="fe9e7-127">Creator creates a rule set.</span></span>  
  
3.  <span data-ttu-id="fe9e7-128">RE_ADMIN_USERS 组的成员创建授权 AG1，为 User2 授予 MODIFY_DELETE 权限。</span><span class="sxs-lookup"><span data-stu-id="fe9e7-128">Member of the RE_ADMIN_USERS group creates authorization AG1 with MODIFY_DELETE permission to User2.</span></span>  
  
4.  <span data-ttu-id="fe9e7-129">创建者将 AG1 与该规则集相关联。</span><span class="sxs-lookup"><span data-stu-id="fe9e7-129">Creator associates AG1 with the rule set.</span></span>  
  
5.  <span data-ttu-id="fe9e7-130">启用规则存储授权。</span><span class="sxs-lookup"><span data-stu-id="fe9e7-130">Enable the rule store authorization.</span></span>  
  
6.  <span data-ttu-id="fe9e7-131">RE_ADMIN_USERS 组的成员创建授权 AG2，为 User2 授予 READ_EXECUTE 权限。</span><span class="sxs-lookup"><span data-stu-id="fe9e7-131">Member of the RE_ADMIN_USERS group creates authorization AG2 with READ_EXECUTE permission to User2.</span></span>  
  
7.  <span data-ttu-id="fe9e7-132">创建者将 AG2 与该规则集相关联。</span><span class="sxs-lookup"><span data-stu-id="fe9e7-132">Creator associates AG2 with the rule set.</span></span> <span data-ttu-id="fe9e7-133">尽管创建者不具有足够权限执行此操作，但不显示任何错误消息。</span><span class="sxs-lookup"><span data-stu-id="fe9e7-133">Although the creator does not have sufficient right to do so, no error message appears.</span></span>  
  
8.  <span data-ttu-id="fe9e7-134">尝试读取规则集重写用户 2 将失败。</span><span class="sxs-lookup"><span data-stu-id="fe9e7-134">Attempt to read the rule set by User2 fails.</span></span>