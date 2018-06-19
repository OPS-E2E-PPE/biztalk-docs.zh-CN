---
title: 出现故障。 处理 X12 发送端口上的消息： 接收方和发件人标识符限定符对没有协议 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72ae7926-f5c1-42f4-8c29-11f34c138dd4
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 637cd174b2c9723f4391417392700e3a4f079b79
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240853"
---
# <a name="a-failure-occurred-in-processing-x12-message-on-send-port-no-agreement-for-receiver-and-sender-identifier-qualifier-pairs"></a>出现故障。 处理 X12 发送端口上的消息： 接收方和发件人标识符限定符对没有协议
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|-|  
|消息正文|在发送端口 {0} 上处理 X12 消息时发生故障。 没有协议的接收方和发件人标识符/限定符对 {1}、 {2}、 {3}、 \ {4 \ 存在。|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表示 BizTalk Server 无法解决当事方 EDIFACT 交换因为 BizTalk Server 无法匹配提升发件人限定符和标识符属性，并且提升收件人限定符和标识符属性，使用方的相应值。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保参与方的“EDI 属性”对话框的“ISA 段定义”页中定义的发送方限定符和标识符（ISA5 和 ISA6）以及接收方限定符和标识符（ISA7 和 ISA8）与交换的上下文中相对应的升级后的属性匹配。