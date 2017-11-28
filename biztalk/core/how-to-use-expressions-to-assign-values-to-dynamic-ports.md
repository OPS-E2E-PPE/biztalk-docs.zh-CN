---
title: "如何使用表达式将值分配到动态端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dynamic send ports, variables
- send ports, dynamic
ms.assetid: 6bdb937c-8702-43ff-914a-a02adc88658b
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59c2d11b5da44e94beee914704f46ac6b0346e85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="use-expressions-to-assign-values-to-dynamic-ports"></a><span data-ttu-id="8c378-102">使用表达式将值分配到动态端口</span><span class="sxs-lookup"><span data-stu-id="8c378-102">Use Expressions to Assign Values to Dynamic Ports</span></span>

## <a name="assign-values"></a><span data-ttu-id="8c378-103">将值分配</span><span class="sxs-lookup"><span data-stu-id="8c378-103">Assign values</span></span>
<span data-ttu-id="8c378-104">如果将发送端口标记为动态，则可向该端口分配包含要在表达式形状中使用的端口的 URI 的某个类型字符串变量的值。</span><span class="sxs-lookup"><span data-stu-id="8c378-104">If a send port is marked as dynamic, you can assign to it the value of some variable of type string that contains the URI of the port you want to use in the Expression shape.</span></span> <span data-ttu-id="8c378-105">例如：</span><span class="sxs-lookup"><span data-stu-id="8c378-105">For example,</span></span>  
  
```  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="mailto:johnd@contoso.com";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)=@"file://C:\MyLocation\%SourceFileName%.xml";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)=@"msmq://.\private$\MyQueue";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="http://MyOrder.contoso.com";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="ftp://MyServer/MyDirectory/%MessageID%.xml";  
```  
  
 <span data-ttu-id="8c378-106">然后可以进一步为属性分配传出消息。</span><span class="sxs-lookup"><span data-stu-id="8c378-106">Then you can further assign the properties to the outgoing messages.</span></span> <span data-ttu-id="8c378-107">例如：</span><span class="sxs-lookup"><span data-stu-id="8c378-107">For example,</span></span>  
  
```  
MyOutgoingMessage(SMTP.Subject)="Purcahse Order Received";  
MyOutgoingMessage(FILE.ReceivedFileName)="MyFileName.xml";  
MyOutgoingMessage(FTP.UserName)="MyUserName";  
MyOutgoingMessage(FTP.Password)="MyPassword";  
MyOutgoingMessage((MSMQ.Transactional)=true;  
```  
  
## <a name="see-also"></a><span data-ttu-id="8c378-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c378-108">See Also</span></span>  
[<span data-ttu-id="8c378-109">配置文件适配器时的限制</span><span class="sxs-lookup"><span data-stu-id="8c378-109">Restrictions when configuring the File adapter</span></span>](restrictions-when-configuring-the-file-adapter.md)