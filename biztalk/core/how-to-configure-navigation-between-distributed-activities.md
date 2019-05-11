---
title: 如何配置之间的导航分布式活动 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f8faf0a-eb06-4383-932d-4106306d6cf3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd43576f9571cd34aa69f6f666fca6777434cf4c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341287"
---
# <a name="how-to-configure-navigation-between-distributed-activities"></a>如何配置分布式活动之间的导航
分布式的导航，用户可以查看远程 BAM 部署中存在的活动。 启用分布式的导航时，一台计算机上的 BAM 门户的用户将能够查看 BAM 门户上的另一个部署中的活动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
 本主题中的过程描述如何能够在以下方案中的分布式的导航：  
  
- 销售部门的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署在计算机 1 上。  
  
- 运输部门的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署在计算机 2 上。  
  
- 名为 myBusinessView 视图名为部署在计算机 1 上的销售数据的活动。  
  
- 名为 myBusinessView 视图名为安装在计算机 2 传送数据的活动。  
  
- 销售部门的企业的业务用户需要两台计算机上看到活动。  
  
### <a name="how-to-set-up-distributed-navigation-for-remote-activities"></a>如何设置为远程活动的分布式导航  
  
1.  计算机 1 的管理员授予业务用户对计算机 1 上的 myBusinessView 视图的访问。 使用 bm.exe 命令中，按如下所示：**添加帐户-AccountName:\<帐户名称\>的视图：** myBusinessView  
  
2.  计算机 1 上的管理员通过按如下所示运行启用引用命令，来启用分布式的导航： **bm.exe 启用引用-TargetServer:** computer2 **-TargetDatabase:\<目标数据库\>**  
  
    > [!NOTE]
    >  通常的帐户访问 BAM Web services 部门间用于将不同的计算机上不同。 因此，在这种情况下计算机 1 的管理员必须添加计算机 1 的 Web 服务模拟帐户到计算机 2 的 BAM 主导入数据库的 BAM_ManagementWS 角色。 详细信息，请参阅"查看和修改角色成员身份"网址[ http://go.microsoft.com/fwlink/?LinkId=66990 ](http://go.microsoft.com/fwlink/?LinkId=66990)。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
3.  计算机 2 的管理员授予业务用户对计算机使用在步骤 1 中记下的 BM.exe 命令 2 上的 myBusinessView 视图的访问。  
  
## <a name="results-of-setting-up-distributed-navigation"></a>设置分布式导航的结果  
 启用分布式的导航时添加到两台计算机上的视图的用户将看到其主页门户的我的视图窗格中的两台计算机上部署的视图的活动。 当这些用户单击托管在远程部署的活动时，它们将无缝地定向到所在的门户的托管活动，并能够查看它好像在自己的默认门户上的活动。  
  
> [!NOTE]
>  可以在这两个方向上启用分布式的导航。 要共享远程活动的两台计算机上执行以上过程启用任何一台计算机上的门户的业务用户可以使用分布式的导航。  
  
## <a name="see-also"></a>请参阅  
 [管理远程活动的分布式的导航](../core/managing-distributed-navigation-of-remote-activities.md)   
 [BAM 门户](../core/bam-portal.md)