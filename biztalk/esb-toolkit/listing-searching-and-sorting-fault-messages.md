---
title: "列出、 搜索和排序错误消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 850b9682-8eba-4a3f-8508-d3eefcd715b7
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 768dd7f51ff09bad76115f8a7e2a95a11ce47981
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="listing-searching-and-sorting-fault-messages"></a>列出、 搜索和排序错误消息
ESB 管理门户主页上可用于获取在 Microsoft BizTalk Server 中执行的应用程序的状态的总体视图。 可以使用的错误页的错误消息，基于对一系列的条件的查询。  
  
### <a name="to-see-an-overview-of-the-status-of-current-biztalk-server-applications"></a>若要查看当前的 BizTalk Server 应用程序的状态的概述  
  
1.  打开[门户主页上](../esb-toolkit/portal-home-page.md)。 此页显示整个应用程序状态、 错误的摘要、 通用、 描述、 发现和集成 (UDDI) 注册和显示的错误以及按应用程序类型和细分的图表的最近的请求。  
  
2.  若要选择你想要查看的信息的应用程序，请单击**选择应用程序**链接上方的第一个图表，然后选择或清除复选框中显示的已安装 BizTalk Server 应用程序的列表。  
  
3.  若要更改时间为其门户显示的信息，请选择**小时、 天、 周、 月、 季度、 每年，**或**所有**第二个图表上方的下拉列表中。  
  
4.  若要更改默认设置用于在主页上的应用程序和显示时间的列表，请编辑设置上[门户我设置页](../esb-toolkit/portal-my-settings-page.md)。  
  
### <a name="to-list-search-for-and-sort-fault-messages-in-the-esb-management-portal"></a>若要列出，搜索和排序错误 ESB 管理门户中的消息  
  
1.  打开[错误设置页](../esb-toolkit/fault-settings-page.md)。 此页面显示截断的每个错误的属性的列表，并由一系列条件支持的故障分析。  
  
2.  若要筛选的页面上显示的错误的列表，请使用下拉列表和列表上方的错误的文本框。 你可以筛选显示的应用程序、 段、 错误代码编号、 错误类别名称、 错误键入文本，和最小/最大错误严重级别的行。 任何控件留空以检索而不考虑其值为此条件的所有消息。  
  
3.  单击**应用筛选器**以查看匹配的错误的列表。 请注意，筛选非常大的容错的数据库可能需要几秒钟才会显示结果。  
  
4.  若要在页中显示更多或更少的行，选择相应的值**记录每个页**下拉列表。  
  
5.  若要排序的错误消息的列表，请单击列标题。 若要以相反顺序对行进行排序，请单击相同的列标题。  
  
6.  单击**导出到 Excel**下载可以在 Microsoft Excel 中查看的格式的错误消息的完整列表。