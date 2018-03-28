---
title: 如何删除关联应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec290d38-0220-4bf2-b596-2d6453e51c8d
caps.latest.revision: ''
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: d0632f7e4217cb9bbccd2ee604688f22eb6de348
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-delete-an-affiliate-application"></a>如何删除关联应用程序
使用 Mmc 管理单元或**deleteapps**命令以从凭据数据库中删除指定的关联应用程序。  
  
> [!IMPORTANT]
>  在删除关联应用程序时，SSO 系统将自动删除与之关联的所有映射。  
  
> [!IMPORTANT]
>  只有 SSO 管理员或 SSO 关联管理员才能执行此任务。  
  
### <a name="to-delete-an-affiliate-application-using-the-mmc-snap-in"></a>使用 MMC 管理单元删除关联应用程序  
  
1.  单击**启动**，指向**程序**，单击**Microsoft Enterprise 上单一登录**，然后单击**SSO 管理**。  
  
2.  在的 MMC 管理单元中的作用域窗格中，展开 **企业单一登录** 节点。  
  
3.  右键单击关联应用程序，并依次 **删除**。  
  
### <a name="to-delete-an-affiliate-application-using-the-command-line"></a>使用命令行删除关联应用程序  
  
1.  单击 **启动**, ，单击 **运行**, ，类型 `cmd`, ，然后按 ENTER。  
  
2.  在命令提示符处，转到企业单一登录安装目录。  
  
     默认安装目录是*\<驱动器 >*: \program Files\Enterprise 单一登录。  
  
3.  类型`ssomanage –deleteapp <application name>`，其中*\<应用程序名称 >*是你想要从凭据数据库中删除关联应用程序的名称。  
  
## <a name="see-also"></a>另请参阅  
 [SSO 关联应用程序](../esso/sso-affiliate-applications.md)   
 [如何启用关联应用程序](../esso/how-to-enable-an-affiliate-application.md)   
 [管理用户映射](../esso/managing-user-mappings.md)   
 [管理关联应用程序](../esso/managing-affiliate-applications.md)