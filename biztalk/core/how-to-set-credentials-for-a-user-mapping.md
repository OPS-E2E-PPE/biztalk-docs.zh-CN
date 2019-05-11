---
title: 如何为用户映射设置凭据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps [SSO], credentials
- managing [SSO maps], configuring credentials
ms.assetid: 75b29114-56b6-4db0-8666-61cf6c675401
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 228661c4e35175cf5f2e05c86bb0e10123f8e468
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383963"
---
# <a name="how-to-set-credentials-for-a-user-mapping"></a>如何为用户映射设置凭据
使用此命令为用户访问特定应用程序设置凭据。  
  
 此命令不显示密码，并在您键入。  
  
 如果用户映射已存在，此命令将设置为现有映射的凭据。 如果尚未创建用户映射，SSO 系统将提示你提供应用程序的用户 ID。  
  
### <a name="to-set-credentials-for-a-user-mapping"></a>若要为用户映射设置凭据  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行中，转至企业单一登录安装目录。 默认安装目录**\<驱动器\>**: \Program Files\Common Files\Enterprise Single Sign-on。  
  
3.  类型**ssomanage – setcredentials\<域\>\\< 用户名\> \<applicationname\>**，其中 **\<域\>** 是用户帐户的 Windows 域**\<用户名\>** 是 Windows 用户名，以及**\<应用程序名称\>** 是你想要设置的凭据的特定应用程序。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
4.  当 SSO 系统将提示您输入用户凭据时，输入此应用程序的用户密码。  
  
5.  如果尚未创建用户映射，SSO 系统将提示你提供应用程序的用户 ID。  
  
### <a name="to-set-credentials-for-a-user-mapping-from-the-client-utility"></a>若要为从客户端实用工具的用户映射设置凭据  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行中，转至企业单一登录安装目录。 默认安装目录**\<驱动器\>**: \Program Files\Common Files\Enterprise Single Sign-on。  
  
3.  类型**ssoclient-setcredentials\<应用程序名称\>**，其中**\<应用程序名称\>** 是关联应用程序的名称，想要删除的用户映射。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>请参阅  
 [如何创建用户映射](../core/how-to-create-user-mappings.md)   
 [SSO 映射](../core/sso-mappings.md)   
 [管理关联应用程序](../core/managing-affiliate-applications.md)   
 [管理用户映射](../core/managing-user-mappings.md)