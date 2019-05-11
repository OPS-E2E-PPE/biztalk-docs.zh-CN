---
title: 如何为使用客户端实用工具的关联应用程序设置凭据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO applications], configuring credentials
- SSOClient [SSO], configuring credentials
- applications [SSO], credentials
ms.assetid: 454b6257-3538-40be-840c-00172a2c1dce
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abc8c329b46e5eab5f04f5082064f1dea63505bd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334523"
---
# <a name="how-to-set-credentials-for-the-affiliate-application-using-the-client-utility"></a>如何为使用客户端实用工具的关联应用程序设置凭据
使用此命令为用户设置凭据，以便用户能够访问特定应用程序。 此命令还会自动启用映射。  
  
 此命令不显示密码，并在您键入。  
  
 如果用户映射已存在，此命令将设置为现有映射的凭据。 如果尚未创建用户映射，SSO 系统将提示你提供应用程序的用户 ID。  
  
### <a name="to-set-credentials-for-the-affiliate-application-using-the-client-utility"></a>为关联应用程序使用客户端实用工具设置凭据  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行中，转至企业单一登录安装目录。 默认安装目录*\<驱动器\>*: \Program Files\Common Files\Enterprise Single Sign-on。  
  
3.  类型**ssoclient – setcredentials\<应用程序名称\>**，其中**\<应用程序名称\>** 是为其所需的特定应用程序若要设置的凭据。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
4.  当系统提示输入用户凭据，请输入此应用程序的用户密码。  
  
5.  如果尚未创建用户映射，SSO 系统将提示你提供应用程序的用户 ID。  
  
## <a name="see-also"></a>请参阅  
 [SSO 关联应用程序](../core/sso-affiliate-applications.md)   
 [管理关联应用程序](../core/managing-affiliate-applications.md)