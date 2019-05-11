---
title: 如何设置 SSO 服务器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- servers, selecting [SSO]
- SSO, selecting servers
- managing [SSO], selecting servers
- SSOManage [SSO]
ms.assetid: a0b0176d-b426-4ab1-8a7e-1f96f4214683
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 804c1da3cec2fa13d82d6b0c9a7ae5f2e33989ed
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334086"
---
# <a name="how-to-set-the-sso-server"></a>如何设置 SSO 服务器
每次使用 ssomanage 时，您必须首先将用户指引到想要连接到单一登录服务器。  
  
 可以通过两种方法执行此操作：  
  
-   单个用户可以自己指向正确单一登录的服务器。  
  
-   单一登录服务器的本地计算机管理员可以将 Single Sign-on Users 帐户的所有成员都指向此服务器。  
  
### <a name="to-set-the-enterprise-single-sign-on-server-using-the-mmc-snap-in"></a>若要设置企业单一登录服务器使用 Mmc 管理单元  
  
1.  单击**启动**，单击**所有程序**，单击**Microsoft 企业单一登录**，然后单击**SSO 管理**。  
  
2.  在 Mmc 管理单元下**控制台根节点**，右键单击**企业单一登录**，然后单击**选择**。  
  
3.  浏览到所需的服务器。  
  
4.  如果适用，请选择**为所有用户设置 SSO 服务器**复选框。  
  
5.  单击“确定” 。  
  
### <a name="to-set-the-enterprise-single-sign-on-server-for-a-single-user-using-the-command-line"></a>若要为单个用户使用命令行设置企业单一登录服务器  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行提示符下，转至企业单一登录安装目录。 默认安装目录**\<驱动器\>**: \Program Files\Common Files\Enterprise Single Sign-on。  
  
3.  类型**ssomanage – server \<SSO 服务器名称\>**，其中 **\<SSO 服务器名称\>** 是用户的单一登录服务器的计算机名想要连接到。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
### <a name="to-set-the-enterprise-single-sign-on-server-for-all-users-using-the-command-line"></a>若要使用命令行的所有用户都设置企业单一登录服务器  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行提示符下，转至企业单一登录安装目录。 默认安装目录**\<驱动器\>**: \Program Files\Common Files\Enterprise Single Sign-on。  
  
3.  类型**ssomanage-serverall \<SSO 服务器名称\>**，其中 **\<SSO 服务器名称\>** 是单一登录服务器的所有计算机名称将指向的单一登录的用户帐户的成员。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
### <a name="to-determine-the-enterprise-single-sign-on-server-to-which-a-user-is-connected-using-the-command-line"></a>若要确定企业单一登录到用户所连接的服务器使用命令行  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行提示符下，转至企业单一登录安装目录。 默认安装目录**\<驱动器\>**: \Program Files\Common Files\Enterprise Single Sign-on。  
  
3.  类型**ssomanage – showserver**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
> [!NOTE]
>  如果它们存在，则此命令显示当前用户以及其他用户的设置。  
  
## <a name="see-also"></a>请参阅  
 [如何启用 SSO](../core/how-to-enable-sso.md)   
 [如何禁用 SSO](../core/how-to-disable-sso.md)   
 [如何显示 SSO 数据库信息](../core/how-to-display-the-sso-database-information.md)   
 [使用 SSO](../core/using-sso.md)