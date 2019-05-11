---
title: 订阅消息和提取消息 |Microsoft Docs
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
ms.openlocfilehash: 38a0df2f3c56681634f717f8e92bcf429002d208
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65268816"
---
# <a name="subscribing-to-and-extracting-messages"></a><span data-ttu-id="941b1-102">订阅消息和提取消息</span><span class="sxs-lookup"><span data-stu-id="941b1-102">Subscribing to and Extracting Messages</span></span>
<span data-ttu-id="941b1-103">业务流程可以包含代码以订阅并从到 ESB 的错误消息中提取消息。</span><span class="sxs-lookup"><span data-stu-id="941b1-103">Orchestration can contain code to subscribe to and extract messages from an ESB fault message.</span></span> <span data-ttu-id="941b1-104">例如，下面的代码使用**GetMessage**并**GetException**方法来提取两个强类型化消息并**System.Exception** ESB 中的对象错误消息。</span><span class="sxs-lookup"><span data-stu-id="941b1-104">For example, the following code uses the **GetMessage** and **GetException** methods to extract two strongly typed messages and the **System.Exception** object from an ESB fault message.</span></span>  
  
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
  
 <span data-ttu-id="941b1-105">若要提取无类型的消息，下面的代码，请使用**GetMessages**方法来提取所有消息，然后循环访问它们。</span><span class="sxs-lookup"><span data-stu-id="941b1-105">To extract type-less messages, the following code uses the **GetMessages** method to extract all the messages and then iterate through them.</span></span>  
  
```csharp  
Microsoft.Practices.ESB.ExceptionHandling.MessageCollection msgs;  
msgs = Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.GetMessages(faultMsg);  
System.Xml.XmlDocument tmpMsg;  
while (msgs.MoveNext())  
{  
  tmpMsg = msgs.Current;  
}  
```