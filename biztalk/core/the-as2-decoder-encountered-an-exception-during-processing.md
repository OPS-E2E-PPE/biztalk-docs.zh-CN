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
ms.openlocfilehash: e80ce8b53e6b5eb77770d7abcf9dbfbd157d9d64
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010262"
---
# <a name="the-as2-decoder-encountered-an-exception-during-processing"></a>AS2 解码器在处理期间遇到异常
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                         |
| 产品版本 |                                                                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                     |
|    事件 ID     |                                                                                                 -                                                                                                 |
|  事件源   |                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                       |
|    组件    |                                                                                            AS2 引擎                                                                                             |
|  符号名称  |                                                                          AS2DecoderExceptionEncounteredDuringProcessing                                                                           |
|  消息正文   | AS2 解码器在处理期间遇到异常。  消息和异常的详细信息如下所示： AS2-从:"{0}"AS2-到:"{1}"MessageID:"{2}"MessageType:"{3}"异常:"{4}" |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明由于 AS2 解码器有问题，接收管道无法处理传入的 AS2 消息。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请通过检查 AS2 错误代码来确定错误条件的性质。 有关 AS2 错误代码的详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助文件中的“AS2 错误代码”主题。