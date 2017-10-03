---
title: "无效的控件标准标识符 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d2b5a54-7f29-49c9-8bcf-a5b4b6d07ad3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94975e63d5781200ee1bfd9d14896c1e5fe722a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-control-standard-identifier"></a>控制标准标识符无效
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|X12Ta1InvalidControlStandardIdentifierDescription|  
|消息正文|控制标准标识符无效|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的交换，因为交换中交换控制标准标识符的值（字段 ISA11）与架构指定的枚举中的条目不匹配。 在 BaseArtifacts.dll 中，架构为 X12ServiceSchema 或 EdifactServiceSchema。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保交换中使用的交换控制标准标识符与 ISA11 字段的枚举中的条目相匹配，然后重新发送交换。