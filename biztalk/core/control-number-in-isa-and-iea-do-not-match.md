---
title: "在 ISA 和 IEA 控制编号不匹配 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6f9091ea-460b-464b-acd5-8dc0488b61e5
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd2f86d767b6065a6aeaa02f887dc8b6bd056fbb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="control-number-in-isa-and-iea-do-not-match"></a>ISA 和 IEA 中的控件编号不匹配
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|AS2 引擎|  
|符号名称|-|  
|消息正文|ISA 和 IEA 中的控件编号不匹配|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 AS2 接收管道无法处理传入的交换，因为交换的 ISA13 和 IEA02 字段中包含的交换控制编号具有不同的值。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保交换的 ISA13 和 IEA02 字段中包含的交换控制编号具有相同的值，然后重新发送交换。