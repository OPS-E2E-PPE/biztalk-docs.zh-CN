---
title: "如何清除应用程序缓存 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- caching, applications
- managing [SSO applications], clearing cache
- applications [SSO], caching
ms.assetid: 6230b9a4-c7b8-47b4-854b-12853d9bf5b0
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 184569a3eed693a7b699b2ad14cfb8461cc496e8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-clear-the-application-cache"></a>如何清除应用程序缓存
你可以使用 MMC 管理单元中或命令行删除凭据缓存 （所有与关联的信息关联应用程序） 的内容的所有单一登录在服务器上的指定应用程序。  
  
### <a name="to-clear-the-cache-using-the-mmc-snap-in"></a>若要清除缓存使用 Mmc 管理单元  
  
1.  在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  单击**Affiliate 应用程序**。  
  
4.  在结果窗格中，右键单击关联应用程序，然后单击**清除**。  
  
### <a name="to-clear-the-cache-using-the-command-line"></a>若要清除缓存使用命令行  
  
1.  上**启动**菜单上，单击**运行**，然后键入**cmd**。  
  
2.  在命令行上，转至企业单一登录安装目录。 默认安装目录是\<*驱动器*\>: \program Files\Enterprise 单一登录。  
  
3.  类型**ssomanage-purgecache *\<应用程序名称\>***，其中\<*应用程序名称*\>是的名称关联应用程序，你想要清除的缓存。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>另请参阅  
 [SSO 关联应用程序](../core/sso-affiliate-applications.md)   
 [管理关联应用程序](../core/managing-affiliate-applications.md)