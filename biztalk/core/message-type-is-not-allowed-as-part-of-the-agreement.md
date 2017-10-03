---
title: "消息类型不允许作为协议的一部分 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 829f8230-33b8-4b5f-a56a-d0c1d3a17271
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 979aa43d23d2fca95c244e10cb9d4768d76cf3db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-type-is-not-allowed-as-part-of-the-agreement"></a>不允许将消息类型作为协议的一部分
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|TransactionSetNotAllowedDescription|  
|消息正文|消息类型 {0} 不允许作为协议的一部分。|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 能够处理文档，因为不允许该文档的消息类型是协议的一部分。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请查看允许是协议的一部分以及不允许是协议的一部分的消息类型。