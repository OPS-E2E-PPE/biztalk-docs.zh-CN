---
title: 处理通知选项无效 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1b807a8-eec9-45a5-83cc-075c91b4bc9e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72221c98dfcac42f735f63a1ce01a7c26bc45387
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239045"
---
# <a name="disposition-notification-option-is-invalid"></a>Disposition-Notification-Option 无效
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|AS2 引擎|  
|符号名称|-|  
|消息正文|处理通知选项值:"{0}"无效。 {1}|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 AS2 接收管道无法生成 MDN，因为 Disposition-Notification-Option 标头无效。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保 AS2 消息中的 Disposition-Notification-Option 标头符合 RFC 4130“MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)”（针对使用 HTTP 进行基于 MIME 的安全对等业务数据交换的 Applicability Statement 2 (AS2)）中描述的语法。 确保 Signed-Receipt-Protocol 标头设置为“可选”或“pcks7-signature”，并且确保 Signed-Receipt-MICAlg 标头设置为“可选”、“MD5”或“SHA1”。 （这两个这些标头包括在处置通知选项标头。）