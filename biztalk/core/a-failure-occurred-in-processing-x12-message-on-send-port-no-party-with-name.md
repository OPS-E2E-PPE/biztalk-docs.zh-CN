---
title: 故障发生在处理 X12 消息在发送端口： 无带名称参与方 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af059a04-3b7c-48e2-a3bf-48ad62deb139
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 817840dae0db408d4f78732f5d470605a05edf71
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014790"
---
# <a name="a-failure-occurred-in-processing-x12-message-on-send-port-no-party-with-name"></a>故障发生在处理 X12 消息在发送端口： 无带名称参与方
## <a name="details"></a>详细信息  
  
|                 |                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------|
|  产品名称   |      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]       |
| 产品版本 |                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                   |
|    事件 ID     |                                               -                                               |
|  事件源   |    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI     |
|    组件    |                                          EDI 引擎                                           |
|  符号名称  |                                               -                                               |
|  消息正文   | 故障发生在处理 X12 消息发送端口上的{0}。 不存在名称为 {1} 的参与方。 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 无法解析的参与方的 X12 交换，因为 BizTalk Server 无法将订阅该交换的参与方与关联的发送端口的发送端口匹配。 如果既 DestinationPartyName 属性，也不发送方限定符、 发送方标识符、 接收方限定符和接收方标识符属性进行升级，因此不可用于发送端参与方解析，将发生这种情况。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保订阅交换的发送端口匹配与参与方关联的发送端口。