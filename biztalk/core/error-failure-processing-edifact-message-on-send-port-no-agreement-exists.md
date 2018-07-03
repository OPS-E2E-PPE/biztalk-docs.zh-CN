---
title: 在发送端口上处理 Edifact 消息时发生故障： 不存在用于收件人和发件人标识符限定符对和不带名称的参与方协议 |Microsoft Docs
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
ms.openlocfilehash: f0b4e66ce918f59502125e77b7c19615cb281660
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009910"
---
# <a name="a-failure-occurred-in-processing-edifact-message-on-send-port-no-agreement-for-receiver-and-sender-identifier-qualifier-pairs-and-no-party-with-name"></a>在发送端口上处理 Edifact 消息时发生故障： 不存在用于收件人和发件人标识符限定符对和不带名称的参与方协议
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                        |
| 产品版本 |                                                                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                    |
|    事件 ID     |                                                                                                -                                                                                                 |
|  事件源   |                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                      |
|    组件    |                                                                                            EDI 引擎                                                                                            |
|  符号名称  |                                                                                                -                                                                                                 |
|  消息正文   | 在发送端口上处理 Edifact 消息时发生故障{0}。 不存在 {1}、{2}、{3}、{4} 的接收方和发送方标识符/限定符对的协议。 不存在名称为 {5} 的参与方。 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 无法解析 EDIFACT 交换的参与方，因为 BizTalk Server 无法通过某一方的相应值来匹配升级后的发送方限定符和标识符属性、升级后的接收方限定符和标识符属性。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保参与方的“EDI 属性”对话框的“UNB 段定义”页中定义的发送方限定符和标识符（UNB2.1 和 UNB2.2）以及接收方限定符和标识符（UNB3.1 和 UNB3.2）与交换的上下文中相对应的升级后的属性匹配。