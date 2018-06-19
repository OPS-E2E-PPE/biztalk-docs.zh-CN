---
title: 通过最大时间将会发生循环 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0ac9f5d3-04ec-4c40-8a1f-17ef0b143cda
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 827ab88a2676cd052ee1ea3ba3a4bd7bd80f1912
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261877"
---
# <a name="loop-occurs-over-maximum-times"></a>循环次数超过最大次数
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|X12LoopOccursOverMaximumTimesDescription|  
|消息正文|循环通信发生在最大次数|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的交换，因为该交换包含一个重复次数高于消息架构所需最多次数的循环。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保交换中的循环重复次数不超过消息架构中为循环指定的 maxOccurs 属性中的次数，然后重新发送交换。