---
title: 数据元素中的无效字符 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db7e2c72-f2cc-4157-aa26-062d2cc1210b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 635706c4614c2d0e874a288068b8f8408bae0c75
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330909"
---
# <a name="invalid-character-in-data-element"></a>数据元素中的无效字符
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                     X12DeInvalidCharacterInDataElementDescription                      |
|  消息正文   |                           数据元素中的无效字符                            |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道不无法处理传入的交换，因为数据元素的值不符合 EDI 架构中指定的值。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保数据元素中的值符合 EDI 架构，然后重新发送交换。