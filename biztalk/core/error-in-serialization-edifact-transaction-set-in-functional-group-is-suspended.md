---
title: "在序列化期间遇到错误。 出现以下错误正在挂起 Edifact 事务集包含在功能组 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24b76086-334b-45fb-85f8-82e3335daac4
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb09bfecc2efc5e6878b7cc3d0149f2b56c07b68
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-during-serialization-the-edifact-transaction-set-contained-in-functional-group-is-being-suspended-with-following-errors"></a>在序列化期间遇到错误。 功能组中包含的 EDIFACT 事务集由于以下错误被挂起
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|EfactTransactionSetSendError|  
|消息正文|在序列化期间遇到错误。 Id 为"{0}"中 id 为 {1} 功能组包含设置 Edifact 事务 id 为 {2} 发件人 id {3} 使用的交换中接收方 id \ {4 \ 正在挂起出现以下错误：|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明由于通过标识的事务集指明的错误，在序列化传出的 EDIFACT 交换期间 EDI 发送管道遇到错误。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请使用错误消息中的信息来标识事务集中的错误，然后在产品帮助中确定问题解决方案。