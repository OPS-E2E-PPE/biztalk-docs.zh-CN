---
title: BAM 通知的命令行脚本服务配置文件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6aa4a460-58f9-439d-af28-0a9cb2288236
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b22607193ed7c345388a6435e2d58c16b8986370
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965795"
---
# <a name="bam-command-line-script-for-notification-services-configuration-files"></a>BAM 通知的命令行脚本服务配置文件
管理员使用 ProcessBamNSFiles.vbs 脚本自定义 BAM 警报的 SQL Server Notification Services 的行为。 您可以使用该脚本获取 Notification Services 应用程序定义文件 (ADF) 和 Notification Services 配置文件。 可以对这些文件进行修改，然后使用该脚本来应用这些更改。  
  
 应该从 Notification Services 命令提示符而不是常规的命令提示符来运行该脚本。 从常规的命令提示符运行该脚本将导致脚本执行错误。 运行脚本时，所有参数都是必需的。  
  
## <a name="get-command"></a>Get 命令  
 **用法**  
  
 **cscript ProcessBamNSFiles-获取\<配置文件路径\> \<ADF 文件路径\>\<主导入服务器\>\<主导入数据库  \>**  
  
|参数|Description|  
|---------------|-----------------|  
|配置文件路径|指定配置文件的名称和存储位置。|  
|ADF 文件路径|指定 ADF 文件的名称和存储位置。|  
|主导入服务器|存储 BAM 主导入数据库的计算机的名称。|  
|主导入数据库|BAM 主导入数据库的名称。|  
  
 从 BAM 主导入数据库检索 Notification Services 配置文件和应用程序定义文件，并将这些文件保存到指定路径。  
  
## <a name="update-command"></a>Update 命令  
 **用法**  
  
 **cscript ProcessBamNSFiles-更新\<configfilepath\> \<adffilepath\>\<primaryimport 服务器\>\<主导入数据库  \>**  
  
|参数|Description|  
|---------------|-----------------|  
|配置文件路径|指定从其更新 Notification Services 配置信息的名称和位置。|  
|ADF 文件路径|指定从其更新 ADF 信息的名称和位置。|  
|主导入服务器|存储 BAM 主导入数据库的计算机的名称。|  
|主导入数据库|BAM 主导入数据库的名称。|  
  
 调用 Notification Services，并用指定文件中的信息更新设置。 配置文件和 ADF 文件存储在 BAM 主导入数据库中。  
  
## <a name="see-also"></a>另请参阅  
 [BAM 命令行工具](../core/bam-command-line-tools.md)