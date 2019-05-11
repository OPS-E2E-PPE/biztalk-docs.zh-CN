---
title: 在发送端口上处理 Edifact 消息时发生故障：不存在用于收件人和发件人标识符限定符对协议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cffc4705-164f-4779-8f04-c6a2a7f1bbda
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c2937dc29be315ef5298b43a50ab95f52c4573a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348300"
---
# <a name="a-failure-occurred-in-processing-edifact-message-on-send-port-no-agreement-for-receiver-and-sender-identifier-qualifier-pairs"></a>在发送端口上处理 Edifact 消息时发生故障：没有收件人和发件人标识符限定符对的协议
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                         |
| 产品版本 |                                                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                     |
|    事件 ID     |                                                                                 -                                                                                 |
|  事件源   |                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                       |
|    组件    |                                                                            EDI 引擎                                                                             |
|  符号名称  |                                                                                 -                                                                                 |
|  消息正文   | 在发送端口上处理 Edifact 消息时发生故障{0}。 不存在协议的接收方和发件人标识符/限定符对的{1}， {2}， {3}， {4}。 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 无法解析 EDIFACT 交换的参与方，因为它无法匹配提升发件人限定符和标识符属性，并提升接收方限定符和标识符为参与方的相应值的属性。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保发送方限定符和标识符 （UNB2.1 和 UNB2.2） 和接收方限定符和标识符 （UNB3.1 和 unb3.2 一起使用） 的 EDI 属性对话框中的参与方的 UNB 段定义页中定义的匹配相应交换的上下文中的升级的属性。