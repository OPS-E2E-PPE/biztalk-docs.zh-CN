---
title: "如何为使用客户端实用工具的关联应用程序设置凭据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [SSO applications], configuring credentials
- SSOClient [SSO], configuring credentials
- applications [SSO], credentials
ms.assetid: 454b6257-3538-40be-840c-00172a2c1dce
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ebe3e1a9e8d2ea8df421d0bade60f35d6925459
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-set-credentials-for-the-affiliate-application-using-the-client-utility"></a>如何为使用客户端实用工具的关联应用程序设置凭据
使用此命令可为用户设置凭据以便该用户能够访问特定的应用程序。 此命令还将自动启用映射。  
  
 在键入密码时，此命令不显示该密码。  
  
 如果用户映射已存在，则此命令将设置该现有映射的凭据。 如果尚未创建用户映射，则 SSO 系统将提示您输入该应用程序的用户 ID。  
  
### <a name="to-set-credentials-for-the-affiliate-application-using-the-client-utility"></a>使用客户端实用工具设置关联应用程序的凭据  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行上，转至企业单一登录安装目录。 默认安装目录是*\<驱动器\>*: \program Files\Enterprise 单一登录。  
  
3.  类型**ssoclient – setcredentials\<应用程序名称\>**，其中**\<应用程序名称\>**是为其所需的特定应用程序若要设置的凭据。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
4.  当提示输入用户凭据时，请输入此应用程序的用户密码。  
  
5.  如果尚未创建用户映射，则 SSO 系统将提示您输入该应用程序的用户 ID。  
  
## <a name="see-also"></a>另请参阅  
 [SSO 关联应用程序](../core/sso-affiliate-applications.md)   
 [管理关联应用程序](../core/managing-affiliate-applications.md)