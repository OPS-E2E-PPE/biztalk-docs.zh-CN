---
title: BAM 定义概述 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- definitions [BAM], observation models
- definitions [BAM], about BAM definitions
- definitions [BAM]
ms.assetid: 1ba1f45e-85fe-492f-8a2e-98bf3570c633
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89366ff3d55edd41719fe6465be6a7d918617b2e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302289"
---
# <a name="what-is-a-bam-definition"></a>BAM 定义概述
BAM 定义是 BAM 观察模型，这是你想要监视的业务流程的高级定义的 XML 表示形式。 观察模型，并因此 BAM 定义的主要组成部分是里程碑和数据要收集事件 （BAM 活动）;任何数据聚合; 的说明以及如何向用户 （BAM 视图） 显示信息。  
  
> [!NOTE]
>  您可以手动创建遵循 BAM 架构的 XML 文件，但这不是建议的方法是创建 BAM 定义，因为它不提供已验证的定义。  
  
 BAM 定义可以包含以下各项：  
  
- 业务活动-有效的 BAM 定义必须包含业务活动 （也称为 BAM 活动）。 在定义中的所有其他项是可选的。 有关向定义中添加业务活动的信息，请参阅[如何定义业务活动](../core/how-to-define-a-business-activity.md)。  
  
- 视图 – 视图定义的用户可以访问业务活动定义的数据集。 视图包含已筛选数据，聚合的已筛选的数据，并显示所筛选的数据，如数据透视图报表的方式。 BAM 支持每个活动的一个或多个视图的定义。  
  
   在视图中可以定义以下业务流程：  
  
  -   使用别名的业务数据的别名，可将友好名称应用于数据项。 例如，开发人员可能定义数据项名为"LName"。 您可以创建一个别名，以便"LName"显示为"Last Name"时查看 BAM 实时数据。  有关使用别名的详细信息，请参阅[如何重命名视图项](../core/how-to-rename-view-items.md)。  
  
  -   持续时间-对其监视活动的时间段。  
  
  -   里程碑组-业务里程碑的。 可以使用组作为开始业务里程碑或结束业务里程碑的持续时间。  
  
  -   聚合-这些可以是实时聚合 (Rta) 或计划的聚合 （也称为联机分析处理 (OLAP)），并包含以下各项：  
  
- 度量值的一系列数值中基于多维数据集的事实数据表中的列的 Analysis Services (OLAP) 多维数据集。  
  
- 进度维度-表示创建的活动的过程中仍在聚合的进度。  
  
- 数据维度-用于对聚合进行分类。 数据维度基于 BAM 活动中的字符串的格式化数据项目的值。  
  
- 时间维度-用于在定义的时间段创建聚合。  
  
- 数值范围维度-用于对基于的友好名称的聚合进行分类给定数值范围。  
  
  BAM 定义可以包含在视图中定义的警报定义。 BAM 定义还可以包含数据透视表布局。 部署 BAM 定义，其中包含可以使用 Excel 实时数据工作簿查看实时业务数据的数据透视表报表后或通过 BAM 门户。  
  
> [!NOTE]
>  创建使用 Excel BAM 外接程序的 BAM 定义不能包含警报。  
  
## <a name="see-also"></a>请参阅  
 [在 Excel 中定义业务活动和视图](../core/defining-business-activities-and-views-in-excel.md)   
 [BAM 门户](../core/bam-portal.md)   
 [BAM 动态基础结构](../core/bam-dynamic-infrastructure.md)