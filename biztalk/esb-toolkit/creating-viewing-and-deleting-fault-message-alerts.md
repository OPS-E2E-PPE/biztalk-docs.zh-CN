---
title: 创建、 查看和删除故障消息警报 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59df2b40-b42c-4167-873c-0819839919da
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f38c365e1d26c384ff9437059dccbd17f6c2182
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394664"
---
# <a name="creating-viewing-and-deleting-fault-message-alerts"></a>创建、 查看和删除故障消息警报
ESB 管理门户可以在门户中，错误消息到达时生成警报基于警报指定的条件的消息中的值的比较。 在门户还可以维护的通知链接到单个警报和用户，列表和主动会发出警报时，它会通知这些用户。  
  
### <a name="to-create-and-configure-a-new-alert"></a>若要创建和配置新的警报  
  
1.  打开[门户警报页](../esb-toolkit/portal-alerts-page.md)若要查看现有警报的列表，以及对这些警报在当前订阅。  
  
2.  单击**创建警报**链接以打开[添加警报页](../esb-toolkit/add-alert-page.md)。  
  
3.  在中**输入警报名称**文本框中，键入的新警报的名称。  
  
4.  在**条件**部分的添加警报页，选择一个字段 (如**应用程序**，**错误类型**，或者**故障严重性**) 中**条件**下拉列表; 选择比较类型 (例如 +、 =、 ！ =、 > =、 < =、 或**等**) 中**运算符**下拉列表; 并键入或选择从第三个列表或文本中的值 (名为**值**)。 在您选择**条件**值，页面发生变化，显示一个文本框或匹配值的下拉列表。 所有条件将都结合使用**AND**运算符。  
  
5.  单击**添加**链接添加到列表中，这种情况，然后重复上述步骤以在需要时添加更多条件。  
  
6.  单击**保存**按钮以创建新的警报具有指定的名称和条件。  
  
### <a name="to-view-details-of-an-existing-alert-or-delete-an-existing-alert"></a>若要查看现有警报的详细信息或删除现有的警报  
  
1.  打开[门户警报页](../esb-toolkit/portal-alerts-page.md)。  
  
2.  若要删除警报，请单击**删除警报**现有警报的操作列中的图标。  
  
    > [!NOTE]
    >  非管理用户可以删除警报它们是所有者，以及其中有当前没有订阅服务器。 您必须登录到门户以管理员身份中删除其他警报。  
  
3.  若要查看警报的详细信息，请单击**视图**现有警报的操作列中的图标。 这将打开警报查看器页。  
  
4.  单击**导出到 Excel**若要下载可以在 Microsoft Excel 中查看的格式中的警报的完整列表。