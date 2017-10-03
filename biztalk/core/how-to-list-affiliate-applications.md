---
title: "如何列出关联应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [SSO applications], listing applications
- applications [SSO], listing applications
ms.assetid: b51ff597-824e-4488-a47f-3a9b3d4437c6
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d01ae0a8d94b38583745ba706524c1b02c295b71
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-list-affiliate-applications"></a>如何列出关联应用程序
使用此命令可列出所有关联应用程序。 如果用户为 Application Administrators 帐户成员，则此命令将只显示用户是其管理员的应用程序。  
  
### <a name="to-list-affiliate-applications-using-the-administration-utility"></a>使用管理实用工具列出关联应用程序  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行上，转至企业单一登录安装目录。 默认安装目录是\<*驱动器*>: \program Files\Enterprise 单一登录。  
  
3.  类型**ssomanage listapps [全部]**其中**所有**是也将显示使用的配置存储功能的应用程序的可选参数。 如果运行此命令的用户为应用程序管理员，将只列出用户是其管理员的应用程序。 如果运行此命令的用户是关联管理员或 SSO 管理员，则将列出所有关联应用程序。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
### <a name="to-list-affiliate-applications-using-the-client-utility"></a>使用客户端实用工具列出关联应用程序  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行上，转至企业单一登录安装目录。 默认安装目录是\<*驱动器*>: \program Files\Enterprise 单一登录。  
  
3.  类型**ssoclient – listapps**列出关联应用程序。 这样，将只列出执行此任务的用户所属的关联应用程序，即这些用户必须属于该关联应用程序的应用程序用户组帐户。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>另请参阅  
 [SSO 关联应用程序](../core/sso-affiliate-applications.md)   
 [如何创建关联应用程序](../core/how-to-create-an-affiliate-application.md)   
 [管理用户映射](../core/managing-user-mappings.md)   
 [管理关联应用程序](../core/managing-affiliate-applications.md)