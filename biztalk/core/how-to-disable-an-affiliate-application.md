---
title: "如何禁用关联应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disabling, applications
- managing [SSO applications], disabling
- applications [SSO], disabling
ms.assetid: febf1687-f0d0-4f87-b462-23535bbddf6d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe1a19ee34a98be4130be2ac72e9ad27e83b0c13
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-disable-an-affiliate-application"></a>如何禁用关联应用程序
可以使用 MMC 管理单元或命令行来禁用指定的关联应用程序。  
  
### <a name="to-disable-an-affiliate-application-using-the-mmc-snap-in"></a>使用 MMC 管理单元禁用关联应用程序  
  
1.  上**启动**菜单上，单击**程序**，单击**Microsoft Enterprise 上单一登录**，然后单击**SSO 管理**。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击关联应用程序，并依次**禁用**。  
  
### <a name="to-disable-an-affiliate-application-using-the-command-line"></a>使用命令行禁用关联应用程序  
  
1.  单击**启动**，单击**运行**，然后键入**cmd**。  
  
2.  在命令行上，转至企业单一登录安装目录。 默认安装目录是\<*驱动器*>: \program Files\Enterprise 单一登录。  
  
3.  类型**ssomanage-disableapp *\<应用程序名称 >***，其中\<*应用程序名称*> 是的关联应用程序的名称你想要禁用。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>另请参阅  
 [SSO 关联应用程序](../core/sso-affiliate-applications.md)   
 [如何启用关联应用程序](../core/how-to-enable-an-affiliate-application.md)   
 [管理用户映射](../core/managing-user-mappings.md)   
 [管理关联应用程序](../core/managing-affiliate-applications.md)