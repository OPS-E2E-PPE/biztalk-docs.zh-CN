---
title: 基于指定的分隔符集，就无法生成有效的时间值 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7e22958-e1fa-474d-85a2-aa69e05b7228
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9a1dfb93db66dc6bb339df34359e21e328066ff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979350"
---
# <a name="based-on-the-specified-delimiter-set-no-valid-time-value-could-be-generated"></a>基于指定的分隔符集，就无法生成有效的时间值
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                 |
|-----------------|-----------------------------------------------------------------------------------------------------------------|
|  产品名称   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                |
| 产品版本 |                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                            |
|    事件 ID     |                                                        -                                                        |
|  事件源   |             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI              |
|    组件    |                                                   EDI 引擎                                                    |
|  符号名称  |                                                        -                                                        |
|  消息正文   | 基于指定的分隔符集，无法生成有效的时间值。 请使用其他分隔符集。 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息十表明 EDI 发送管道无法生成有效的时间值，因为传出交换的时间字段中使用的某个字符与分隔符相同。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请更改 EDI 发送管道使用的分隔符值以创建一个消息，以便没有分隔符与时间字段中使用的字符相同。 执行以下操作之一：  
  
-   若要使 X12 交换发送给解析后的参与方，请更改“作为交换接收方的参与方”的“ISA 段定义”页中的分隔符设置。  
  
-   若要使 X12 交换发送给尚未解析的参与方，请更改“ISA 段定义”全局属性页中的分隔符设置。  
  
-   若要使 EDIFACT 交换发送给解析后的参与方，请更改“作为交换接收方的参与方”的“UNA 段定义”页中的分隔符设置。  
  
-   若要使 EDIFACT 交换发送给尚未解析的参与方，请更改“UNA 段定义”全局属性页中的分隔符设置。