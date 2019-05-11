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
ms.openlocfilehash: 5ebfeec80fb9775fbb99c07fc1c694f38f6b11c7
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530756"
---
# <a name="the-interchange-had-structural-error-the-part-after-the-error-is-being-suspended"></a>交换发生了结构错误。 正在挂起错误之后的部分
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                               |
| 产品版本 |                                                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                           |
|    事件 ID     |                                                                                       -                                                                                        |
|  事件源   |                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                             |
|    组件    |                                                                                   EDI 引擎                                                                                   |
|  符号名称  |                                                                        EfactInterchangeStructuralError                                                                         |
|  消息正文   | 交换 id 为 '{0}，发送方 id{1}，接收方 id{2}发生了结构错误。 有关详细信息到挂起队列参阅该错误被挂起之后, 的部分 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的 EDIFACT 交换，因为交换中发生了结构错误。 会发生此错误的事务集被挂起的错误，正在保留的交换。 此错误，事务集 （或集） 的结果，包括错误被挂起，但是其余事务设置为已处理保留的批处理的一部分。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请让交换的修复方法结构错误，发送方，然后重新发送交换。