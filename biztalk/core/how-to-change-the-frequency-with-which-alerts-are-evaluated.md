---
title: 如何更改的警报的频率进行评估 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 68f326ed-2017-4853-89b9-146cb0785554
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de8ef990f851b9268e4cd6496b57a38318034534
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342441"
---
# <a name="how-to-change-the-frequency-with-which-alerts-are-evaluated"></a>如何更改的警报的频率进行评估
有些情况下在其中 SQL Notifications services 生成器可能无法及时处理 BAM 事件提供程序使用默认设置部署时所引发的事件。 您可以增加与评估事件警报通过修改 Notification Services adf.xml 文件的频率 （量程持续时间）。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程必须作为的成员身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]属于有权读取和写入主导入数据库中，通常是组[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
### <a name="to-modify-the-notification-services-generator-quantum-duration"></a>若要修改 Notification Services 生成器量程持续时间  
  
1.  打开 Notification Services 命令提示符。 单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2005**，单击**配置工具**，然后单击**Notification Services 命令提示符下**。  
  
2.  获取 Notification Services 配置文件。 在命令提示符处，键入： **cscript ProcessBamNSFiles.vbs-Get config.xml adf.xml \<PimaryImport 数据库服务器\> \< PimaryImport 数据库名称\>**。  
  
3.  修改或添加\<QuantumDuration\>元素下的\<ApplicationExecutionSettings\>中的节点在 adf.xml 文件中。 有关 QuantumDuration 元素的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=78803 ](http://go.microsoft.com/fwlink/?LinkId=78803)。  
  
4.  在命令提示符处，键入： **cscript ProcessBamNSFiles.vbs-更新 config.xml adf.xml \<PimaryImport 数据库服务器\> \< PimaryImport 数据库名称\>。**  
  
## <a name="see-also"></a>请参阅  
 [用于 Notification Services 配置文件的 BAM 命令行脚本](../core/bam-command-line-script-for-notification-services-configuration-files.md)