---
title: "如何禁用警报 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- alerts, disabling
- managing [BAM definitions], disabling alerts
- Disable-Alerts command [BAM]
ms.assetid: c5938bc2-1043-4633-8cad-02caf442f2e8
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0252fc98cdf792626094ffee75fae95c1cab3b00
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-disable-alerts"></a>如何禁用警报
管理员使用**禁用警报**命令以禁用所有指定的视图上的警报。  
  
### <a name="to-disable-an-alert"></a>若要禁用警报  
  
1.  如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2.  通过在命令提示符处键入 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking，导航到跟踪文件夹。 按 **Enter**。  
  
3.  类型**bm 禁用警报的视图：\<视图名称 >**。  
  
    > [!NOTE]
    >  如果您已经将 BAM 配置作为 XML 导出，则不要修改与警报相关的 XML。 如果您更改与警报相关的 XML 并部署这些更改，则 bm.exe 将检测到该更改并启用 BAM 警报。  
  
4.  按 **Enter**。  
  
## <a name="see-also"></a>另请参阅  
 [管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理实用工具](../core/bam-management-utility.md)   
 [如何启用警报](../core/how-to-enable-alerts.md)