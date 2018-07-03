---
title: 循环次数超过最大次数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0ac9f5d3-04ec-4c40-8a1f-17ef0b143cda
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6587e5b5dcef641f37f24005fe594a084e5de12d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979598"
---
# <a name="loop-occurs-over-maximum-times"></a>循环次数超过最大次数
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                        X12LoopOccursOverMaximumTimesDescription                        |
|  消息正文   |                            循环次数超过最大次数                             |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的交换，因为该交换包含一个重复次数高于消息架构所需最多次数的循环。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保交换中的循环重复次数不超过消息架构中为循环指定的 maxOccurs 属性中的次数，然后重新发送交换。