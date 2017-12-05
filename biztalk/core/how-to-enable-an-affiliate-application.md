---
title: "如何启用关联应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications [SSO], enabling
- managing [SSO applications], enabling
- enabling, applications [SSO]
ms.assetid: 81c94e1b-cd3d-482e-9a78-9b1476af9e5f
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a0e4776b60b81256552552c60aa1abb8abdcde8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-enable-an-affiliate-application"></a>如何启用关联应用程序
可以使用 MMC 管理单元或命令行来启用指定的关联应用程序。  
  
### <a name="to-enable-an-affiliate-application-using-the-mmc-snap-in"></a>使用 MMC 管理单元启用关联应用程序  
  
1.  在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击 affililate 应用程序，并依次**启用**。  
  
### <a name="to-enable-an-affiliate-application-using-the-command-line"></a>使用命令行启用关联应用程序  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行上，转至企业单一登录安装目录。 默认安装目录是\<*驱动器*\>: \program Files\Enterprise 单一登录。  
  
3.  类型**ssomanage-enableapp *\<应用程序名称\>***，其中\<*应用程序名称*\>是的名称你想要启用关联的应用程序。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>另请参阅  
 [SSO 关联应用程序](../core/sso-affiliate-applications.md)   
 [如何创建关联应用程序](../core/how-to-create-an-affiliate-application.md)   
 [管理用户映射](../core/managing-user-mappings.md)   
 [管理关联应用程序](../core/managing-affiliate-applications.md)