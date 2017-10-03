---
title: "如何定义 BAM 聚合 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, BAM
- aggregations [BAM], creating
- Excel add-in [BAM], security
- Excel add-in [BAM], creating aggregations
- managing [BAM], creating aggregations
ms.assetid: a5ef3a15-b1de-4099-8e94-64af4b5ec746
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef1b5b377611eb8e28088cb2d0c2f2ed6f829de8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-define-bam-aggregations"></a>如何定义 BAM 聚合
BAM 支持以下两种类型的数据聚合：  
  
-   联机分析处理 (OLAP) 聚合  
  
-   实时聚合 (RTA)  
  
 BAM 使用 Microsoft SQL Server Analysis Services 实现 OLAP 聚合。  
  
 必须在定义 RTA 的 BAM 主导入数据库上配置触发器。  
  
### <a name="to-define-olap-aggregations"></a>定义 OLAP 聚合  
  
1.  在 BAM Excel 工作簿中，创建一个视图，向数据透视表中至少添加一个维度和一个度量值，清除 RTA 工具栏按钮，然后保存该工作簿。  
  
    -   有关打开 BAM 工作簿，创建视图，以及添加维度和度量值，请参阅[定义 BAM 视图](../core/defining-a-bam-view.md)。  
  
2.  部署工作簿。  
  
    -   若要部署工作簿，按照中的说明[如何部署 BAM 定义](../core/how-to-deploy-bam-definitions.md)。  
  
3.  解决方案开发人员使用**DirectEventStream**类来导入 BAM 主导入数据库的事件。  
  
    -   璝惠**DirectEventStream**类，请参阅[DirectEventStream 类](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.directeventstream.aspx)。  
  
4.  运行更新多维数据集数据转换服务 (DTS) 包。  
  
    -   有关运行更新多维数据集 DTS 包的信息，请参阅[BAM DTS 包](../core/bam-dts-packages.md)。  
  
5.  打开工作簿的最新实时数据副本以查看 OLAP 聚合。  
  
    > [!IMPORTANT]
    >  出于安全原因，BAM 不删除工作簿的现有实时数据副本。 BAM 而是递增实时数据副本的文件名中的数字。  
  
### <a name="to-define-the-rta"></a>定义 RTA  
  
1.  在 BAM Excel 工作簿中，创建一个视图，向数据透视表中至少添加一个维度和一个度量值，选择 RTA 工具栏按钮，然后保存该工作簿。  
  
    > [!WARNING]
    >  不要定义使用同一个 BAM 活动的多个 RTA。 否则，当您存档 BAM 数据时，RTA 数据将不正确。  
  
    -   有关打开 BAM 工作簿，创建视图，以及添加维度和度量值，请参阅"定义业务活动视图"和"定义聚合"中*信息工作者用户指南*。  
  
2.  部署工作簿。  
  
    -   若要部署工作簿，按照中的说明[如何部署 BAM 定义](../core/how-to-deploy-bam-definitions.md)。  
  
3.  解决方案开发人员使用**DirectEventStream**类来导入 BAM 主导入数据库的事件。  

  
4.  打开工作簿的最新实时数据副本以查看 RTA。  
  
    > [!IMPORTANT]
    >  出于安全原因，BAM 不删除工作簿的现有实时数据副本。 BAM 而是递增实时数据副本的文件名中的数字。  
  
## <a name="see-also"></a>另请参阅  
 [BAM DTS 包](../core/bam-dts-packages.md)   
 [如何部署 BAM 定义](../core/how-to-deploy-bam-definitions.md)   
 [更新 OLAP 和 RTA 连接字符串属性](../core/updating-olap-and-rta-connection-string-properties.md)   
 [管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)