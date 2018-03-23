---
title: 管理 BAM 定义文件所需的用户权限 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb4fb73f-b783-4a04-9bd6-a135b3dd2655
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5e39c86eec0cf198a5b879cbc98d29321de71dc
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="required-user-rights-for-managing-bam-definition-files"></a>管理 BAM 定义文件所需的用户权限
任何角色的用户均可以创建、管理和查看 BAM 定义文件。 管理 BAM 定义文件包括部署和删除这些文件，以及管理与定义文件相关联的活动、视图、警报和项目。  
  
 管理员应采取适当的资产保护措施，如创建具有相应访问权限的共享文件夹。 使用 Excel BAM 外接程序时，我们建议用户将宏安全级别设置为高。  
  
 虽然原则上任何用户都可以修改 BAM 定义文件，但具体要取决于对存储定义文件的位置所设置的权限。 对定义文件所做的更改不会自动应用到 BAM 基础结构。 若要应用这些更改，必须使用 BAM 管理实用程序。  
  
 若要使用 BAM 管理实用程序，您必须是 BAM 定义要应用到的计算机的管理员或 BizTalk Server Administrators 组的成员。  
  
> [!NOTE]
>  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>另请参阅  
 [管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 定义是什么？](../core/what-is-a-bam-definition.md)   
 [如何部署 BAM 定义](../core/how-to-deploy-bam-definitions.md)