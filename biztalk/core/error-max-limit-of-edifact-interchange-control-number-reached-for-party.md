---
title: "当事方达到可接受的 Edifact 交换控制编号的最大限制 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5c00c357-4c7b-42ea-a031-15bad0195a75
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7fdb92781d137f57a09ce8c45693c2928646af24
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="max-limit-of-acceptable-edifact-interchange-control-number-has-reached-for-party"></a>已达到参与方的可接受 EDIFACT 交换控制编号最大限制
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|PartyEdifactUnbNumberError|  
|消息正文|已达到参与方 {0} 的可接受 Edifact 交换控制编号最大限制。 导航到合作伙伴协议管理器的接收方角色屏幕中“参与方”中的字段 UNB 5 可重置计数器|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明发送管道无法处理传出的交换，因为在参与方设置中指定的 UNB5 字段中的交换控制编号（具体来说就是字段 UNB5.2 中的参考编号）大于所允许的最大值。 所允许的交换控制编号的最大值取决于 UNB5 中三个字段的值。 最大字符数是 14（对于字段 UNB5.2 中的参考编号）、13（对于 UNB5.1 中的前缀）、13（对于 UNB5.3 中的后缀）以及 14（对于所有三个字段的组合）。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请按照如下方式重置交换控制编号的参考编号字段 (UNB5.2)：  
  
1.  在为交换解析的参与方的“EDI 属性”对话框中，打开作为交换接收方的参与方的“UNB 段定义”页。  
  
2.  单击与 UNB5 字段关联的“编辑”字段。  
  
3.  将交换控制编号的中间字段（UNB5.2 中的参考编号）设置为新值，以便该字段具有可接受的位数。