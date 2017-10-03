---
title: "如何更改的警报的频率进行评估 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68f326ed-2017-4853-89b9-146cb0785554
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a686c7de8057fdf843ff855da109e77e8ba7b8ae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-change-the-frequency-with-which-alerts-are-evaluated"></a>如何更改计算的警报的频率
有时会出现这样的情况：使用默认设置部署 SQL Notifications Services 生成器后，它可能无法及时处理 BAM 事件提供程序引发的事件。 您可以通过修改 Notification Services adf.xml 文件来加快评估事件是否需要发出警报的频率（量程持续时间）。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程，必须以具有主导入数据库读写权限的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组成员的身份（通常是 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组）登录。  
  
### <a name="to-modify-the-notification-services-generator-quantum-duration"></a>修改 Notification Services 生成器量程持续时间  
  
1.  打开 Notification Services 命令提示窗口。 单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2005**，单击**配置工具**，然后单击**通知服务命令提示符**。  
  
2.  获取 Notification Services 配置文件。 在命令提示符处，键入： **cscript ProcessBamNSFiles.vbs-Get config.xml adf.xml \<PimaryImport 数据库服务器 > \< PimaryImport 数据库名称 >**。  
  
3.  修改或添加\<QuantumDuration > 元素下的\<ApplicationExecutionSettings > 中的节点 adf.xml 文件中。 QuantumDuration 元素的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=78803](http://go.microsoft.com/fwlink/?LinkId=78803)。  
  
4.  在命令提示符处，键入： **cscript ProcessBamNSFiles.vbs-更新 config.xml adf.xml \<PimaryImport 数据库服务器 > \< PimaryImport 数据库名称 >。**  
  
## <a name="see-also"></a>另请参阅  
 [BAM 通知的命令行脚本服务配置文件](../core/bam-command-line-script-for-notification-services-configuration-files.md)