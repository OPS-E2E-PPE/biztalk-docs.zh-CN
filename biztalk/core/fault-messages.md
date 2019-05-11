---
title: 错误消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- error messages
- ports, error messages
- Catch Exception block [Orchestration Designer], error messages
- error messages, receiving
- messages, errors
- error messages, sending
ms.assetid: 33d62260-b5e0-4d14-b2d2-996733d588e7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fe3ab052612166b55fb966507a4a4c95b1b8f81
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388081"
---
# <a name="fault-messages"></a><span data-ttu-id="af9f7-102">错误消息</span><span class="sxs-lookup"><span data-stu-id="af9f7-102">Fault Messages</span></span>
<span data-ttu-id="af9f7-103">请求-响应端口可以具有与其相关联的错误消息，因此，如果出现问题后发送的请求，响应服务可以将错误发送给请求者，代替响应。</span><span class="sxs-lookup"><span data-stu-id="af9f7-103">Request-response ports can have fault messages associated with them, so that if something goes wrong after a request is sent, the responding service can communicate the error to the requester, in lieu of the response.</span></span>  
  
 <span data-ttu-id="af9f7-104">每个操作的请求-响应端口可以处理任意数量的不同错误。</span><span class="sxs-lookup"><span data-stu-id="af9f7-104">Each operation of a request-response port can handle an arbitrary number of different faults.</span></span> <span data-ttu-id="af9f7-105">错误消息可具有多种消息类型，但消息类型必须是唯一的操作，并不能使用该端口操作中的响应的类型。</span><span class="sxs-lookup"><span data-stu-id="af9f7-105">A fault message can have any message type, but the message type must be unique for the operation, and it must not be the type used by the response in that port operation.</span></span>  
  
## <a name="receiving-fault-messages"></a><span data-ttu-id="af9f7-106">接收错误消息</span><span class="sxs-lookup"><span data-stu-id="af9f7-106">Receiving fault messages</span></span>  
 <span data-ttu-id="af9f7-107">如果端口操作发送请求，然后接收响应，可用于接收一个或多个不同的故障消息类型。</span><span class="sxs-lookup"><span data-stu-id="af9f7-107">If your port operation sends a request, then receives a response, you can use it to receive one or more different fault message types.</span></span>  
  
 <span data-ttu-id="af9f7-108">你可以配置**捕获异常**块来处理传入的错误消息，通过从作为其异常对象类型的请求-响应端口操作中选择相应的错误。</span><span class="sxs-lookup"><span data-stu-id="af9f7-108">You can configure a **Catch Exception** block to handle an incoming fault message by selecting the appropriate fault from the request-response port operation as its Exception Object Type.</span></span>  
  
## <a name="sending-fault-messages"></a><span data-ttu-id="af9f7-109">发送错误消息</span><span class="sxs-lookup"><span data-stu-id="af9f7-109">Sending fault messages</span></span>  
 <span data-ttu-id="af9f7-110">如果端口操作接收响应，然后发送请求，可用于将一个或多个不同的故障消息类型发送。</span><span class="sxs-lookup"><span data-stu-id="af9f7-110">If your port operation receives a response, then sends a request, you can use it to send one or more different fault message types.</span></span>  
  
 <span data-ttu-id="af9f7-111">如果例如您的业务流程遇到错误情况并引发异常，您可以在发送错误消息**捕获异常**块处理异常。</span><span class="sxs-lookup"><span data-stu-id="af9f7-111">If for example your orchestration encounters an error condition and throws an exception, you can send a fault message from within the **Catch Exception** block that handles the exception.</span></span> <span data-ttu-id="af9f7-112">构造相应类型的错误消息来传达给参与的服务，这种情况，并将在端口操作中使用该相应错误的发送形状上指定该错误消息。</span><span class="sxs-lookup"><span data-stu-id="af9f7-112">You construct a fault message of an appropriate type to convey the situation to the participating service, and specify that fault message on a Send shape that will use the corresponding fault in the port operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af9f7-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="af9f7-113">See Also</span></span>  
 [<span data-ttu-id="af9f7-114">异常</span><span class="sxs-lookup"><span data-stu-id="af9f7-114">Exceptions</span></span>](../core/exceptions.md)