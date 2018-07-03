---
title: 基于指定的分隔符集，就无法找到有效的数字 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 08887f7d-8256-4de3-8db9-b890451521ff
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6fc117a9c9d08d664f397557ab08f9c6f2e7dc7c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989222"
---
# <a name="based-on-the-specified-delimiter-set-no-valid-digit-could-be-found"></a>基于指定的分隔符集，找不到有效的数字
## <a name="details"></a>详细信息  
  
|                 |                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------|
|  产品名称   |           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]           |
| 产品版本 |                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                       |
|    事件 ID     |                                                   -                                                    |
|  事件源   |         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI         |
|    组件    |                                               EDI 引擎                                               |
|  符号名称  |                                                   -                                                    |
|  消息正文   | 根据指定的分隔符集，无法找到有效的数字。 请使用其他分隔符集。 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明生成传出交换时 EDI 发送管道无法找到有效的数字，因为在传出交换的某个字段中使用的数字与某个分隔符相同。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请更改 EDI 发送管道用来创建消息的分隔符值，以便没有分隔符与传出交换的某个字段中使用的数字相同。 执行以下操作之一：  
  
-   若要使 X12 交换发送给解析后的参与方，请更改“作为交换接收方的参与方”的“ISA 段定义”页中的分隔符设置。  
  
-   若要使 X12 交换发送给尚未解析的参与方，请更改“ISA 段定义”全局属性页中的分隔符设置。  
  
-   若要使 EDIFACT 交换发送给解析后的参与方，请更改“作为交换接收方的参与方”的“UNA 段定义”页中的分隔符设置。  
  
-   若要使 EDIFACT 交换发送给尚未解析的参与方，请更改“UNA 段定义”全局属性页中的分隔符设置。