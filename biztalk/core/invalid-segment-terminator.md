---
title: "无效的段终止符 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 508dac21-4731-439d-bf4a-a50858f1ffa0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47d5a79af0616baed6d401b4df7b68f5f596ef07
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-segment-terminator"></a>段终止符无效
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|X12Ta1InvalidSegmentTerminatorDescription|  
|消息正文|段终止符无效|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的交换，因为交换中段终止符的值不限于 ASCII 字符集中的字符。 在 X12 中，段终止符被定义为 ISA 段中的最后一个字符。 在 EDIFACT 中，段终止符为 UNA6 字段。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保段终止符（X12 交换中 ISA 段的最后一个字符或者 EDIFACT 交换中的 UNA6 字段）仅限于 ASCII 字符集中的字符。 然后重新发送交换。