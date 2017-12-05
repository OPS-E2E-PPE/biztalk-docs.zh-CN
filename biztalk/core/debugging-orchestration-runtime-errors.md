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
# <a name="debugging-orchestration-runtime-errors"></a>调试业务流程运行时错误
本部分包含可帮助您解决业务流程运行时问题的一系列问题与解答。  
  
## <a name="why-do-i-get-intermittent-subscription-errors-when-sending-to-a-child-orchestration-that-was-just-started-by-the-parent"></a>在发送到刚由父业务流程启动的子业务流程时，为什么会遇到间歇订阅错误？  
 订阅错误“找不到订阅”是由于争用情况造成的。 在进程结果依赖于执行进程所采用的特定顺序时，将发生争用情况。 在此情况下，如果子业务流程未及时启动以接收父业务流程发送的消息，将发生此争用情况。  
  
 为了避免这一问题发生，子业务流程可以在父业务流程已启动并且准备接收消息后，将消息发送回父业务流程。 这样，启动了它的父业务流程就会在发送消息前知道存在接收方。  
  
## <a name="why-do-i-get-errors-when-i-attach-a-dynamic-send-port-to-a-logical-port"></a>在将某一动态发送端口附加到逻辑端口时，为什么会显示错误？  
 动态端口并没有设计为继承分配给它的所有端口属性和特性。 动态端口只获取地址，它并不继承与逻辑端口关联的其他信息。  
  
 例如，如果您将某一动态发送端口附加到某一逻辑端口且送达通知为“已传输”，则运行时将不会传递送达通知。 如果端口实际上是以静态方式配置的，XLANGs 运行时将只侦听送达通知。  
  
> [!NOTE]
>  在 XLANGs 中，端口只是表现得像是用静态方式配置的。  
  
## <a name="when-i-try-to-run-my-application-after-deploying-an-orchestration-with-custom-components-why-do-i-get-the-error-file-or-assembly-name-or-one-of-its-dependencies-not-found"></a>在使用自定义组件部署业务流程后尝试运行应用程序时，为什么系统会显示错误消息“未找到文件或程序集名称或它的某个依赖项”？  
 此错误通常意味着 BizTalk 业务流程引擎无法定位自定义组件。 您必须在作为某一 BizTalk 应用程序宿主的计算机的全局程序集缓存中，安装该应用程序中包括的所有程序集。  
  
## <a name="an-assemblyname-context-property-was-not-valid-error-occurs-when-submitting-a-document-to-a-web-service-via-an-orchestration"></a>在将文档通过业务流程提交到 Web Services 时，发生“AssemblyName 上下文属性无效”错误  
  
### <a name="problem"></a>问题  
 通过业务流程将文档提交到 Web Services 将导致“AssemblyName 上下文属性无效”错误。  
  
### <a name="cause"></a>原因  
 BizTalk 应用程序最初是使用“消息传送”方法设计的，没有涉及业务流程。 此类型的解决方案使用发送端口筛选器来链接接收端口和发送端口，以便文档在接收后传递到发送端口。 在后来，修改了该解决方案，从而包括了绑定到发送端口的业务流程。  
  
### <a name="resolution"></a>解决方法  
 删除发送端口上的筛选器。 如果您将某一筛选器应用于绑定到某一业务流程的发送端口，则消息将常常会绕过该业务流程，从而导致上下文属性错误。  
  
## <a name="a-wrongbodypartexception-occurs-when-handling-a-multipart-mime-message-in-an-orchestration"></a>在业务流程中处理多部分 MIME 消息时，发生了“WrongBodyPartException”异常  
  
### <a name="problem"></a>问题  
 接收到业务流程的多部分 MIME 消息导致**WrongBodyPartException**异常。  
  
### <a name="cause"></a>原因  
 如果错误地指定了各部分的顺序或者消息与您已指定的部分位置不符，则可能会发生此错误。 例如，如果您指定第三个部分是正文部分，但消息到达时在第三个位置中却是标头部分。  
  
### <a name="resolution"></a>解决方法  
 确认正文部分索引设置是正确的，然后确保通过适配器到达的所有消息都与该设置一致。 您可以通过停止业务流程（但保持它被登记），检查在业务流程内失败的 MIME 消息的内容；这将强制发布消息，以便您可以通过使用管理控制台检查它并验证各部分的顺序。  
  
## <a name="multipart-mime-message-part-cannot-be-found"></a>找不到多部分 MIME 消息部分  
  
### <a name="problem"></a>问题  
 尝试检索 MIME 消息的索引值大于 0 的结果引发错误类似于 BizTalk Server 运行时中的一部分"找不到具有索引的多个部分消息 =\<值\>"。  
  
### <a name="cause"></a>原因  
 导致此错误的最常见原因是：  
  
-   MIME 消息所具有的部分少于预期。  
  
-   MIME 消息无法被完全解析。  
  
### <a name="resolution"></a>解决方法  
 您可以通过确保您的代码只检索在预期消息源范围内的消息部分，解决这一问题。 在出现解析问题时，您应该确认原始 MIME 消息在结构上合理并且正确构建。 如果您偶尔遇到解析问题，则确保您的业务流程具有适当的异常处理程序。  
  
## <a name="you-receive-a-the-file-send-adapter-cannot-open-file-for-writing-error-when-sending-using-a-dynamic-send-port"></a>使用动态发送端口进行发送时，收到“文件发送适配器无法打开文件进行写入”错误  
  
### <a name="problem"></a>问题  
 你收到"FILE 发送适配器无法打开文件 *\<filename\>* 为写入"错误在 BizTalk Server 事件日志时发送使用动态发送端口。  
  
 出现此问题时**BTS。OutBoundTransportLocation** orchestration 表达式中定义属性并指定文件传输，例如，以下表达式将导致在运行时此错误：  
  
```  
Message2=Message1;  
Message2(BTS.OutboundTransportLocation) = "file:///c:/test/out";  
MySendPort(Microsoft.XLANGs.BaseTypes.Address)=Message2(BTS.OutboundTransportLocation);  
```  
  
 \- 或 -  
  
```  
Message2=Message1;  
Message2(BTS.OutboundTransportLocation) = "file://mymachine/test/out";  
MySendPort(Microsoft.XLANGs.BaseTypes.Address)=Message2(BTS.OutboundTransportLocation);  
```  
  
### <a name="cause"></a>原因  
 出现此问题的原因在运行时业务流程引擎中删除的文本"**file://"**从指定的 URL。 因此，使用上面的示例时，“file:///c:/test/out”的计算结果为 \c:\test\out，“file://mymachine/test/out”的计算结果为“mymachine\test\out”。  
  
### <a name="resolution"></a>解决方法  
 当指定的 URL **BTS。OutBoundTransportLocation**属性在表达式中，添加或删除"/"字符根据需要。 使用上面的示例**BTS。OutBoundTransportLocation**属性应定义为"file://c:/test/out"，将计算结果为 c:\test\out 或"file:///mymachine/test/out"，将计算为\\\mymachine\test\out。