---
title: 如何为用户映射设置凭据 |Microsoft 文档
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
ms.openlocfilehash: c4853499dbfd85cd5114212e37f4d22770d64a22
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972139"
---
# <a name="how-to-set-credentials-for-a-user-mapping"></a>如何为用户映射设置凭据
使用此命令为用户访问特定的应用程序设置凭据。  
  
 在键入密码时，此命令不显示该密码。  
  
 如果用户映射已存在，则此命令将为现有映射设置凭据。 如果尚未创建用户映射，则 SSO 系统将提示您输入该应用程序的用户 ID。  
  
### <a name="to-set-credentials-for-a-user-mapping"></a>为用户映射设置凭据  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行上，转至企业单一登录安装目录。 默认安装目录是**\<驱动器\>**: \program Files\Enterprise 单一登录。  
  
3.  类型**ssomanage-setcredentials\<域\>\\< 用户名\> \<applicationname\>**，其中 **\<域\>** 是用户帐户的 Windows 域**\<用户名\>** 是 Windows 用户名称，并**\<applicationname\>** 是你想要设置的凭据的特定应用程序。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
4.  当 SSO 系统提示您输入用户凭据时，请输入此应用程序的用户密码。  
  
5.  如果尚未创建用户映射，则 SSO 系统将提示您输入该应用程序的用户 ID。  
  
### <a name="to-set-credentials-for-a-user-mapping-from-the-client-utility"></a>从客户端实用工具为用户映射设置凭据  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行上，转至企业单一登录安装目录。 默认安装目录是**\<驱动器\>**: \program Files\Enterprise 单一登录。  
  
3.  类型**ssoclient setcredentials\<应用程序名称\>**，其中**\<应用程序名称\>** 是关联应用程序的名称你想要删除的用户映射。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>另请参阅  
 [如何创建用户映射](../core/how-to-create-user-mappings.md)   
 [SSO 映射](../core/sso-mappings.md)   
 [管理关联应用程序](../core/managing-affiliate-applications.md)   
 [管理用户映射](../core/managing-user-mappings.md)