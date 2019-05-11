---
title: 可接受 X12 事务集控制编号已达到来宾设置的最大限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e5a4aa5c-13a7-4234-916e-562b52644c51
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f35efea65a1ee4741c86679797f5f218a1cbaf0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347437"
---
# <a name="max-limit-of-acceptable-x12-transaction-set-control-number-has-reached-for-guest-settings"></a>可接受 X12 事务集控制编号已达到来宾设置的最大限制
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                            |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                             |
| 产品版本 |                                                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                         |
|    事件 ID     |                                                                                                     -                                                                                                      |
|  事件源   |                                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                           |
|    组件    |                                                                                                 EDI 引擎                                                                                                 |
|  符号名称  |                                                                                           GlobalX12TsNumberError                                                                                           |
|  消息正文   | 可接受 X12 事务集控制编号已达到来宾设置的最大限制。 导航到合作伙伴协议管理器的全局配置发送方角色屏幕中的字段 ST 2 可重置计数器 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明发送管道无法处理传出的 X12 交换，因为在全局设置中，特别是字段 ST02.2 中的参考编号指定的 ST02 字段中的事务集控制编号大于允许的最大值。 所允许的事务集控制编号的最大值取决于 ST02 中三个字段的值。 最大字符数是字段 UNH1.2，8 对于 UNH1.1 中的前缀和后缀中 UNH1.3，8 和 9 对于所有三个字段的组合中的参考编号的 9。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请按如下所示重置事务集控制编号的参考编号字段 (ST02.2):  
  
1.  在“EDI 全局属性”对话框中，打开“GS 和 ST 段定义”页。  
  
2.  单击与 ST02 字段关联的编辑字段。  
  
3.  将组控制编号 （ST02.2 中的参考编号） 的中间字段设置为新值中，以便该字段具有可接受的位数。