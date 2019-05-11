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
ms.openlocfilehash: 6140a6684f0548f2c9acfd0682b8bb42b025df89
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388287"
---
# <a name="an-exception-has-occurred-during-the-batch-submission-in-the-batching-orchestration"></a>在批处理业务流程的批提交期间出现异常
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                  |
| 产品版本 |                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                              |
|    事件 ID     |                                                          -                                                          |
|  事件源   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                |
|    组件    |                                                   批处理引擎                                                   |
|  符号名称  |                                                  ExceptionOccured                                                   |
|  消息正文   | 在批处理业务流程的批提交期间出现异常。 批处理 Id = {0}，ErrorMessage {1} |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表示，批处理业务流程无法添加批处理元素到批因为 ErrorMessage 字段中指出了错误条件。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确定 ErrorMessage 字段中的错误条件，解决此错误，然后重新提交消息。