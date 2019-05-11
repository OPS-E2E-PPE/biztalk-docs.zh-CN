---
title: 在序列化期间遇到错误。 X12 功能组发生以下错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dad987c3-92f3-4a6b-ba1a-b60f6ea2fbe4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a461a5db58a2ca41fdd7e42211fbb798bc6e197
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394759"
---
# <a name="error-encountered-during-serialization-the-x12-functional-group-had-the-following-errors"></a>在序列化期间遇到错误。 X12 功能组发生以下错误
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                 |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                |
| 产品版本 |                                                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                            |
|    事件 ID     |                                                                                        -                                                                                        |
|  事件源   |                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                              |
|    组件    |                                                                                   EDI 引擎                                                                                    |
|  符号名称  |                                                                           X12FunctionalGroupSendError                                                                           |
|  消息正文   | 在序列化期间遇到错误。 X12 功能组 id 为 '{0}，交换中包含的 id{1}，发送方 id'{2}，接收方 id{3}发生以下错误： |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 EDI 发送管道遇到错误，在序列化传出的 X12 交换，由于通过标识的功能组指出的错误。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，需要使用错误消息中的信息来标识功能组中的错误，然后确定问题解决方案产品帮助中。