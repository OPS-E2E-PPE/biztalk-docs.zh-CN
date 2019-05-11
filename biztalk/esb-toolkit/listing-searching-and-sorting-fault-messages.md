---
title: 列出、 搜索和排序错误消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 850b9682-8eba-4a3f-8508-d3eefcd715b7
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c68d5411bc7f9837a1e1f41892b2741d0b56a3d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65261498"
---
# <a name="listing-searching-and-sorting-fault-messages"></a>列出、 搜索和排序故障消息
ESB 管理门户的主页上可用于获取 Microsoft BizTalk Server 内执行的应用程序的状态的总体视图。 可以使用的错误页错误消息，根据一系列条件的查询。  
  
### <a name="to-see-an-overview-of-the-status-of-current-biztalk-server-applications"></a>若要查看当前的 BizTalk Server 应用程序的状态的概述  
  
1.  打开[门户主页上](../esb-toolkit/portal-home-page.md)。 此页显示的应用程序的总体状态、 错误的摘要、 通用描述、 发现和集成 (UDDI) 注册和显示的错误类型和应用程序细分的图表的最近的请求。  
  
2.  若要选择你想要查看的信息的应用程序，请单击**选择应用程序**链接上方的第一个图表，然后选择或清除复选框将显示已安装 BizTalk Server 应用程序列表中。  
  
3.  若要更改的期限为其在门户中显示的信息，请选择**小时、 天、 周、 月、 季度、 年**或**所有**的第一个图表上方的下拉列表中。  
  
4.  若要更改默认设置应用程序和显示时间的列表所用的主页上，编辑设置上[门户我的设置网页](../esb-toolkit/portal-my-settings-page.md)。  
  
### <a name="to-list-search-for-and-sort-fault-messages-in-the-esb-management-portal"></a>若要列出，搜索以搜索和排序故障 ESB 管理门户中的消息  
  
1.  打开[容错设置页](../esb-toolkit/fault-settings-page.md)。 此页显示被截断的每个错误的属性列表，并由一系列条件支持的错误进行的分析。  
  
2.  若要筛选的错误页上显示的列表，请使用下拉列表和列表上方的错误的文本框。 您可以筛选的行显示的应用程序、 时间、 错误代码编号、 错误类别名称、 错误类型文本和最小/最大故障严重性。 保留的任何控件为空以检索所有消息而不考虑它们的值为此条件。  
  
3.  单击**将应用筛选器**若要查看匹配的错误的列表。 请注意，筛选非常大的容错数据库上可能需要几秒钟来显示结果。  
  
4.  若要在页中显示更多或更少的行，选择相应的值**记录每个页面**下拉列表。  
  
5.  若要排序的错误消息的列表，请单击列标题。 若要以相反顺序的行进行排序，请单击同一个列标题。  
  
6.  单击**导出到 Excel**若要下载可以在 Microsoft Excel 中查看的格式的错误消息的完整列表。