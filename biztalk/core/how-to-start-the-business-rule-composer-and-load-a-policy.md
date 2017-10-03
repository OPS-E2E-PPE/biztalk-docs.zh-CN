---
title: "如何启动业务规则编辑器和加载策略 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- policies, loading
- opening, Busines Rule Composer
- Business Rule Composer, policies
- Business Rule Composer, opening
ms.assetid: 34a6034d-90b3-4ce0-9770-3790763affe3
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 420517c51fd6c7a6c854afe161a11a58f952db83
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-start-the-business-rule-composer-and-load-a-policy"></a>如何启动业务规则编辑器和加载策略
本部分将介绍如何启动业务规则编辑器和加载策略。  
  
### <a name="to-start-the-business-rule-composer"></a>启动业务规则编辑器  
  
-   上**启动**菜单上，指向**所有程序**，指向 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，然后单击**业务规则编辑器**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。  
  
### <a name="to-load-a-policy"></a>加载策略  
  
1.  业务规则编辑器，在上**规则存储**菜单上，单击**负载**。  
  
2.  在**规则存储**对话框中，在**SQL Server**下拉列表中，选择你想要连接的 SQL Server™ 计算机。  
  
3.  在**数据库**下拉列表中，选择包含你想要打开规则存储的数据库。  
  
> [!NOTE]
>  安装的规则存储的默认数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是**BizTalkRuleEngineDb**。  
  
> [!NOTE]
>  如果你使用新创建的 SQL Server 帐户具有**强制密码过期**和**用户必须更改密码在下次登录**选项集，业务规则编辑器将无法连接到该规则引擎数据库。