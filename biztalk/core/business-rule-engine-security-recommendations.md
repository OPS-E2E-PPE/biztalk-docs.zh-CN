---
title: 业务规则引擎安全性建议 |Microsoft Docs
ms.custom: ''
ms.date: 09/27/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, business rules
- Business Rules Framework, security
- business rules, security
ms.assetid: d5df1cd0-112a-4c72-b95d-cbcd1bc6a2c3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ca5506d8ed9acab63e32a4ec86b057a4b775b63
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752749"
---
# <a name="business-rule-engine-security-recommendations"></a>业务规则引擎安全性建议
业务规则引擎是业务规则框架的运行时组件。 使用业务规则框架，可以将可读性高、声明性强和语义丰富的规则连接到任何业务对象（.NET 组件）、XML 文档或数据库表。 有关业务规则框架的详细信息，请参阅[创建和使用业务规则](../core/creating-and-using-business-rules.md)。 有关业务规则引擎的详细信息，请参阅[规则引擎](../core/rule-engine.md)。  
  
 业务规则引擎没有 Windows 用户组，而只有单个帐户。 BizTalk Server 使用两个 SQL Server 角色来限制对业务规则引擎资源的访问：  
  
 RE_Admin_Users SQL Server 角色是供需要在业务规则引擎中执行管理任务（如部署规则）的用户使用的。 RE_Admin_Users SQL Server 角色的成员包括 BizTalk 管理员。  
  
 RE_Host_Users 组是供业务规则引擎的不需要管理用户权限并且执行读取和执行规则等任务的所有其他用户使用的。 RE_Host_Users 角色的成员包括 BizTalk_Host_Users 角色。 您可使用 SQL Server 角色来实现与 BizTalk Server 权限无关的针对业务规则引擎的权限。 有关使用业务规则引擎所需的最小权限的详细信息，请参阅[最低安全用户权限](../core/minimum-security-user-rights.md)。 建议您按照这些准则在您的环境中保护和部署业务规则引擎。  
  
-   BizTalk Server 为您用来安装更新服务的帐户授予“作为服务登录”权限，并将该帐户添加到业务规则数据库的 RE_Host_Users SQL Server 角色中。 如果您安装时所用的帐户与将用以运行更新服务的帐户不同，则您必须从 RE_Host_Users SQL Server 角色删除该安装帐户。  

-   如果不以另一个 BizTalk 主机服务帐户使用相同的帐户，还 RuleEngine 服务帐户添加到 BTS_HOST_USERS BizTalkMgmtDb 和 BizTalkMsgBoxDb 中。

-   如果使用更新服务组件，则必须将其安装到所有 BizTalk 运行时计算机上。 为了从规则引擎数据库检索规则，该更新服务需要模拟服务调用方。  
  
-   默认情况下，所有 BizTalk 主机对规则引擎项目具有相同的访问级别。 并没有为了安全而授予各个主机不同的访问级别。 您可使用规则引擎 API 来配置基于策略的安全性。 有关如何配置基于策略的安全性的详细信息，请参阅[业务规则框架安全性](../core/business-rules-framework-security.md)。  
  
## <a name="see-also"></a>请参阅  
 [用于处理服务器的端口](../core/ports-for-the-processing-servers.md)
