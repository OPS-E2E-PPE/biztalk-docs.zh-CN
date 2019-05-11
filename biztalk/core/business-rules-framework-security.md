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
# <a name="business-rules-framework-security"></a>业务规则框架安全性
业务规则引擎会在宿主应用程序的安全上下文运行。 在执行过程的规则引擎实例的标识是，线程上下文的调用**Policy.Execute**方法。  
  
## <a name="default-security-configuration"></a>默认的安全配置  
 当你安装 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、 两个默认情况下，管理员和用户创建 Microsoft Windows 组："BizTalk Server 管理员"和"BizTalk 应用程序用户"。 这两个 Windows 组是 BTS_ADMIN_USERS 和 BTS_HOST_USERS SQL 角色分别为 RE_ADMIN_USERS 和 RE_HOST_USERS SQL 角色的成员的成员。  
  
 每当创建规则存储时，会创建默认 SQL 角色：BTS_ADMIN_USERS、 BTS_HOST_USERS、 RE_ADMIN_USERS 和 RE_HOST_USERS。  
  
|默认 Windows 组|SQL 角色|  
|----------------------------|---------------|  
|BizTalk Server Administrators|RE_ADMIN_USERS|  
|BizTalk Application Users|RE_HOST_USERS|  
  
 只有 RE_ADMIN_USERS 角色中的用户可以执行更新部署表和实体访问保护配置表的存储的过程。 这意味着，部署、 取消部署和保护配置所有这样的是仅由规则引擎管理员。 RE_HOST_USERS 角色中的用户可以在 SQL 规则存储中执行的其他存储的过程。  
  
 而不考虑的规则引擎的安装顺序，规则引擎配置进程授予规则引擎更新服务帐户成员身份为 RE_HOST_USERS SQL 角色中，如果它尚不包含数据库访问权限。 但是，如果安装规则引擎后初始 BizTalk 安装 BizTalk，特定于宿主的用户组未添加到规则引擎数据库中的 BTS_HOST_USERS SQL 角色由于主机创建已完成。 您需要手动执行此步骤。  
  
## <a name="artifact-level-security"></a>项目级别安全性  
 除了默认的安全配置，业务规则引擎还可以提供该项目的安全性，策略和词汇级别。  
  
 每个策略或词汇版本都具有一个或多个与之关联的授权组。 授权组是 Microsoft Windows 用户、 SQL 用户、 SQL 角色和具有特定访问级别对每种类型的 Windows 组的一个命名的列表。  
  
 规则存储中创建新策略或词汇后，只有创建了它以及规则引擎管理员的用户具有读取/执行和默认情况下修改/删除访问权限。 规则引擎管理员可以配置哪些用户 （根据用户凭据运行进程） 具有的访问级别或权限，以执行不同的操作-读取/执行、 修改/删除、 完全权限或没有权限。  
  
 默认情况下不启用项目特定安全性。 设置项目级别安全性不是当前可通过用户界面。 但是，它可以设置以编程方式使用业务规则引擎管理员凭据。 下面的代码段演示如何创建新的授权并将关联到规则集的组。  
  
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
>  使用项目级别 l 安全性会降低性能，因为该策略将只需每次执行返回的规则引擎实例前评估应用程序的访问级别上进行的数据库查找。  
  
## <a name="see-also"></a>请参阅  
 [业务规则引擎的重要安全说明](../core/important-security-notes-for-the-business-rule-engine.md)