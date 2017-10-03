---
title: "最大限制的事务集控制编号已达到来宾设置的可接受 Edifact |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3924a18c-87bc-4727-b7cd-598d3e5ade2a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 709d6069d143cea2271e6311fad571a0290133db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="max-limit-of-acceptable-edifact-transaction-set-control-number-has-reached-for-guest-settings"></a>来宾设置达到可接受的 Edifact 事务集控制编号的最大限制
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|GlobalEdifactUnhNumberError|  
|消息正文|来宾设置达到可接受的 Edifact 事务集控制编号的最大限制。 导航到合作伙伴协议管理器的全局配置接收方角色屏幕中的字段 UNH 1 可重置计数器|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明发送管道无法处理传出的交换，因为在全局设置中指定的 UNH1 字段中的事务集控制编号（具体来说就是字段 UNH1.2 中的参考编号）大于所允许的最大值。 所允许的组控制编号的最大值取决于 UNH1 中三个字段的值。 最大字符数为 14 中字段 UNH1.2，13 for UNH1.1 中的前缀和 13 中 UNH1.3，该后缀和 14 的组合的所有三个字段的引用编号。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请按照如下方式重置事务集控制编号的参考编号字段 (UNH1.2)：  
  
1.  在“EDI 全局属性”对话框中，打开“UNH 段定义”页。  
  
2.  单击与 UNH1 字段关联的“编辑”字段。  
  
3.  将组控制编号的中间字段（UNH1.2 中的参考编号）设置为新值，以便该字段具有可接受的位数。