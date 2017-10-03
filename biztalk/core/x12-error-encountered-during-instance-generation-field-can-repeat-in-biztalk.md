---
title: "字段可以重复实例生成-期间遇到错误，但尚未定义重复分隔符 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7a6783c-cb35-4ce8-9164-ec34ae500de1
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 366caec69fd84b91cf815a58e4975e8e5d7b4d06
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-during-instance-generation--field-can-repeat-but-repetition-delimiter-has-not-been-defined"></a>实例生成期间遇到错误 - 字段可以重复，但尚未定义重复分隔符
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|-|  
|消息正文|实例生成期间遇到错误。 字段 {0} 可以重复，但尚未定义重复分隔符。|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 无法生成 X12 消息实例，因为指出的字段可以重复（如架构所指定的那样），但尚未定义重复分隔符。 当架构中某个字段的 minOccurs 大于 1，但已定义了标准标识符而非重复分隔符时会发生此错误。 （对于 EDIFACT 交换，默认情况下定义了重复分隔符。）  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请在作为交换接收方的参与方的“ISA 段定义”页中为 ISA11 选择重复分隔符而非标准标识符，然后输入用作分隔符的字符。 如果尚未为交换解析任何参与方，则在全局属性的“ISA 段定义”页中定义重复分隔符（对于 X12 交换）。