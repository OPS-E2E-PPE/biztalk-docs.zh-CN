---
title: "错误 Ack 生成已失败，因为最大限制为 X12 事务全局 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8bbcae14-6e5c-4f79-87c6-311b4b54c7ff
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e648a40b11d94ce97b5c327f392585e313de06f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error-ack-generation-has-failed-as-maximum-limit-of-x12-transaction-global"></a>错误 Ack 生成具有失败的 X12 全局事务的最大限制
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|-|  
|消息正文|无法生成确认，因为“来宾”设置已达到可接受的 X12 事务集控制编号的最大限制。 导航到合作伙伴协议管理器的全局配置发送方角色屏幕中的字段 ST 2 可重置计数器|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 无法生成对 X12 交换的确认，因为在确认的事务集控制编号 (ST2) 中输入的控制编号大于 ST2 所允许的最大值。 在这种情况下，BizTalk Server 使用 EDI 全局属性来创建确认。  
  
 事务集控制编号的最大值取决于用于控制编号的位数。 所有三个字段的最大长度是 9；前缀和后缀字段的最大长度是 8。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请将“GS 和 ST 段定义”页的事务集控制编号 (ST2) 的控制编号字段 (ST2.2) 重置为低于最大限制的值。 在 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 管理控制台的“EDI 全局属性”对话框中设置此属性。