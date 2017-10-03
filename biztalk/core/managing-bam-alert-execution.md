---
title: "管理 BAM 警报执行 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [BAM definitions], executing alerts
- Notification Services, configuration files
- BAM Management utility
- alerts, executing
ms.assetid: 44bb738e-fa2c-4b32-9e8d-e756d6c3778e
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5607bed785ee4f91a341b546dbe81ec39458c4e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="managing-bam-alert-execution"></a>管理 BAM 警报执行
可以通过以下三种渠道修改 BAM 警报执行，即 BAM 门户、BAM 管理实用程序和 ProcessBamNSFiles.vbs 脚本。  
  
## <a name="bam-portal"></a>BAM 门户  
 知识工作者和管理员可以使用 BAM 门户的警报管理器来修改传送警报的方式。 在 BAM 门户中，可以启用或禁用警报，还可以修改阈值级别、传送位置以及影响警报执行的其他参数。  
  
 有关修改警报的详细信息，请参阅[BAM 门户页上的警报管理器](../core/alert-manager-on-the-bam-portal-page.md)和[BAM 门户中的警报](../core/alerts-in-the-bam-portal.md)。  
  
### <a name="bam-management-utility"></a>BAM 管理实用程序  
 管理员可以使用 BAM 管理实用程序来启用、禁用和删除警报。  
  
 有关使用 BAM 管理实用程序管理警报的信息，请参阅以下主题：  
  
-   [如何启用警报](../core/how-to-enable-alerts.md) 
  
-   [如何禁用警报](../core/how-to-disable-alerts.md)  
  
-   [如何删除 BAM 警报](../core/how-to-remove-bam-alerts.md)  
  
### <a name="modifying-notification-services-configuration-files"></a>修改 Notification Services 配置文件  
 管理员可使用 ProcessBamNSFiles.vbs 脚本更改 Notification Services 传送警报的方式。 Notification services 的详细的信息的应用程序定义文件 (ADF)，请参阅[http://go.microsoft.com/fwlink/?LinkId=127016](http://go.microsoft.com/fwlink/?LinkId=127016)。  
  
 若要修改与 BAM 相关的 ADF，可以按照以下常规步骤执行操作：  
  
1.  运行脚本，以获得当前的配置文件和 ADF 文件。  
  
2.  修改这些文件。  
  
3.  运行脚本以应用更改。  
  
 ProcessBamNSFiles.vbs 脚本的详细信息，请参阅[BAM 通知服务配置文件的命令行脚本](../core/bam-command-line-script-for-notification-services-configuration-files.md)。  
  
## <a name="see-also"></a>另请参阅  
 [管理 BAM 门户](../core/managing-the-bam-portal.md)   
 [管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理实用工具](../core/bam-management-utility.md)