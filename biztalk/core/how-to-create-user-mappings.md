---
title: 如何创建用户映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps [SSO], creating
- managing [SSO maps], creating user maps
ms.assetid: c2e9f0db-920b-4d89-8e1e-5dc92805fd23
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df63045a5627bd3d7c356e76e4c836ee6ce28622
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2019
ms.locfileid: "65338919"
---
# <a name="how-to-create-user-mappings"></a>如何创建用户映射
使用此命令创建一个或多个用户映射，按照指定的 XML 文件中。 下面是示例 XML 文件。  
  
```  
<sso>  
<mapping>  
<windowsDomain>domain</windowsDomain>   
<windowsUserId>WindowsUserName</windowsUserId>   
<externalApplication>Application name1</externalApplication>   
<externalUserId>App1UserName</externalUserId>   
</mapping>  
<mapping>  
<windowsDomain>domain</windowsDomain>   
<windowsUserId>WindowsUserName</windowsUserId>   
<externalApplication>Application name2</externalApplication>   
<externalUserId>App2UserName</externalUserId>   
</mapping>  
</sso>  
  
```  
  
 如果更改用户帐户，则必须使用此命令创建新的用户帐户的映射。 此外应删除旧的用户映射。 有关删除映射的详细信息，请参阅[如何删除用户映射](../core/how-to-delete-user-mappings.md)。  
  
 创建用户映射后，你必须启用它，然后才能在 SSO 系统中使用此映射。 有关详细信息，请参阅[如何启用用户映射](../core/how-to-enable-a-user-mapping.md)。  
  
> [!IMPORTANT]
>  用户映射的支持仅域组。  
  
### <a name="to-create-user-mappings-using-the-administration-utility"></a>若要创建使用管理实用工具的用户映射  
  
1. 上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2. 在命令行中，转至企业单一登录安装目录。 默认安装目录 \<*驱动器*\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
3. 类型 * * ssomanage – createmappings *\<映射文件名称\>**<em>，其中 *\<映射文件名称\></em>是包含你希望用户映射文件的名称若要创建。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
### <a name="to-create-user-mappings-using-the-client-utility"></a>若要创建使用客户端实用工具的用户映射  
  
1. 上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2. 在命令行中，转至企业单一登录安装目录。 默认安装目录 \<*驱动器*\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
3. 类型 * * ssoclient – setcredentials *\<应用程序名称\> ** <em>，其中 *\<应用程序名称\></em>是用户想要的关联应用程序的名称创建的映射。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>请参阅  
 [SSO 映射](../core/sso-mappings.md)   
 [管理关联应用程序](../core/managing-affiliate-applications.md)   
 [管理用户映射](../core/managing-user-mappings.md)