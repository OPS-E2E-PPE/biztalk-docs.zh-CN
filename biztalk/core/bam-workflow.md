---
title: BAM 工作流 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- monitoring business activities [BAM], collecting business data
- XML files
- orchestrations, XML files
- business activities, business data
- infrastructure, managing [BAM]
- business activities, monitoring
- monitoring business activities [BAM], monitoring flow
- managing [BAM], infrastructure
- monitoring business activities [BAM], viewing business data
- managing [orchestrations], mapping XML to orchestrations
ms.assetid: 8b4ae145-3e16-4bb8-bfba-09b9f666218d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19356d6191963ec441f0b85c0e987c8515dcf1f4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232037"
---
# <a name="bam-workflow"></a>BAM 工作流
下图显示了使用业务活动监视的 4 个用户角色，以及他们使用的工具。  
  
 ![](../core/media/ebiz-tut-bamworkflow.gif "ebiz_tut_bamworkflow")  
BAM 角色  
  
 以下步骤对用于使用业务活动监视的工作流进行了高级概述。  
  
## <a name="specifying-the-business-data-to-collect"></a>指定要收集的业务数据  
 按以下方式收集业务数据：  
  
-   业务分析员使用“BAM 活动向导”来指定要收集所有业务用户的哪些数据。  
  
-   业务分析员使用“BAM 视图向导”来定义业务用户的每个类别的视图。  
  
-   完成后，他将这些活动和视图保存在一个名为“BAM 定义工作簿”的 Microsoft® Excel 工作簿中。  
  
-   业务分析员将 BAM 定义工作簿导出到 XML 文件。  
  
-   系统管理员和开发人员使用该 XML 文件来执行他们的角色。  
  
-   有关使用 BAM 定义工作簿的说明位于[定义业务活动和在 Excel 中的视图](../core/defining-business-activities-and-views-in-excel.md)。  
  
## <a name="managing-the-bam-infrastructure"></a>管理 BAM 基础结构  
 业务分析员定义了其所需的 BAM 视图后，系统管理员使用 BAM 管理实用程序（即 BM.EXE，它是一个命令行工具）根据 BAM 定义工作簿或从该工作簿导出的 XML 文件来部署 BAM 基础结构。  
  
 BAM 管理实用程序动态创建支持 BAM 视图所需的表、触发器、DTS 包，以及 OLAP 多维数据集。  
  
 每当业务分析员定义其他 BAM 视图或更改现有 BAM 视图时，系统管理员都必须重新部署 BAM 定义工作簿。  
  
## <a name="mapping-the-xml-to-an-orchestration"></a>将 XML 文件映射到业务流程  
 业务分析员将 BAM 定义工作簿导出到 XML 文件后，开发人员将该 XML 文件导入到跟踪配置文件编辑器中。 然后，开发人员实现业务分析员的信息要求，并将 XML 文件映射到业务流程。  
  
 使用跟踪配置文件编辑器，开发人员可以执行以下步骤将 XML 文件映射到业务流程：  
  
-   加载存储在 BizTalk 管理数据库（又称为配置数据库）中的已部署程序集。 该已部署程序集包含与业务分析员在上面的第 1 步中指定的要求相对应的一个或多个业务流程。  
  
-   定义要从业务流程中提取的数据。 为此，您可以将消息架构和业务流程形状中的项放到相应的业务里程碑（事件）和数据项文件夹中。  
  
-   完成后，开发人员将配置文件另存为 BizTalk® Server 跟踪文件 (.btt)，存放到某个存储数据库中，例如 Visual SourceSafe。  
  
 开发人员将该 .btt 文件部署到测试数据库，然后通过集成测试来验证结果。  
  
## <a name="deploying-the-tracking-profile"></a>部署跟踪配置文件  
 使用跟踪配置文件编辑器，系统管理员可以将配置文件部署到一个或多个 BizTalk 管理数据库。  
  
 每当开发人员更改业务流程时，或业务用户的要求发生变化并且他们要跟踪更多数据时，系统管理员都需要使用 bttdeploy.exe 命令行实用工具重新部署跟踪配置文件。  
  
## <a name="viewing-the-business-data"></a>查看业务数据  
 业务用户使用 _LiveData 工作簿，该工作簿是由 BM.exe 实用工具生成的。 每当业务用户打开 _LiveData 工作簿时，他都会收到为监视业务流程的特定方面而收集的数据的实时版本。  
  
-   若要查看被定义为实时聚合的数据，业务用户只需单击**刷新**工作簿来查看数据中。  
  
-   如果聚合数据不是实时的，则业务用户看到的是在计划的 DTS 包运行时拍摄的业务数据快照。  
  
-   如果您的组织有协作要求，业务用户可以从 BAS Web 站点访问实时数据。  
  
## <a name="see-also"></a>另请参阅  
 [在 Excel 中定义的业务活动和视图](../core/defining-business-activities-and-views-in-excel.md)   
 [监视与 BAM 业务活动](../core/monitoring-business-activities-with-bam.md)