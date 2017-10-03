---
title: "事务集重复控制编号找到 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b2779a0-b365-4c4b-81c7-8f9284748b6e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe63d3814bcce178164054ab8dcf673eeb4f395a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="transaction-set-duplicate-control-number-found"></a>发现事务集重复控制编号
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|X12TsDuplicateNumberFoundDescription|  
|消息正文|发现事务集重复控制编号|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的 X12 交换，因为该交换的组中某个事务集的事务集控制编号与该组中的另一个事务集的控制编号相同。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作之一：  
  
-   请更改传入交换中事务集的事务集控制编号，以便组中的事务集没有重复的控制编码。  
  
-   按照如下方式禁用检查重复的事务集控制编号：  
  
    1.  打开 BizTalk Server 管理控制台。  
  
    2.  打开发送交换的参与方的“EDI 属性”对话框。  
  
    3.  对于 X12 交换，请清除“EDI 属性”对话框的“X12 交换处理属性”页中的“检查组中重复的 ST2（事务集控制编号）”。  
  
    4.  对于 EDIFACT 交换，请清除“EDI 属性”对话框的“EDIFACT 交换处理属性”页中的“检查组中重复的 UNH1（事务集参考编号）”。