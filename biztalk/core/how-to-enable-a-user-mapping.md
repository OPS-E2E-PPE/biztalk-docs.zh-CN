---
title: 如何启用用户映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- enabling, user maps [SSO]
- maps [SSO], enabling
- managing [SSO maps], enabling
ms.assetid: 0f6448c9-944e-45f6-9436-87a4f3743498
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 917f3eb2d1438bb53b9a8a583e3985b0843f09b4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385136"
---
# <a name="how-to-enable-a-user-mapping"></a>如何启用用户映射
必须启用用户映射，然后才能在单一登录系统中使用该映射。  
  
 启用用户映射时，它将显示为 (E) **\<域\>\\< 用户名\>** 时列出用户映射。  
  
 请注意，是否将使用-setcredentials 命令的凭据，该映射将已启用。  
  
### <a name="to-enable-a-user-mapping-using-the-administration-utility"></a>若要启用用户映射使用管理实用工具  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行中，转至企业单一登录安装目录。 默认安装目录**\<驱动器\>**: \Program Files\Common Files\Enterprise Single Sign-on。  
  
3.  类型**ssomanage-enablemapping\<域\>\\< 用户名\>\<应用程序名称\>**，其中 **\<域\>** 是用户帐户的 Windows 域**\<用户名\>** 是 Windows 用户名，你想要启用凭据，并选择**\<应用程序名称\>** 是你想要删除的用户映射，然后按 ENTER 关联应用程序的名称。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
### <a name="to-enable-a-user-mapping-using-the-client-utility"></a>若要启用使用客户端实用工具的用户映射  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行中，转至企业单一登录安装目录。 默认安装目录**\<驱动器\>**: \Program Files\Common Files\Enterprise Single Sign-on。  
  
3.  类型**ssoclient-enablemapping\<应用程序名称\>**，其中**\<应用程序名称\>** 是所需的关联应用程序的名称若要删除其用户映射。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>请参阅  
 [如何创建用户映射](../core/how-to-create-user-mappings.md)   
 [SSO 映射](../core/sso-mappings.md)   
 [管理关联应用程序](../core/managing-affiliate-applications.md)   
 [管理用户映射](../core/managing-user-mappings.md)