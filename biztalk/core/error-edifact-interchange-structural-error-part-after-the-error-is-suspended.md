---
title: 交换发生了结构错误。 之后的部分被挂起错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9071825d-7b90-42bf-bcf9-2a15ae36086d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e77100200a4fb2eacb24c6745fcd17011231b991
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967302"
---
# <a name="the-interchange-had-structural-error-the-part-after-the-error-is-being-suspended"></a>交换发生了结构错误。 错误之后的部分被挂起
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                               |
| 产品版本 |                                                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                           |
|    事件 ID     |                                                                                       -                                                                                        |
|  事件源   |                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                             |
|    组件    |                                                                                   EDI 引擎                                                                                   |
|  符号名称  |                                                                        EfactInterchangeStructuralError                                                                         |
|  消息正文   | 交换 id 为 '{0}，发送方 id{1}，接收方 id{2}发生了结构错误。 错误之后的部分已被挂起，请参阅“挂起队列”以获取详细信息。 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的 EDIFACT 交换，因为该交换中发生了结构错误。 正在保留的交换会发生此错误，由于此错误事务集被挂起。 由于此错误，包含此错误的事务集被挂起，但是作为保留的批处理的一部分对其余事务集进行处理。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请让交换的发送方解决此结构错误，然后重新发送交换。