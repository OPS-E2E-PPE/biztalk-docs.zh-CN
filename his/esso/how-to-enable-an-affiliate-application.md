---
title: 如何启用关联应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 051bc35f-55e6-4811-9559-b1bb66a570ce
caps.latest.revision: ''
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 53dcd9886bc808f84b112146971a6f9519c404e2
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-enable-an-affiliate-application"></a>如何启用关联应用程序
你可以使用 Mmc 管理单元或**enableapp**命令以启用指定的关联应用程序。  
  
### <a name="to-enable-an-affiliate-application-using-the-mmc-snap-in"></a>使用 MMC 管理单元启用关联应用程序  
  
1.  单击**启动**，指向**程序**，单击**Microsoft Enterprise 上单一登录**，然后单击**SSO 管理**。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击 affililate 应用程序，并依次 **启用**。  
  
### <a name="to-enable-an-affiliate-application-using-the-command-line"></a>使用命令行启用关联应用程序  
  
1.  单击 **启动**, ，单击 **运行**, ，类型 `cmd`, ，然后按 ENTER。  
  
2.  在命令提示符处，转到企业单一登录安装目录。  
  
     默认安装目录是\<*驱动器*>: \program Files\Enterprise 单一登录。  
  
3.  类型`ssomanage –enableapp <application name>`，其中\<*应用程序名称*> 是你想要启用的关联应用程序的名称。  
  
## <a name="see-also"></a>另请参阅  
 [SSO 关联应用程序](../esso/sso-affiliate-applications.md)   
 [如何创建关联应用程序](../esso/how-to-create-an-affiliate-application.md)   
 [管理用户映射](../esso/managing-user-mappings.md)   
 [管理关联应用程序](../esso/managing-affiliate-applications.md)