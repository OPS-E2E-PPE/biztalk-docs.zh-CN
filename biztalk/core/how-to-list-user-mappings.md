---
title: 如何列出用户映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO maps], listing maps
- maps [SSO], listing maps
ms.assetid: f9b73785-3a59-45c8-9e88-d2d16b5a46aa
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7df4606b9ba594a134bdba1e924543dbf6dbca6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336871"
---
# <a name="how-to-list-user-mappings"></a>如何列出用户映射
使用此命令列出指定用户的所有现有的映射。  
  
 必须是 SSO 管理员、 应用程序管理员、 SSO 关联管理员或用户来执行此任务。  
  
 已启用的用户映射显示为 (E) \<*域*\>\\ *\<用户名\>* ，而禁用用户映射显示为 (D) \<*域*\>\\ *\<用户名\>* 。  
  
### <a name="to-list-user-mappings-using-the-administration-utility"></a>使用管理实用工具列出用户映射  
  
1. 上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2. 在命令行中，转至企业单一登录安装目录。 默认安装目录\<*驱动器*\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
3. 执行以下操作之一：  
  
   - 类型**ssomanage-listmappings *\<域\>\\< 用户名\>* **若要列出给定的用户具有关联应用程序中的所有映射他/她所属到何处 *\<域\>* 是 Microsoft Windows 域用户帐户，并且 *\<用户名\>* 是你想要列出用户映射的 Windows 用户名。 如果用户是关联管理员或 SSO 管理员，此命令将列出所有关联应用程序中的用户的所有映射。  
  
      或  
  
   - 类型**ssomanage-listmappings *\<应用程序名称\>* **列出给定应用程序的所有用户映射。  
  
      或  
  
   - 如果你是应用程序管理员，请键入**ssomanage-listmappings *\<域\>\\< 用户名\>* *\<应用程序名称\>* **若要列出的所有映射你是管理员的关联应用程序中的、 给定的用户拥有。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
### <a name="to-list-user-mappings-using-the-client-utility"></a>使用客户端实用工具列出用户映射  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行中，转至企业单一登录安装目录。 默认安装目录\<*驱动器*\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
3.  类型**ssoclient – listmappings**列出你拥有的所有映射。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>请参阅  
 [如何创建用户映射](../core/how-to-create-user-mappings.md)   
 [SSO 映射](../core/sso-mappings.md)   
 [管理关联应用程序](../core/managing-affiliate-applications.md)   
 [管理用户映射](../core/managing-user-mappings.md)