---
title: "确认生成已失败，因为已经达到了最大限制为 Edifact 事务集控制编号的全局设置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6adc02d7-ebc4-4da0-a19a-3a423d63499d
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 252f0fd6dbe77eb83018e2bb34d4a6cd07cdbdf2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="acknowledgement-generation-has-failed-as-maximum-limit-of-edifact-transaction-set-control-number-has-been-reached-for-global-settings"></a>确认生成失败，因为已达到全局设置的 EDIFACT 事务集控制编号的上限
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|-|  
|消息正文|无法生成确认，因为“来宾”设置已达到可接受的 Edifact 事务集控制编号的最大限制。 导航到“全局”配置发送方角色屏幕、合作伙伴协议管理器中的字段 UNH 1 可重置计数器。|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 无法生成对 EDIFACT 交换的确认，因为在确认的事务集参考编号 (UNH1) 中输入的控制编号大于 UNH1 所允许的最大值。 在这种情况下，BizTalk Server 使用 EDI 全局属性来创建确认。  
  
 事务集参考编号的最大值取决于用于参考编号的位数。 参考编号最多 14 个字符，前缀和后缀最多 13 个字符，三个字段合起来最多 14 个字符。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请将“UNG 和 UNH 段定义”页的事务集参考编号 (UNH1) 的参考编号字段 (UNH1.2) 重置为低于最大限制的值。 在 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 管理控制台的“EDI 全局属性”对话框中设置此属性。