---
title: BAM 门户页面布局 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM portal
- Portal page [BAM portal]
ms.assetid: 0d8833b7-dd2f-475c-a890-e925ee47d219
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5569021698eb856d7584a2510a27d69f092f37a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231525"
---
# <a name="bam-portal-page-layout"></a>BAM 门户页面布局
BAM 门户页由以下三个框架组成：  
  
-   横幅  
  
-   我的视图  
  
-   内容  
  
## <a name="banner"></a>横幅  
 **横幅**帧分布门户页的顶部。 横幅框架包含诸如公司名称和徽标之类的商标信息、该用户界面 (UI) 页的帮助链接以及页面标题。 您可以自定义商标，使其满足您所在组织的需要。 有关自定义标题栏中的品牌信息的详细信息，请参阅[自定义 BAM 门户配置](../core/customizing-the-bam-portal-configuration.md)。  
  
## <a name="my-views"></a>我的视图  
 **我视图**帧是在门户页面左侧。 “我的视图”向用户展示了其有权访问的所有视图。 用户可以展开任何视图，以查看该视图的可用功能。 如果没有显示任何视图，则是因为视图尚未创建（此任务通常由业务分析员执行），或尚未向用户授予权限（此任务通常由管理员执行）。  
  
 在每个视图中，您都可以使用以下三个功能来执行相应的任务：  
  
-   **活动搜索**： 允许你创建查询和基于活动的警报。  
  
-   **聚合**： 允许你查看聚合数据并根据数据透视表图中的总计创建警报。  
  
-   **警报管理器**： 允许你可以创建、 编辑、 查看和订阅警报。  
  
> [!NOTE]
>  从“我的视图”框架中选择警报管理器后，您只能编辑现有警报。 要创建新警报，必须从“活动搜索”或“聚合”页内转到“警报管理器”页。  
  
## <a name="content"></a>内容  
 **内容**帧是在门户页面的右侧。 内容页包含由每个“我的视图”任务（即活动搜索、聚合和警报管理）提供的信息。 在选择任务后，内容框架将更改为反映与该任务相关联的各个功能。  
  
## <a name="see-also"></a>另请参阅  
 [BAM 门户上的活动搜索页](../core/activity-search-on-the-bam-portal-page.md)   
 [BAM 门户上的聚合页](../core/aggregations-on-the-bam-portal-page.md)   
 [警报管理器上 BAM 门户页](../core/alert-manager-on-the-bam-portal-page.md)   
 [BAM 门户](../core/bam-portal.md)