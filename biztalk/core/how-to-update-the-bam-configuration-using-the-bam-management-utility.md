---
title: "如何更新 BAM 配置使用 BAM 管理实用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 714a834e-1879-4019-9b54-e511705bd67a
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee5958120e364cc0c2661ead6100bd2ba5502226
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-update-the-bam-configuration-using-the-bam-management-utility"></a>如何使用 BAM 管理实用程序更新 BAM 配置
管理员可以使用 BAM 管理实用程序更新安装的现有 BAM。  
  
## <a name="prerequisites"></a>先决条件  
 您必须具有要更新的 BAM 数据库的管理员权限。  
  
### <a name="to-update-the-bam-configuration-using-the-bam-management-utility"></a>使用 BAM 管理实用程序更新 BAM 配置  
  
1.  如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2.  导航到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking。  
  
3.  在命令行提示符下键入以下内容： **bm 更新-config FileName:\<配置文件 >**，其中\<*配置文件*> 替换为你 BAM 的名称配置文件。 按 **Enter**。  
  
## <a name="see-also"></a>另请参阅  
 [BAM 管理实用工具](../core/bam-management-utility.md)