---
title: 管理 BAM 动态基础结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- infrastructure, managing [BAM]
- managing [BAM], infrastructure
ms.assetid: af8a76b5-407a-484d-aff4-0d911f88313e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 861390d71c7cd16815ae7f3d446e956f0ae3bb74
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004702"
---
# <a name="managing-the-bam-dynamic-infrastructure"></a>管理 BAM 动态基础结构
业务活动监视 (BAM) 功能使用动态生成的 SQL 和联机分析处理 (OLAP) 基础结构。 管理员使用 BAM 管理实用程序来部署 BAM 定义工作簿或 XML 文件，业务分析人员开发。  
  
 BAM 动态基础结构组成的 BAM 工作簿视图、 BAM 部署、 BAM 数据转换服务 (DTS) 包和 BAM 数据库。 有关 BAM 动态基础结构的详细信息，请参阅[BAM 动态基础结构](../core/bam-dynamic-infrastructure.md)。  
  
 配置 BizTalk Server 时，BizTalk Server 将创建以下 BAM 数据库：  
  
- BAM 主导入 (BAMPrimaryImport) 数据库  
  
- BAM 星型架构 (BAMStarSchema) 数据库 （可选）  
  
- BAM 分析 (BAMAnalysis) 数据库 （可选）  
  
- BAM 存档 (BAMArchive) 数据库  
  
  有关 BAM 数据库的信息，请参阅[管理 BAM 数据库](../core/managing-bam-databases.md)。  
  
  管理员执行以下管理任务的 BAM 基础结构，在本部分中所述：  
  
- 部署和取消部署 BAM 定义和视图  
  
- 管理用户访问权限的 BAM 视图  
  
- 运行 BAM DTS 包  
  
- 备份 BAM 数据库  
  
## <a name="in-this-section"></a>本节内容  
  
-   [管理 BAM 定义](../core/managing-bam-definitions.md)
  
-   [管理 BAM 安全性](../core/managing-bam-security.md)  
  
-   [管理聚合](../core/managing-aggregations.md) 
  
-   [管理 BAM 数据库](../core/managing-bam-databases.md)
  
## <a name="see-also"></a>请参阅  
 [管理 BAM](../core/managing-bam.md)