---
title: 如何部署跟踪配置文件与跟踪配置文件管理实用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracking profiles, deploying
- deploying, tracking profiles
- bttdeploy.exe [BAM]
- managing [BAM], deploying tracking profiles
ms.assetid: b3023379-cae1-45fc-a773-2660d3e4abf1
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c4402c8e2951e069c908e431fac203c582c80be
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385269"
---
# <a name="how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility"></a>如何部署跟踪配置文件与跟踪配置文件管理实用程序
业务经理要求解决方案开发人员若要创建新的跟踪配置文件或修改现有更好地管理和监视你的组织的特定业务流程。  
  
 解决方案开发人员使用跟踪配置文件编辑器 (TPE) 来定义业务分析员所需的数据。  
  
 解决方案开发人员创建或修改跟踪配置文件后，管理员使用 bttdeploy.exe 命令行实用程序来部署，以便所做的更改生效并收集的数据。 解决方案开发人员可以将部署跟踪配置文件使用 TPE。  
  
> [!IMPORTANT]
>  您必须部署在部署跟踪配置文件之前，与跟踪配置文件相关联的程序集。  
  
> [!IMPORTANT]
>  必须具有 BizTalk® 管理员权限才能使用此工具。  
  
### <a name="to-deploy-the-tracking-profile-from-the-command-line-utility"></a>若要部署跟踪配置文件从命令行实用程序  
  
1.  从命令提示符下，移动到的目录\<安装路径\>\Program Files\Microsoft BizTalk Server\<版本\>\Tracking\\。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
2.  类型**bttdeploy.exe\<配置文件名称\>.btt**。  
  
3.  按 Enter。  
  
## <a name="see-also"></a>请参阅  
 [管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 安全建议](../core/bam-security-recommendations.md)   
 [业务活动监视 (BAM)](../core/business-activity-monitoring-bam.md)