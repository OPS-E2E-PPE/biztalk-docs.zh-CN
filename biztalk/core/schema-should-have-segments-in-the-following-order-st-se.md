---
title: "架构应该让段处于以下顺序 ST ....SE |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f4d1c6a-7d48-413a-9ef5-a0c49773dc16
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2563247dc6fc4c092fe2867c6b4d03239c4be7e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="schema-should-have-segments-in-the-following-order-st--se"></a>架构应该让段处于以下顺序 ST ....SE
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|SchemaCode116ETransactionSetSchemaStSeOutOfOrder|  
|消息正文|架构应该让段处于以下顺序 ST ....SE|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明自定义文档架构无效，因为标头和尾部未处于正确的顺序。 BizTalk Server 在部署架构时执行此验证。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请更改自定义的文档架构以便标头和尾部处于正确的顺序，然后重新部署架构。