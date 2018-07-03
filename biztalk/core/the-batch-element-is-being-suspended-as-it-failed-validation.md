---
title: 因为验证失败，批元素被挂起 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea5e19e8-4592-40f4-bffe-85ab27653fd5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90f82c88adc18899aac6d481b7a5d3e31e1a72c8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021963"
---
# <a name="the-batch-element-is-being-suspended-as-it-failed-validation"></a>因为验证失败，批元素被挂起
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                    批处理引擎                                     |
|  符号名称  |                                 BatchElementSuspended                                  |
|  消息正文   |    因为验证失败，批元素被挂起。 错误为： {0}    |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明批处理业务流程无法添加设置为批处理交换，因为事务集未能通过验证由批处理业务流程执行的事务。 将不验证失败的事务集生成交换。 批处理业务流程设置 EDI。BatchElementValidationFailure 上下文属性设置为"True"。 BatchSuspend 业务流程根据该上下文属性提取消息，发布错误信息，然后就会被挂起。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请指出发生错误的事务集的发送方，如错误消息中所示。 让发送方解决导致其未通过验证的问题，然后重新发送该事务集。