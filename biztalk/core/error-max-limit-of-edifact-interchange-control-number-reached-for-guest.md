---
title: 来宾设置达到可接受的 Edifact 交换控制编号的最大限制 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5d2dcc0-61fd-47c9-9339-8a85319c5398
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6dc8110f9aa9a48e098f970383b65266cc544c19
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241525"
---
# <a name="max-limit-of-acceptable-edifact-interchange-control-number-has-reached-for-guest-settings"></a>已达到“来宾”设置的可接受 EDIFACT 交换控制编号最大限制
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|GlobalEdifactUnbNumberError|  
|消息正文|已达到“来宾”设置的可接受 Edifact 交换控制编号最大限制。 导航到“全局”配置接收方角色屏幕、合作伙伴协议管理器中的字段 UNB 5 可重置计数器|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明发送管道无法处理传出的交换，因为在全局设置中指定的 ISA13 字段中的交换控制编号（具体来说就是字段 UNB5.2 中的参考编号）大于所允许的最大值。 所允许的交换控制编号的最大值取决于 UNB5 中三个字段的值。 最大字符数是 14（对于字段 UNB5.2 中的参考编号）、13（对于 UNB5.1 中的前缀）、13（对于 UNB5.3 中的后缀）以及 14（对于所有三个字段的组合）。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请按照如下方式重置交换控制编号的参考编号字段 (UNB5.2)：  
  
1.  在“EDI 全局属性”对话框中，打开“UNB 段定义”页。  
  
2.  单击与 UNB5 字段关联的“编辑”字段。  
  
3.  将交换控制编号的中间字段（UNB5.2 中的参考编号）设置为新值，以便该字段具有可接受的位数。