---
title: "根据指定的分隔符集，就可以生成没有有效的时间值 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e7e22958-e1fa-474d-85a2-aa69e05b7228
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00b8b06922109ae5817c67b26f1a23977d1b607b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="based-on-the-specified-delimiter-set-no-valid-time-value-could-be-generated"></a>根据指定的分隔符集，就可以生成没有有效的时间值
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|-|  
|消息正文|基于指定的分隔符集，无法生成有效的时间值。 请使用其他分隔符集。|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息十表明 EDI 发送管道无法生成有效的时间值，因为传出交换的时间字段中使用的某个字符与分隔符相同。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请更改 EDI 发送管道使用的分隔符值以创建一个消息，以便没有分隔符与时间字段中使用的字符相同。 执行以下操作之一：  
  
-   若要使 X12 交换发送给解析后的参与方，请更改“作为交换接收方的参与方”的“ISA 段定义”页中的分隔符设置。  
  
-   若要使 X12 交换发送给尚未解析的参与方，请更改“ISA 段定义”全局属性页中的分隔符设置。  
  
-   若要使 EDIFACT 交换发送给解析后的参与方，请更改“作为交换接收方的参与方”的“UNA 段定义”页中的分隔符设置。  
  
-   若要使 EDIFACT 交换发送给尚未解析的参与方，请更改“UNA 段定义”全局属性页中的分隔符设置。