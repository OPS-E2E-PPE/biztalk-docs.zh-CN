---
title: "配置 EDI 和 AS2 状态报告 |Microsoft 文档"
description: "创建 EDI 或 AS2 状态报告查询表达式中，并选择要在 BizTalk Server 中的报表中显示的数据"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6490864d-f1e6-4932-aefb-c332a595aad7
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 833e3c6c26cdac57d7cc57d828b66a66b9eb37f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-an-edi-and-as2-status-report"></a>配置 EDI 和 AS2 状态报表
已启用 EDI 或 AS2 状态报告，你显示的状态报告后你需要从**EDI 状态报告**或**EDIINT 状态报告**部分**组中心数据库**选项卡**组概述**页面[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 在所显示的状态报告中将看到一组默认数据。 您可以配置状态报告的如下方面：  
  
-   查询表达式：运行查询表达式可确定要报告的状态的数据范围，例如，日期范围、数据方向（接收或发送）或者状态值（“已接受”、“已拒绝”、“所有”等）  
  
-   显示在状态报告窗格中的数据类型：由报告中的数据列确定。  
  
    > [!NOTE]
    >  如果启用了状态报告，则所有状态都将保存在存储区中。 通过自定义查询表达式或状态列，可以定义要显示的保存数据。  
  
 五个不同的 EDI 和 AS2 状态报表才可用 (请参阅[类型的 EDI 和 AS2 状态报告](../core/types-of-edi-and-as2-status-reports.md))。 即使每个报告的数据有所不同，每个报告的配置方式也是相同的。  
  
## <a name="prerequisites"></a>先决条件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
## <a name="configure-the-status-report-query-expression"></a>配置状态报表查询表达式  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**BizTalk 组**节点以查看**组概述**窗格。  
  
2.  在底部**组中心数据库**选项卡中**组概述**窗格中，单击你想要配置，如状态报表**EDI 交换和关联 ACK 状态**。  
  
3.  在**查询表达式**区域状态报表窗格中，验证是否所有你想要定义查询的筛选条件都存在。 否则，请单击在空行中的向下箭头**字段名称**底部的查询表达式中，然后选择你想要添加到查询表达式的条件的任何筛选的列。 你可以通过选择行，然后单击删除筛选器条件行**删除**键盘上的按钮。  
  
4.  验证筛选表达式的值是否符合预期。 否则，请单击向下的箭头**运算符**列以选择一个查询操作，并输入中的相应值**值**列。  
  
    > [!NOTE]
    >  中所述的运算符和值可用于在查询表达式中的筛选条件[类型的 EDI 和 AS2 状态报告](../core/types-of-edi-and-as2-status-reports.md)和**EDI AS2 状态报表 UI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
5.  若要运行查询，显示根据筛选器条件中，状态报表单击**运行查询**。  
  
6.  若要将查询表达式另存为.btq 文件，请单击**另存为**、 指定的文件夹并输入文件名，然后单击**保存**。  
  
7.  若要打开已保存的.btq 文件，请单击**打开查询**。  
  
## <a name="configure-the-type-of-data-displayed-in-the-status-report-pane"></a>配置状态报表窗格中显示的数据的类型  
  
1.  右键单击状态报表窗格中，状态结果区域，然后单击**添加/删除列**。  
  
2.  若要将一种状态类别添加到显示的列列表，请单击中的列**可用列**列表，，然后单击**添加**。  
  
3.  若要从显示的列列表中删除一种状态类别，请单击中的列**显示的列**列表，，然后单击**删除**。  
  
## <a name="see-also"></a>另请参阅  
 [监视 EDI 和 AS2 解决方案](../core/monitoring-edi-and-as2-solutions.md)   
 [EDI 和 AS2 状态报告](../core/edi-and-as2-status-reporting.md)   
 [启用 EDI 和 AS2 状态报表](../core/enabling-edi-and-as2-status-reports.md)   
 [显示的 EDI 或 AS2 状态报表](../core/displaying-an-edi-or-as2-status-report.md)