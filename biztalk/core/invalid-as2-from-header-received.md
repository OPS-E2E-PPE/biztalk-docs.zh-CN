---
title: "无效的 AS2-从收到的标头 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d773e09-8526-4533-9066-8e743e65a688
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f20a74e60a6365c0c16e139e8b2caca1bc33646
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-as2-from-header-received"></a>收到的 AS2-From 头部无效
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|AS2 引擎|  
|符号名称|InvalidAS2FromNameHeaderReceivedError|  
|消息正文|收到的 AS2-From 头部无效。  值： {0}|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的交换，因为消息中 AS2-From 标头的值不符合 AS2 RFC 4130 中的规范。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保消息中 AS2-From 标头的值符合 AS2 RFC 4130 第 6.2 节中的规范，然后重新发送消息。