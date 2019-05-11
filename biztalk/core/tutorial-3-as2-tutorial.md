---
title: 教程 3:AS2 教程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 018829a9-e670-4b87-bac5-7f7b1332d90e
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0fb5f48a8e85c318b85322557ac940e36ecd142
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401714"
---
# <a name="tutorial-3-as2-tutorial"></a><span data-ttu-id="eab6b-102">教程 3:AS2 教程</span><span class="sxs-lookup"><span data-stu-id="eab6b-102">Tutorial 3: AS2 Tutorial</span></span>
<span data-ttu-id="eab6b-103">在本教程中，您将设置接收并通过 HTTP 传输发送 EDIINT/AS2 编码的消息的解决方案。</span><span class="sxs-lookup"><span data-stu-id="eab6b-103">In this tutorial, you set up a solution that receives and sends EDIINT/AS2-encoded messages over an HTTP transport.</span></span>  
  
 <span data-ttu-id="eab6b-104">**教程解决方案的工作原理**</span><span class="sxs-lookup"><span data-stu-id="eab6b-104">**How the Tutorial Solution Works**</span></span>  
  
 <span data-ttu-id="eab6b-105">该解决方案将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="eab6b-105">The solution will do the following:</span></span>  
  
- <span data-ttu-id="eab6b-106">从合作伙伴 (Fabrikam) 接收的 AS2 消息</span><span class="sxs-lookup"><span data-stu-id="eab6b-106">Receive an AS2 message from a partner (Fabrikam)</span></span>  
  
- <span data-ttu-id="eab6b-107">返回向合作伙伴异步 MDN 响应</span><span class="sxs-lookup"><span data-stu-id="eab6b-107">Return an MDN response asynchronously to the partner</span></span>  
  
- <span data-ttu-id="eab6b-108">处理 AS2 消息的 EDI 负载</span><span class="sxs-lookup"><span data-stu-id="eab6b-108">Process the EDI payload of the AS2 message</span></span>  
  
- <span data-ttu-id="eab6b-109">通过 AS2 向合作伙伴 (Fabrikam) 返回一个 997 确认。</span><span class="sxs-lookup"><span data-stu-id="eab6b-109">Return a 997 acknowledgment to the partner (Fabrikam) over AS2</span></span>  
  
- <span data-ttu-id="eab6b-110">将路由到后端应用程序的本组织 (Contoso) EDI 消息的负载包含的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="eab6b-110">Route an XML file containing the payload of the EDI message to a backend application of the home organization (Contoso).</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="eab6b-111">此解决方案不使用签名或加密来帮助确保 AS2 消息的安全性。</span><span class="sxs-lookup"><span data-stu-id="eab6b-111">This solution does not use signing or encryption to help ensure the security of AS2 messages.</span></span>  
  
  <span data-ttu-id="eab6b-112">**教程组件**</span><span class="sxs-lookup"><span data-stu-id="eab6b-112">**Tutorial Components**</span></span>  
  
  <span data-ttu-id="eab6b-113">此解决方案将使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="eab6b-113">This solution will use the following:</span></span>  
  
- <span data-ttu-id="eab6b-114">一个 BTS Http 接收 ISAPI 筛选器以接收来自发送方的 AS2/EDI 消息 **(/Contoso/BTSHTTPReceive.dll**)。</span><span class="sxs-lookup"><span data-stu-id="eab6b-114">A BTS Http Receive ISAPI Filter to receive the AS2/EDI message from the sender **(/Contoso/BTSHTTPReceive.dll**).</span></span>  
  
- <span data-ttu-id="eab6b-115">一个 ASPX 网页来通过返回一个 997 确认和 MDN 来模拟合作伙伴 (**http://localhost/Fabrikam/Default.aspx**)。</span><span class="sxs-lookup"><span data-stu-id="eab6b-115">An ASPX Web page to simulate the partner by returning a 997 acknowledgment and an MDN (**http://localhost/Fabrikam/Default.aspx**).</span></span>  
  
- <span data-ttu-id="eab6b-116">将用于部署 864 架构和其他架构的项目文件 (**Schemas.btproj**)。</span><span class="sxs-lookup"><span data-stu-id="eab6b-116">A project file that you will use to deploy an 864 schema and other schemas (**Schemas.btproj**).</span></span>  
  
- <span data-ttu-id="eab6b-117">一个单向 HTTP 接收位置以接收 EDI 文件 (**Receive_AS2**)。</span><span class="sxs-lookup"><span data-stu-id="eab6b-117">A one-way HTTP receive location to receive the EDI file (**Receive_AS2**).</span></span> <span data-ttu-id="eab6b-118">此接收位置使用默认的 AS2EdiReceive 管道包含 AS2 解码器和 EDI 拆装器。</span><span class="sxs-lookup"><span data-stu-id="eab6b-118">This receive location uses the default AS2EdiReceive pipeline that contains the AS2 Decoder and EDI Disassembler.</span></span>  
  
- <span data-ttu-id="eab6b-119">一个动态 HTTP 发送端口返回异步 MDN (**Send_Async_MDN**)。</span><span class="sxs-lookup"><span data-stu-id="eab6b-119">A dynamic HTTP send port to return an asynchronous MDN (**Send_Async_MDN**).</span></span> <span data-ttu-id="eab6b-120">此发送端口使用包含 AS2 编码器的 AS2Send 管道。</span><span class="sxs-lookup"><span data-stu-id="eab6b-120">This send port uses the AS2Send pipeline that contains the AS2 Encoder.</span></span>  
  
- <span data-ttu-id="eab6b-121">一个静态单向 FILE 发送端口以将 EDI 负载路由到后端文件夹的 XML 文件中 (**Send_Payload_EdiXml**)。</span><span class="sxs-lookup"><span data-stu-id="eab6b-121">A static one-way FILE send port to route the EDI payload in an XML file to a back-end folder (**Send_Payload_EdiXml**).</span></span> <span data-ttu-id="eab6b-122">此发送端口使用 PassThruTransmit 发送管道。</span><span class="sxs-lookup"><span data-stu-id="eab6b-122">This send port uses the PassThruTransmit send pipeline.</span></span>  
  
- <span data-ttu-id="eab6b-123">一个静态单向 HTTP 发送端口以通过 AS2 向合作伙伴返回一个 997 确认 (**Send_Async_997**)。</span><span class="sxs-lookup"><span data-stu-id="eab6b-123">A static one-way HTTP send port to return a 997 acknowledgment to the partner over AS2 (**Send_Async_997**).</span></span> <span data-ttu-id="eab6b-124">此发送端口使用包括 AS2 编码器，但无需 EDI 组装器的 AS2Send 管道。</span><span class="sxs-lookup"><span data-stu-id="eab6b-124">This send port uses the AS2Send pipeline that includes the AS2 Encoder, but has no need for the EDI Assembler.</span></span>  
  
- <span data-ttu-id="eab6b-125">将用于生成应用程序以将 EDI 文件从 Fabrikam 合作伙伴发送到 BizTalk 项目文件 (**Sender.csproj**)。</span><span class="sxs-lookup"><span data-stu-id="eab6b-125">A project file that you will use to build an application to send the EDI file from the Fabrikam partner to BizTalk (**Sender.csproj**).</span></span>  
  
  <span data-ttu-id="eab6b-126">**消息流**</span><span class="sxs-lookup"><span data-stu-id="eab6b-126">**Message Flow**</span></span>  
  
  <span data-ttu-id="eab6b-127">已完成的解决方案中的消息流将在下图中所示：</span><span class="sxs-lookup"><span data-stu-id="eab6b-127">The message flow in the completed solution will be as shown in the following figure:</span></span>  
  
  <span data-ttu-id="eab6b-128">![AS2 教程消息流](../core/media/31710c1d-4070-433e-953d-dcbfd0bb07a0.gif "31710c1d-4070-433e-953d-dcbfd0bb07a0")</span><span class="sxs-lookup"><span data-stu-id="eab6b-128">![AS2 tutorial message flow](../core/media/31710c1d-4070-433e-953d-dcbfd0bb07a0.gif "31710c1d-4070-433e-953d-dcbfd0bb07a0")</span></span>  
  
  <span data-ttu-id="eab6b-129">教程组件处理消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="eab6b-129">The tutorial components process the message as follows:</span></span>  
  
1. <span data-ttu-id="eab6b-130">您使用**sender.exe 应用程序**将从合作伙伴 Fabrikam 的原始 EDI/AS2 消息发送到 BizTalk Server 计算机。</span><span class="sxs-lookup"><span data-stu-id="eab6b-130">You use the **sender.exe application** to send the original EDI/AS2 message from the partner Fabrikam to the BizTalk Server computer.</span></span> <span data-ttu-id="eab6b-131">Sender.exe 将 EDI/AS2 消息发送到 Contoso 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="eab6b-131">Sender.exe sends the EDI/AS2 message to the Contoso virtual directory.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="eab6b-132">显示的顺序可能不是此列表中的事件。</span><span class="sxs-lookup"><span data-stu-id="eab6b-132">The events in this list may not occur in the order shown.</span></span>  
   >   
   >  <span data-ttu-id="eab6b-133">测试消息是 X12_00401_864.edi \Program Files\Microsoft BizTalk Server 20xx\SDK\AS2 Tutorial 中。</span><span class="sxs-lookup"><span data-stu-id="eab6b-133">The test message is X12_00401_864.edi in \Program Files\Microsoft BizTalk Server 20xx\SDK\AS2 Tutorial.</span></span>  
  
2. <span data-ttu-id="eab6b-134">**Receive_AS2**单向接收位置接收来自 Fabrikam，使用 BTSHTTPReceive.dll ISAPI 扩展从 Contoso 虚拟目录提取文件的 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="eab6b-134">The **Receive_AS2** one-way receive location receives the EDI message from Fabrikam, using the BTSHTTPReceive.dll ISAPI extension to pick the file up from the Contoso virtual directory.</span></span> <span data-ttu-id="eab6b-135">接收管道对 AS2 消息进行解码、 拆装 EDI 交换，然后将消息 XML 放入 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="eab6b-135">The receive pipeline decodes the AS2 message, disassembles the EDI interchange, and then drops the message XML into the MessageBox.</span></span>  
  
3. <span data-ttu-id="eab6b-136">接收管道生成 MDN 的 AS2 消息，并由于 MDN 设置为异步，接收管道会将此 MDN 放入 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="eab6b-136">The receive pipeline generates an MDN for the AS2 message, and since the MDN is set up to be asynchronous, the receive pipeline drops the MDN into the MessageBox.</span></span>  
  
4. <span data-ttu-id="eab6b-137">接收管道生成 997 确认以响应 EDI 交换，并将 997 放入 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="eab6b-137">The receive pipeline generates a 997 acknowledgment in response to the EDI interchange, and drops the 997 into the MessageBox.</span></span>  
  
5. <span data-ttu-id="eab6b-138">**Send_Payload_EdiXml**静态单向发送端口提取 EDI 负载从 MessageBox 中，对 BTS 进行筛选。MessageType 的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="eab6b-138">The **Send_Payload_EdiXml** static one-way send port picks up the EDI payload from the MessageBox, filtering on the BTS.MessageType context property.</span></span>  
  
6. <span data-ttu-id="eab6b-139">有效负载发送端口将包含到后端 Contoso 应用程序，由 EDI 负载的 XML 文件\\_EDIXMLToContoso 文件夹。</span><span class="sxs-lookup"><span data-stu-id="eab6b-139">The payload send port sends the XML file containing the EDI payload to the back-end Contoso application, represented by the \\_EDIXMLToContoso folder.</span></span> <span data-ttu-id="eab6b-140">此发送端口使用 PassThruTransmit 发送管道。</span><span class="sxs-lookup"><span data-stu-id="eab6b-140">This send port uses a PassThruTransmit send pipeline.</span></span>  
  
7. <span data-ttu-id="eab6b-141">**Send_Async_MDN**动态发送端口提取异步 MDN 从 MessageBox EdiIntAS.IsAS2AsynchronousMdn 上下文属性进行筛选。</span><span class="sxs-lookup"><span data-stu-id="eab6b-141">The **Send_Async_MDN** dynamic send port picks up the asynchronous MDN from the MessageBox, filtering on the EdiIntAS.IsAS2AsynchronousMdn context property.</span></span>  
  
8. <span data-ttu-id="eab6b-142">将 MDN 发送端口返回 MDN \\_MDNToFabrikam 文件夹。</span><span class="sxs-lookup"><span data-stu-id="eab6b-142">The MDN send port returns the MDN to the \\_MDNToFabrikam folder.</span></span> <span data-ttu-id="eab6b-143">由于这是一个动态发送端口，将在消息标头中的回执送达选项行中使用的地址 (**http://localhost/Fabrikam/Default.aspx?Destination=_MDNToFabrikam**) 以将消息路由到\\_MDNToFabrikam 文件夹。</span><span class="sxs-lookup"><span data-stu-id="eab6b-143">Since this is a dynamic send port, it will use the address in the Receipt-Delivery-Option line in the header of the message (**http://localhost/Fabrikam/Default.aspx?Destination=_MDNToFabrikam**) to route the message to the \\_MDNToFabrikam folder.</span></span>  
  
9. <span data-ttu-id="eab6b-144">**Send_Async_997**发送端口提取 997 消息框，从对 BTS 进行筛选。MessageType 的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="eab6b-144">The **Send_Async_997** send port picks up the 997 from the MessageBox, filtering on the BTS.MessageType context property.</span></span>  
  
10. <span data-ttu-id="eab6b-145">997 发送端口使用 HTTP 传输发送 997 消息生成的 EdiReceive 接收管道为\\_997ToFabrikam 文件夹。</span><span class="sxs-lookup"><span data-stu-id="eab6b-145">The 997 send port uses HTTP transport to send the 997 message generated by the EdiReceive receive pipeline to the \\_997ToFabrikam folder.</span></span> <span data-ttu-id="eab6b-146">发送端口将消息发送到 Fabrikam default.aspx 页，使用 URI **http://localhost/Fabrikam/Default.aspx?Destination=_997ToFabrikam**。</span><span class="sxs-lookup"><span data-stu-id="eab6b-146">The send port sends the message to the Fabrikam default.aspx page, using the URI **http://localhost/Fabrikam/Default.aspx?Destination=_997ToFabrikam**.</span></span> <span data-ttu-id="eab6b-147">Default.aspx 页然后将发送到 997 \\_997ToFabrikam 文件夹。</span><span class="sxs-lookup"><span data-stu-id="eab6b-147">The default.aspx page then sends the 997 to the \\_997ToFabrikam folder.</span></span>  
  
    <span data-ttu-id="eab6b-148">若要执行本教程中，您应该了解以下：</span><span class="sxs-lookup"><span data-stu-id="eab6b-148">To do this tutorial, you should be knowledgeable about the following:</span></span>  
  
-   <span data-ttu-id="eab6b-149">BizTalk Server 管道和管道组件</span><span class="sxs-lookup"><span data-stu-id="eab6b-149">BizTalk Server pipelines and pipeline components</span></span>  
  
-   <span data-ttu-id="eab6b-150">HTTP 适配器</span><span class="sxs-lookup"><span data-stu-id="eab6b-150">HTTP Adapter</span></span>  
  
-   <span data-ttu-id="eab6b-151">接收端口和位置</span><span class="sxs-lookup"><span data-stu-id="eab6b-151">Receive ports and locations</span></span>  
  
-   <span data-ttu-id="eab6b-152">发送端口</span><span class="sxs-lookup"><span data-stu-id="eab6b-152">Send ports</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eab6b-153">本节内容</span><span class="sxs-lookup"><span data-stu-id="eab6b-153">In This Section</span></span>  
  
-   [<span data-ttu-id="eab6b-154">步骤 1：AS2 教程的准备工作</span><span class="sxs-lookup"><span data-stu-id="eab6b-154">Step 1: Prepare for the AS2 Tutorial</span></span>](../core/step-1-prepare-for-the-as2-tutorial.md)  
  
-   [<span data-ttu-id="eab6b-155">步骤 2：创建和部署示例 X12 架构</span><span class="sxs-lookup"><span data-stu-id="eab6b-155">Step 2: Create and Deploy the Sample X12 Schema</span></span>](../core/step-2-create-and-deploy-the-sample-x12-schema.md)  
  
-   [<span data-ttu-id="eab6b-156">步骤 3：为你的组织配置参与方和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="eab6b-156">Step 3: Configure a Party and Business Profile for Your Organization</span></span>](../core/step-3-configure-a-party-and-business-profile-for-your-organization2.md)  
  
-   [<span data-ttu-id="eab6b-157">步骤 4：为您的贸易合作伙伴配置参与方和业务配置文件</span><span class="sxs-lookup"><span data-stu-id="eab6b-157">Step 4: Configure a Party and Business Profile for Your Trading Partner</span></span>](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner2.md)  
  
-   [<span data-ttu-id="eab6b-158">步骤 5：配置贸易合作伙伴网页</span><span class="sxs-lookup"><span data-stu-id="eab6b-158">Step 5: Configure the Trading Partner Web Pages</span></span>](../core/step-5-configure-the-trading-partner-web-pages.md)  
  
-   [<span data-ttu-id="eab6b-159">步骤 6：配置 EDI-AS2 接收位置</span><span class="sxs-lookup"><span data-stu-id="eab6b-159">Step 6: Configure the EDI-AS2 Receive Location</span></span>](../core/step-6-configure-the-edi-as2-receive-location.md)  
  
-   [<span data-ttu-id="eab6b-160">步骤 7：配置 MDN 发送端口</span><span class="sxs-lookup"><span data-stu-id="eab6b-160">Step 7: Configure the MDN Send Port</span></span>](../core/step-7-configure-the-mdn-send-port.md)  
  
-   [<span data-ttu-id="eab6b-161">步骤 8：配置 997 发送端口</span><span class="sxs-lookup"><span data-stu-id="eab6b-161">Step 8: Configure the 997 Send Port</span></span>](../core/step-8-configure-the-997-send-port.md)  
  
-   [<span data-ttu-id="eab6b-162">步骤 9：配置 EDI 有效负载发送端口</span><span class="sxs-lookup"><span data-stu-id="eab6b-162">Step 9: Configure the EDI Payload Send Port</span></span>](../core/step-9-configure-the-edi-payload-send-port.md)  
  
-   [<span data-ttu-id="eab6b-163">步骤 10：配置 X12 和 AS2 贸易合作伙伴协议</span><span class="sxs-lookup"><span data-stu-id="eab6b-163">Step 10: Configure the X12 and AS2 Trading Partner Agreement</span></span>](../core/step-10-configure-the-x12-and-as2-trading-partner-agreement.md)  
  
-   [<span data-ttu-id="eab6b-164">步骤 11:测试 AS2 解决方案</span><span class="sxs-lookup"><span data-stu-id="eab6b-164">Step 11: Test the AS2 Solution</span></span>](../core/step-11-test-the-as2-solution.md)  
  
## <a name="see-also"></a><span data-ttu-id="eab6b-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="eab6b-165">See Also</span></span>  
 [<span data-ttu-id="eab6b-166">BizTalk Server 教程</span><span class="sxs-lookup"><span data-stu-id="eab6b-166">BizTalk Server Tutorials</span></span>](../core/biztalk-server-tutorials.md)