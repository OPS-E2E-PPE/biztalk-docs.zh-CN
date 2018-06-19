---
title: 可接受的 X12 交换控制编号为方已达到最大限制 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: adc49089-3c7b-4ce2-9fbc-68e582c3a822
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fba803260af4879e4e2a286c0f7864af7ccf2747
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262477"
---
# <a name="max-limit-of-acceptable-x12-interchange-control-number-has-reached-for-party"></a>已达到参与方的可接受 X12 交换控制编号最大限制
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|PartyX12IsaNumberError|  
|消息正文|已达到参与方 {0} 的可接受 X12 交换控制编号最大限制。 导航到接收方角色屏幕中的“参与方”、合作伙伴协议管理器中的字段 ISA 13 可重置计数器|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明发送管道无法处理传出的 X12 交换，因为在参与方设置中指定的 ISA13 字段中的交换控制编号大于所允许的最大值。 交换控制编号的最大字符数为 9。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请按照如下方式重置交换控制编号：  
  
1.  在用于参与方解决交换的“EDI 属性”对话框中，打开“作为交换接收方的参与方”的“ISA 段定义”页。  
  
2.  单击与 ISA13 字段关联的“编辑”字段。  
  
3.  将交换控制编号设置为一个新值，以便该字段具有可接受的位数。