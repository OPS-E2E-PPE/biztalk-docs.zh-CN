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
# <a name="important-security-notes-for-the-business-rule-engine"></a>业务规则引擎的重要安全说明
本主题概述了 Microsoft BizTalk Server 和缓解安全风险所必须采取的步骤中的已知的安全问题。  
  
## <a name="malicious-schema-input-causing-denial-of-service-attack"></a>导致拒绝服务攻击的恶意架构输入  
 在添加事实，时根据每个对象都与匹配策略中受支持的类型验证每个规则。 假定有一个规则的策略中，通过使用一个选择器，传递架构中使用的一个元素。 现在，如果与选择器匹配此元素/属性的实例出现数千次，如果添加每个此类实例，从而导致性能下降和后续可能拒绝服务 (DoS)。  
  
 若要缓解这种潜在问题，你需要验证所有执行策略时传递的不明确的输入。  
  
## <a name="ruleset-not-validating-objects-before-asserting-the-facts"></a>添加事实前不验证对象的规则集  
 任何架构实例作为事实传递**RuleSet**添加任何规则使用选择器前不根据架构验证。 你应验证所有执行策略时传递的输入。  
  
## <a name="expected-behaviors-of-the-business-rule-composer-when-rulestore-security-is-on"></a>当 RuleStore 安全性为业务规则编辑器的工作方式  
 可以通过调用启用规则存储的基于角色的安全性功能**EnableAuthorization**方法**RuleStore**类。 启用此安全功能后，业务规则编辑器中的预期的行为如下所示：  
  
-   对象模型筛选出规则集和词汇到的用户不具有读取访问权限。 因此，它们不显示在业务规则编辑器中。  
  
-   如果用户没有对策略或词汇的写访问权限，任何保存尝试会引发异常。  
  
## <a name="user-types-for-rule-store-administrator"></a>规则存储管理员的用户类型  
 规则存储管理员有权定义在规则存储中保存的项目的授权组。 但请注意两种类型的规则存储管理员可以为属于的用户的以下区别：  
  
-   如果规则存储管理员是 Windows 用户，即使用 Windows 身份验证连接规则存储，则规则存储管理员可以定义的用户可以是 Windows 组或 Windows 用户的授权组。  
  
-   如果规则存储管理员是 SQL 用户，这意味着使用 SQL 身份验证连接规则存储，则规则存储管理员不能定义授权组的用户可以是 Windows 组，但可以定义授权组的用户可以是Windows 用户。  
  
## <a name="user-cannot-associate-an-authorization-group-with-an-artifact-without-sufficient-rights"></a>用户无法将授权组与没有足够权限的项目关联  
 如果项目创建者既不 SQL dbo 用户，也不属于 RE_ADMIN_USERS，且不安装到的项目的 MODIFY_DELETE 权限不能将新的授权组与项目相关联。 下面的方案是此行为的示例：  
  
1.  规则集创建者不是 dbo，是不在 RE_ADMIN_USERS 组中，创建规则集后不具备 MODIFY_DELETE 权限。  
  
2.  创建者创建一个规则集。  
  
3.  RE_ADMIN_USERS 组的成员创建授权 AG1，为 User2 授予 MODIFY_DELETE 权限。  
  
4.  创建者将 AG1 与该规则集相关联。  
  
5.  启用规则存储授权。  
  
6.  RE_ADMIN_USERS 组的成员创建授权 AG2，为 User2 授予 READ_EXECUTE 权限。  
  
7.  创建者将 AG2 与该规则集相关联。 尽管创建者不具有足够权限执行此操作，但不显示任何错误消息。  
  
8.  尝试读取规则集重写用户 2 将失败。