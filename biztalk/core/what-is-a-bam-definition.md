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
ms.openlocfilehash: 6cbc600f66be7167aabb4cf0273cb1c0bda78973
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289677"
---
# <a name="what-is-a-bam-definition"></a>BAM 定义概述
BAM 定义是 BAM 观察模型的 XML 表示形式，它是要监视的业务流程的高级定义。 观察模型的主要部分（即 BAM 定义）包括里程碑和要收集的数据事件（BAM 活动）、所有数据聚合的说明，以及如何向用户显示信息（BAM 视图）。  
  
> [!NOTE]
>  还可以手动创建遵循 BAM 架构的 XML 文件，但不建议以这种方式创建 BAM 定义，因为此方式不能提供经过验证的定义。  
  
 BAM 定义可以包含以下项：  
  
-   业务活动 - 有效的 BAM 定义必须包含业务活动（也称为 BAM 活动）。 定义中的所有其他项都是可选的。 有关将业务活动添加到定义的信息，请参阅[如何定义业务活动](../core/how-to-define-a-business-activity.md)。  
  
-   视图 – 视图定义了可访问业务活动所定义数据的一组用户 。 视图包括筛选出的数据、所筛选数据的聚合，以及显示所筛选数据的方式（如数据透视图）。 BAM 支持为每个活动定义一个或多个视图。  
  
     可以在视图中定义以下业务流程：  
  
    -   具有别名的业务数据 - 使用别名能够将友好名称应用于数据项。 例如，开发人员可能定义了一个名为“LName”的数据项。 您可以创建一个别名，以便在查看 BAM 实时数据时“LName”显示为“Last Name”。  有关别名的详细信息，请参阅[如何重命名视图项](../core/how-to-rename-view-items.md)。  
  
    -   持续时间 - 监视活动的时间段。  
  
    -   里程碑组 - 业务里程碑的集合。 可以将组用作一段持续时间中的开始业务里程碑或结束业务里程碑。  
  
    -   聚合 - 可以是实时聚合 (RTA)，也可以是计划聚合（也称为联机分析处理 (OLAP)）。它包括以下各项：  
  
-   度量值 - Analysis Services (OLAP) 多维数据集中的一组数值，这些数值基于此多维数据集的事实表中的一列。  
  
-   进度维度 - 表示对仍在进行的活动的进度创建聚合的过程。  
  
-   数据维度 - 用于对聚合进行分类。 数据维度基于 BAM 活动中格式化的字符串数据项的值。  
  
-   时间维度 - 用于为已定义的时间段创建聚合。  
  
-   数值范围维度 - 用于根据给定数值范围的友好名称对聚合进行分类。  
  
 BAM 定义可以包含在视图中定义的警报定义。 BAM 定义还可以包含数据透视表布局。 部署了 BAM 定义后，数据透视表将包含可使用 Excel 实时数据工作簿或通过 BAM 门户查看的实时业务数据。  
  
> [!NOTE]
>  创建使用用于 Excel BAM 外接 BAM 定义不能包含警报。  
  
## <a name="see-also"></a>另请参阅  
 [在 Excel 中定义的业务活动和视图](../core/defining-business-activities-and-views-in-excel.md)   
 [BAM 门户](../core/bam-portal.md)   
 [BAM 动态基础结构](../core/bam-dynamic-infrastructure.md)