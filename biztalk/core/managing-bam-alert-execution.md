---
title: 管理 BAM 警报执行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM definitions], executing alerts
- Notification Services, configuration files
- BAM Management utility
- alerts, executing
ms.assetid: 44bb738e-fa2c-4b32-9e8d-e756d6c3778e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 485842a1cb2bfe315c6b8570409eb9beeb9dac41
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65327473"
---
# <a name="managing-bam-alert-execution"></a>管理 BAM 警报执行
可以通过以下三种渠道，即 BAM 门户、 BAM 管理实用程序和 ProcessBamNSFiles.vbs 脚本修改 BAM 警报执行。  
  
## <a name="bam-portal"></a>BAM 门户  
 知识工作者和管理员可以修改 BAM 门户中使用警报管理器传送警报的方式。 在 BAM 门户中，可以启用或禁用警报，可以修改阈值级别、 传送位置可以修改，以及其他参数会影响警报执行。  
  
 有关修改警报的详细信息，请参阅[BAM 门户页上的警报管理器](../core/alert-manager-on-the-bam-portal-page.md)并[BAM 门户中的警报](../core/alerts-in-the-bam-portal.md)。  
  
### <a name="bam-management-utility"></a>BAM 管理实用程序  
 管理员可以使用 BAM 管理实用程序来启用、 禁用和删除警报。  
  
 有关使用 BAM 管理实用程序管理警报，以下主题的信息：  
  
-   [如何启用警报](../core/how-to-enable-alerts.md) 
  
-   [如何禁用警报](../core/how-to-disable-alerts.md)  
  
-   [如何删除 BAM 警报](../core/how-to-remove-bam-alerts.md)  
  
### <a name="modifying-notification-services-configuration-files"></a>修改 Notification Services 配置文件  
 管理员可以使用 ProcessBamNSFiles.vbs 脚本更改在其中 Notification Services 传送警报的方式。 Notification Services 的详细信息应用程序定义文件 (ADF)，请参阅[ http://go.microsoft.com/fwlink/?LinkId=127016 ](http://go.microsoft.com/fwlink/?LinkId=127016)。  
  
 要修改与 BAM 相关的 ADF 可以遵循以下常规步骤：  
  
1. 运行脚本，以获得当前配置文件和 ADF 文件。  
  
2. 修改的文件。  
  
3. 运行脚本以应用所做的更改。  
  
   有关 ProcessBamNSFiles.vbs 脚本的详细信息，请参阅[BAM 通知服务配置文件的命令行脚本](../core/bam-command-line-script-for-notification-services-configuration-files.md)。  
  
## <a name="see-also"></a>请参阅  
 [管理 BAM 门户](../core/managing-the-bam-portal.md)   
 [管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理实用工具](../core/bam-management-utility.md)