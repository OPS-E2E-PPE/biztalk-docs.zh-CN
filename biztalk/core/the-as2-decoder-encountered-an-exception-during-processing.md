---
title: AS2 解码器过程中遇到异常处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5f16d2e-e83c-4e2c-84be-41b5ed012dce
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3635a824fbd551daa265d3448434430eba252867
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299064"
---
# <a name="the-as2-decoder-encountered-an-exception-during-processing"></a>AS2 解码器过程中遇到异常处理
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                         |
| 产品版本 |                                                                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                     |
|    事件 ID     |                                                                                                 -                                                                                                 |
|  事件源   |                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                       |
|    组件    |                                                                                            AS2 引擎                                                                                             |
|  符号名称  |                                                                          AS2DecoderExceptionEncounteredDuringProcessing                                                                           |
|  消息正文   | AS2 解码器过程中遇到异常处理。  消息和异常的详细信息如下所示：AS2-从:"{0}"AS2-到:"{1}"MessageID:"{2}"MessageType:"{3}"异常:"{4}" |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的 AS2 消息由于 AS2 解码器的问题。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请通过检查 AS2 错误代码来确定错误条件的性质。 有关 AS2 错误代码的详细信息，请参阅中的"AS2 错误代码"主题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助文件。