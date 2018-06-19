---
title: 重要的安全注意事项业务规则引擎 |Microsoft 文档
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
ms.openlocfilehash: e54a532d33e4f84eb5f1ecea67f957d415344a7c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007062"
---
# <a name="important-security-notes-for-the-business-rule-engine"></a>业务规则引擎的重要的安全注意事项
本主题总结了 Microsoft BizTalk Server 和缓解安全风险时必须执行的步骤中的已知的安全问题。  
  
## <a name="malicious-schema-input-causing-denial-of-service-attack"></a>导致拒绝服务攻击的恶意架构输入  
 在添加事实时，将根据与策略内所支持类型匹配的每个对象来验证每条规则。 假定策略中有一条规则根据一个选择器使用所传递架构中的某个元素。 在此情形下，如果与该选择器匹配的元素/属性的实例出现数千次，则会添加所有此类实例，这将导致性能下降，随后可能导致拒绝服务 (DoS)。  
  
 若要缓解这种潜在问题，则需要对执行策略时传递的所有不明确的输入进行验证。  
  
## <a name="ruleset-not-validating-objects-before-asserting-the-facts"></a>规则集在添加事实前不验证对象  
 任何架构实例传递与的事实数据到**RuleSet**然后再判断使用选择器的所有规则不针对架构验证。 您应在执行策略时验证传递的所有输入。  
  
## <a name="expected-behaviors-of-the-business-rule-composer-when-rulestore-security-is-on"></a>当 RuleStore 安全性为启用状态时业务规则编辑器的工作方式  
 你可以通过调用启用规则存储的基于角色的安全性功能**EnableAuthorization**方法**RuleStore**类。 当此安全功能为启用状态时，业务规则编辑器的工作方式如下所述：  
  
-   对象模型将筛选出用户不具备读取权限的规则集和词汇。 因此，这些规则集和词汇将不显示在业务规则编辑器中。  
  
-   如果用户对策略或词汇不具备写权限，则任何保存尝试都将引发异常。  
  
## <a name="user-types-for-rule-store-administrator"></a>规则存储管理员的用户类型  
 规则存储管理员有权为规则存储中保存的项目定义授权组。 但是，请注意规则存储管理员可以属于的两种用户类型之间存在以下区别：  
  
-   如果规则存储管理员是 Windows 用户（即，使用 Windows 身份验证连接规则存储），则规则存储管理员定义的授权组的用户可以是 Windows 组或 Windows 用户。  
  
-   如果规则存储管理员是 SQL 用户（即，使用 SQL 验证连接规则存储），则规则存储管理员定义的授权组的用户不能是 Windows 组，但授权组的用户可以是 Windows 用户。  
  
## <a name="user-cannot-associate-an-authorization-group-with-an-artifact-without-sufficient-rights"></a>用户无法将授权组与没有足够权限的项目关联。  
 如果项目创建者既非 SQL dbo 用户，也非 RE_ADMIN_USERS 的成员，而且不具备对项目的 MODIFY_DELETE 权限，则无法为该项目关联新的授权组。 下面举例说明了这种情况：  
  
1.  规则集创建者不是 dbo，也不在 RE_ADMIN_USERS 组中，并且在创建该规则集后不具备 MODIFY_DELETE 权限。  
  
2.  创建者创建一个规则集。  
  
3.  RE_ADMIN_USERS 组的成员创建授权 AG1，为 User2 授予 MODIFY_DELETE 权限。  
  
4.  创建者将 AG1 与该规则集关联。  
  
5.  启用规则存储授权。  
  
6.  RE_ADMIN_USERS 组的成员创建授权 AG2，为 User2 授予 READ_EXECUTE 权限。  
  
7.  创建者将 AG2 与该规则集关联。 尽管创建者没有足够的权限执行此操作，但不会显示错误消息。  
  
8.  User2 尝试读取该规则集时将失败。