---
title: 组件不能重复，因为它具有无效的重复计数 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 040d7ea4-60a9-495f-91d7-b5b868957e2d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d535d72b5f265f07e6ae3fb468ed56efdc7975b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231677"
---
# <a name="component-cannot-repeat-because-it-has-an-invalid-repetition-count"></a>组件不能重复，因为它的重复计数无效
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|SchemaCode118EInvalidRepetition|  
|消息正文|组件不能重复，它具有无效的重复计数 {0}|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的交换或者发送管道无法处理传出的交换，因为交换中的元素组件、元素、段或循环重复，而架构是不允许重复的。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保根据架构的需要，交换中的元素组件、元素、段或循环不重复，然后重新发送消息。