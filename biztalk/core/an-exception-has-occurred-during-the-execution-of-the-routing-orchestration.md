---
title: 路由业务流程执行期间发生了异常 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 68ec8921-ba05-496e-8dcc-fd8994fcb8b7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 917349fe1157bc672ad3f3897f504625c59e7ba3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007318"
---
# <a name="an-exception-has-occurred-during-the-execution-of-the-routing-orchestration"></a>在路由业务流程的执行期间出现异常
## <a name="details"></a>详细信息  
  
|                 |                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------|
|  产品名称   |       [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]       |
| 产品版本 |                   [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                   |
|    事件 ID     |                                               -                                                |
|  事件源   |     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI     |
|    组件    |                                        批处理引擎                                         |
|  符号名称  |                                 ExceptionOccuredDuringRouting                                  |
|  消息正文   | 在执行路由业务流程期间发生异常。 错误消息 = {0} |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明路由业务流程无法正确处理每个 XML 批处理元素的副本，因为 ErrorMessage 字段中指出了错误条件。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，确定 ErrorMessage 字段中为的错误条件，解决错误，并重新提交消息。