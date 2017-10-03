---
title: "为出站的参与方解析编写 AS2 上下文属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 808d63d9-076d-4eed-8420-aee12b130fee
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c89804c42554825e387d01ff592e3a628e8225b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="writing-as2-context-properties-for-outbound-party-resolution"></a><span data-ttu-id="e9934-102">写入 AS2 上下文属性以进行出站参与方解析</span><span class="sxs-lookup"><span data-stu-id="e9934-102">Writing AS2 Context Properties for Outbound Party Resolution</span></span>
<span data-ttu-id="e9934-103">可以使用 AS2To 上下文属性或 `Http.UserHttpHeaders` 上下文属性中的 AS2To 属性来执行出站 AS2 消息的协议解析。</span><span class="sxs-lookup"><span data-stu-id="e9934-103">Agreement resolution of outbound AS2 message can be performed using the AS2To context property or the AS2To property in the `Http.UserHttpHeaders` context property.</span></span> <span data-ttu-id="e9934-104">但是，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在收到 AS2 消息后不会将 AS2To 属性写入上下文。</span><span class="sxs-lookup"><span data-stu-id="e9934-104">However, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] does not write the AS2To property to the context upon receiving an AS2 message.</span></span> <span data-ttu-id="e9934-105">如果要对 AS2To 或 UserHttpHeaders 上下文属性执行协议解析，您必须写入一个自定义业务流程或自定义管道组件来执行此解析。</span><span class="sxs-lookup"><span data-stu-id="e9934-105">If you want to perform agreement resolution on the AS2To or UserHttpHeaders context property, you have to write a custom orchestration or a custom pipeline component to do so.</span></span> <span data-ttu-id="e9934-106">只有在发送端口未与此协议链接的情况下才需要进行此解析。</span><span class="sxs-lookup"><span data-stu-id="e9934-106">This is required only if the send port is not linked to the agreement.</span></span>  
  
 <span data-ttu-id="e9934-107">在自定义业务流程中，可以使用下面的代码将 AS2-To 附加到现有 `Http.UserHttpHeaders` 上下文属性的开头：</span><span class="sxs-lookup"><span data-stu-id="e9934-107">In a custom orchestration, you can append AS2-To to the beginning of the existing `Http.UserHttpHeaders` context property using the following code:</span></span>  
  
```  
Message_1(Http.UserHttpHeaders) = “AS2-To: MyPartner\r\n” + Message_1(Http.UserHttpHeaders);  
```  
  
 <span data-ttu-id="e9934-108">在自定义管道组件中，可以使用下面的代码将 AS2-To 附加到现有 `Http.UserHttpHeaders` 上下文属性的开头。</span><span class="sxs-lookup"><span data-stu-id="e9934-108">In a custom pipeline component, you can append AS2-To to the beginning of the existing `Http.UserHttpHeaders` context property using the following code.</span></span> <span data-ttu-id="e9934-109">您需要在 As2Encoder 组件处理消息前将 AS2-To 附加到 `Http.UserHttpHeaders` 上下文属性。</span><span class="sxs-lookup"><span data-stu-id="e9934-109">You need to append AS2-To to `Http.UserHttpHeaders` context property before the message is processed by the As2Encoder component.</span></span>  
  
```  
string strName="UserHttpHeaders";  
string strValue = "AS2-To: MyPartner\r\n" + (string)baseMessage.Context.Read(strName, "http://schemas.microsoft.com/BizTalk/2003/http-properties");  
baseMessage.Context.Write(strName, "http://schemas.microsoft.com/BizTalk/2003/http-properties", strValue);  
```  
  
 <span data-ttu-id="e9934-110">有关详细信息将提升`EDIIntAS.AS2To`属性或`BTS.UseHttpHeaders`属性为上下文，请参阅"提升 AS2 标头上下文属性"中[通过文件发送端口发送 AS2 消息](../core/sending-an-as2-message-over-a-file-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="e9934-110">For more information on promoting the `EDIIntAS.AS2To` property or the `BTS.UseHttpHeaders` property to the context, see "Promoting AS2 Header Context Properties" in the [Sending an AS2 Message over a FILE Send Port](../core/sending-an-as2-message-over-a-file-send-port.md).</span></span>  
  
 <span data-ttu-id="e9934-111">对于你可以将其添加到要写入从 HTTP 标头的自定义管道组件的代码。UserHttpHeaders 上下文属性为消息，请参阅[通过文件发送端口发送 AS2 消息](../core/sending-an-as2-message-over-a-file-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="e9934-111">For code that you can add to a custom pipeline component to write the headers from the HTTP.UserHttpHeaders context property into the message, see [Sending an AS2 Message over a FILE Send Port](../core/sending-an-as2-message-over-a-file-send-port.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9934-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e9934-112">See Also</span></span>  
 [<span data-ttu-id="e9934-113">开发和配置 BizTalk Server AS2 解决方案</span><span class="sxs-lookup"><span data-stu-id="e9934-113">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)