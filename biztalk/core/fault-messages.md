---
title: "错误消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- error messages
- ports, error messages
- Catch Exception block [Orchestration Designer], error messages
- error messages, receiving
- messages, errors
- error messages, sending
ms.assetid: 33d62260-b5e0-4d14-b2d2-996733d588e7
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4127fd5718ee910cb298436c0d0f7058ccba55b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="fault-messages"></a><span data-ttu-id="14be5-102">错误消息</span><span class="sxs-lookup"><span data-stu-id="14be5-102">Fault Messages</span></span>
<span data-ttu-id="14be5-103">请求-响应端口可以关联错误消息，这样，如果在发送请求后发生任何错误，相应的服务可以根据响应将错误发送给请求方。</span><span class="sxs-lookup"><span data-stu-id="14be5-103">Request-response ports can have fault messages associated with them, so that if something goes wrong after a request is sent, the responding service can communicate the error to the requester, in lieu of the response.</span></span>  
  
 <span data-ttu-id="14be5-104">请求-响应端口的每一操作都可以处理任意数量的不同错误。</span><span class="sxs-lookup"><span data-stu-id="14be5-104">Each operation of a request-response port can handle an arbitrary number of different faults.</span></span> <span data-ttu-id="14be5-105">错误消息可具有多种消息类型，不过消息类型对操作而言必须唯一，而且不能是该端口操作中响应所使用的类型。</span><span class="sxs-lookup"><span data-stu-id="14be5-105">A fault message can have any message type, but the message type must be unique for the operation, and it must not be the type used by the response in that port operation.</span></span>  
  
## <a name="receiving-fault-messages"></a><span data-ttu-id="14be5-106">接收错误消息</span><span class="sxs-lookup"><span data-stu-id="14be5-106">Receiving fault messages</span></span>  
 <span data-ttu-id="14be5-107">如果端口操作先发送请求，然后接收响应，则可以使用该操作接收一种或多种不同的错误消息。</span><span class="sxs-lookup"><span data-stu-id="14be5-107">If your port operation sends a request, then receives a response, you can use it to receive one or more different fault message types.</span></span>  
  
 <span data-ttu-id="14be5-108">你可以配置**捕获异常**块来通过从请求-响应端口操作作为其异常对象类型选择相应的错误处理传入的错误消息。</span><span class="sxs-lookup"><span data-stu-id="14be5-108">You can configure a **Catch Exception** block to handle an incoming fault message by selecting the appropriate fault from the request-response port operation as its Exception Object Type.</span></span>  
  
## <a name="sending-fault-messages"></a><span data-ttu-id="14be5-109">发送错误消息</span><span class="sxs-lookup"><span data-stu-id="14be5-109">Sending fault messages</span></span>  
 <span data-ttu-id="14be5-110">如果端口操作先接收响应，然后发送请求，则可以使用该操作来发送一种或多种不同的错误消息。</span><span class="sxs-lookup"><span data-stu-id="14be5-110">If your port operation receives a response, then sends a request, you can use it to send one or more different fault message types.</span></span>  
  
 <span data-ttu-id="14be5-111">如果例如您的业务流程遇到的错误条件，并且会引发异常，你可以在发送错误消息**捕获异常**处理异常的块。</span><span class="sxs-lookup"><span data-stu-id="14be5-111">If for example your orchestration encounters an error condition and throws an exception, you can send a fault message from within the **Catch Exception** block that handles the exception.</span></span> <span data-ttu-id="14be5-112">您需要构造相应类型的错误消息，将该情况传达给参与的服务，然后在要在端口操作中使用该相应错误的发送形状上指定该错误消息。</span><span class="sxs-lookup"><span data-stu-id="14be5-112">You construct a fault message of an appropriate type to convey the situation to the participating service, and specify that fault message on a Send shape that will use the corresponding fault in the port operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14be5-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="14be5-113">See Also</span></span>  
 [<span data-ttu-id="14be5-114">异常</span><span class="sxs-lookup"><span data-stu-id="14be5-114">Exceptions</span></span>](../core/exceptions.md)