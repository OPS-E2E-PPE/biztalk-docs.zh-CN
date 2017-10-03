---
title: "管理 BAM 动态基础结构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- infrastructure, managing [BAM]
- managing [BAM], infrastructure
ms.assetid: af8a76b5-407a-484d-aff4-0d911f88313e
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 631a6bb3bab613004e11410a382687147e4adad8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="managing-the-bam-dynamic-infrastructure"></a>管理 BAM 动态基础结构
业务活动监视 (BAM) 功能使用动态生成的 SQL 和联机分析处理 (OLAP) 基础结构。 管理员使用 BAM 管理实用程序部署的 BAM 定义工作簿或业务分析人员开发的 XML 文件。  
  
 BAM 动态基础结构由 BAM 工作簿视图、 BAM 部署、 BAM 数据转换服务 (DTS) 包，以及 BAM 数据库。 有关 BAM 动态基础结构的详细信息，请参阅[BAM 动态基础结构](../core/bam-dynamic-infrastructure.md)。  
  
 BizTalk Server 创建以下的 BAM 数据库，当你配置[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]:  
  
-   BAM 主导入 (BAMPrimaryImport) 数据库  
  
-   BAM 星型架构 (BAMStarSchema) 数据库 （可选）  
  
-   BAM Analysis (BAMAnalysis) 数据库 （可选）  
  
-   BAM 存档 (BAMArchive) 数据库  
  
 BAM 数据库有关的信息，请参阅[管理 BAM 数据库](../core/managing-bam-databases.md)。  
  
 管理员执行以下管理任务 BAM 基础结构，此部分所述：  
  
-   部署和取消部署 BAM 定义和视图  
  
-   管理用户访问权限到 BAM 视图  
  
-   运行 BAM DTS 包  
  
-   BAM 数据库备份  
  
## <a name="in-this-section"></a>本节内容  
  
-   [管理 BAM 定义](../core/managing-bam-definitions.md)
  
-   [管理 BAM 安全性](../core/managing-bam-security.md)  
  
-   [管理聚合](../core/managing-aggregations.md) 
  
-   [管理 BAM 数据库](../core/managing-bam-databases.md)
  
## <a name="see-also"></a>另请参阅  
 [管理 BAM](../core/managing-bam.md)