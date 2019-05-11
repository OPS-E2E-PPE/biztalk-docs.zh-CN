---
title: BAM 开发过程的概述 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 098db3f6-2a61-4cc8-88c7-2299c2e2a55e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a5665e5c8b9cdf098972b6d2c82d772c5cdfee7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393402"
---
# <a name="overview-of-the-bam-development-process"></a>BAM 开发过程概述
本主题介绍在开发过程的数据库和存储 BAM 数据的表。  
  
## <a name="prerequisites-for-developing-with-bam"></a>BAM 开发必备条件  
 在开始 BAM 开发之前，请注意以下先决条件：  
  
-   若要检测应用程序必须部署活动。  
  
-   您必须具有 SQL Server 数据库的 DBO 权限，并且是 BAM 事件写入者角色安全上下文的成员。  
  
-   必须使用 Microsoft.NET 4 开发应用程序。 可以使用任何.NET 语言一样，尽管我们建议你使用C#。  
  
-   您必须具有在计算机上安装 Microsoft.BizTalk.BAM.EventObservation.dll。 你可以获取以下两种方式的 DLL:  
  
    -   使用 BizTalk Server 配置管理器安装 BAM 工具。 我们建议使用配置管理器，因为它便于升级在注册表中将相应的条目。 有关配置 BAM 的详细信息，请参阅[使用配置管理器配置 BAM 工具](http://go.microsoft.com/fwlink/?LinkId=70561)(http://go.microsoft.com/fwlink/?LinkId=70561)。  
  
    -   从其在已安装的计算机复制 DLL。 此 DLL 位于 Microsoft BizTalk Server\<版本\>\Tracking 文件夹。  
  
## <a name="bam-development-process"></a>BAM 开发过程  
 下图描述了 BAM 开发流程。  
  
 ![BAM 开发工作流](../core/media/dwb-bamdevelopmentflowc.gif "dwb_bamdevelopmentflowc")  
  
 以下过程列出了开发 BAM 解决方案的基本步骤。  
  
#### <a name="to-develop-a-bam-enabled-solution"></a>若要开发启用了 BAM 的解决方案  
  
1.  为 Excel 的 BAM 外接程序创建观察模型。  
  
    > [!NOTE]
    >  可以在 BAM API （BizTalk Server 示例） 中找到的在此过程中所述的步骤示例[ http://go.microsoft.com/fwlink/?LinkId=69968 ](http://go.microsoft.com/fwlink/?LinkId=69968)。  
  
2.  使用 BAM 管理实用程序将活动部署到 PID。  
  
3.  通过添加 BAM EventStream 代码来检测应用程序。  
  
4.  运行应用程序。 当执行此操作时，代码将：  
  
    -   将占位符记录添加到 BAM_\<*活动名称*\>_Active 表。  
  
    -   更新记录中的数据项目。  
  
    -   结束活动并将该记录移到 BAM_\<* 活动名称 * *\>_completed 表。  
  
## <a name="where-bam-data-is-stored"></a>BAM 数据的存储位置  
 BAM 提供 EventObservation 命名空间，其中包含用于处理 BAM 事件的 EventStream 类。  
  
 BAM 跟踪数据存储在 BAM 主导入数据库 (PID)。 部署观察模型使用 BAM 管理实用程序时，PID 中创建以下五个表。  
  
|“属性”|Description|  
|----------|-----------------|  
|活动表|名为 bam_\<*活动名称*\>_Active，此表用于存储尚未完成此类型的活动。|  
|活动关系表|名为 bam_\<*活动名称*\>_ActiveRelationships，此表包含尚未完成的活动的相关的活动。|  
|继续符表|名为 bam_\<*活动名称*\>_continuations，此表列出了活动的继续符活动。|  
|已完成的表|名为 bam_\<*活动名称*\>_completed。|  
|已完成的关系表|名为 bam_\<*活动名称*\>_CompletedRelationships，此表包含的活动已完成的相关的活动。|  
  
 捕获 BAM 活动中的数据的四种类型：  
  
-   String  
  
-   日期/时间 （通常称为里程碑）  
  
-   Integer  
  
-   float