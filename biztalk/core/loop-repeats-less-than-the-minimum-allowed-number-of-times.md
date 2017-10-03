---
title: "小于允许的最小次数循环重复 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0be21d1d-86da-456b-83e6-c91f1dc9fb48
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00d9b38712d8b8336daa9357bd20eb34148691b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="loop-repeats-less-than-the-minimum-allowed-number-of-times"></a>循环重复次数小于允许的最小次数
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|X12SeLoopRepeatsLessTimesDescription|  
|消息正文|循环重复次数小于允许的最小次数|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的交换，因为该交换包含一个重复次数小于消息架构所需最小次数的循环。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保交换中的循环重复次数至少为消息架构中为循环指定的 minOccurs 属性中的次数，然后重新发送交换。