---
title: 故障发生在处理 X12 消息在发送端口：不存在用于收件人和发件人标识符限定符对和不带名称的参与方协议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fdf445e8-51a3-44fb-aa71-e0b0ab9c428f
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e33f187c2804032b881305652f76cd9e45cc081e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388513"
---
# <a name="a-failure-occurred-in-processing-x12-message-on-send-port-no-agreement-for-receiver-and-sender-identifier-qualifier-pairs-and-no-party-with-name"></a>故障发生在处理 X12 消息在发送端口：不存在用于收件人和发件人标识符限定符对和不带名称的参与方协议
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                      |
| 产品版本 |                                                                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                  |
|    事件 ID     |                                                                                              -                                                                                               |
|  事件源   |                                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                    |
|    组件    |                                                                                          EDI 引擎                                                                                          |
|  符号名称  |                                                                                              -                                                                                               |
|  消息正文   | 故障发生在处理 X12 消息发送端口上的{0}。 不存在协议的接收方和发件人标识符/限定符对的{1}， {2}， {3}， {4}。 存在具有名称的参与方{5}。 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 无法解析该参与方的 EDIFACT 交换，因为 BizTalk Server 无法匹配提升发件人限定符和标识符属性，并提升接收方限定符和为参与方的相应值的标识符属性。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保发送方限定符和标识符 （ISA5 和 ISA6） 和接收方限定符和标识符 （ISA7 和 ISA8） 中的 EDI 属性对话框中的参与方的 ISA 段定义页定义匹配相应的提升交换的上下文中的属性。