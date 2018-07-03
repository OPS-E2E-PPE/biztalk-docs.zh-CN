---
title: 可接受 Edifact 事务集控制编号已达到参与方的最大限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a64cc5d3-a845-4044-9c6e-879ecda15fce
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85fd53beb1484d1e9ffbddf1bbc4f4ac69ae1e67
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004534"
---
# <a name="max-limit-of-acceptable-edifact-transaction-set-control-number-has-reached-for-party"></a>已达到参与方的可接受 EDIFACT 事务集控制编号最大限制
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                        |
| 产品版本 |                                                                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                    |
|    事件 ID     |                                                                                                -                                                                                                 |
|  事件源   |                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                      |
|    组件    |                                                                                            EDI 引擎                                                                                            |
|  符号名称  |                                                                                   GlobalEdifactUnhNumberError                                                                                    |
|  消息正文   | 可接受 Edifact 事务集控制编号已达到参与方的最大限制{0}。 导航到接收方角色屏幕中的“参与方”、合作伙伴协议管理器中的字段 UNH 1 可重置计数器 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明发送管道无法处理传出的交换，因为在参与方设置中指定的 UNH1 字段中的事务集控制编号（具体来说就是字段 UNH1.2 中的参考编号）大于所允许的最大值。 所允许的事务集控制编号的最大值取决于 UNH1 中三个字段的值。 最大字符数是 14 个字段 UNH1.2，13 个 UNH1.1 中的前缀和 UNH1.3 中的后缀的 13 和 14 个所有三个字段的组合中的参考编号。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请按照如下方式重置事务集控制编号的参考编号字段 (UNH1.2)：  
  
1.  在为交换解析的参与方的“EDI 属性”对话框中，打开“UNG 和 UNH 段定义”页。  
  
2.  单击与 UNH1 字段关联的“编辑”字段。  
  
3.  将事务集控制编号的中间字段（UNH1.2 中的参考编号）设置为新值，以便该字段具有可接受的位数。