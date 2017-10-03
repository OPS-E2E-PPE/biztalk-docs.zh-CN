---
title: "安装和运行动态解析示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4359987-b18c-44f5-a2cf-e30e17ac5e9f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04d697028eb76cf922cf4bf5e5db85c561c67d00
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="installing-and-running-the-dynamic-resolution-sample"></a>安装和运行动态解析示例
此动态解析示例演示 ESB 调度程序和 ESB 调度程序反汇编程序管道组件的典型使用方案。 它演示如何使用组件来动态解析终结点的位置、 设置路由的属性，并解决，并执行在消息级别的 Microsoft BizTalk 映射，而无需使用业务流程。 它还演示了单向和双向消息模式。  
  
> [!NOTE]
>  为获得最佳结果时您熟悉在解决机制[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，应运行[安装和运行解析程序服务示例](../esb-toolkit/installing-and-running-the-resolver-service-sample.md)运行动态解析示例之前。  
  
 示例应用程序包含两个接收位置和两个动态发送端口，此示例使用来演示多个用例的动态解析组件。 每个用例显示了解析程序和适配器中解析的提供程序和适配器提供程序框架中，当结合使用，可以提供各种松耦合的消息传递解决方案的基础。  
  
## <a name="one-way-messaging-scenarios"></a>单向消息传递方案  
 所有单向消息传送 （除了使用 XPATH 解析程序的一个） 的方案使用文件 NAOrderDoc.xml，位于 \Source\Samples\DynamicResolution\Test\Data 文件夹中，作为输入接收位置名为 DynamicResolution_FILE。 有七个单向消息传送示例，由唯一绑定表示所有文件，则必须导入才能执行每个示例。  
  
## <a name="two-way-messaging-scenarios"></a>双向消息处理方案  
 所有的双向消息传递方案使用示例 ESB。NorthAmericanServices Web 位于 http://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx 以将请求消息发布到 BizTalk 服务。 你可以执行此 Web 服务使用 Microsoft InfoPath 或通过从可用 Storm 之类的实用工具[CodePlex](http://go.microsoft.com/fwlink/?LinkID=187762&clcid=0x409) ([http://go.microsoft.com/fwlink/?LinkID=187762&clcid=0x409](http://go.microsoft.com/fwlink/?LinkID=187762&clcid=0x409))。  
  
 每个示例动态解析要提交到示例 ESB 消息的终结点 URL。位于 http://localhost/ESB.CanadianServices/SubmitPOService.asmx CanadianServices Web 服务。 该示例将执行**将订单**操作或**submitPurchase**操作，具体取决于解析过程的结果。 接收位置为双向消息传递方案是 DynamicResolutionReqResp_SOAP。 有 10 双向消息传送示例，由唯一绑定表示所有文件，则必须导入才能执行每个示例。  
  
## <a name="binding-files"></a>绑定文件  
 此示例的绑定文件位于名为 \Source\Samples\DynamicResolution\Samples\Release 的文件夹。  
  
 所有绑定文件名称以 GlobalBank.ESB.DynamicResolution_SubmitOrder_To，跟相对值它们应用到的各个示例的开头。 例如，"文件入站文件出站到使用静态冲突解决程序"示例的绑定文件是 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_STATIC_Bindings.xml。  
  
 每次你导入到 GlobalBank.ESB BizTalk 应用程序，基础文件接收的绑定之一时将重置示例应用程序中的位置。 接收端口名称关联的动态发送端口筛选器。 因此，若要执行测试，你只需将一个绑定文件，则除去适当地命名的消息导入输入文件夹 （对于单向消息传递方案） 或调用 NorthAmerican Web 服务使用 InfoPath、 在内的 Storm 实用程序或任何其他合适的客户端。  
  
## <a name="sample-dependencies"></a>示例依赖关系  
 动态解析示例有大量的作为核心 ESB 安装的一部分的程序集依赖项。 这些程序集如下所示：  
  
-   **Microsoft.Practices.ESB.PipelineComponents.dll**。 这包含 ESB 调度程序管道组件。  
  
-   **Microsoft.Practices.ESB.Resolver.dll**。 这将实现由管道调用冲突解决程序管理器。  
  
-   **Microsoft.Practices.ESB.Resolver.BRE.dll**。 这将会实现此业务规则引擎冲突解决程序。  
  
-   **Microsoft.Practices.ESB.Resolver.STATIC.dll**。 这将实现静态解析程序。  
  
-   **Microsoft.Practices.ESB.Resolver.UDDI.dll**。 这将实现 UDDI 解析程序。  
  
-   **Microsoft.Practices.ESB.Resolver.UDDI3.dll**。 这将实现 UDDI3 解析程序。  
  
-   **Microsoft.Practices.ESB.Resolver.XPATH.dll**。 这将实现由 XPATH 冲突解决程序。  
  
-   **Microsoft.Practices.ESB.Resolver.Schemas.dll**。 这包含的冲突解决程序架构。  
  
-   **Microsoft.Practices.ESB.Adapter.dll**。 这将实现的适配器管理器。  
  
-   **Microsoft.Practices.ESB.Adapter.FTP.dll**。 这将实现 FTP 适配器提供程序。  
  
-   **Microsoft.Practices.ESB.Adapter.FILE.dll**。 这将实现文件适配器提供程序。  
  
-   **Microsoft.Practices.ESB.Adapter.MQSeries.dll**。 这将实现 MQSeries 适配器提供程序。  
  
-   **Microsoft.Practices.ESB.Adapter.WcfBasicHttp.dll**。 这将实现 WCF BasicHttp 适配器提供程序。  
  
-   **Microsoft.Practices.ESB.Adapter.WcfWSHttp.dll**。 这将实现 WCF WSHttp 适配器提供程序。  
  
 动态解析示例也是依赖于前面的解析程序和适配器的正确配置的。 请确保你完成配置这些过程，安装中所述[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。  
  
 本节包含下列主题：  
  
-   [安装动态解析示例](../esb-toolkit/installing-the-dynamic-resolution-sample.md)  
  
-   [运行动态解析示例](../esb-toolkit/running-the-dynamic-resolution-sample.md)