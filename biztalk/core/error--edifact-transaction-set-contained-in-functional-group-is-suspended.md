---
title: 在解析过程中遇到错误。 出现以下错误正在挂起 Edifact 事务集包含在功能组 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 986a7220-d35a-4047-8996-7d44c7d2b823
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70428ae8f430ea5ccb9ff13e068716cb35555f69
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239941"
---
# <a name="error-encountered-during-parsing-the-edifact-transaction-set-contained-in-functional-group-is-being-suspended-with-following-errors"></a>在解析过程中遇到错误。 功能组中包含的 EDIFACT 事务集由于以下错误被挂起
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|EfactTransactionSetReceiveError|  
|消息正文|在解析过程中遇到错误。 Id 为"{0}"中 id 为 {1} 功能组包含设置 Edifact 事务 id 为 {2} 发件人 id {3} 使用的交换中接收方 id \ {4 \ 正在挂起出现以下错误：|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 EDI 接收管道无法分析传入的 EDIFACT 交换（该交换具有一个组），因为通过标识的事务集指明了错误。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请使用错误消息中的信息来标识事务集中的错误，然后在文档中确定问题解决方案。