---
title: 写入 AS2 上下文属性以进行出站参与方解析 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 808d63d9-076d-4eed-8420-aee12b130fee
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 603d4ce029f3518f262274767da2a2da3e819eb7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262054"
---
# <a name="writing-as2-context-properties-for-outbound-party-resolution"></a><span data-ttu-id="961d8-102">写入 AS2 上下文属性以进行出站参与方解析</span><span class="sxs-lookup"><span data-stu-id="961d8-102">Writing AS2 Context Properties for Outbound Party Resolution</span></span>
<span data-ttu-id="961d8-103">可以使用 AS2To 上下文属性或中的 AS2To 属性执行协议解析出站 AS2 消息的`Http.UserHttpHeaders`上下文属性。</span><span class="sxs-lookup"><span data-stu-id="961d8-103">Agreement resolution of outbound AS2 message can be performed using the AS2To context property or the AS2To property in the `Http.UserHttpHeaders` context property.</span></span> <span data-ttu-id="961d8-104">但是，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不会将 AS2To 属性写入收到的 AS2 消息的上下文。</span><span class="sxs-lookup"><span data-stu-id="961d8-104">However, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] does not write the AS2To property to the context upon receiving an AS2 message.</span></span> <span data-ttu-id="961d8-105">如果你想要对 AS2To 或 UserHttpHeaders 上下文属性执行协议解析，您必须编写自定义业务流程或自定义管道组件来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="961d8-105">If you want to perform agreement resolution on the AS2To or UserHttpHeaders context property, you have to write a custom orchestration or a custom pipeline component to do so.</span></span> <span data-ttu-id="961d8-106">仅当发送端口未链接到协议，这是必需的。</span><span class="sxs-lookup"><span data-stu-id="961d8-106">This is required only if the send port is not linked to the agreement.</span></span>  
  
 <span data-ttu-id="961d8-107">可以在自定义业务流程中，追加 AS2-到开头的现有`Http.UserHttpHeaders`上下文属性使用以下代码：</span><span class="sxs-lookup"><span data-stu-id="961d8-107">In a custom orchestration, you can append AS2-To to the beginning of the existing `Http.UserHttpHeaders` context property using the following code:</span></span>  
  
```  
Message_1(Http.UserHttpHeaders) = “AS2-To: MyPartner\r\n” + Message_1(Http.UserHttpHeaders);  
```  
  
 <span data-ttu-id="961d8-108">可以在自定义管道组件中，追加 AS2-到开头的现有`Http.UserHttpHeaders`使用下面的代码的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="961d8-108">In a custom pipeline component, you can append AS2-To to the beginning of the existing `Http.UserHttpHeaders` context property using the following code.</span></span> <span data-ttu-id="961d8-109">您需要追加 AS2-到`Http.UserHttpHeaders`之前在 As2Encoder 组件处理消息的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="961d8-109">You need to append AS2-To to `Http.UserHttpHeaders` context property before the message is processed by the As2Encoder component.</span></span>  
  
```  
string strName="UserHttpHeaders";  
string strValue = "AS2-To: MyPartner\r\n" + (string)baseMessage.Context.Read(strName, "http://schemas.microsoft.com/BizTalk/2003/http-properties");  
baseMessage.Context.Write(strName, "http://schemas.microsoft.com/BizTalk/2003/http-properties", strValue);  
```  
  
 <span data-ttu-id="961d8-110">有关详细信息将提升`EDIIntAS.AS2To`属性或`BTS.UseHttpHeaders`属性设置为上下文，请参阅中的"升级 AS2 标头上下文属性"[通过 FILE 发送端口发送 AS2 消息](../core/sending-an-as2-message-over-a-file-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="961d8-110">For more information on promoting the `EDIIntAS.AS2To` property or the `BTS.UseHttpHeaders` property to the context, see "Promoting AS2 Header Context Properties" in the [Sending an AS2 Message over a FILE Send Port](../core/sending-an-as2-message-over-a-file-send-port.md).</span></span>  
  
 <span data-ttu-id="961d8-111">有关可以添加到自定义管道组件，将从 HTTP 标头的代码。UserHttpHeaders 上下文属性到消息，请参阅[通过 FILE 发送端口发送 AS2 消息](../core/sending-an-as2-message-over-a-file-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="961d8-111">For code that you can add to a custom pipeline component to write the headers from the HTTP.UserHttpHeaders context property into the message, see [Sending an AS2 Message over a FILE Send Port](../core/sending-an-as2-message-over-a-file-send-port.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="961d8-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="961d8-112">See Also</span></span>  
 [<span data-ttu-id="961d8-113">开发和配置 BizTalk Server AS2 解决方案</span><span class="sxs-lookup"><span data-stu-id="961d8-113">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)