---
title: "如何设置 SSO 服务器使用客户端实用工具 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications [SSO], selecting servers
- managing [SSO applications], selecting servers
- SSOClient [SSO], selecting servers
ms.assetid: a0f1038c-60c9-4e9d-a730-1ecfa036743b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d917114d21ceed37eb68ee4bb9503aac97735ffa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-the-sso-server-using-the-client-utility"></a>如何设置 SSO 服务器使用客户端实用工具
每次使用 ssoclient，你必须首先指向用户正确上单一登录服务器包含它们的配置信息。  
  
### <a name="to-set-the-sso-server-for-a-user-using-the-client-utility"></a>若要使用客户端实用工具的用户设置 SSO 服务器  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行上，转至企业单一登录安装目录。 默认安装目录是*\<驱动器 >*: \program Files\Enterprise 单一登录。  
  
3.  类型**ssoclient – 服务器*\<单一登录服务器 >***，其中\<*单一登录服务器 >*是的单一登录的名称服务器用户想要连接到。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>另请参阅  
 [SSO 关联应用程序](../core/sso-affiliate-applications.md)   
 [管理关联应用程序](../core/managing-affiliate-applications.md)