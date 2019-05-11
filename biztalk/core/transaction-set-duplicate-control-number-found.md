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
ms.openlocfilehash: 4f273d7e66f4ebe942044e30adccbc7994720a99
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279719"
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
 此错误/警告/信息事件表明接收管道无法处理传入的 X12 交换，因为事务集控制编号的组中的事务集的交换已与另一个的控制编号相同事务集在该组中。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作之一：  
  
-   组中的更改的事务集数量的事务设置中传入的交换，因此事务没有重复的控制编号的控件集。  
  
-   禁用对重复的事务集控制编号的检查，如下所示：  
  
    1.  打开 BizTalk Server 管理控制台。  
  
    2.  打开发送交换的参与方 EDI 属性对话框。  
  
    3.  对于 X12 交换，清除"检查重复的 st2 （事务集控制编号） 组中"x12 交换处理属性页 EDI 属性对话框。  
  
    4.  对于 EDIFACT 交换，清除"检查重复的 unh1 （事务集参考编号） 组中"EDIFACT 交换处理属性页的 EDI 属性对话框中的属性。