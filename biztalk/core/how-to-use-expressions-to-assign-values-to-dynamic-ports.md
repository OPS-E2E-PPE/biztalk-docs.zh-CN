---
title: 如何使用表达式向动态端口赋值 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- dynamic send ports, variables
- send ports, dynamic
ms.assetid: 6bdb937c-8702-43ff-914a-a02adc88658b
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88e049772fcdcb9c5b15f9647d126c74faacf407
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333475"
---
# <a name="use-expressions-to-assign-values-to-dynamic-ports"></a>使用表达式向动态端口赋值

## <a name="assign-values"></a>将值分配
如果发送端口标记为动态，则可以向其分配包含你想要在表达式形状中使用的端口的 URI 的字符串类型的某些变量的值。 例如，  
  
```  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="mailto:johnd@contoso.com";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)=@"file://C:\MyLocation\%SourceFileName%.xml";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)=@"msmq://.\private$\MyQueue";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="http://MyOrder.contoso.com";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="ftp://MyServer/MyDirectory/%MessageID%.xml";  
```  
  
 然后可以进一步将属性分配给传出消息。 例如，  
  
```  
MyOutgoingMessage(SMTP.Subject)="Purcahse Order Received";  
MyOutgoingMessage(FILE.ReceivedFileName)="MyFileName.xml";  
MyOutgoingMessage(FTP.UserName)="MyUserName";  
MyOutgoingMessage(FTP.Password)="MyPassword";  
MyOutgoingMessage((MSMQ.Transactional)=true;  
```  
  
## <a name="see-also"></a>请参阅  
[配置文件适配器时的限制](restrictions-when-configuring-the-file-adapter.md)