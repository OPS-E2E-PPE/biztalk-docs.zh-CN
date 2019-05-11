---
title: 无效的时间 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6942eb77-3ef1-460c-ac4f-8f1339c25d1b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c305afe09a7ff116d04554bb1c1962a137274945
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330094"
---
# <a name="invalid-time"></a>无效的时间
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                              X12Ta1InvalidTimeDescription                              |
|  消息正文   |                                      无效的时间                                      |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道不无法处理传入的交换，因为数据元素中的时间值不符合指定的 EDI 架构或 GS05 字段标头在 X12 中的时间值的数据类型交换不符合服务架构 (baseartifacts.dll 中的 X12ServiceSchema)。 对于 X12，服务架构在 GS05 字段 X12_TM 数据类型和长度的四个和 8 个字符之间定义的时间。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保时间数据元素中的值符合 EDI 架构或时间值的 X12 交换符合服务架构在 GS05 标头中指定的数据类型，然后重新发送交换。