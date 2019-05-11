---
title: 如何禁用关联应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disabling, applications
- managing [SSO applications], disabling
- applications [SSO], disabling
ms.assetid: febf1687-f0d0-4f87-b462-23535bbddf6d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0a64026dcf699c1d643aa50eca797111bac3227
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338149"
---
# <a name="how-to-disable-an-affiliate-application"></a>如何禁用关联应用程序
可以使用 MMC 管理单元或命令行来禁用指定的关联应用程序。  
  
### <a name="to-disable-an-affiliate-application-using-the-mmc-snap-in"></a>若要禁用关联应用程序使用 Mmc 管理单元  
  
1.  上**启动**菜单上，单击**程序**，单击**Microsoft 企业单一登录**，然后单击**SSO 管理**。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  右键单击关联应用程序，然后依次**禁用**。  
  
### <a name="to-disable-an-affiliate-application-using-the-command-line"></a>若要禁用关联应用程序使用命令行  
  
1. 单击**启动**，单击**运行**，然后键入**cmd**。  
  
2. 在命令行中，转至企业单一登录安装目录。 默认安装目录\<*驱动器*\>: \Program Files\Common Files\Enterprise Single Sign-on。  
  
3. 类型<strong>ssomanage-disableapp *\<应用程序名称\></strong><em>，其中\<</em>应用程序的名称*\>名称您要禁用的关联应用程序。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>请参阅  
 [SSO 关联应用程序](../core/sso-affiliate-applications.md)   
 [如何启用关联应用程序](../core/how-to-enable-an-affiliate-application.md)   
 [管理用户映射](../core/managing-user-mappings.md)   
 [管理关联应用程序](../core/managing-affiliate-applications.md)