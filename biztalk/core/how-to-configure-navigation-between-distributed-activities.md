---
title: "如何配置之间的导航分布式活动 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6f8faf0a-eb06-4383-932d-4106306d6cf3
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ab210f5ab728134b406b5c4bdaf25a1ec6db1c2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-configure-navigation-between-distributed-activities"></a>如何配置分布式活动之间的导航
利用分布式导航，用户可以查看远程 BAM 部署中的活动。 当启用分布式的导航时，一台计算机上 BAM 门户的用户将能够查看活动上的另一个部署的 BAM 门户中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
 本主题中的过程介绍了如何在以下情形中启用分布式导航：  
  
-   与销售部门[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署在 1 台计算机。  
  
-   传送部门[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署在 2 台计算机。  
  
-   名为 myBusinessView 的视图和名为“销售数据”的活动部署在计算机 1 中。  
  
-   名为 myBusinessView 的视图和名为“运输数据”的活动安装在计算机 2 中。  
  
-   销售部门中的业务用户因业务需要，必须查看这两台计算机中的活动。  
  
### <a name="how-to-set-up-distributed-navigation-for-remote-activities"></a>如何为远程活动设置分布式导航  
  
1.  计算机 1 的管理员授予对计算机 1 上的 myBusinessView 视图的业务用户访问权限。 按以下方式使用 bm.exe 命令，：**添加帐户 AccountName:\<帐户名称\>的视图：** myBusinessView  
  
2.  计算机 1 上的管理员，如下所示运行启用引用命令中，通过启用分布式的导航： **bm.exe 启用引用 TargetServer:** computer2 **-TargetDatabase:\<目标数据库\>**  
  
    > [!NOTE]
    >  通常，部门间用于访问 BAM Web Services 的帐户在不同计算机上是不同的。 因此，在此方案中的计算机 1 管理员必须将添加计算机 1 的 Web 服务模拟帐户到 BAM_ManagementWS 角色计算机 2 的 BAM 主导入数据库。 有关详细信息，请参阅"查看和修改角色成员身份" [http://go.microsoft.com/fwlink/?LinkId=66990](http://go.microsoft.com/fwlink/?LinkId=66990)。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
3.  计算机 2 的管理员授予业务用户访问计算机 2 中的 myBusinessView 视图的权限，同样使用步骤 1 中介绍的 BM.exe 命令。  
  
## <a name="results-of-setting-up-distributed-navigation"></a>设置分布式导航的结果  
 启用分布式导航后，添加到两台计算机上的视图中的用户将可以在其主页门户的“我的视图”窗格中看到两台计算机上部署的视图的活动。 这些用户单击的活动远程部署上承载的它们会无缝地将转到门户在其上的托管活动，并才能进行查看的活动，就像它是在其默认门户上。  
  
> [!NOTE]
>  在两个方向上都可以启用分布式导航。 在要共享远程活动的两台计算机上执行以上过程，可以使任一计算机上的门户的业务用户使用分布式导航。  
  
## <a name="see-also"></a>另请参阅  
 [管理远程活动的分布式的的导航](../core/managing-distributed-navigation-of-remote-activities.md)   
 [BAM 门户](../core/bam-portal.md)