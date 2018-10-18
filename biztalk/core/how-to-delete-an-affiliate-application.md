---
title: 如何删除关联应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications [SSO], deleting
- managing [SSO applications], deleting
- deleting, applications [SSO]
ms.assetid: c7ec065e-ef10-49ff-a350-105dd08dc4a9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97315d21e3793ec6a282deb5f8cdd69d79ab7491
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003318"
---
# <a name="how-to-delete-an-affiliate-application"></a>如何删除关联应用程序
可以使用 MMC 管理单元或命令行从 SSO 数据库中删除指定的关联应用程序。  
  
> [!IMPORTANT]
>  在删除关联应用程序时，SSO 系统将自动删除与之关联的所有映射。  
  
> [!IMPORTANT]
>  只有 SSO 管理员或 SSO 关联管理员才能执行此任务。  
  
### <a name="to-delete-an-affiliate-application-using-the-mmc-snap-in"></a>使用 MMC 管理单元删除关联应用程序  
  
1.  上**启动**菜单上，单击**程序**，单击**Microsoft 企业单一登录**，然后单击**SSO 管理**。  
  
2.  中的 Mmc 管理单元的作用域窗格中，展开**企业单一登录**节点。  
  
3.  右键单击关联应用程序，然后依次**删除**。  
  
### <a name="to-delete-an-affiliate-application-using-the-command-line"></a>使用命令行删除关联应用程序  
  
1. 上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2. 在命令行上，转至企业单一登录安装目录。 默认安装目录*\<驱动器\>*: \Program Files\Common Files\Enterprise Single Sign-on。  
  
3. 类型 * * ssomanage-deleteapp *\<应用程序名称\>**<em>，其中 *\<应用程序名称\></em>是你想要删除从关联应用程序的名称SSO 数据库。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>请参阅  
 [SSO 关联应用程序](../core/sso-affiliate-applications.md)   
 [如何启用关联应用程序](../core/how-to-enable-an-affiliate-application.md)   
 [管理用户映射](../core/managing-user-mappings.md)   
 [管理关联应用程序](../core/managing-affiliate-applications.md)