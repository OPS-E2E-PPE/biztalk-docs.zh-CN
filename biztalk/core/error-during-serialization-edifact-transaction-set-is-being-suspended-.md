---
title: "Edifact 事务集包含在交换错误 |Microsoft 文档"
description: "在序列化期间遇到错误。 正在挂起 Edifact 事务集包含 （没有组） 的交换中出现以下错误"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a0a33ac-d83e-495c-ba75-88c15ad7cfcd
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67f089e49941ffec7d3392b3bc35edcbc4eefec5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="edifact-transaction-set-is-suspended-error-and-details"></a>Edifact 事务集是挂起的错误和详细信息

`Error encountered during serialization. The Edifact transaction set contained in interchange (without group) is being suspended with following errors`

## <a name="details"></a>详细信息  
  
|||  
|---|---|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|EfactTransactionSetSendErrorWithoutGroup|  
|消息正文|在序列化期间遇到错误。 Id 为"{0}"中 （不带组） 的交换 id {1}，发件人 id {2} 的包含设置 Edifact 事务正在与挂起接收方 id {3} 以下错误：|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明由于通过标识的事务集指明的错误，在序列化传出的 EDIFACT 交换期间 EDI 发送管道遇到错误。 请注意，该事务集不在交换的组中。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，需要使用错误消息中的信息确定在事务集中的错误，然后确定问题解决方法。