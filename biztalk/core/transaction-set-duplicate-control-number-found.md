---
title: 发现事务集重复控制编号 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1b2779a0-b365-4c4b-81c7-8f9284748b6e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6b9b55dc5cd61bc4c8c806f2dc42259cadf2f69
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977703"
---
# <a name="transaction-set-duplicate-control-number-found"></a>发现事务集重复控制编号
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                          X12TsDuplicateNumberFoundDescription                          |
|  消息正文   |                     发现事务集重复控制编号                     |
  
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