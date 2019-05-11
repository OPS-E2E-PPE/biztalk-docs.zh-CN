---
title: 如何列出关联应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO applications], listing applications
- applications [SSO], listing applications
ms.assetid: b51ff597-824e-4488-a47f-3a9b3d4437c6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b254be21078a53f7efa7291606bdd0038466bb3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336933"
---
# <a name="how-to-list-affiliate-applications"></a>如何列出关联应用程序
使用此命令列出所有关联应用程序。 如果用户是应用程序管理员帐户的成员，此命令将仅显示为其用户是管理员的应用程序。  
  
### <a name="to-list-affiliate-applications-using-the-administration-utility"></a>使用管理实用工具列出关联应用程序  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行中，转至企业单一登录安装目录。 默认安装目录\<*驱动器*\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
3.  类型**ssomanage-listapps [all]** 其中**所有**是一个可选参数，还将显示使用的配置存储功能的应用程序。 如果运行此命令的用户是应用程序管理员，它将仅列出它们是管理员的应用程序。 如果运行此命令的用户是关联管理员或 SSO 管理员，它将列出所有关联应用程序。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
### <a name="to-list-affiliate-applications-using-the-client-utility"></a>使用客户端实用工具列出关联应用程序  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行中，转至企业单一登录安装目录。 默认安装目录\<*驱动器*\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
3.  类型**ssoclient – listapps**以列出关联应用程序。 这将列出仅的关联应用程序执行此任务的用户所在的即，它们需要属于该关联应用程序的应用程序用户组帐户。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>请参阅  
 [SSO 关联应用程序](../core/sso-affiliate-applications.md)   
 [如何创建关联应用程序](../core/how-to-create-an-affiliate-application.md)   
 [管理用户映射](../core/managing-user-mappings.md)   
 [管理关联应用程序](../core/managing-affiliate-applications.md)