---
title: 无效的 AS2-To 标头接收 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 56cd16b3-511b-4716-8806-817f174f0b0e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9acfbb11edabc26d1a01d36e545820892c65139
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330928"
---
# <a name="invalid-as2-to-header-received"></a>无效的 AS2-To 标头接收
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       AS2 引擎                                       |
|  符号名称  |                          InvalidAS2ToNameHeaderReceivedError                           |
|  消息正文   |                      无效的 AS2-To 标头接收。  值： {0}                       |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道不无法处理传入的交换，因为 as2-To 标头消息中不符合 AS2 RFC 4130 中的规范。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保值中 AS2-到消息标头符合 AS2 RFC 4130 第 6.2 节中的规范。