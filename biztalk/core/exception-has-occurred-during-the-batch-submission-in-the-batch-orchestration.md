---
title: 在批处理业务流程的批提交期间出现异常 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c58b2fa9-d036-4e09-a0f8-77a2f983881a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 838e9aff43dd260fd4af8e46ca88782c2389dfc7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971526"
---
# <a name="an-exception-has-occurred-during-the-batch-submission-in-the-batching-orchestration"></a>在批处理业务流程的批提交过程中发生了异常
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                  |
| 产品版本 |                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                              |
|    事件 ID     |                                                          -                                                          |
|  事件源   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                |
|    组件    |                                                   批处理引擎                                                   |
|  符号名称  |                                                  ExceptionOccured                                                   |
|  消息正文   | 在批处理业务流程中的批处理提交期间出现异常。 批处理 Id = {0}，ErrorMessage {1} |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明由于 ErrorMessage 字段中指出的错误条件，批处理业务流程无法向某个批处理中添加批处理元素。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确定 ErrorMessage 字段中的错误条件，解决此错误，然后重新提交消息。