---
title: 管理 TPE 的用户权限 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, Tracking Profile Editor
- Tracking Profile Editor, security
ms.assetid: a0353c4d-2aaa-49ac-8e50-88885962abba
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d88532b21d2a57a2260761ae8b4194ddc0bf5dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399920"
---
# <a name="user-rights-for-managing-tpe"></a>管理 TPE 的用户权限
解决方案开发人员、 系统管理员或 IT / 操作人员必须具有管理权限才能检索或将跟踪配置文件部署到与程序集关联的数据库。  
  
> [!IMPORTANT]
>  不能定义用户角色或授予或拒绝使用跟踪配置文件编辑器 (TPE) 的用户权限。 仅可以在 Microsoft SQL Server 中定义这些用户角色和关联的权限。  
  
 使用 TPE，管理员可以：  
  
-   检索与从 BizTalk 管理数据库的一个或多个程序集关联的活动的跟踪配置文件  
  
-   修改跟踪配置文件  
  
-   将新的或修改跟踪配置文件应用到 BizTalk 管理数据库  
  
-   修改保存跟踪配置文件 (.btt)  
  
    > [!NOTE]
    >  跟踪配置文件不是配置文件的内容上的最后一个颁发机构。 TPE 可以将一个配置文件保存到文件，尽管它主要从拉取并将配置文件内容发布到 BizTalk Server 和 BAM 数据库。 跟踪配置文件仍可以使用编辑或更新存储的配置文件，只要该文件的内容匹配的信息存储在数据库中的功能。 此外，BizTalk Server 应用程序包中打包跟踪配置文件。 包含自动跟踪配置文件的应用程序包调用 BTTDeploy.exe 以应用跟踪配置文件，MSI 包导入到给定的 BizTalk Server 安装时。  
  
> [!IMPORTANT]
>  在 TPE 的工作流，假设开发和部署任务被分开的因为通常情况下，负责部署应具有到该.btt 文件和关联的程序集文件的只读访问权限的人员。  
  
## <a name="see-also"></a>请参阅  
 [BAM 工作流](../core/bam-workflow.md)   
 [跟踪配置文件编辑器](../core/tracking-profile-editor.md)