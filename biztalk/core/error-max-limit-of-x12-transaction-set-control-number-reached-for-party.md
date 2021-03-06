---
title: 可接受 X12 事务集控制编号已达到参与方的最大限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a402f6d0-4399-47c9-a39a-56d7fa1efa86
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76aade02065fbfb001bf1a02ceea26f0901854f2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388659"
---
# <a name="max-limit-of-acceptable-x12-transaction-set-control-number-has-reached-for-party"></a>可接受 X12 事务集控制编号已达到参与方的最大限制
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                      |
| 产品版本 |                                                                 [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                  |
|    事件 ID     |                                                                                              -                                                                                              |
|  事件源   |                                                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                    |
|    组件    |                                                                                         EDI 引擎                                                                                          |
|  符号名称  |                                                                                    PartyX12TsNumberError                                                                                    |
|  消息正文   | 可接受 X12 事务集控制编号已达到参与方的最大限制{0}。 导航到合作伙伴协议管理器的接收方角色屏幕中“参与方”中的字段 ST 2 可重置计数器 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明发送管道无法处理传出的 X12 交换，因为在参与方设置中指定的 ST02 字段中的事务集控制编号（具体来说就是字段 ST02.2 中的参考编号）大于所允许的最大值。 所允许的事务集控制编号的最大值取决于 ST02 中三个字段的值。 最大字符数分别是 9（对于字段 ST02.2 中的参考编号）、8（对于 ST02.1 中的前缀）、8（对于 ST02.3 中的后缀）以及 9（对于所有三个字段的组合）。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请按照如下方式重置事务集控制编号的参考编号字段 (UNH1.2)：  
  
1.  在为交换解析的参与方的“EDI 属性”对话框中，打开“UNG 和 UNH 段定义”页。  
  
2.  单击与 UNH1 字段关联的“编辑”字段。  
  
3.  将事务集控制编号的中间字段（UNH1.2 中的参考编号）设置为新值，以便该字段具有可接受的位数。