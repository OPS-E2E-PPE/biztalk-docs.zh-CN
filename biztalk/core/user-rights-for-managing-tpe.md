---
title: "用于管理键入的用户权限 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, Tracking Profile Editor
- Tracking Profile Editor, security
ms.assetid: a0353c4d-2aaa-49ac-8e50-88885962abba
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3319a807b1357201dade0c53d04c26146c2b1e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="user-rights-for-managing-tpe"></a>管理 TPE 的用户权限
解决方案开发人员、 系统管理员或 IT 操作人员必须有管理员权限才能检索或将跟踪配置文件部署到与程序集关联的数据库。  
  
> [!IMPORTANT]
>  不能定义用户角色或授予或拒绝使用跟踪配置文件编辑器 （键入） 的用户权限。 仅可以在 Microsoft SQL Server 中定义这些用户角色和关联的权限。  
  
 通过键入，管理员可以：  
  
-   检索与从 BizTalk 管理数据库的一个或多个程序集关联的活动的跟踪配置文件  
  
-   修改跟踪配置文件  
  
-   将新的或已修改的跟踪配置文件应用到 BizTalk 管理数据库  
  
-   修改保存跟踪配置文件 (.btt)  
  
    > [!NOTE]
    >  跟踪配置文件文件不是上一个配置文件的内容的最终颁发机构。 键入可以保存到文件，一个配置文件，尽管它主要从提取并将配置文件内容发布到 BizTalk Server 和 BAM 数据库。 跟踪配置文件仍可用来编辑或更新存储配置文件，只要该文件的内容匹配数据库中存储的信息。 另外，跟踪配置文件可以打包到 BizTalk Server 应用程序包中。 在 MSI 包被导入给定 BizTalk Server 安装时，包含跟踪配置文件的应用程序包可自动调用 BTTDeploy.exe 以应用跟踪配置文件。  
  
> [!IMPORTANT]
>  在键入流中，假定开发和部署任务被隔离，因为通常是这种情况，负责部署应具有到.btt 文件和关联的程序集文件的只读访问权限的人员。  
  
## <a name="see-also"></a>另请参阅  
 [BAM 工作流](../core/bam-workflow.md)   
 [跟踪配置文件编辑器](../core/tracking-profile-editor.md)