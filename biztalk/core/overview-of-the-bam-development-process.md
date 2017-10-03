---
title: "BAM 开发过程的概述 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 098db3f6-2a61-4cc8-88c7-2299c2e2a55e
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adfe1e552c0f129df67ec5ea790f8e685b214fe6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="overview-of-the-bam-development-process"></a>BAM 开发过程概述
本主题介绍 BAM 开发过程以及存储 BAM 数据所用的数据库和表。  
  
## <a name="prerequisites-for-developing-with-bam"></a>BAM 开发必备条件  
 请注意，在开始 BAM 开发前，必须满足下面的必备条件：  
  
-   必须部署活动后才能检测应用程序。  
  
-   你必须拥有 SQL Server 数据库的 DBO 权限，并且是 BAM 事件写入者角色安全上下文的成员。  
  
-   你必须使用 Microsoft .NET 4 开发自己的应用程序。 你可以使用任何 .NET 语言，但建议你使用 C#。  
  
-   你的计算机上必须已安装 Microsoft.BizTalk.BAM.EventObservation.dll。 有两种方法可获得 DLL：  
  
    -   使用 BizTalk Server 配置管理器来安装 BAM 工具。 我们建议你使用配置管理器，因为它在注册表中放入相应的项，便于升级。 有关配置 BAM 的详细信息，请参阅[使用 Configuration Manager 配置 BAM 工具](http://go.microsoft.com/fwlink/?LinkId=70561)(http://go.microsoft.com/fwlink/?LinkId=70561)。  
  
    -   从已安装了 DLL 的计算机复制 DLL。 DLL 驻留在 Microsoft BizTalk Server\<版本 > \Tracking 文件夹。  
  
## <a name="bam-development-process"></a>BAM 开发过程  
 下图对 BAM 开发流程进行了说明。  
  
 ![BAM 开发工作流](../core/media/dwb-bamdevelopmentflowc.gif "dwb_bamdevelopmentflowc")  
  
 下面的过程列出了开发 BAM 解决方案的步骤。  
  
#### <a name="to-develop-a-bam-enabled-solution"></a>开发启用了 BAM 的解决方案  
  
1.  借助用于 Excel 的 BAM 外接程序创建观察模型  
  
    > [!NOTE]
    >  可以在 BAM API （BizTalk Server 示例） 中找到此过程中所述的步骤的示例[http://go.microsoft.com/fwlink/?LinkId=69968](http://go.microsoft.com/fwlink/?LinkId=69968)。  
  
2.  使用 BAM 管理实用程序将活动部署到 PID。  
  
3.  通过添加 BAM EventStream 代码来检测应用程序。  
  
4.  运行该应用程序。 执行此操作时，代码将：  
  
    -   将占位符记录添加到 BAM_\<*活动名称*> _Active 表。  
  
    -   更新该记录中的数据项。  
  
    -   结束活动并将该记录移到 BAM_\<*活动名称*e > _completed 表。  
  
## <a name="where-bam-data-is-stored"></a>BAM 数据的存储位置  
 BAM 提供 EventObservation 命名空间，它包含用于处理 BAM 事件的 EventStream 类。  
  
 BAM 跟踪数据存储在 BAM 主导入数据库 (PID) 中。 使用 BAM 管理实用程序部署观察模型时，PID 中会创建下面 5 个表。  
  
|Name|Description|  
|----------|-----------------|  
|活动表|名为 bam_\<*活动名称*> _Active，此表包含此类型的尚未完成的活动。|  
|活动关系表|名为 bam_\<*活动名称*> _ActiveRelationships，此表包含活动尚未完成相关的活动。|  
|继续符表|名为 bam_\<*活动名称*> _continuations，此表列出活动的延续活动。|  
|已完成表|名为 bam_\<*活动名称*> _completed。|  
|已完成关系表|名为 bam_\<*活动名称*> _CompletedRelationships，此表包含的活动已完成的相关的活动。|  
  
 在 BAM 活动中可捕获 4 种类型的数据：  
  
-   字符串  
  
-   Date/Time（通常指里程碑）  
  
-   Integer  
  
-   Float