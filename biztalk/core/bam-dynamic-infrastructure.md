---
title: BAM 动态基础结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- infrastructure, BAM
- BAM, infrastructure
ms.assetid: 88f39438-3213-4f0d-8b8d-e6426c266138
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ed2c99ad52068d26a1144bb47cf3d247c6456d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358554"
---
# <a name="bam-dynamic-infrastructure"></a>BAM 动态基础结构
BAM 基础结构包括 SQL Server 表、 BAM 视图、 存储的过程和 BAM 数据库 （主导入、 存档、 星型架构和分析） 配置和管理通过增量中的数据转换服务 (DTS) 包部署 BAM 定义。 基础结构是位置，在运行时，事件是相关、 聚合，之后可用于查询的用户。  
  
 本部分介绍一些基础结构流程。 例如后从您的应用程序 （BAM 定义） 中提取所需的数据，, 您可以将其存储，这样就可用于查询。 此外，可以维护更快地聚合查询的数据的某些预创建的聚合。  
  
 通常情况下，通过广泛的开发工作来实现数据仓库实现此类功能。 Microsoft 中的 BAM[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]极大地简化了此过程中，但是，自动生成基于活动和视图定义的 SQL 和 OLAP 基础结构。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [BAM 定义概述](../core/what-is-a-bam-definition.md)  
  
-   [BAM 定义架构概述](../core/what-is-a-bam-definition-schema.md)  
  
-   [活动数据存储](../core/activity-data-storage.md)  
  
-   [聚合概述](../core/what-is-an-aggregation.md)  
  
-   [查询 BAM 数据](../core/querying-bam-data.md)  
  
-   [BAM 基础结构限制](../core/bam-infrastructure-limitations.md)  
  
-   [如何在非英语系统中定义的范围的数值维度警报](../core/define-out-of-range-numeric-dimension-alerts-in-non-english-installations--bam.md)