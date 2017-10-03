---
title: "配置错误。 上一种方法的 HTTP 请求的同步 MDN 接收端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f140c7a4-46bf-4557-9679-cdaf2fbe66f4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa49120ecbdbd0a00de1bbd6cd552f56cb626ddd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuration-error-synchronous-mdn-requested-on-a-one-way-http-receive-port"></a>配置错误。 在单向 HTTP 接收端口上请求了同步 MDN
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|-|  
|消息正文|配置错误。 在单向 HTTP 发送端口上请求了同步 MDN。|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明在接收 AS2 消息后 BizTalk Server 无法返回同步 MDN，因为处理传入的 AS2 消息的 HTTP 接收端口是单向端口。 双向请求-响应接收端口需要响应传入 AS2 消息中返回同步的 MDN。 在这种情况下，必须同步返回 MDN，因为 AS2 消息包含 Disposition-Notification-To 标头，或者在作为 AS2 消息发送方的参与方的配置中，选中了属性“替代入站消息属性”，选中了“生成 MDN”属性，并且清除了“异步传输 MDN”属性。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请将接收 AS2 消息的接收端口改为请求响应接收端口，而不是单向接收端口。 将请求响应接收位置的发送管道设置为 AS2EdiSend（对于 EDI 交换）或 AS2Send（对于非 EDI 交换）。