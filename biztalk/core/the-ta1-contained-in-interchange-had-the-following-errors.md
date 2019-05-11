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
ms.openlocfilehash: b6ce98988b8e52b808a5deaa9a8199bb37deb85e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254347"
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
 此错误/警告/信息事件表明接收管道无法处理传入的 TA1 确认由于指出的错误条件。 这可能表明确认不符合 TA1Schema。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请让发送方的确认解决的问题的确认，确保确认符合 ta1schema，然后重新发送确认。