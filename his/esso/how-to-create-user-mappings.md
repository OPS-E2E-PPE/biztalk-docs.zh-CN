---
title: 如何创建用户映射 |Microsoft 文档
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb91879c-73f4-4e9e-9e5b-534f48cd5584
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 89fd7ab2ca83d23a37944447997becd2d3f008c2
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250961"
---
# <a name="how-to-create-user-mappings"></a>如何创建用户映射
使用**createmappings**命令以创建一个或多个用户映射，按照指定的 XML 文件中。 下面是示例 XML 文件。  
  
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
  
 如果更改用户帐户，你必须使用此命令创建新的用户帐户的映射。 你还应删除旧的用户映射。 有关删除映射的详细信息，请参阅[如何删除用户映射](../esso/how-to-delete-user-mappings.md)。  
  
 创建用户映射后，你必须启用它，然后才能在单一登录 (SSO) 系统中使用此映射。 有关详细信息，请参阅[如何启用用户映射](../esso/how-to-enable-a-user-mapping.md)。  
  
> [!IMPORTANT]
>  用户映射支持仅域组。  
  
### <a name="to-create-user-mappings-using-the-administration-utility"></a>若要创建使用管理实用程序的用户映射  
  
1.  单击 **启动**, ，单击 **运行**, ，类型 `cmd`, ，然后按 ENTER。  
  
2.  在命令提示符处，转到企业单一登录安装目录。  
  
     默认安装目录是\<*驱动器*>: \program Files\Enterprise 单一登录。  
  
3.  类型`ssomanage –createmappings <mappings file name>`，其中*\<映射文件名称 >* 是包含你想要创建的用户映射的文件的名称。  
  
### <a name="to-create-user-mappings-using-the-client-utility"></a>若要创建使用客户端实用工具的用户映射  
  
1.  单击 **启动**, ，单击 **运行**, ，类型 `cmd`, ，然后按 ENTER。  
  
2.  在命令提示符处，转到企业单一登录安装目录。  
  
     默认安装目录是\<*驱动器*>: \program Files\Enterprise 单一登录。  
  
3.  类型`ssoclient –setcredentials <application name >`，其中*\<应用程序名称 >* 是用户想要创建的映射的关联应用程序的名称。  
  
## <a name="see-also"></a>另请参阅  
 [SSO 映射](../esso/sso-mappings.md)   
 [管理关联应用程序](../esso/managing-affiliate-applications.md)   
 [管理用户映射](../esso/managing-user-mappings.md)