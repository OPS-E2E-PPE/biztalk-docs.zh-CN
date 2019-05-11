---
title: 如何从业务流程引发 SOAP 异常发布为 Web 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- errors, SOAP exceptions
- orchestrations, SOAP errors
- Web services, orchestrations
ms.assetid: e1c7cd74-d1c8-4b9d-a418-4601b1f040d7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12c849d592a7cdce5968678f524ec15562830eba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333795"
---
# <a name="how-to-throw-soap-exceptions-from-orchestrations-published-as-a-web-service"></a><span data-ttu-id="0b14b-102">如何从发布为 Web 服务的业务流程引发 SOAP 异常</span><span class="sxs-lookup"><span data-stu-id="0b14b-102">How to Throw SOAP Exceptions from Orchestrations Published as a Web Service</span></span>
<span data-ttu-id="0b14b-103">你可以从业务流程发布为 Web 服务返回 SOAP 异常。</span><span class="sxs-lookup"><span data-stu-id="0b14b-103">You can return a SOAP exception from an orchestration that you have published as a Web service.</span></span> <span data-ttu-id="0b14b-104">将错误消息添加到 SOAP 端口和发送错误消息而不是响应。</span><span class="sxs-lookup"><span data-stu-id="0b14b-104">You add a fault message to your SOAP port and send the fault message instead of the response.</span></span>  
  
### <a name="to-throw-a-soap-exception-from-an-orchestration-published-as-a-web-service"></a><span data-ttu-id="0b14b-105">若要引发 SOAP 异常从业务流程发布为 Web 服务</span><span class="sxs-lookup"><span data-stu-id="0b14b-105">To throw a SOAP exception from an orchestration published as a Web service</span></span>  
  
1. <span data-ttu-id="0b14b-106">将错误消息添加到 SOAP 端口类型。</span><span class="sxs-lookup"><span data-stu-id="0b14b-106">Add a fault message to the SOAP port type.</span></span> <span data-ttu-id="0b14b-107">错误消息的消息类型可以是任何符合的 XML 架构 (XSD) 架构或简单类型。</span><span class="sxs-lookup"><span data-stu-id="0b14b-107">The message type for the fault message can be any XML Schema (XSD) compliant schema or simple type.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="0b14b-108">返回一个字符串作为**SoapException**错误信息，可以使用简单类型字符串，作为错误消息类型。</span><span class="sxs-lookup"><span data-stu-id="0b14b-108">To return a string as a **SoapException** with error information, you can use the simple type string as the fault message type.</span></span>  
  
2. <span data-ttu-id="0b14b-109">在业务流程中创建的错误消息。</span><span class="sxs-lookup"><span data-stu-id="0b14b-109">In your orchestration, create the fault message.</span></span>  
  
3. <span data-ttu-id="0b14b-110">使用**发送**形状链接到对应于错误消息的 SOAP 端口中的错误操作。</span><span class="sxs-lookup"><span data-stu-id="0b14b-110">Use the **Send** shape to link to the fault operation in the SOAP port that corresponds to the fault message.</span></span> <span data-ttu-id="0b14b-111">SOAP 异常包装返回的错误消息。</span><span class="sxs-lookup"><span data-stu-id="0b14b-111">A SOAP exception wraps the returned fault message.</span></span>  
  
   <span data-ttu-id="0b14b-112">如果您的业务流程不返回错误，使用不同**发送**用于将使用正常响应操作的标准 SOAP 响应消息的发送形状。</span><span class="sxs-lookup"><span data-stu-id="0b14b-112">If your orchestration does not return an error, use a different **Send** shape to send the standard SOAP response message using the usual response operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b14b-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b14b-113">See Also</span></span>  
 <span data-ttu-id="0b14b-114">[错误消息](../core/fault-messages.md) </span><span class="sxs-lookup"><span data-stu-id="0b14b-114">[Fault Messages](../core/fault-messages.md) </span></span>  
 [<span data-ttu-id="0b14b-115">将业务流程发布为 Web 服务</span><span class="sxs-lookup"><span data-stu-id="0b14b-115">Publishing an Orchestration as a Web Service</span></span>](../core/publishing-an-orchestration-as-a-web-service.md)