---
title: BAM 门户 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM portal, alerts
- activities [BAM], searching
- BAM portal
- BAM portal, features
- aggregations [BAM], BAM portal
- BAM portal, activity searches
- alerts, Alert Manager
- BAM portal, about BAM portal
- BAM, portals
- BAM portal, aggregations
ms.assetid: 593c9637-6b97-4ad8-8af7-2b49325acf10
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f86aad2a183653f00f1f7fc2533ac6956b2a85f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232077"
---
# <a name="bam-portal"></a>BAM 门户
业务最终用户使用 BAM 门户监视关键绩效指标 (Kpi) 度量的业务目标，以及有关其业务流程的其他信息的进度。 业务分析师使用 BAM 门户监督的观察模型，高级别定义的业务流程中的可见性要求创建。 管理员将其用于各种监视活动，包括监视业务流程管理系统的运行状况。  
  
## <a name="what-is-the-bam-portal"></a>什么是 BAM 门户？  
 BAM 门户向业务流程提供实时、端对端可见性。 这是一种基于 Web 的功能，由 ASP.NET 页的集合组成。 您可以自定义 BAM，为用户改善性能和体验。  
  
## <a name="why-use-the-bam-portal"></a>为什么使用 BAM 门户吗？  
 BAM 门户允许您在 BAM 视图中执行搜索、聚合数据以及设置警报，BAM 视图反映了业务数据的一个方面。 此可见性可为您的业务提供所需的 KPI 信息，或者可用作实现其他解决方案（如扩展 Microsoft Office Excel 电子表格、使用 SQL 报告或生成自定义用户界面，即 UI）之前的概念的证明。  
  
## <a name="bam-portal-components"></a>BAM 门户组件  
 下面是 BAM 门户组件的简短说明。 有关更详细的说明，请参阅另请参阅中的主题。  
  
### <a name="activity-searches"></a>活动搜索  
 BAM 门户用于执行针对 BAM 数据来查找特定的 BAM 活动的搜索。 通过添加和删除，可以显示这些活动与你要为其发出警报的条件匹配的搜索子句创建查询。  
  
 可以保存并重用查询。 它们可以是一个警报，例如从特定客户的采购订单到达时的通知的基础。  
  
### <a name="aggregations"></a>Aggregations  
 门户可以捕获数据的快照并将其显示形式图形图表和随附的数据透视表图。 此数据为您提供了该过程或整体业务的运行状况的可见性。 例如，用户可能希望看到简单的饼图，显示的方面处理中的哪个阶段已达到每个发票 (400 仍在"计算中，"将被拒绝，400 100 付费，而是 100 仍然处于"资金分配") 的一天中收到的 1000 个发票明细.  
  
 显示的数据可以是创建一个警报，如"通知我如果过程的计算阶段中有数多于 500 发票。"的基础  
  
### <a name="alert-manager"></a>警报管理器  
 门户提供了有关警报的创建和编辑现有警报的用户界面。 警报需要要从活动搜索或聚合页监视的条件。 警报管理器操作就是其中填充一个警报，如要通知，谁的相关部分 （例如，通过电子邮件），如何是否其他人可以看到和警报订阅。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [BAM 门户的组件](../core/components-of-the-bam-portal.md)  
  
-   [规划 BAM 门户](../core/planning-for-the-bam-portal.md)  
  
-   [BAM 门户中的活动搜索](../core/activity-searches-in-the-bam-portal.md)  
  
-   [BAM 门户中的聚合](../core/aggregations-in-the-bam-portal.md)  
  
-   [BAM 门户中的警报](../core/alerts-in-the-bam-portal.md)  
  
-   [针对 BAM 门户的辅助功能](../core/accessibility-for-the-bam-portal.md)  
  
-   [BAM 门户的安全注意事项](../core/security-considerations-for-the-bam-portal.md)  
  
-   [BAM 门户中的已知的问题](../core/known-issues-in-the-bam-portal.md)  
  
## <a name="see-also"></a>另请参阅  
 [BAM 门户上的活动搜索页](../core/activity-search-on-the-bam-portal-page.md)   
 [BAM 门户上的聚合页](../core/aggregations-on-the-bam-portal-page.md)   
 [警报管理器上 BAM 门户页](../core/alert-manager-on-the-bam-portal-page.md)