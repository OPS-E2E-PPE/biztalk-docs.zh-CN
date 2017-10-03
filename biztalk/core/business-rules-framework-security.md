---
title: "业务规则 Framework 安全性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, code samples
- security, business rules
- artifacts, security
- security, artifacts
- business rules, security
ms.assetid: 86582d3a-259e-47f2-9f72-8dbbe0051503
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2c3a38190d242c85b134a791a8c2cd05c208050
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="business-rules-framework-security"></a>业务规则框架安全性
业务规则引擎在宿主应用程序的安全上下文中运行。 在执行期间的规则引擎实例的标识是，线程上下文调用**Policy.Execute**方法。  
  
## <a name="default-security-configuration"></a>默认安全配置  
 当你安装 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、 两个默认情况下，管理员和用户创建 Microsoft Windows 组:"BizTalk Server Administrators"和"BizTalk 应用程序用户。 上述两个 Windows 组分别是 BTS_ADMIN_USERS 和 BTS_HOST_USERS 这两个 SQL 角色的成员，而这两个角色又分别是另外两个 SQL 角色 RE_ADMIN_USERS 和 RE_HOST_USERS 的成员。  
  
 创建规则存储时会创建以下默认 SQL 角色：BTS_ADMIN_USERS、BTS_HOST_USERS、RE_ADMIN_USERS 和 RE_HOST_USERS。  
  
|默认的 Windows 组|SQL 角色|  
|----------------------------|---------------|  
|BizTalk Server Administrators|RE_ADMIN_USERS|  
|BizTalk Application Users|RE_HOST_USERS|  
  
 只有 RE_ADMIN_USERS 角色中的用户可以执行用于更新部署表和实体访问保护配置表的存储过程。 这意味着只有规则引擎管理员才能执行部署、取消部署和保护配置等操作。 RE_HOST_USERS 角色中的用户可以执行 SQL 规则存储中的其他存储过程。  
  
 不管规则引擎的安装顺序如何，规则引擎配置进程都会向 RE_HOST_USERS SQL 角色授予规则引擎更新服务帐户成员身份（如果该角色尚未拥有数据库访问权限）。 但是，如果在 BizTalk 初始安装后安装规则引擎，则由于已经完成主机创建任务，因此不会将特定于主机的 BizTalk 用户组添加到规则引擎数据库内的 BTS_HOST_USERS SQL 角色中。 您需要手动执行此步骤。  
  
## <a name="artifact-level-security"></a>项目级别安全性  
 除了默认安全配置中，业务规则引擎还可以提供在项目的安全-策略和词汇级别。  
  
 每个策略或词汇版本都具有一个或多个与其关联的授权组。 授权组是对相应类型具有特定访问级别的 Microsoft Windows 用户、SQL 用户、SQL 角色和 Windows 组的命名列表。  
  
 在规则存储中创建新的策略或词汇后，默认情况下，只有创建该策略或词汇的用户和规则引擎管理员才拥有读取/执行和修改/删除的权限。 规则引擎管理员可以配置 （进程运行在用户凭据） 的用户具有访问级别或权限，才能执行不同的操作-读取/执行、 修改/删除、 完全权限，或没有权限。  
  
 默认情况下，将不启用项目特定安全性。 目前不能通过用户界面设置项目级别安全性。 但是，可以使用业务规则引擎管理员凭据以编程方式设置该安全性。 以下代码段显示了如何创建新授权并将该组与规则集关联：  
  
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
>  使用项目级别 l 安全性会降低性能，因为策略在每次执行时都必须进行数据库查找，以在返回规则引擎实例前评估应用程序的访问级别。  
  
## <a name="see-also"></a>另请参阅  
 [业务规则引擎的重要的安全注意事项](../core/important-security-notes-for-the-business-rule-engine.md)