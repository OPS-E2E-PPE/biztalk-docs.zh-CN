---
title: 在发送端口上处理 Edifact 消息时发生故障： 无带名称参与方 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 678baacb-1f21-4081-b788-ef346c3598ca
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 823b0d1315c82676017f0cc5e1bfa45b9ed9e342
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979334"
---
# <a name="a-failure-occurred-in-processing-edifact-message-on-send-port-no-party-with-name"></a>在发送端口上处理 Edifact 消息时发生故障： 无带名称参与方
## <a name="details"></a>详细信息  
  
|                 |                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------|
|  产品名称   |        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]         |
| 产品版本 |                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                     |
|    事件 ID     |                                                 -                                                 |
|  事件源   |                                        BizTalk Server EDI                                         |
|    组件    |                                            EDI 引擎                                             |
|  符号名称  |                                                 -                                                 |
|  消息正文   | 在发送端口上处理 Edifact 消息时发生故障{0}。 不存在名称为 {1} 的参与方。 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 无法解析 EDIFACT 交换的参与方，因为 BizTalk Server 无法订阅该交换的参与方与关联的发送端口的发送端口匹配。 如果既 DestinationPartyName 属性也不发送方限定符和标识符和接收方限定符和标识符属性进行升级，因此不可用于发送端参与方解析，将发生这种情况。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保订阅交换的发送端口和与某个参与方关联的发送端口匹配。