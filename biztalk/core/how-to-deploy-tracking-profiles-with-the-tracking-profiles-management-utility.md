---
title: "如何部署跟踪配置文件使用跟踪配置文件管理实用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tracking profiles, deploying
- deploying, tracking profiles
- bttdeploy.exe [BAM]
- managing [BAM], deploying tracking profiles
ms.assetid: b3023379-cae1-45fc-a773-2660d3e4abf1
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2dde3f351c583be9037127c060d02c98d12b2fcb
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility"></a>如何使用跟踪配置文件管理实用程序部署跟踪配置文件
业务经理要求解决方案开发人员创建一个新的跟踪配置文件或修改现有跟踪配置文件以便更好地管理和监视组织的特定业务流程。  
  
 解决方案开发人员使用跟踪配置文件编辑器 (TPE) 定义业务分析员需要的数据。  
  
 在解决方案开发人员创建或修改跟踪配置文件后，管理员使用 bttdeploy.exe 命令行实用程序对其进行部署，以便所做的更改能够生效并收集数据。 解决方案开发人员可以使用 TPE 部署跟踪配置文件。  
  
> [!IMPORTANT]
>  在部署跟踪配置文件前，必须部署与跟踪配置文件相关联的程序集。  
  
> [!IMPORTANT]
>  你必须拥有 BizTalk® 管理员特权才能使用此工具。  
  
### <a name="to-deploy-the-tracking-profile-from-the-command-line-utility"></a>通过命令行实用工具部署跟踪配置文件  
  
1.  从命令提示符处，将移动到目录\<安装路径\>files\microsoft BizTalk Server\<版本\>\Tracking\\。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
2.  类型**bttdeploy.exe\<配置文件名称\>.btt**。  
  
3.  按 Enter。  
  
## <a name="see-also"></a>另请参阅  
 [管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 安全建议](../core/bam-security-recommendations.md)   
 [业务活动监视 (BAM)](../core/business-activity-monitoring-bam.md)