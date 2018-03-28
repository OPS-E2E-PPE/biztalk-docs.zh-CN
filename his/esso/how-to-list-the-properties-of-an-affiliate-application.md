---
title: 如何列出关联应用程序的属性 |Microsoft 文档
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fac15775-39d0-470e-b9d2-21b2d02e1de7
caps.latest.revision: ''
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: e35f1f068f63d4db9738733bcada55047e81a19a
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-list-the-properties-of-an-affiliate-application"></a>如何列出关联应用程序的属性
**Displayapp**命令显示有关关联应用程序的以下信息。 有关关联应用程序的属性的详细信息，请参阅[SSO Affiliate 应用程序](../esso/sso-affiliate-applications.md)。  
  
 单一登录 (SSO) 系统中获取此信息用于更新关联应用程序的 XML 文件。 有关详细信息，请参阅[如何更新关联的应用程序的属性](../esso/how-to-update-the-properties-of-an-affiliate-application.md)。  
  
### <a name="to-display-the-properties-of-an-affiliate-application-using-the-administration-utility"></a>使用管理实用工具显示关联应用程序的属性  
  
1.  单击 **启动**, ，单击 **运行**, ，类型 `cmd`, ，然后按 ENTER。  
  
2.  在命令提示符处，转到企业单一登录安装目录。  
  
     默认安装目录是\<*驱动器*>: \program Files\Enterprise 单一登录。  
  
3.  类型`ssomanage –displayapp <application name>`，其中*\<应用程序名称 >*是你想要显示的属性的关联应用程序的名称。  
  
### <a name="to-display-the-properties-of-an-affiliate-application-using-the-client-utility"></a>使用客户端实用工具显示关联应用程序的属性  
  
1.  单击 **启动**, ，单击 **运行**, ，类型 `cmd`, ，然后按 ENTER。  
  
2.  在命令提示符处，转到企业单一登录安装目录。  
  
     默认安装目录是\<*安装驱动器*>: \program Files\Enterprise 单一登录。  
  
3.  类型`ssoclient –displayapp <application name>`，其中*\<应用程序名称 >*是你想要显示的属性的关联应用程序的名称。  
  
## <a name="see-also"></a>另请参阅  
 [管理用户映射](../esso/managing-user-mappings.md)   
 [管理关联应用程序](../esso/managing-affiliate-applications.md)