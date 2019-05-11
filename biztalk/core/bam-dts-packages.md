---
title: BAM DTS 包 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DTS packages, BAM
- BAM, DTS packages
ms.assetid: bba70d81-6ddf-4f1f-a1f7-d5a5bf453bae
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30cbcb583f1e175f5d65565c2108361ec9121721
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528887"
---
# <a name="bam-dts-packages"></a>BAM DTS 包
管理员可以更新以下 BAM DTS 包的参数：  
  
- **CubeUpdate** Data Transformation Services (DTS) 包始终位于星型架构数据库所在的同一服务器上。  
  
- **DataMaintenance** DTS 包始终位于主导入数据库所在的同一服务器上。  
  
  DTS 包使用 BAMConfiguration.xml 文件中的以下参数。  
  
|参数|Description|  
|---------------|-----------------|  
|ConnectionTimeOut|DTS 连接超时值 （以秒为单位） 是一个整数。 如果省略 ConnectionTimeOut 参数，该配置文件使用 60 秒，默认值。|  
|加密|默认情况下，DTS 包执行数据时不加密这些转换数据 （加密值为 0）。 将加密设置为 1，以便在转换期间加密数据。|  
|OwnerPassword|DTS 包所有者密码。 DTS 包所有者可以打开和修改 DTS 包。 有关 DTS 包所有者的信息，请参阅 SQL Server 联机丛书。|  
|UserPassword|DTS 用户的密码。 DTS 包的用户可以运行 DTS 包。 有关 DTS 包的用户的信息，请参阅 SQL Server 联机丛书。|  
  
 DTS 包使用 BAMConfiguration.xml 文件中的以下命名约定：  
  
- **CubeUpdate** DTS 包  
  
   **bam_AN_\<**  ***多维数据集名称* \>** ，其中 CubeName 是多维数据集的名称。 BAM 工作簿从视图名称生成多维数据集名称。 如果您修改 BAM 配置 XML 文档中的多维数据集名称，DTS 包名称中使用新的多维数据集名称。  
  
- **DataMaintenance** DTS 包  
  
   **bam_DM_\<**  ***ActivityName* \>**，其中 ActivityName 是活动的名称。  
  
  运行 CubeUpdate DTS 包来聚合计划的聚合。 在下一部分中，可以指定实时数据聚合的时间窗口。  
  
## <a name="see-also"></a>请参阅  
 [BAM 配置架构](../core/bam-configuration-schema.md)   
 [BAM 安全建议](../core/bam-security-recommendations.md)   
 [管理 BAM](../core/managing-bam.md)