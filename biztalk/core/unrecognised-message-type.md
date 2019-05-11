---
title: 不可识别的消息类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad4094bf-af00-4d5c-9661-7c8abcb1b722
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d1173304d39a0818f59aab990ef0b8f5412cb4e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292631"
---
# <a name="unrecognised-message-type"></a>不可识别的消息类型
## <a name="details"></a>详细信息  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                                UnRecognizedMessageType                                 |
|  消息正文   |                   不可识别的消息类型。 无法进一步处理。                   |

## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道不无法处理传入的交换，因为已为该交换中的事务集的文档类型部署没有文档架构或 BizTalk Server 无法确定文档类型从事务集标识符代码、 版本和命名空间。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作之一：  

- 部署文档架构的文档类型的交换中事务集，然后重新发送交换。  

- 验证以下值定义是有效的架构： 对于 X12，目标命名空间、 版本/发行版和文档类型;对于 EDIFACT，目标命名空间、 消息版本号、 消息发行版号和消息类型。 有关详细信息，请参阅中的"参与方解析、 架构发现和授权的接收的 EDI 消息"主题中的"架构发现"部分[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。
