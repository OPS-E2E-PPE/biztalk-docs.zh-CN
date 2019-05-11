---
title: BAM 工作流 |Microsoft Docs
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
ms.openlocfilehash: 82cfe7fe5f29994c72b9f9026c03321ba44e3575
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529165"
---
# <a name="bam-workflow"></a>BAM 工作流
下图显示了四个用户角色的用户使用业务活动监视，以及他们使用的工具。  
  
 ![](../core/media/ebiz-tut-bamworkflow.gif "ebiz_tut_bamworkflow")  
BAM 角色  
  
 以下步骤提供使用业务活动监视的工作流的高级概述。  
  
## <a name="specifying-the-business-data-to-collect"></a>指定要收集的业务数据  
 按以下方式收集业务数据：  
  
-   业务分析员使用 BAM 活动向导来指定要收集所有业务用户的数据。  
  
-   业务分析员使用 BAM 视图向导来为每个类别的业务用户定义视图。  
  
-   完成后，他将保存活动和视图的 Microsoft® Excel 工作簿中名为 BAM 定义工作簿。  
  
-   业务分析员将 BAM 定义工作簿导出到 XML。  
  
-   系统管理员和开发人员使用 XML 来执行他们的角色。  
  
-   有关使用 BAM 定义工作簿的说明位于[定义业务活动和在 Excel 中的视图](../core/defining-business-activities-and-views-in-excel.md)。  
  
## <a name="managing-the-bam-infrastructure"></a>管理 BAM 基础结构  
 业务分析员定义的 BAM 视图后，系统管理员使用 BAM 管理实用工具 (BM。Exe 文件），从工作簿导出的命令行工具，以部署 BAM 基础结构从 BAM 定义工作簿或 XML。  
  
 BAM 管理实用程序动态创建表、 触发器、 DTS 包和 OLAP 多维数据集支持 BAM 视图所需。  
  
 每次业务分析员定义其他 BAM 视图，或更改现有 BAM 视图时，系统管理员必须重新部署 BAM 定义工作簿。  
  
## <a name="mapping-the-xml-to-an-orchestration"></a>XML 文件映射到业务流程  
 业务分析员将 BAM 定义工作簿导出到 XML 后，开发人员 XML 文件导入跟踪配置文件编辑器。 开发人员实现业务分析员的信息要求 XML 文件映射到业务流程。  
  
 使用跟踪配置文件编辑器，开发人员可以执行以下步骤以将 XML 映射到业务流程：  
  
- 加载存储在 BizTalk 管理数据库 （也称为配置数据库） 中的已部署程序集。 已部署的程序集包含与业务分析员在上面的步骤 1 中指定的要求相对应的一个或多个业务流程。  
  
- 定义要从业务流程中提取的数据。 执行此操作的消息架构中的项放和业务流程形状的相应的业务里程碑 （事件） 和数据插入项的文件夹。  
  
- 完成后，他将保存该配置文件为 BizTalk® Server 跟踪 (.btt) 文件，例如 Visual SourceSafe 存储数据库。  
  
  开发人员将该.btt 文件部署到测试数据库，并验证通过集成测试的结果。  
  
## <a name="deploying-the-tracking-profile"></a>部署跟踪配置文件  
 系统管理员使用跟踪配置文件编辑器，将该配置文件部署到一个或多个 BizTalk 管理数据库。  
  
 每次开发人员更改业务流程中或业务用户变化的要求和他们想要跟踪更多数据，系统管理员需要重新部署跟踪配置文件使用 bttdeploy.exe 命令行实用工具。  
  
## <a name="viewing-the-business-data"></a>查看业务数据  
 业务用户使用 _LiveData 工作簿，这由 BM.exe 实用工具生成。 业务用户打开 _LiveData 工作簿中，每次他接收新收集要监视的业务流程特定方面的数据的实时版本。  
  
-   若要查看被定义为实时聚合的数据，业务用户只需单击**刷新**要查看的数据的工作簿中。  
  
-   如果不是实时聚合数据，则业务用户将看到在计划的 DTS 包运行时执行的业务数据的快照。  
  
-   如果你的组织有协作要求，业务用户可以从 BAS 网站访问实时数据。  
  
## <a name="see-also"></a>请参阅  
 [在 Excel 中定义业务活动和视图](../core/defining-business-activities-and-views-in-excel.md)   
 [使用 BAM 监视业务活动](../core/monitoring-business-activities-with-bam.md)