---
title: 如何禁用警报 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- alerts, disabling
- managing [BAM definitions], disabling alerts
- Disable-Alerts command [BAM]
ms.assetid: c5938bc2-1043-4633-8cad-02caf442f2e8
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9666c6db97a181a3ff4c3ada204fe11b2b99c8a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385195"
---
# <a name="how-to-disable-alerts"></a>如何禁用警报
管理员使用**禁用警报**命令，以禁用所有指定的视图上的警报。  
  
### <a name="to-disable-an-alert"></a>若要禁用警报  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2. 通过键入导航到跟踪文件夹[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪在命令提示符处。 按 **Enter**。  
  
3. 类型**bm 禁用警报的视图：\<视图名称\>**。  
  
   > [!NOTE]
   >  如果您已经以 XML 形式导出 BAM 配置，不要修改与警报相关的 XML。 如果您更改与警报相关的 XML 和部署所做的更改，则 bm.exe 将检测更改，启用 BAM 警报。  
  
4. 按 **Enter**。  
  
## <a name="see-also"></a>请参阅  
 [管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理实用程序](../core/bam-management-utility.md)   
 [如何启用警报](../core/how-to-enable-alerts.md)