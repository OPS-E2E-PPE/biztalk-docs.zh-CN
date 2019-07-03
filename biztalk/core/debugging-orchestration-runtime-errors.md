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
# <a name="debugging-orchestration-runtime-errors"></a>调试业务流程运行时错误
本部分包含一系列问题与解答可帮助您解决您的业务流程的运行时问题。  
  
## <a name="why-do-i-get-intermittent-subscription-errors-when-sending-to-a-child-orchestration-that-was-just-started-by-the-parent"></a>将发送到只需启动了父级的子业务流程时，为何遇到间歇订阅错误？  
 订阅错误"在找不到订阅"是争用条件的结果。 在进程结果依赖于过程发生的特定顺序时发生的争用条件。 在这种情况下，会出现此子业务流程尚未启动的时间，以接收父发送的消息时。  
  
 若要避免此问题，子业务流程无法发送消息返回到父级时它已启动并且已准备好接收的消息。 这样一来，启动它的父业务流程发送消息前没有为接收方会知道。  
  
## <a name="why-do-i-get-errors-when-i-attach-a-dynamic-send-port-to-a-logical-port"></a>将动态发送端口附加到逻辑端口时，为什么收到错误？  
 动态端口没有设计为继承的所有属性和特性为其分配的端口。 动态端口只获取地址;它不会继承与逻辑端口相关联的其他信息。  
  
 例如，如果将动态发送端口附加到逻辑端口且送达通知 = 传输，运行时将不会传递送达通知。 如果端口实际上已设置，以静态方式将 XLANGs 运行时只侦听送达通知。  
  
> [!NOTE]
>  在 XLANGs，端口只是表现已以静态方式配置它们。  
  
## <a name="when-i-try-to-run-my-application-after-deploying-an-orchestration-with-custom-components-why-do-i-get-the-error-file-or-assembly-name-or-one-of-its-dependencies-not-found"></a>当我尝试运行我的应用程序部署自定义组件与业务流程后时，为什么我收到错误"文件或程序集名称或其某个依赖项找不到"？  
 此错误通常意味着 BizTalk 业务流程引擎找不到自定义组件。 必须安装在 BizTalk 应用程序中托管的应用程序的计算机的全局程序集缓存中包含的所有程序集。  
  
## <a name="an-assemblyname-context-property-was-not-valid-error-occurs-when-submitting-a-document-to-a-web-service-via-an-orchestration"></a>提交到业务流程通过 Web 服务的文档时，发生"AssemblyName 上下文属性不是有效的"错误  
  
### <a name="problem"></a>问题  
 将文档提交到 Web 服务通过业务流程将导致"AssemblyName 上下文属性无效"错误。  
  
### <a name="cause"></a>原因  
 BizTalk 应用程序最初是使用"消息传送"方法而无需涉及业务流程设计的。 此类型的解决方案使用发送端口筛选器来链接接收端口和发送端口，以便该文档将传递给在收到后的发送端口。 更高版本，修改了该解决方案包含已绑定到发送端口业务流程。  
  
### <a name="resolution"></a>解决方法  
 删除发送端口上的筛选器。 如果绑定到业务流程的发送端口应用筛选器，消息通常将绕过该业务流程，并导致上下文属性错误。  
  
## <a name="a-wrongbodypartexception-occurs-when-handling-a-multipart-mime-message-in-an-orchestration"></a>当处理业务流程中的多部分 MIME 消息时出现"WrongBodyPartException"  
  
### <a name="problem"></a>问题  
 接收到业务流程的多部分 MIME 消息会导致**WrongBodyPartException**异常。  
  
### <a name="cause"></a>原因  
 如果未正确指定的部分的顺序或者消息不符合您指定的部分位置可以出现此错误。 例如，如果指定的第三部分是正文部分，但消息到达的第三个位置中的标头部分。  
  
### <a name="resolution"></a>解决方法  
 验证正文部分索引设置正确，然后确保通过适配器到达的所有消息都都与该设置一致。 可以检查失败的业务流程内部停止业务流程的 MIME 消息的内容 （但保持它被登记）;这将强制使您可以对其使用管理控制台进行检查并验证的部分的顺序发布消息。  
  
## <a name="multipart-mime-message-part-cannot-be-found"></a>找不到多部分 MIME 消息部分  
  
### <a name="problem"></a>问题  
 尝试检索 MIME 消息部分的索引值大于 0 个结果在 BizTalk Server 运行时引发错误类似于"找不到具有索引的多部分消息 =\<值\>"。  
  
### <a name="cause"></a>原因  
 此错误的最常见原因是：  
  
-   MIME 消息具有的部分少于预期。  
  
-   无法完全分析 MIME 消息。  
  
### <a name="resolution"></a>解决方法  
 您可以解决此问题通过确保你的代码检索预期消息源范围内的消息部分。 如果解析问题时，应验证原始 MIME 消息是结构上合理并且正确构建。 如果希望偶尔遇到解析问题，请确保您的业务流程具有适当的异常处理程序。  
  
## <a name="you-receive-a-the-file-send-adapter-cannot-open-file-for-writing-error-when-sending-using-a-dynamic-send-port"></a>发送使用动态发送端口时收到"文件发送适配器无法打开文件进行写入"错误  
  
### <a name="problem"></a>问题  
 你收到"文件发送适配器无法打开文件 *\<文件名\>* 进行写入"错误时使用动态发送，BizTalk Server 事件日志中的发送端口。  
  
 发生此问题时**BTS。OutBoundTransportLocation**属性在业务流程表达式中定义和指定的文件传输，例如以下表达式将导致此错误在运行时：  
  
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
 发生此问题的原因在运行时业务流程引擎中删除的文本"**file://"** 从指定的 URL。 因此，使用上面的示例，作为 \c:\test\out 计算"file:///c:/test/out"和"file://mymachine/test/out"计算结果为 \c: \test\out。  
  
### <a name="resolution"></a>解决方法  
 指定的 URL 时**BTS。OutBoundTransportLocation**属性在表达式中，添加或删除"/"字符根据需要。 使用上面的示例**BTS。OutBoundTransportLocation**属性应定义为"file://c:/test/out"，将计算结果为 c:\test\out 或"file:///mymachine/test/out"计算结果为\\\mymachine\test\out。