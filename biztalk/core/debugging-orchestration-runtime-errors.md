---
title: 调试业务流程运行时错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7be9ee5a-b9fa-428b-8b92-0fa0f801c724
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b74291083afc5c25df0723bcbdf105ba51016a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389756"
---
# <a name="debugging-orchestration-runtime-errors"></a><span data-ttu-id="ca9e3-102">调试业务流程运行时错误</span><span class="sxs-lookup"><span data-stu-id="ca9e3-102">Debugging Orchestration Runtime Errors</span></span>
<span data-ttu-id="ca9e3-103">本部分包含一系列问题与解答可帮助您解决您的业务流程的运行时问题。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-103">This section contains a set of questions and answers designed to help you resolve runtime issues with your orchestrations.</span></span>  
  
## <a name="why-do-i-get-intermittent-subscription-errors-when-sending-to-a-child-orchestration-that-was-just-started-by-the-parent"></a><span data-ttu-id="ca9e3-104">将发送到只需启动了父级的子业务流程时，为何遇到间歇订阅错误？</span><span class="sxs-lookup"><span data-stu-id="ca9e3-104">Why do I get intermittent subscription errors when sending to a child orchestration that was just started by the parent?</span></span>  
 <span data-ttu-id="ca9e3-105">订阅错误"在找不到订阅"是争用条件的结果。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-105">The subscription error "could not find subscription" is a result of a race condition.</span></span> <span data-ttu-id="ca9e3-106">在进程结果依赖于过程发生的特定顺序时发生的争用条件。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-106">A race condition occurs when the outcome of a process depends on the particular order in which the process takes place.</span></span> <span data-ttu-id="ca9e3-107">在这种情况下，会出现此子业务流程尚未启动的时间，以接收父发送的消息时。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-107">In this case, the condition occurs when the child orchestration has not been started in time to receive the message sent by the parent.</span></span>  
  
 <span data-ttu-id="ca9e3-108">若要避免此问题，子业务流程无法发送消息返回到父级时它已启动并且已准备好接收的消息。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-108">To avoid this problem, the child orchestration could send a message back to the parent when it has been started and is prepared to receive a message.</span></span> <span data-ttu-id="ca9e3-109">这样一来，启动它的父业务流程发送消息前没有为接收方会知道。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-109">In this way, the parent orchestration that started it would know that there is a receiver before sending a message.</span></span>  
  
## <a name="why-do-i-get-errors-when-i-attach-a-dynamic-send-port-to-a-logical-port"></a><span data-ttu-id="ca9e3-110">将动态发送端口附加到逻辑端口时，为什么收到错误？</span><span class="sxs-lookup"><span data-stu-id="ca9e3-110">Why do I get errors when I attach a dynamic send port to a logical port?</span></span>  
 <span data-ttu-id="ca9e3-111">动态端口没有设计为继承的所有属性和特性为其分配的端口。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-111">A dynamic port is not designed to inherit all of the attributes and characteristics of the port assigned to it.</span></span> <span data-ttu-id="ca9e3-112">动态端口只获取地址;它不会继承与逻辑端口相关联的其他信息。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-112">A dynamic port gets an address only; it does not inherit the other information associated with the logical port.</span></span>  
  
 <span data-ttu-id="ca9e3-113">例如，如果将动态发送端口附加到逻辑端口且送达通知 = 传输，运行时将不会传递送达通知。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-113">For example, if you attach a dynamic send port to a logical port with Delivery Notification = Transmitted, the runtime will not deliver a delivery notification.</span></span> <span data-ttu-id="ca9e3-114">如果端口实际上已设置，以静态方式将 XLANGs 运行时只侦听送达通知。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-114">The XLANGs runtime only listens for a delivery notification if the port has actually been set up that way statically.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca9e3-115">在 XLANGs，端口只是表现已以静态方式配置它们。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-115">In XLANGs, ports will behave only as they have been configured statically.</span></span>  
  
## <a name="when-i-try-to-run-my-application-after-deploying-an-orchestration-with-custom-components-why-do-i-get-the-error-file-or-assembly-name-or-one-of-its-dependencies-not-found"></a><span data-ttu-id="ca9e3-116">当我尝试运行我的应用程序部署自定义组件与业务流程后时，为什么我收到错误"文件或程序集名称或其某个依赖项找不到"？</span><span class="sxs-lookup"><span data-stu-id="ca9e3-116">When I try to run my application after deploying an orchestration with custom components, why do I get the error "File or Assembly name or one of its dependencies not found"?</span></span>  
 <span data-ttu-id="ca9e3-117">此错误通常意味着 BizTalk 业务流程引擎找不到自定义组件。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-117">This error usually means the BizTalk orchestration engine cannot locate the custom component.</span></span> <span data-ttu-id="ca9e3-118">必须安装在 BizTalk 应用程序中托管的应用程序的计算机的全局程序集缓存中包含的所有程序集。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-118">You must install all assemblies included in a BizTalk application in the global assembly cache of the computer that hosts the application.</span></span>  
  
## <a name="an-assemblyname-context-property-was-not-valid-error-occurs-when-submitting-a-document-to-a-web-service-via-an-orchestration"></a><span data-ttu-id="ca9e3-119">提交到业务流程通过 Web 服务的文档时，发生"AssemblyName 上下文属性不是有效的"错误</span><span class="sxs-lookup"><span data-stu-id="ca9e3-119">An "AssemblyName context property was not valid" error occurs when submitting a document to a Web service via an orchestration</span></span>  
  
### <a name="problem"></a><span data-ttu-id="ca9e3-120">问题</span><span class="sxs-lookup"><span data-stu-id="ca9e3-120">Problem</span></span>  
 <span data-ttu-id="ca9e3-121">将文档提交到 Web 服务通过业务流程将导致"AssemblyName 上下文属性无效"错误。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-121">Submitting a document to a Web service via an orchestration results in an "AssemblyName context property not valid" error.</span></span>  
  
### <a name="cause"></a><span data-ttu-id="ca9e3-122">原因</span><span class="sxs-lookup"><span data-stu-id="ca9e3-122">Cause</span></span>  
 <span data-ttu-id="ca9e3-123">BizTalk 应用程序最初是使用"消息传送"方法而无需涉及业务流程设计的。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-123">The BizTalk application was originally designed using a "messaging" approach without an intervening orchestration.</span></span> <span data-ttu-id="ca9e3-124">此类型的解决方案使用发送端口筛选器来链接接收端口和发送端口，以便该文档将传递给在收到后的发送端口。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-124">This type of solution uses a send port filter to link the receive port and the send port so that the document is passed through to the send port upon receipt.</span></span> <span data-ttu-id="ca9e3-125">更高版本，修改了该解决方案包含已绑定到发送端口业务流程。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-125">Later, the solution was modified to include an orchestration that was bound to the send port.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="ca9e3-126">解决方法</span><span class="sxs-lookup"><span data-stu-id="ca9e3-126">Resolution</span></span>  
 <span data-ttu-id="ca9e3-127">删除发送端口上的筛选器。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-127">Remove the filter on the send port.</span></span> <span data-ttu-id="ca9e3-128">如果绑定到业务流程的发送端口应用筛选器，消息通常将绕过该业务流程，并导致上下文属性错误。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-128">If you apply a filter to a send port that is bound to an orchestration, messages will often bypass the orchestration and cause the context property error.</span></span>  
  
## <a name="a-wrongbodypartexception-occurs-when-handling-a-multipart-mime-message-in-an-orchestration"></a><span data-ttu-id="ca9e3-129">当处理业务流程中的多部分 MIME 消息时出现"WrongBodyPartException"</span><span class="sxs-lookup"><span data-stu-id="ca9e3-129">A "WrongBodyPartException" occurs when handling a multipart MIME message in an orchestration</span></span>  
  
### <a name="problem"></a><span data-ttu-id="ca9e3-130">问题</span><span class="sxs-lookup"><span data-stu-id="ca9e3-130">Problem</span></span>  
 <span data-ttu-id="ca9e3-131">接收到业务流程的多部分 MIME 消息会导致**WrongBodyPartException**异常。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-131">Receiving a multipart MIME message into an orchestration results in a **WrongBodyPartException** exception.</span></span>  
  
### <a name="cause"></a><span data-ttu-id="ca9e3-132">原因</span><span class="sxs-lookup"><span data-stu-id="ca9e3-132">Cause</span></span>  
 <span data-ttu-id="ca9e3-133">如果未正确指定的部分的顺序或者消息不符合您指定的部分位置可以出现此错误。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-133">This error can occur if the order of the parts is specified incorrectly or messages do not conform to the part positions you have specified.</span></span> <span data-ttu-id="ca9e3-134">例如，如果指定的第三部分是正文部分，但消息到达的第三个位置中的标头部分。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-134">For example, if you specify that the third part is a body part but messages arrive with a header part in the third position.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="ca9e3-135">解决方法</span><span class="sxs-lookup"><span data-stu-id="ca9e3-135">Resolution</span></span>  
 <span data-ttu-id="ca9e3-136">验证正文部分索引设置正确，然后确保通过适配器到达的所有消息都都与该设置一致。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-136">Verify that the body part index setting is correct and then ensure that all messages arriving through the adapter are consistent with the setting.</span></span> <span data-ttu-id="ca9e3-137">可以检查失败的业务流程内部停止业务流程的 MIME 消息的内容 （但保持它被登记）;这将强制使您可以对其使用管理控制台进行检查并验证的部分的顺序发布消息。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-137">You can inspect the contents of MIME messages that fail inside an orchestration by stopping the orchestration (but keeping it enlisted); this will force the message to be published so you can examine it using the Administration console and verify the order of the parts.</span></span>  
  
## <a name="multipart-mime-message-part-cannot-be-found"></a><span data-ttu-id="ca9e3-138">找不到多部分 MIME 消息部分</span><span class="sxs-lookup"><span data-stu-id="ca9e3-138">Multipart MIME message part cannot be found</span></span>  
  
### <a name="problem"></a><span data-ttu-id="ca9e3-139">问题</span><span class="sxs-lookup"><span data-stu-id="ca9e3-139">Problem</span></span>  
 <span data-ttu-id="ca9e3-140">尝试检索 MIME 消息部分的索引值大于 0 个结果在 BizTalk Server 运行时引发错误类似于"找不到具有索引的多部分消息 =\<值\>"。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-140">Attempts to retrieve a MIME message part with an index value greater than 0 results in the BizTalk Server runtime throwing an error similar to "can't find multi-part message with index = \<value\>".</span></span>  
  
### <a name="cause"></a><span data-ttu-id="ca9e3-141">原因</span><span class="sxs-lookup"><span data-stu-id="ca9e3-141">Cause</span></span>  
 <span data-ttu-id="ca9e3-142">此错误的最常见原因是：</span><span class="sxs-lookup"><span data-stu-id="ca9e3-142">The most common causes for this error are:</span></span>  
  
-   <span data-ttu-id="ca9e3-143">MIME 消息具有的部分少于预期。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-143">The MIME message has fewer parts than expected.</span></span>  
  
-   <span data-ttu-id="ca9e3-144">无法完全分析 MIME 消息。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-144">The MIME message could not be fully parsed.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="ca9e3-145">解决方法</span><span class="sxs-lookup"><span data-stu-id="ca9e3-145">Resolution</span></span>  
 <span data-ttu-id="ca9e3-146">您可以解决此问题通过确保你的代码检索预期消息源范围内的消息部分。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-146">You can resolve this problem by ensuring that your code retrieves only message parts that are within the range expected from the message source.</span></span> <span data-ttu-id="ca9e3-147">如果解析问题时，应验证原始 MIME 消息是结构上合理并且正确构建。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-147">In the case of a parsing issue, you should verify that the original MIME message is structurally sound and properly constructed.</span></span> <span data-ttu-id="ca9e3-148">如果希望偶尔遇到解析问题，请确保您的业务流程具有适当的异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-148">If you expect occasional parsing problems, ensure that your orchestration has appropriate exception handlers.</span></span>  
  
## <a name="you-receive-a-the-file-send-adapter-cannot-open-file-for-writing-error-when-sending-using-a-dynamic-send-port"></a><span data-ttu-id="ca9e3-149">发送使用动态发送端口时收到"文件发送适配器无法打开文件进行写入"错误</span><span class="sxs-lookup"><span data-stu-id="ca9e3-149">You receive a "The FILE send adapter cannot open file for writing" error when sending using a dynamic send port</span></span>  
  
### <a name="problem"></a><span data-ttu-id="ca9e3-150">问题</span><span class="sxs-lookup"><span data-stu-id="ca9e3-150">Problem</span></span>  
 <span data-ttu-id="ca9e3-151">你收到"文件发送适配器无法打开文件 *\<文件名\>* 进行写入"错误时使用动态发送，BizTalk Server 事件日志中的发送端口。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-151">You receive a "The FILE send adapter cannot open file *\<filename\>* for writing" error in the BizTalk Server event log when sending using a dynamic send port.</span></span>  
  
 <span data-ttu-id="ca9e3-152">发生此问题时**BTS。OutBoundTransportLocation**属性在业务流程表达式中定义和指定的文件传输，例如以下表达式将导致此错误在运行时：</span><span class="sxs-lookup"><span data-stu-id="ca9e3-152">This problem occurs when the **BTS.OutBoundTransportLocation** property is defined in an orchestration expression and the file transport is specified, for example the following expressions will cause this error at runtime:</span></span>  
  
```  
Message2=Message1;  
Message2(BTS.OutboundTransportLocation) = "file:///c:/test/out";  
MySendPort(Microsoft.XLANGs.BaseTypes.Address)=Message2(BTS.OutboundTransportLocation);  
```  
  
 <span data-ttu-id="ca9e3-153">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="ca9e3-153">\- Or -</span></span>  
  
```  
Message2=Message1;  
Message2(BTS.OutboundTransportLocation) = "file://mymachine/test/out";  
MySendPort(Microsoft.XLANGs.BaseTypes.Address)=Message2(BTS.OutboundTransportLocation);  
```  
  
### <a name="cause"></a><span data-ttu-id="ca9e3-154">原因</span><span class="sxs-lookup"><span data-stu-id="ca9e3-154">Cause</span></span>  
 <span data-ttu-id="ca9e3-155">发生此问题的原因在运行时业务流程引擎中删除的文本"**file://"** 从指定的 URL。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-155">This problem occurs because at runtime the orchestration engine removes the text "**file://"** from the specified URL.</span></span> <span data-ttu-id="ca9e3-156">因此，使用上面的示例，作为 \c:\test\out 计算"file:///c:/test/out"和"file://mymachine/test/out"计算结果为 \c: \test\out。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-156">So, using the examples above, "file:///c:/test/out" is evaluated as \c:\test\out and "file://mymachine/test/out" is evaluated as mymachine\test\out.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="ca9e3-157">解决方法</span><span class="sxs-lookup"><span data-stu-id="ca9e3-157">Resolution</span></span>  
 <span data-ttu-id="ca9e3-158">指定的 URL 时**BTS。OutBoundTransportLocation**属性在表达式中，添加或删除"/"字符根据需要。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-158">When specifying the URL for the **BTS.OutBoundTransportLocation** property in an expression, add or remove "/" characters as needed.</span></span> <span data-ttu-id="ca9e3-159">使用上面的示例**BTS。OutBoundTransportLocation**属性应定义为"file://c:/test/out"，将计算结果为 c:\test\out 或"file:///mymachine/test/out"计算结果为\\\mymachine\test\out。</span><span class="sxs-lookup"><span data-stu-id="ca9e3-159">Using the examples above the **BTS.OutBoundTransportLocation** property should be defined as "file://c:/test/out", which would evaluate to c:\test\out or "file:////mymachine/test/out", which would evaluate to \\\mymachine\test\out.</span></span>