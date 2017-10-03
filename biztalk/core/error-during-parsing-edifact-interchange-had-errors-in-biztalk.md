---
title: "在解析过程中遇到错误。 Edifact 交换了以下错误 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2fa8f9d5-5b7c-47c9-96d3-77be280b78e9
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4585966de7ecb410f8f46fa675fa4eae0c6715a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-during-parsing-the-edifact-interchange-had-the-following-errors"></a>在解析过程中遇到错误。 EDIFACT 交换发生了以下错误
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|EfactInterchangeReceiveError|  
|消息正文|在解析过程中遇到错误。 Id 为"{0}"，发件人 id {1} Edifact 交换，接收方 id {2} 具有以下错误：|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明由于在交换中指出的错误，在分析传入的 EDIFACT 交换时 EDI 接收管道遇到错误。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请使用错误消息中的信息来标识交换中的错误，然后在产品帮助中确定问题解决方案。