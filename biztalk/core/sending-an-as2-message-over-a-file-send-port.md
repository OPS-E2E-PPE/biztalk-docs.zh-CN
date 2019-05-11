---
title: 通过 FILE 发送端口发送 AS2 消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8c5ce9ff-fd73-4d5f-9b16-387c1e520c3a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 184a6a1b6a0111dffaf9096e23e60945d8310ecf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399059"
---
# <a name="sending-an-as2-message-over-a-file-send-port"></a><span data-ttu-id="70f21-102">通过 FILE 发送端口发送 AS2 消息</span><span class="sxs-lookup"><span data-stu-id="70f21-102">Sending an AS2 Message over a FILE Send Port</span></span>
<span data-ttu-id="70f21-103">AS2 消息通常是通过 HTTP 适配器发送的。</span><span class="sxs-lookup"><span data-stu-id="70f21-103">AS2 messages are normally sent over an HTTP adapter.</span></span> <span data-ttu-id="70f21-104">然而，如果创建了自定义组件，则可以通过 FILE 适配器发送 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="70f21-104">You can, however, send AS2 messages over a FILE adapter if you create custom components.</span></span> <span data-ttu-id="70f21-105">本主题介绍了这种解决方案的工作原理并提供了该解决方案的示例代码。</span><span class="sxs-lookup"><span data-stu-id="70f21-105">This topic describes how such a solution would work and provides sample code for the solution.</span></span>  
  
 <span data-ttu-id="70f21-106">通过 HTTP 发送 AS2 消息时，发送管道中的 AS2 编码器会使用发送消息时所需的 HTTP（和 AS2）标头来填充 `HTTP.UserHttpHeaders` 上下文属性。</span><span class="sxs-lookup"><span data-stu-id="70f21-106">When AS2 messages are sent over HTTP, the AS2 Encoder in the send pipeline populates the `HTTP.UserHttpHeaders` context property with the HTTP (and AS2) headers required for sending the message.</span></span> <span data-ttu-id="70f21-107">它将从现有 `HTTP.UserHttpHeaders` 上下文属性、单独的上下文属性或协议属性（按该优先级顺序）中获取这些标头。</span><span class="sxs-lookup"><span data-stu-id="70f21-107">It takes these headers either from the existing `HTTP.UserHttpHeaders` context property, from separate context properties, or from agreement properties (in that order of precedence).</span></span> <span data-ttu-id="70f21-108">发送端口中的 HTTP 适配器会将标头写入消息，并通过 HTTP 发送该消息。</span><span class="sxs-lookup"><span data-stu-id="70f21-108">The HTTP adapter in the send port will write the headers to the message, and send the message over HTTP.</span></span>  
  
 <span data-ttu-id="70f21-109">如果发送端口中使用的是 FILE 适配器而非 HTTP 适配器，则 `HTTP.UserHttpHeaders` 上下文属性中的标头值将不会被写入该消息。</span><span class="sxs-lookup"><span data-stu-id="70f21-109">If you use a FILE adapter instead of an HTTP adapter in the send port, the header values in the `HTTP.UserHttpHeaders` context property will not be written to the message.</span></span> <span data-ttu-id="70f21-110">您必须创建一个自定义管道组件以将 `HTTP.UserHttpHeaders` 中的标头置于该消息之前。</span><span class="sxs-lookup"><span data-stu-id="70f21-110">You have to create a custom pipeline component to prepend the headers in `HTTP.UserHttpHeaders` to the message.</span></span> <span data-ttu-id="70f21-111">然后，可由 FILE 适配器将该消息放入文件夹中，该消息就成了一个包含必需的 HTTP 标头的 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="70f21-111">The message can then be dropped into a folder by the FILE adapter, and will be an AS2 message that includes the required HTTP headers.</span></span>  
  
 <span data-ttu-id="70f21-112">您还可能需要创建一个自定义组件，以确保所有 AS2 标头都包含在 `HTTP.UserHttpHeaders` 上下文属性中。</span><span class="sxs-lookup"><span data-stu-id="70f21-112">You may also need to create a custom component to ensure that all the AS2 headers are included in the `HTTP.UserHttpHeaders` context property.</span></span> <span data-ttu-id="70f21-113">您可以在 AS2Encoder 之前创建一个自定义业务流程或一个自定义管道组件，以设置 AS2 编码器生成 `HTTP.UserHttpHeaders` 时所使用的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="70f21-113">You can create either a custom orchestration, or a custom pipeline component before the AS2Encoder, to set the context properties that the AS2 Encoder uses to build `HTTP.UserHttpHeaders`.</span></span>  
  
## <a name="writing-headers-to-an-as2-message"></a><span data-ttu-id="70f21-114">将标头写入 AS2 消息</span><span class="sxs-lookup"><span data-stu-id="70f21-114">Writing Headers to an AS2 Message</span></span>  
 <span data-ttu-id="70f21-115">若要使用 FILE 适配器（而非 HTTP 适配器）生成 AS2 消息，请在自定义 AS2 发送管道中的 AS2 编码器之后添加一个自定义管道组件。</span><span class="sxs-lookup"><span data-stu-id="70f21-115">To generate an AS2 message using a FILE adapter, rather than an HTTP adapter, add a custom pipeline component after the AS2 Encoder in a custom AS2 send pipeline.</span></span> <span data-ttu-id="70f21-116">将代码包含在该自定义管道组件中，该自定义管道组件可将 `HTTP.UserHttpHeaders` 上下文属性中的标头写入该消息。</span><span class="sxs-lookup"><span data-stu-id="70f21-116">Include code in the custom pipeline component that writes the headers from the `HTTP.UserHttpHeaders` context property into the message.</span></span> <span data-ttu-id="70f21-117">以下为示例代码：</span><span class="sxs-lookup"><span data-stu-id="70f21-117">An example is the following sample code:</span></span>  
  
```  
public IBaseMessage Execute(IPipelineContext pContext, IBaseMessage pInMsg)  
        {  
            IPipelineContext pipelineContext = pContext;  
            IBaseMessage baseMessage = pInMsg;  
  
            //Prepend Headers  
            MemoryStream ms = new MemoryStream();  
            string strName = "UserHttpHeaders";  
            string strValue = (string)baseMessage.Context.Read(strName,  
              "http://schemas.microsoft.com/BizTalk/2003/  
              http-properties");  
  
            //Leave an empty line between the headers and the body  
            strValue += "\r\n";  
            ms.Write(Encoding.ASCII.GetBytes(strValue), 0,   
               Encoding.ASCII.GetByteCount(strValue));  
  
            //Append Body  
            Stream sr = baseMessage.BodyPart.Data;  
  
            //Read the body of the message and append it to the memory   
              stream containing the headers  
            int size = 1024;  
            byte[] buffer = new byte[size];  
            while (0 != (size = sr.Read(buffer, 0, buffer.Length)))  
            {  
                ms.Write(buffer, 0, size);  
            }  
  
            //Set the body of the message to the new memory stream  
            baseMessage.BodyPart.Data = ms;  
  
            //Rewind the stream  
            ms.Seek(0, SeekOrigin.Begin);  
  
            return baseMessage;  
        }  
```  
  
## <a name="promoting-as2-header-context-properties"></a><span data-ttu-id="70f21-118">升级 AS2 标头上下文属性</span><span class="sxs-lookup"><span data-stu-id="70f21-118">Promoting AS2 Header Context Properties</span></span>  
 <span data-ttu-id="70f21-119">您可以使用自定义业务流程或自定义管道组件将 AS2 标头属性升级到消息上下文。</span><span class="sxs-lookup"><span data-stu-id="70f21-119">You can promote AS2 header properties into the context of a message using either a custom orchestration or a custom pipeline component.</span></span>  
  
 <span data-ttu-id="70f21-120">若要使用自定义管道组件升级 AS2 标头属性，请在自定义 AS2 发送管道中的 AS2 编码器之前添加一个自定义管道组件。</span><span class="sxs-lookup"><span data-stu-id="70f21-120">To promote AS2 header properties using a custom pipeline component, add a custom pipeline component before the AS2 Encoder in a custom AS2 send pipeline.</span></span> <span data-ttu-id="70f21-121">您可以使用如上所示的示例代码中的代码将 `HTTP.UserHttpHeaders` 中的标头写入消息，不过您需将 Read 方法替换为 Promote 方法，并提供要升级的上下文属性的名称、值和命名空间。</span><span class="sxs-lookup"><span data-stu-id="70f21-121">You can use code from the sample code shown above for writing headers from `HTTP.UserHttpHeaders` into the message, with the exception that you would replace the Read method with a Promote method, providing the name, value, and namespace of the context property to be promoted.</span></span>  
  
 <span data-ttu-id="70f21-122">若要使用自定义业务流程升级 AS2 标头属性，请创建一个具有 FILE 接收端口、构造消息形状和 FILE 发送端口的业务流程。</span><span class="sxs-lookup"><span data-stu-id="70f21-122">To promote AS2 header properties using a custom orchestration, create an orchestration with a FILE receive port, a Construct Message shape, and a FILE send port.</span></span> <span data-ttu-id="70f21-123">向构造消息形状添加用于设置包含 AS2 标头的已升级属性的代码。</span><span class="sxs-lookup"><span data-stu-id="70f21-123">To the Construct Message shape, add code setting the promoted properties that contain the AS2 headers.</span></span> <span data-ttu-id="70f21-124">您必须在自定义业务流程中添加到 `Microsoft.BizTalk.HttpTransport.dll` 的引用。</span><span class="sxs-lookup"><span data-stu-id="70f21-124">You must add a reference to `Microsoft.BizTalk.HttpTransport.dll` in the custom orchestration.</span></span>  
  
 <span data-ttu-id="70f21-125">HTTP 标头的命名空间是非 AS2 HTTP 标头的 `http://schemas.microsoft.com/BizTalk/2003/http-properties` 和 AS2 标头的 `http://schemas.microsoft.com/BizTalk/2003/as2-properties`。</span><span class="sxs-lookup"><span data-stu-id="70f21-125">The namespaces for HTTP headers is `http://schemas.microsoft.com/BizTalk/2003/http-properties` for non-AS2 HTTP headers and `http://schemas.microsoft.com/BizTalk/2003/as2-properties` for AS2 headers.</span></span>  
  
 <span data-ttu-id="70f21-126">下面的示例代码说明了如何升级业务流程的构造消息形状中的 AS2 标头属性。</span><span class="sxs-lookup"><span data-stu-id="70f21-126">The following sample code shows how to promote AS2 header properties in the Construct Message shape of an orchestration.</span></span> <span data-ttu-id="70f21-127">此代码可为 MDN 升级 AS2 标头。</span><span class="sxs-lookup"><span data-stu-id="70f21-127">This code promotes AS2 headers for an MDN.</span></span>  
  
```  
Message_2=new System.Xml.XmlDocument();  
Message_2=Message_1;  
Message_2(EdiIntAS.IsAS2PayloadMessage)=false;  
Message_2(EdiIntAS.IsAS2AsynchronousMdn)=true;  
Message_2(EdiIntAS.IsAS2MdnResponseMessage)=true;  
Message_2(EdiIntAS.SendMDN)=true;  
Message_2(EdiIntAS.IsAS2MessageSigned)=false;  
Message_2(EdiIntAS.AS2To)="Party1";  
Message_2(EdiIntAS.AS2From)="Home";  
Message_2(EdiIntAS.MessageId)="123456";  
Message_2(EdiIntAS.OriginalMessageId)="2123456";  
Message_2(HTTP.UserHttpHeaders)="Message1-Id: xyz\r\nMyHeader: MyValue";  
```  
  
## <a name="see-also"></a><span data-ttu-id="70f21-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="70f21-128">See Also</span></span>  
 [<span data-ttu-id="70f21-129">开发和配置 BizTalk Server AS2 解决方案</span><span class="sxs-lookup"><span data-stu-id="70f21-129">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)