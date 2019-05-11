---
title: BAM 命令行脚本，用于通知服务配置文件 |Microsoft Docs
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
ms.openlocfilehash: cf28ea2c1ff0defd7696b548ff86bc050259925d
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528718"
---
# <a name="bam-command-line-script-for-notification-services-configuration-files"></a>BAM 命令行脚本，用于通知服务配置文件
管理员使用 ProcessBamNSFiles.vbs 脚本自定义 BAM 警报的 SQL Server Notification Services 的行为。 您可以使用脚本获取 Notification Services 应用程序定义文件 (ADF) 和 Notification Services 配置文件。 可以修改这些文件，然后使用该脚本以应用更改。  
  
 Notification Services 命令提示符下，而不是从常规的命令提示符运行该脚本。 在典型的命令提示符下运行该脚本将导致脚本执行错误。 运行脚本时所有参数都是必需的。  
  
## <a name="get-command"></a>获取命令  
 **Usage**  
  
 **cscript ProcessBamNSFiles-Get\<配置文件路径\> \<ADF 文件路径\>\<主导入服务器\>\<主导入数据库  \>**  
  
|参数|Description|  
|---------------|-----------------|  
|配置文件路径|指定的名称和要在其中存储配置文件的位置。|  
|ADF 文件路径|指定的名称和要在其中存储该 ADF 文件的位置。|  
|主导入服务器|在其中存储 BAM 主导入数据库的计算机的名称。|  
|主导入数据库|BAM 主导入数据库的名称。|  
  
 检索 Notification Services 配置和应用程序定义文件从 BAM 主导入数据库，并将保存到指定的路径。  
  
## <a name="update-command"></a>Update 命令  
 **Usage**  
  
 **cscript ProcessBamNSFiles -Update \<configfilepath\> \<adffilepath\>  \<primaryimport server\> \<primary import db\>**  
  
|参数|Description|  
|---------------|-----------------|  
|配置文件路径|指定的名称和从其更新 Notification Services 配置信息的位置。|  
|ADF 文件路径|指定的名称和从其更新 ADF 信息的位置。|  
|主导入服务器|在其中存储 BAM 主导入数据库的计算机的名称。|  
|主导入数据库|BAM 主导入数据库的名称。|  
  
 调用 Notification Services，并使用指定的文件中的信息将更新的设置。 配置文件和 ADF 文件存储在 BAM 主导入数据库中。  
  
## <a name="see-also"></a>请参阅  
 [BAM 命令行工具](../core/bam-command-line-tools.md)