---
title: "如何将与 SQL Server Reporting Services 集成 BAM |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6e2d66b7-c8eb-4871-8a47-544955ccd51e
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61478bde3dd224029a6e3d6fd7c73ee84554f93e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-integrate-bam-with-sql-server-reporting-services"></a>如何集成 BAM 与 SQL Server Reporting Services
基于 BAM 基础结构中的数据创建报表时，使用与为任何其他 SQL Server 数据源创建报表相关联的典型任务。 有关使用报表设计器创建报表的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=82437](http://go.microsoft.com/fwlink/?LinkId=82437)。  
  
## <a name="prerequisites"></a>先决条件  
 您必须拥有访问必要的数据以创建报表的权限。  
  
### <a name="how-to-create-a-report-in-bam-by-using-sql-server-reporting-service"></a>如何在 BAM 中使用 SQL Server Reporting Services 创建报表  
  
1.  选择创建报表所用的数据源。  
  
     BAM 提供两个 Reporting Services 可以指向的数据源。  
  
    |数据源|Description|  
    |-----------------|-----------------|  
    |BAM 主导入数据库|包含关于活动实例和实时聚合的视图。 选择类型 ="Microsoft SQL Server"和连接字符串 ="数据源 =\<*服务器名称*>;初始目录 =\<*数据库名称*>"，其中\<*服务器名称*> 和\<*数据库名称*> 是Bam 主导入数据库的服务器和数据库名称。|  
    |BAM 分析数据库|包含用于查询分析多维数据集的数据。 选择类型 ="Microsoft SQL Server 分析服务器"和连接字符串 ="数据源 =\<*服务器名称*>;初始目录 =\<*数据库名称*>"，其中\<*服务器名称*> 和\<*数据库名称*> 是BAM 分析数据库的服务器和数据库名称。|  
  
2.  设计查询。 对于 BAM 主导入数据库，有两种类型的视图：  
  
    |视图名称|Description|  
    |---------------|-----------------|  
    |dbo.bam_\<*视图名称*> _\<*活动名称*> View_View。|此视图包含实例数据。|  
    |dbo.bam_\<*视图名称*> _\<*实时聚合数据透视表名称*> _RTAView|此视图包含在实时聚合中使用的数据。|  
  
    > [!NOTE]
    >  你可以键入**选择\*从视图**以返回所需的结果设置。 对于 BAM 分析数据库中，单击查询生成器并拖动的维度和度量值的多维数据集，名为\<*视图名称*> 若要返回所需的结果。  
  
## <a name="next-steps"></a>后续步骤  
 完成报表向导中的步骤，指定您要呈现哪些数据以及如何呈现这些数据。  
  
## <a name="see-also"></a>另请参阅  
 [管理 BAM 数据库](../core/managing-bam-databases.md)