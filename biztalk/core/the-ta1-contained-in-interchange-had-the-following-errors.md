---
title: 交换中包含的 TA1 发生了以下错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2d63fe9-63ef-44b3-8cb9-45a7abf8d0e4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23bc06cd5f7a7b1e46b34daf5cac2106dcbd543a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002134"
---
# <a name="the-ta1-contained-in-interchange-had-the-following-errors"></a>交换中包含的 TA1 发生了以下错误
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                |
| 产品版本 |                            [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                            |
|    事件 ID     |                                                        -                                                         |
|  事件源   |              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI              |
|    组件    |                                                    EDI 引擎                                                    |
|  符号名称  |                                                   X12TA1Error                                                    |
|  消息正文   | {0} TA1 交换 id 中包含{1}，发件人 id{2}，接收方 id{3}发生以下错误： |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明由于指出的错误条件，接收管道无法处理传入的  TA1  确认。 此错误可能表明确认不符合 TA1Schema。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请让确认的发送方解决确认中的问题，从而确保确认符合 TA1Schema，然后重新发送确认。