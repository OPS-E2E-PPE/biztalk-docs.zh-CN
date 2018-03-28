---
title: 如何禁用关联应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7df6e78-6d18-443d-82dc-4351c20a8c4e
caps.latest.revision: ''
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 6bae89d2a05ec34095e0fa2ac3feafc7b88b894e
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-disable-an-affiliate-application"></a>如何禁用关联应用程序
使用 Mmc 管理单元或**disableapp**命令以禁用指定的关联应用程序。  
  
### <a name="to-disable-an-affiliate-application-using-the-mmc-snap-in"></a>使用 MMC 管理单元禁用关联应用程序  
  
1.  单击**启动**，指向**程序**，单击**Microsoft Enterprise 上单一登录**，然后单击**SSO 管理**。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击关联应用程序，并依次 **禁用**。  
  
### <a name="to-disable-an-affiliate-application-using-the-command-line"></a>使用命令行禁用关联应用程序  
  
1.  单击 **启动**, ，单击 **运行**, ，类型 `cmd`, ，然后按 ENTER。  
  
2.  在命令提示符处，转到企业单一登录安装目录。  
  
     默认安装目录是\<*驱动器*>: \program Files\Enterprise 单一登录。  
  
3.  类型`ssomanage –disableapp <application name>`，其中\<*应用程序名称*> 是你想要禁用的关联应用程序的名称。  
  
## <a name="see-also"></a>另请参阅  
 [SSO 关联应用程序](../esso/sso-affiliate-applications.md)   
 [如何启用关联应用程序](../esso/how-to-enable-an-affiliate-application.md)   
 [管理用户映射](../esso/managing-user-mappings.md)   
 [管理关联应用程序](../esso/managing-affiliate-applications.md)