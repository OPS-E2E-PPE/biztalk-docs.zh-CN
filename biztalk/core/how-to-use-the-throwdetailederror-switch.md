---
title: "如何使用 ThrowDetailedError 交换机 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web services, security
- Web services, debugging
ms.assetid: 8a8af3c0-a9a2-42fe-b0be-a5a106403747
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 194306da3b021e7460b88a3d8e76801a2eeaebba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-the-throwdetailederror-switch"></a>如何使用 ThrowDetailedError 开关
如果发生错误，Web 客户端接收泛型**SoapException**。  
  
 若要调试已发布的 Web Services，您可以向 Web.config 文件添加一个开关来控制由已发布 Web Services 返回的异常详细信息的级别。  
  
 Web.config 文件包含应用程序设置交换机， **ThrowDetailedError**。 **False**是默认设置**ThrowDetailedError**。 如果你将设置更改为**True**，服务器代理将内部异常信息返回给使你能够调试已发布的 Web 服务的 Web 客户端。  
  
 下面的 XML 代码演示**ThrowDetailedError**下 Web.config 文件中出现的交换机\<appSettings > 节点：  
  
```  
<appSettings>  
  <add key="ThrowDetailedError" value="False" />  
<appSettings/>  
```  
  
> [!IMPORTANT]
>  默认情况下 BizTalk Server 不会将内部异常信息返回至 Web 客户端，因为该信息可能包含诸如应用程序调用堆栈之类的敏感信息。 调试后，应设置**ThrowDetailedError**将设置为**False**。  
  
## <a name="see-also"></a>另请参阅  
 [调试已发布的 Web 服务](../core/debugging-published-web-services.md)