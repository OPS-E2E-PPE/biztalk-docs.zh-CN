---
title: "定义时间窗口中，然后时间切片属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [BAM], aggregations
- managing [BAM], real-time data
- Primary Import database [BAM], time properties
- aggregations [BAM], managing
- Primary Import database [BAM], real-time data
- BAMConfiguration.xml file
- aggregations [BAM], real-time data
ms.assetid: 7f07b179-da10-4702-baf7-69516c8f16a6
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d846b03866196e0a31facbbff68db50ec6a00a5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="defining-the-time-window-and-time-slice-properties"></a>定义时间窗口中，然后时间切片属性
管理员可以使用 BAMConfiguration.xml 文件的 TimeWindow 属性和 TimeSlice 属性定义 BAM 主导入数据库的实时聚合表中数据的寿命。  
  
> [!NOTE]
>  若要使自己在 BAM 配置文件中所做的更改生效，管理员必须先取消部署当前 BAM 配置，然后部署已更新的 BAMConfiguration.xml。  
  
 有关取消部署的 BAM 定义的信息，请参阅[如何删除 BAM 定义](../core/how-to-remove-bam-definitions.md)。 有关部署的 BAM 定义的信息，请参阅[如何部署 BAM 定义](../core/how-to-deploy-bam-definitions.md)。  
  
 如果要更改 TimeWindow 和 TimeSlice 值，而不取消部署 BAM 基础结构，则需要修改 BAM 主导入数据库的 BAM_Metadata_Activities 表中的列。  
  
## <a name="timeslice"></a>TimeSlice  
 可以使用 TimeSlice 属性对已完成的 BAM 实例数据进行分组。 TimeSlice 属性按照数据写入 BAM 主导入数据库的时间对 BAM 实例数据进行分组。  
  
 例如，完成并在 1/1/2000 BAM 主导入数据库中持久保存实例 A 凌晨 1:02 实例 B 处于已完成并在 1/1/2000 BAM 主导入数据库中保留凌晨 1:04 如果你将设置五分钟时间间隔属性的值，实例 A 和实例 B 被组合在一起。  
  
#### <a name="to-change-the-timeslice-value-in-the-bam-configuration-file"></a>更改 BAM 配置文件中的 TimeSlice 值  
  
-   更改 BAM 配置文件的下列一行中的值：  
  
    ```  
    <Property Name="RTATimeSlice">5</Property>  
    ```  
  
#### <a name="to-change-the-timeslice-value-in-the-bammetadataactivities-table"></a>更改 BAM_Metadata_Activities 表中的 TimeSlice 值  
  
-   修改 RTATimeSlice 值，该值位于 BAM 主导入数据库的 bam_Metadata_Activities 表中。 如果为一个或多个活动部署多个实时聚合 (RTA)，则可以选择为每个 RTA 指定不同的时段。  
  
    > [!NOTE]
    >  RTAWindow 的值必须为整数，且时间单位始终为分钟。  
  
## <a name="timewindow"></a>TimeWindow  
 运行 CubeUpdate DTS 包时，该程序包将数据从 BAM 主导入数据库移至 BAM 多维数据集中。 在 BAM 数据实例组中所有实时聚合数据都超过 RTA 时段属性中指定的期限后，该程序包就会以组的形式移动这些数据。  
  
#### <a name="to-change-the-timewindow-value-in-the-bam-configuration-file"></a>更改 BAM 配置文件中的 TimeWindow 值  
  
-   更改 BAM 配置文件的下列一行中的值：  
  
    ```  
    <Property Name="RTAWindow">60</Property>  
    ```  
  
#### <a name="to-change-the-timewindow-value-in-the-bammetadataactivities-table"></a>更改 BAM_Metadata_Activities 表中的 TimeWindow 值  
  
-   修改 RTAWindow 值，该值位于 BAM 主导入数据库的 bam_Metadata_Activities 表中。 如果为一个或多个活动部署多个实时聚合 (RTA)，则可以选择为每个 RTA 指定不同的时段。  
  
    > [!NOTE]
    >  RTAWindow 的值必须为整数，且时间单位始终为分钟。  
  
## <a name="see-also"></a>另请参阅  
 [BAM 配置架构](../core/bam-configuration-schema.md)   
 [BAM 安全建议](../core/bam-security-recommendations.md)