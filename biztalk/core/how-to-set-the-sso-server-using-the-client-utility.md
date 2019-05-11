---
title: 如何设置 SSO 服务器使用客户端实用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications [SSO], selecting servers
- managing [SSO applications], selecting servers
- SSOClient [SSO], selecting servers
ms.assetid: a0f1038c-60c9-4e9d-a730-1ecfa036743b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa7b17a713e030c55faf03712a5e3651c7c6280a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383865"
---
# <a name="how-to-set-the-sso-server-using-the-client-utility"></a>如何设置 SSO 服务器使用客户端实用工具
每次使用 ssoclient，您必须首先将用户指引到正确实现单一登录的服务器包含它们的配置信息。  
  
### <a name="to-set-the-sso-server-for-a-user-using-the-client-utility"></a>若要为用户使用客户端实用工具设置 SSO 服务器  
  
1. 上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2. 在命令行中，转至企业单一登录安装目录。 默认安装目录*\<驱动器\>*: \Program Files\Common Files\Enterprise Single Sign-on。  
  
3. 类型<strong>ssoclient – 服务器*\<单一登录服务器\></strong><em>，其中\<</em>单一登录服务器\>* 是要连接到单一登录服务器用户的名称。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>请参阅  
 [SSO 关联应用程序](../core/sso-affiliate-applications.md)   
 [管理关联应用程序](../core/managing-affiliate-applications.md)