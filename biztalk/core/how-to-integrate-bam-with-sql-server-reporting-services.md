---
title: 如何集成 BAM 与 SQL Server Reporting Services |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e2d66b7-c8eb-4871-8a47-544955ccd51e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3cba4a9fe610167105f9bf2b89c78f3a4b0ced0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336942"
---
# <a name="how-to-integrate-bam-with-sql-server-reporting-services"></a>如何集成 BAM 与 SQL Server Reporting Services
报表基于数据创建 BAM 基础结构使用与创建任何其他 SQL Server 数据源的报表相关联的典型任务。 有关使用报表设计器创建报表的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=82437 ](http://go.microsoft.com/fwlink/?LinkId=82437)。  
  
## <a name="prerequisites"></a>先决条件  
 必须有权访问创建报表所需的数据。  
  
### <a name="how-to-create-a-report-in-bam-by-using-sql-server-reporting-service"></a>如何使用 SQL Server Reporting Service 在 BAM 中创建报表  
  
1.  选择要创建报表的数据源。  
  
     BAM 提供 Reporting Services 可以指向两个数据源。  
  
    |数据源|Description|  
    |-----------------|-----------------|  
    |BAM 主导入数据库|包含关于活动实例和实时聚合的视图。 选择类型 ="Microsoft SQL Server"，Connection String ="数据源 =\<*服务器名称*\>;初始目录 =\<*数据库名称*\>"，其中\<*服务器名称*\>并\<*数据库名称*\>是 Bam 主导入数据库的服务器和数据库名称。|  
    |BAM 分析数据库|包含用于查询分析多维数据集的数据。 选择类型 ="Microsoft SQL Server Analysis Server"，Connection String ="数据源 =\<*服务器名称*\>;初始目录 =\<*数据库名称*\>"，其中\<*服务器名称*\>并\<*数据库名称*\>是 BAM 分析数据库的服务器和数据库名称。|  
  
2.  设计查询。 对于 BAM 主导入数据库中，有两种类型的视图：  
  
    |视图名称|Description|  
    |---------------|-----------------|  
    |dbo.bam_\<*视图名称*\>_\<*活动名称*\>View_View。|此视图包含实例数据。|  
    |dbo.bam_\<*视图名称*\>_\<*实时聚合透视表名称*\>_RTAView|此视图包含在实时聚合中使用的数据。|  
  
    > [!NOTE]
    >  您可以键入**选择\*从视图**返回返回所需的结果集。 对于 BAM 分析数据库中，单击查询生成器，将维度和度量值的名为多维数据集拖\<*视图名称*\>返回返回所需的结果集。  
  
## <a name="next-steps"></a>后续步骤  
 完成报表向导来指定为将存在且数据的方式呈现的数据中的步骤。  
  
## <a name="see-also"></a>请参阅  
 [管理 BAM 数据库](../core/managing-bam-databases.md)