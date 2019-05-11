---
title: 配置 EDI 和 AS2 状态报告 |Microsoft Docs
description: 创建 EDI 或 AS2 状态报告查询表达式中，并选择想要在 BizTalk Server 中的报表中显示的数据
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6490864d-f1e6-4932-aefb-c332a595aad7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce12c33570189f8436752d1741957f51779d25d5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391369"
---
# <a name="configure-an-edi-and-as2-status-report"></a>配置 EDI 和 AS2 状态报告
已启用 EDI 或 AS2 状态报告，可显示状态报告后你想从**EDI 状态报告**或**EDIINT 状态报告**一部分**组中心**选项卡**组概述**页中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 显示的状态报告，你将看到默认值的数据集。 你可以配置状态报告的以下方面：  
  
- 用于运行以确定报告的状态，例如数据、 日期范围、 数据方向的范围的查询表达式 （接收或发送） 或者状态值 （接受，将被拒绝，所有等。）  
  
- 显示在状态报告窗格中，由报表中的数据列的数据类型。  
  
  > [!NOTE]
  >  每当启用状态报告后，所有状态都将都保存在存储中。 通过自定义查询表达式或状态列，可以定义显示的已保存的数据。  
  
  五个不同的 EDI 和 AS2 状态报告 (请参阅[类型的 EDI 和 AS2 状态报告](../core/types-of-edi-and-as2-status-reports.md))。 配置每个报表的方式是相同的即使每个报表的数据不同。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
## <a name="configure-the-status-report-query-expression"></a>配置状态报告查询表达式  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**BizTalk 组**节点以查看**组概述**窗格。  
  
2. 在底部**组中心**选项卡**组概述**窗格中，单击你想要配置，如在状态报告**EDI 交换和相关 ACK 状态**。  
  
3. 在中**查询表达式**区域状态报表窗格中，验证想要定义查询的所有筛选器条件是否存在。 如果没有，请单击在空行中的向下箭头**字段名**底部的查询表达式中，并选择你想要添加到查询表达式的条件的任何筛选的列。 可以通过选择行并单击删除筛选条件行**删除**键盘上的按钮。  
  
4. 验证筛选器表达式的值是否为所需。 如果没有，请单击向下的箭头**运算符**要选择查询操作，并输入相应的值的列**值**列。  
  
   > [!NOTE]
   >  中所述的运算符和值可用于在查询表达式中的筛选器条件[类型的 EDI 和 AS2 状态报告](../core/types-of-edi-and-as2-status-reports.md)并**EDI-AS2 状态报告 UI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
5. 若要运行查询，显示在状态报告根据筛选条件中，单击**运行查询**。  
  
6. 若要查询表达式另存为.btq 文件，请单击**另存为**，指定的文件夹并输入一个文件名，然后单击**保存**。  
  
7. 若要打开已保存的.btq 文件，请单击**打开查询**。  
  
## <a name="configure-the-type-of-data-displayed-in-the-status-report-pane"></a>配置状态报告窗格中显示的数据类型  
  
1.  右键单击状态报告窗格的状态结果区域，然后单击**添加/删除列**。  
  
2.  若要将一种状态类别添加到显示的列列表，请单击中的列**可用的列**列表，，然后单击**添加**。  
  
3.  若要从显示的列列表中删除状态类别，请单击中的列**显示的列**列表，，然后单击**删除**。  
  
## <a name="see-also"></a>请参阅  
 [监视 EDI 和 AS2 解决方案](../core/monitoring-edi-and-as2-solutions.md)   
 [EDI 和 AS2 状态报告](../core/edi-and-as2-status-reporting.md)   
 [启用 EDI 和 AS2 状态报告](../core/enabling-edi-and-as2-status-reports.md)   
 [显示 EDI 或 AS2 状态报告](../core/displaying-an-edi-or-as2-status-report.md)