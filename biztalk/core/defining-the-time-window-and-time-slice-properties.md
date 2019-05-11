---
title: 定义时间范围和时间切片属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 902d50596185de13792e5d03b0d7e0dbd4238f55
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352352"
---
# <a name="defining-the-time-window-and-time-slice-properties"></a>定义时间范围和时间切片属性
管理员用于 TimeWindow 和 TimeSlice 属性 BAMConfiguration.xml 文件中定义数据的生存期在 BAM 主导入数据库中的实时聚合表中。  
  
> [!NOTE]
>  若要执行他们所做的更改 BAM 配置文件中，管理员必须取消部署当前 BAM 配置，然后部署已更新的 BAMConfiguration.xml。  
  
 有关取消部署 BAM 定义的信息，请参阅[如何删除 BAM 定义](../core/how-to-remove-bam-definitions.md)。 有关部署 BAM 定义的信息，请参阅[如何部署 BAM 定义](../core/how-to-deploy-bam-definitions.md)。  
  
 如果你想要更改 TimeWindow 和 TimeSlice 值，而取消部署 BAM 基础结构，则可以修改 BAM 主导入数据库中 BAM_Metadata_Activities 表中的列。  
  
## <a name="timeslice"></a>TimeSlice  
 使用 TimeSlice 属性对 BAM 实例数据进行分组已完成。 TimeSlice 属性使用的数据写入 BAM 主导入数据库对 BAM 实例数据进行分组的时间。  
  
 例如，完成并在 1/1/2000 BAM 主导入数据库中保存实例 A 凌晨 1:02 完成并在 1/1/2000 BAM 主导入数据库中保存的实例 B 凌晨 1:04 如果将 TimeSlice 属性的值设置为五分钟，实例 A 和实例 B 组合在一起。  
  
#### <a name="to-change-the-timeslice-value-in-the-bam-configuration-file"></a>若要更改 BAM 配置文件中的 TimeSlice 值  
  
-   更改 BAM 配置文件的这一行中的值：  
  
    ```  
    <Property Name="RTATimeSlice">5</Property>  
    ```  
  
#### <a name="to-change-the-timeslice-value-in-the-bammetadataactivities-table"></a>若要更改 BAM_Metadata_Activities 表中的 TimeSlice 值  
  
-   修改 RTATimeSlice 值，该值在 BAMPrimaryImport 数据库的 bam_Metadata_Activities 表中。 如果一个或多个活动部署多个实时聚合 (RTA)，必须为每个 RTA 指定不同的时间窗口的选项。  
  
    > [!NOTE]
    >  RTAWindow 的值必须是整数，时间单位始终为分钟。  
  
## <a name="timewindow"></a>TimeWindow  
 当您运行 CubeUpdate DTS 包时，包将数据从 BAM 主导入数据库移到 BAM 多维数据集中。 包将移动实时聚合数据，因为 BAM 数据实例毕竟组中的数据的保留时间超过 RTA 时段属性中指定的期限。  
  
#### <a name="to-change-the-timewindow-value-in-the-bam-configuration-file"></a>若要更改 BAM 配置文件中的 TimeWindow 值  
  
-   更改 BAM 配置文件的这一行中的值：  
  
    ```  
    <Property Name="RTAWindow">60</Property>  
    ```  
  
#### <a name="to-change-the-timewindow-value-in-the-bammetadataactivities-table"></a>若要更改 BAM_Metadata_Activities 表中的 TimeWindow 值  
  
-   修改 RTAWindow 值，在 BAMPrimaryImport 数据库的 bam_Metadata_Activities 表中。 如果一个或多个活动部署多个实时聚合 (RTA)，必须为每个 RTA 指定不同的时间窗口的选项。  
  
    > [!NOTE]
    >  RTAWindow 的值必须是整数，时间单位始终为分钟。  
  
## <a name="see-also"></a>请参阅  
 [BAM 配置架构](../core/bam-configuration-schema.md)   
 [BAM 安全建议](../core/bam-security-recommendations.md)