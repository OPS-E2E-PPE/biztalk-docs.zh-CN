---
title: "在解析过程中遇到错误。 正在挂起 Edifact 事务集包含 （没有组） 的交换中出现以下错误 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 901fef68-4649-480a-997c-b061d7d069d6
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2dc5633917c708f457f11fc824997fa7eb6d4c59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-during-parsing-the-edifact-transaction-set-contained-in-interchange-without-group-is-being-suspended-with-following-errors"></a>在解析过程中遇到错误。 正在挂起 Edifact 事务集包含 （没有组） 的交换中出现以下错误
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|EfactTransactionSetReceiveErrorWithoutGroup|  
|消息正文|在解析过程中遇到错误。 Id 为"{0}"中 （不带组） 的交换 id {1}，发件人 id {2} 的包含设置 Edifact 事务正在与挂起接收方 id {3} 以下错误：|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明由于通过交换中标识的事务集指明的错误，在分析传入的 EDIFACT 交换（该交换没有组）时 EDI 接收管道遇到错误。 请注意，该事务集不在交换的组中。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请使用错误消息中的信息来标识事务集中的错误，然后在产品帮助中确定问题解决方案。