---
title: 如何禁用的用户映射 |Microsoft 文档
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51c745dd-4d39-46e5-88bf-b803ae2e0a1b
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 93694ed8a3238be51b255bcad79122169461d885
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250969"
---
# <a name="how-to-disable-a-user-mapping"></a>如何禁用的用户映射
当需要关闭与给定映射关联的所有操作时，可以禁用用户映射。 在删除用户映射之前必须禁用该映射。  
  
 当禁用用户映射时，它将显示为 (D) *\<域 >\\< 用户名\>* 时列出的用户映射。  
  
### <a name="to-disable-a-user-mapping-using-the-administration-utility"></a>使用管理实用工具禁用用户映射  
  
1.  单击**启动**，单击**运行**，类型`cmd`，然后按**ENTER**。  
  
2.  在命令提示符处，转到企业单一登录安装目录。  
  
     默认安装目录是*\<驱动器 >*: \program Files\Enterprise 单一登录。  
  
3.  类型`ssomanage –disablemapping <domain>\<username><application name>`，其中*\<域 >* 是用户帐户的 Windows 域*\<用户名 >* 是你想要禁用的 Windows 用户名称凭据，和*\<应用程序名称 >* 是你想要删除的用户映射的关联应用程序的名称。  
  
### <a name="to-disable-a-user-mapping-using-the-client-utility"></a>使用客户端实用工具禁用用户映射  
  
1.  单击**启动**，单击**运行**，类型`cmd`，然后按**ENTER**。  
  
2.  在命令提示符处，转到企业单一登录安装目录。  
  
     默认安装目录是*\<驱动器 >*: \program Files\Enterprise 单一登录。  
  
3.  类型`ssoclient –disablemapping <application name>`，其中*\<应用程序名称 >* 是你想要删除的用户映射的关联应用程序的名称。  
  
## <a name="see-also"></a>另请参阅  
 [SSO 映射](../esso/sso-mappings.md)   
 [管理关联应用程序](../esso/managing-affiliate-applications.md)   
 [管理用户映射](../esso/managing-user-mappings.md)