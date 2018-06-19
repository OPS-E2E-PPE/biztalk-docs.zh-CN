---
title: 处理在发送端口上的 Edifact 消息时出现故障： 接收方和发件人标识符限定符对和任何一方具有名称没有协议 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11880c7c-6032-449b-b251-27fc2b2f0d72
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7df88a39d9ccbbcd94fd4498c5847c5104bb40cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240093"
---
# <a name="a-failure-occurred-in-processing-edifact-message-on-send-port-no-agreement-for-receiver-and-sender-identifier-qualifier-pairs-and-no-party-with-name"></a>处理在发送端口上的 Edifact 消息时出现故障： 接收方和发件人标识符限定符对和任何一方具有名称没有协议
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|-|  
|消息正文|在发送端口 {0} 上处理 Edifact 消息时发生故障。 没有协议的接收方和发件人标识符/限定符对 {1}、 {2}、 {3}、 \ {4 \ 存在。 任何一方不存在名称 {5}。|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 无法解析 EDIFACT 交换的参与方，因为 BizTalk Server 无法通过某一方的相应值来匹配升级后的发送方限定符和标识符属性、升级后的接收方限定符和标识符属性。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保参与方的“EDI 属性”对话框的“UNB 段定义”页中定义的发送方限定符和标识符（UNB2.1 和 UNB2.2）以及接收方限定符和标识符（UNB3.1 和 UNB3.2）与交换的上下文中相对应的升级后的属性匹配。