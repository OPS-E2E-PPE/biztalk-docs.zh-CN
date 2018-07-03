---
title: 无效的分隔符集，因为至少一个分隔符在允许的范围之外 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1286559-765b-4728-945d-cf3386e1ba06
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a54467c6d611aefd58d2dfd51c21974c3a5df7c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022507"
---
# <a name="invalid-delimiter-set-because-at-least-one-of-the-delimiters-is-outside-the-allowed-range"></a>分隔符设置无效，因为至少有一个分隔符在允许的范围之外
## <a name="details"></a>详细信息  
  
|                 |                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------|
|  产品名称   |           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]           |
| 产品版本 |                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                       |
|    事件 ID     |                                                   -                                                    |
|  事件源   |         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI         |
|    组件    |                                               EDI 引擎                                               |
|  符号名称  |                                          DelimiterOutOfRange                                           |
|  消息正文   | 无效的分隔符集{0}，至少有一个分隔符是 0 到 127 的允许的范围之外 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道不无法处理传入的交换，因为在交换中的一个或多个包含超出范围的 ASCII 字符中的值设置。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保交换中的每个分隔符都在 ASCII 字符集中，然后重新发送交换。