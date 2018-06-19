---
title: 订阅以及提取消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4e7fbc17-44d6-4cc5-a266-b54256e7b453
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22d5a7f6065e8040e390947d44510bb7414e8e10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294717"
---
# <a name="subscribing-to-and-extracting-messages"></a><span data-ttu-id="524dc-102">订阅以及提取消息</span><span class="sxs-lookup"><span data-stu-id="524dc-102">Subscribing to and Extracting Messages</span></span>
<span data-ttu-id="524dc-103">业务流程可以包含代码以订阅并从 ESB 错误消息中提取消息。</span><span class="sxs-lookup"><span data-stu-id="524dc-103">Orchestration can contain code to subscribe to and extract messages from an ESB fault message.</span></span> <span data-ttu-id="524dc-104">例如，下面的代码使用**GetMessage**和**GetException**方法提取两个强类型化消息和**System.Exception**从 ESB 对象错误消息。</span><span class="sxs-lookup"><span data-stu-id="524dc-104">For example, the following code uses the **GetMessage** and **GetException** methods to extract two strongly typed messages and the **System.Exception** object from an ESB fault message.</span></span>  
  
```csharp  
// Retrieve two messages from the fault message.  
requestMsg = Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.GetMessage(  
                                    faultMsg, "ApprovedRequest");  
deniedMsg = Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.GetMessage(  
                                    faultMsg, "DeniedRequest");  
  
// Retrieve the System.Exception object.  
newExc = Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.GetException(  
                                    faultMsg);  
```  
  
 <span data-ttu-id="524dc-105">若要提取类型的消息，下面的代码使用**GetMessages**方法以提取所有消息，然后循环访问它们。</span><span class="sxs-lookup"><span data-stu-id="524dc-105">To extract type-less messages, the following code uses the **GetMessages** method to extract all the messages and then iterate through them.</span></span>  
  
```csharp  
Microsoft.Practices.ESB.ExceptionHandling.MessageCollection msgs;  
msgs = Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.GetMessages(faultMsg);  
System.Xml.XmlDocument tmpMsg;  
while (msgs.MoveNext())  
{  
  tmpMsg = msgs.Current;  
}  
```