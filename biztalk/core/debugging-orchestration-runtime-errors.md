---
title: "调试业务流程运行时错误 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7be9ee5a-b9fa-428b-8b92-0fa0f801c724
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87a47c5b2ee432059365c6f9046a75bb5775fc02
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="debugging-orchestration-runtime-errors"></a><span data-ttu-id="7340c-102">调试业务流程运行时错误</span><span class="sxs-lookup"><span data-stu-id="7340c-102">Debugging Orchestration Runtime Errors</span></span>
<span data-ttu-id="7340c-103">本部分包含可帮助您解决业务流程运行时问题的一系列问题与解答。</span><span class="sxs-lookup"><span data-stu-id="7340c-103">This section contains a set of questions and answers designed to help you resolve runtime issues with your orchestrations.</span></span>  
  
## <a name="why-do-i-get-intermittent-subscription-errors-when-sending-to-a-child-orchestration-that-was-just-started-by-the-parent"></a><span data-ttu-id="7340c-104">在发送到刚由父业务流程启动的子业务流程时，为什么会遇到间歇订阅错误？</span><span class="sxs-lookup"><span data-stu-id="7340c-104">Why do I get intermittent subscription errors when sending to a child orchestration that was just started by the parent?</span></span>  
 <span data-ttu-id="7340c-105">订阅错误“找不到订阅”是由于争用情况造成的。</span><span class="sxs-lookup"><span data-stu-id="7340c-105">The subscription error "could not find subscription" is a result of a race condition.</span></span> <span data-ttu-id="7340c-106">在进程结果依赖于执行进程所采用的特定顺序时，将发生争用情况。</span><span class="sxs-lookup"><span data-stu-id="7340c-106">A race condition occurs when the outcome of a process depends on the particular order in which the process takes place.</span></span> <span data-ttu-id="7340c-107">在此情况下，如果子业务流程未及时启动以接收父业务流程发送的消息，将发生此争用情况。</span><span class="sxs-lookup"><span data-stu-id="7340c-107">In this case, the condition occurs when the child orchestration has not been started in time to receive the message sent by the parent.</span></span>  
  
 <span data-ttu-id="7340c-108">为了避免这一问题发生，子业务流程可以在父业务流程已启动并且准备接收消息后，将消息发送回父业务流程。</span><span class="sxs-lookup"><span data-stu-id="7340c-108">To avoid this problem, the child orchestration could send a message back to the parent when it has been started and is prepared to receive a message.</span></span> <span data-ttu-id="7340c-109">这样，启动了它的父业务流程就会在发送消息前知道存在接收方。</span><span class="sxs-lookup"><span data-stu-id="7340c-109">In this way, the parent orchestration that started it would know that there is a receiver before sending a message.</span></span>  
  
## <a name="why-do-i-get-errors-when-i-attach-a-dynamic-send-port-to-a-logical-port"></a><span data-ttu-id="7340c-110">在将某一动态发送端口附加到逻辑端口时，为什么会显示错误？</span><span class="sxs-lookup"><span data-stu-id="7340c-110">Why do I get errors when I attach a dynamic send port to a logical port?</span></span>  
 <span data-ttu-id="7340c-111">动态端口并没有设计为继承分配给它的所有端口属性和特性。</span><span class="sxs-lookup"><span data-stu-id="7340c-111">A dynamic port is not designed to inherit all of the attributes and characteristics of the port assigned to it.</span></span> <span data-ttu-id="7340c-112">动态端口只获取地址，它并不继承与逻辑端口关联的其他信息。</span><span class="sxs-lookup"><span data-stu-id="7340c-112">A dynamic port gets an address only; it does not inherit the other information associated with the logical port.</span></span>  
  
 <span data-ttu-id="7340c-113">例如，如果您将某一动态发送端口附加到某一逻辑端口且送达通知为“已传输”，则运行时将不会传递送达通知。</span><span class="sxs-lookup"><span data-stu-id="7340c-113">For example, if you attach a dynamic send port to a logical port with Delivery Notification = Transmitted, the runtime will not deliver a delivery notification.</span></span> <span data-ttu-id="7340c-114">如果端口实际上是以静态方式配置的，XLANGs 运行时将只侦听送达通知。</span><span class="sxs-lookup"><span data-stu-id="7340c-114">The XLANGs runtime only listens for a delivery notification if the port has actually been set up that way statically.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7340c-115">在 XLANGs 中，端口只是表现得像是用静态方式配置的。</span><span class="sxs-lookup"><span data-stu-id="7340c-115">In XLANGs, ports will behave only as they have been configured statically.</span></span>  
  
## <a name="when-i-try-to-run-my-application-after-deploying-an-orchestration-with-custom-components-why-do-i-get-the-error-file-or-assembly-name-or-one-of-its-dependencies-not-found"></a><span data-ttu-id="7340c-116">在使用自定义组件部署业务流程后尝试运行应用程序时，为什么系统会显示错误消息“未找到文件或程序集名称或它的某个依赖项”？</span><span class="sxs-lookup"><span data-stu-id="7340c-116">When I try to run my application after deploying an orchestration with custom components, why do I get the error "File or Assembly name or one of its dependencies not found"?</span></span>  
 <span data-ttu-id="7340c-117">此错误通常意味着 BizTalk 业务流程引擎无法定位自定义组件。</span><span class="sxs-lookup"><span data-stu-id="7340c-117">This error usually means the BizTalk orchestration engine cannot locate the custom component.</span></span> <span data-ttu-id="7340c-118">您必须在作为某一 BizTalk 应用程序宿主的计算机的全局程序集缓存中，安装该应用程序中包括的所有程序集。</span><span class="sxs-lookup"><span data-stu-id="7340c-118">You must install all assemblies included in a BizTalk application in the global assembly cache of the computer that hosts the application.</span></span>  
  
## <a name="an-assemblyname-context-property-was-not-valid-error-occurs-when-submitting-a-document-to-a-web-service-via-an-orchestration"></a><span data-ttu-id="7340c-119">在将文档通过业务流程提交到 Web Services 时，发生“AssemblyName 上下文属性无效”错误</span><span class="sxs-lookup"><span data-stu-id="7340c-119">An "AssemblyName context property was not valid" error occurs when submitting a document to a Web service via an orchestration</span></span>  
  
### <a name="problem"></a><span data-ttu-id="7340c-120">问题</span><span class="sxs-lookup"><span data-stu-id="7340c-120">Problem</span></span>  
 <span data-ttu-id="7340c-121">通过业务流程将文档提交到 Web Services 将导致“AssemblyName 上下文属性无效”错误。</span><span class="sxs-lookup"><span data-stu-id="7340c-121">Submitting a document to a Web service via an orchestration results in an "AssemblyName context property not valid" error.</span></span>  
  
### <a name="cause"></a><span data-ttu-id="7340c-122">原因</span><span class="sxs-lookup"><span data-stu-id="7340c-122">Cause</span></span>  
 <span data-ttu-id="7340c-123">BizTalk 应用程序最初是使用“消息传送”方法设计的，没有涉及业务流程。</span><span class="sxs-lookup"><span data-stu-id="7340c-123">The BizTalk application was originally designed using a "messaging" approach without an intervening orchestration.</span></span> <span data-ttu-id="7340c-124">此类型的解决方案使用发送端口筛选器来链接接收端口和发送端口，以便文档在接收后传递到发送端口。</span><span class="sxs-lookup"><span data-stu-id="7340c-124">This type of solution uses a send port filter to link the receive port and the send port so that the document is passed through to the send port upon receipt.</span></span> <span data-ttu-id="7340c-125">在后来，修改了该解决方案，从而包括了绑定到发送端口的业务流程。</span><span class="sxs-lookup"><span data-stu-id="7340c-125">Later, the solution was modified to include an orchestration that was bound to the send port.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="7340c-126">解决方法</span><span class="sxs-lookup"><span data-stu-id="7340c-126">Resolution</span></span>  
 <span data-ttu-id="7340c-127">删除发送端口上的筛选器。</span><span class="sxs-lookup"><span data-stu-id="7340c-127">Remove the filter on the send port.</span></span> <span data-ttu-id="7340c-128">如果您将某一筛选器应用于绑定到某一业务流程的发送端口，则消息将常常会绕过该业务流程，从而导致上下文属性错误。</span><span class="sxs-lookup"><span data-stu-id="7340c-128">If you apply a filter to a send port that is bound to an orchestration, messages will often bypass the orchestration and cause the context property error.</span></span>  
  
## <a name="a-wrongbodypartexception-occurs-when-handling-a-multipart-mime-message-in-an-orchestration"></a><span data-ttu-id="7340c-129">在业务流程中处理多部分 MIME 消息时，发生了“WrongBodyPartException”异常</span><span class="sxs-lookup"><span data-stu-id="7340c-129">A "WrongBodyPartException" occurs when handling a multipart MIME message in an orchestration</span></span>  
  
### <a name="problem"></a><span data-ttu-id="7340c-130">问题</span><span class="sxs-lookup"><span data-stu-id="7340c-130">Problem</span></span>  
 <span data-ttu-id="7340c-131">接收到业务流程的多部分 MIME 消息导致**WrongBodyPartException**异常。</span><span class="sxs-lookup"><span data-stu-id="7340c-131">Receiving a multipart MIME message into an orchestration results in a **WrongBodyPartException** exception.</span></span>  
  
### <a name="cause"></a><span data-ttu-id="7340c-132">原因</span><span class="sxs-lookup"><span data-stu-id="7340c-132">Cause</span></span>  
 <span data-ttu-id="7340c-133">如果错误地指定了各部分的顺序或者消息与您已指定的部分位置不符，则可能会发生此错误。</span><span class="sxs-lookup"><span data-stu-id="7340c-133">This error can occur if the order of the parts is specified incorrectly or messages do not conform to the part positions you have specified.</span></span> <span data-ttu-id="7340c-134">例如，如果您指定第三个部分是正文部分，但消息到达时在第三个位置中却是标头部分。</span><span class="sxs-lookup"><span data-stu-id="7340c-134">For example, if you specify that the third part is a body part but messages arrive with a header part in the third position.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="7340c-135">解决方法</span><span class="sxs-lookup"><span data-stu-id="7340c-135">Resolution</span></span>  
 <span data-ttu-id="7340c-136">确认正文部分索引设置是正确的，然后确保通过适配器到达的所有消息都与该设置一致。</span><span class="sxs-lookup"><span data-stu-id="7340c-136">Verify that the body part index setting is correct and then ensure that all messages arriving through the adapter are consistent with the setting.</span></span> <span data-ttu-id="7340c-137">您可以通过停止业务流程（但保持它被登记），检查在业务流程内失败的 MIME 消息的内容；这将强制发布消息，以便您可以通过使用管理控制台检查它并验证各部分的顺序。</span><span class="sxs-lookup"><span data-stu-id="7340c-137">You can inspect the contents of MIME messages that fail inside an orchestration by stopping the orchestration (but keeping it enlisted); this will force the message to be published so you can examine it using the Administration console and verify the order of the parts.</span></span>  
  
## <a name="multipart-mime-message-part-cannot-be-found"></a><span data-ttu-id="7340c-138">找不到多部分 MIME 消息部分</span><span class="sxs-lookup"><span data-stu-id="7340c-138">Multipart MIME message part cannot be found</span></span>  
  
### <a name="problem"></a><span data-ttu-id="7340c-139">问题</span><span class="sxs-lookup"><span data-stu-id="7340c-139">Problem</span></span>  
 <span data-ttu-id="7340c-140">尝试检索 MIME 消息的索引值大于 0 的结果引发错误类似于 BizTalk Server 运行时中的一部分"找不到具有索引的多个部分消息 =\<值\>"。</span><span class="sxs-lookup"><span data-stu-id="7340c-140">Attempts to retrieve a MIME message part with an index value greater than 0 results in the BizTalk Server runtime throwing an error similar to "can't find multi-part message with index = \<value\>".</span></span>  
  
### <a name="cause"></a><span data-ttu-id="7340c-141">原因</span><span class="sxs-lookup"><span data-stu-id="7340c-141">Cause</span></span>  
 <span data-ttu-id="7340c-142">导致此错误的最常见原因是：</span><span class="sxs-lookup"><span data-stu-id="7340c-142">The most common causes for this error are:</span></span>  
  
-   <span data-ttu-id="7340c-143">MIME 消息所具有的部分少于预期。</span><span class="sxs-lookup"><span data-stu-id="7340c-143">The MIME message has fewer parts than expected.</span></span>  
  
-   <span data-ttu-id="7340c-144">MIME 消息无法被完全解析。</span><span class="sxs-lookup"><span data-stu-id="7340c-144">The MIME message could not be fully parsed.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="7340c-145">解决方法</span><span class="sxs-lookup"><span data-stu-id="7340c-145">Resolution</span></span>  
 <span data-ttu-id="7340c-146">您可以通过确保您的代码只检索在预期消息源范围内的消息部分，解决这一问题。</span><span class="sxs-lookup"><span data-stu-id="7340c-146">You can resolve this problem by ensuring that your code retrieves only message parts that are within the range expected from the message source.</span></span> <span data-ttu-id="7340c-147">在出现解析问题时，您应该确认原始 MIME 消息在结构上合理并且正确构建。</span><span class="sxs-lookup"><span data-stu-id="7340c-147">In the case of a parsing issue, you should verify that the original MIME message is structurally sound and properly constructed.</span></span> <span data-ttu-id="7340c-148">如果您偶尔遇到解析问题，则确保您的业务流程具有适当的异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="7340c-148">If you expect occasional parsing problems, ensure that your orchestration has appropriate exception handlers.</span></span>  
  
## <a name="you-receive-a-the-file-send-adapter-cannot-open-file-for-writing-error-when-sending-using-a-dynamic-send-port"></a><span data-ttu-id="7340c-149">使用动态发送端口进行发送时，收到“文件发送适配器无法打开文件进行写入”错误</span><span class="sxs-lookup"><span data-stu-id="7340c-149">You receive a "The FILE send adapter cannot open file for writing" error when sending using a dynamic send port</span></span>  
  
### <a name="problem"></a><span data-ttu-id="7340c-150">问题</span><span class="sxs-lookup"><span data-stu-id="7340c-150">Problem</span></span>  
 <span data-ttu-id="7340c-151">你收到"FILE 发送适配器无法打开文件 *\<filename\>* 为写入"错误在 BizTalk Server 事件日志时发送使用动态发送端口。</span><span class="sxs-lookup"><span data-stu-id="7340c-151">You receive a "The FILE send adapter cannot open file *\<filename\>* for writing" error in the BizTalk Server event log when sending using a dynamic send port.</span></span>  
  
 <span data-ttu-id="7340c-152">出现此问题时**BTS。OutBoundTransportLocation** orchestration 表达式中定义属性并指定文件传输，例如，以下表达式将导致在运行时此错误：</span><span class="sxs-lookup"><span data-stu-id="7340c-152">This problem occurs when the **BTS.OutBoundTransportLocation** property is defined in an orchestration expression and the file transport is specified, for example the following expressions will cause this error at runtime:</span></span>  
  
```  
Message2=Message1;  
Message2(BTS.OutboundTransportLocation) = "file:///c:/test/out";  
MySendPort(Microsoft.XLANGs.BaseTypes.Address)=Message2(BTS.OutboundTransportLocation);  
```  
  
 <span data-ttu-id="7340c-153">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="7340c-153">\- Or -</span></span>  
  
```  
Message2=Message1;  
Message2(BTS.OutboundTransportLocation) = "file://mymachine/test/out";  
MySendPort(Microsoft.XLANGs.BaseTypes.Address)=Message2(BTS.OutboundTransportLocation);  
```  
  
### <a name="cause"></a><span data-ttu-id="7340c-154">原因</span><span class="sxs-lookup"><span data-stu-id="7340c-154">Cause</span></span>  
 <span data-ttu-id="7340c-155">出现此问题的原因在运行时业务流程引擎中删除的文本"**file://"**从指定的 URL。</span><span class="sxs-lookup"><span data-stu-id="7340c-155">This problem occurs because at runtime the orchestration engine removes the text "**file://"** from the specified URL.</span></span> <span data-ttu-id="7340c-156">因此，使用上面的示例时，“file:///c:/test/out”的计算结果为 \c:\test\out，“file://mymachine/test/out”的计算结果为“mymachine\test\out”。</span><span class="sxs-lookup"><span data-stu-id="7340c-156">So, using the examples above, "file:///c:/test/out" is evaluated as \c:\test\out and "file://mymachine/test/out" is evaluated as mymachine\test\out.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="7340c-157">解决方法</span><span class="sxs-lookup"><span data-stu-id="7340c-157">Resolution</span></span>  
 <span data-ttu-id="7340c-158">当指定的 URL **BTS。OutBoundTransportLocation**属性在表达式中，添加或删除"/"字符根据需要。</span><span class="sxs-lookup"><span data-stu-id="7340c-158">When specifying the URL for the **BTS.OutBoundTransportLocation** property in an expression, add or remove "/" characters as needed.</span></span> <span data-ttu-id="7340c-159">使用上面的示例**BTS。OutBoundTransportLocation**属性应定义为"file://c:/test/out"，将计算结果为 c:\test\out 或"file:///mymachine/test/out"，将计算为\\\mymachine\test\out。</span><span class="sxs-lookup"><span data-stu-id="7340c-159">Using the examples above the **BTS.OutBoundTransportLocation** property should be defined as "file://c:/test/out", which would evaluate to c:\test\out or "file:////mymachine/test/out", which would evaluate to \\\mymachine\test\out.</span></span>