---
title: 安装和运行动态解析示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4359987-b18c-44f5-a2cf-e30e17ac5e9f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0939111bc0a62ecf31286045f412ed160a97c3f9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967726"
---
# <a name="installing-and-running-the-dynamic-resolution-sample"></a>安装和运行动态解析示例
动态解析示例演示了用于 ESB 调度程序和 ESB 调度程序反汇编程序管道组件的典型使用方案。 它演示了如何使用组件动态解析终结点位置、 设置路由属性和解析和执行而无需使用业务流程在消息级别的 Microsoft BizTalk 映射。 它还演示了单向和双向消息传送模式。  
  
> [!NOTE]
>  获得最佳结果，在您熟悉内解决机制[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，则应运行[安装和运行解析程序服务示例](../esb-toolkit/installing-and-running-the-resolver-service-sample.md)运行动态解析示例之前。  
  
 示例应用程序包含两个接收位置和两个动态发送端口，该示例使用演示多个用例的动态解析组件。 每个用例显示了冲突解决程序和适配器提供程序中解析和适配器提供程序框架，在组合中，使用时如何提供各种松散耦合的消息传送解决方案的基础。  
  
## <a name="one-way-messaging-scenarios"></a>单向消息传送方案  
 所有单向消息传送方案 （只使用 XPATH 解析程序） 使用 \Source\Samples\DynamicResolution\Test\Data 文件夹中的文件 NAOrderDoc.xml，作为输入接收位置名为 DynamicResolution_FILE。 有七个单向消息传送示例中，所有由唯一绑定文件，您必须导入之前执行的每个示例。  
  
## <a name="two-way-messaging-scenarios"></a>双向消息传送方案  
 所有的双向消息传送方案使用 ESB 的示例。NorthAmericanServices Web 服务位于 http://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx 以将请求消息发布到 BizTalk。 您可以使用 Microsoft InfoPath 此 Web 服务或通过可从 Storm 之类的实用工具[CodePlex](http://go.microsoft.com/fwlink/?LinkID=187762&clcid=0x409)。  
  
 每个示例动态解析终结点 URL，以便提交到 ESB 的示例消息。CanadianServices Web 服务位于http://localhost/ESB.CanadianServices/SubmitPOService.asmx。 该示例将执行**submitOrder**操作或**submitPurchase**操作，具体取决于解析过程的结果。 双向消息传送方案的接收位置是 DynamicResolutionReqResp_SOAP。 有 10 个双向消息传送示例中，所有由唯一绑定文件，您必须导入之前执行的每个示例。  
  
## <a name="binding-files"></a>绑定文件  
 此示例的绑定文件位于名为 \Source\Samples\DynamicResolution\Samples\Release 的文件夹。  
  
 所有启动 GlobalBank.ESB.DynamicResolution_SubmitOrder_To，跟相对值的指示它们适用于各个示例使用绑定文件的名称。 例如，"文件入站文件的出站到使用静态的冲突解决程序"示例的绑定文件是 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_STATIC_Bindings.xml。  
  
 每次导入一个绑定接收到 GlobalBank.ESB BizTalk 应用程序，基础文件中的示例应用程序的位置重置。 接收端口名称相关的动态发送端口筛选器。 因此，若要执行测试，您只需导入一个绑定文件，则除去适当命名的消息到输入文件夹 （适用于单向消息传送方案） 或调用使用 InfoPath、 Storm 实用程序，或任何其他的 NorthAmerican Web 服务合适的客户端。  
  
## <a name="sample-dependencies"></a>示例依赖关系  
 动态解析示例数是核心 ESB 安装的一部分的程序集具有依赖关系。 这些程序集如下所示：  
  
- **Microsoft.Practices.ESB.PipelineComponents.dll**。 这包含 ESB 调度程序管道组件。  
  
- **Microsoft.Practices.ESB.Resolver.dll**。 这会实现调用管道的解析程序管理器。  
  
- **Microsoft.Practices.ESB.Resolver.BRE.dll**。 这会实现业务规则引擎冲突解决程序。  
  
- **Microsoft.Practices.ESB.Resolver.STATIC.dll**。 这会实现静态冲突解决程序。  
  
- **Microsoft.Practices.ESB.Resolver.UDDI.dll**。 这会实现 UDDI 解析程序。  
  
- **Microsoft.Practices.ESB.Resolver.UDDI3.dll**。 这会实现 UDDI3 冲突解决程序。  
  
- **Microsoft.Practices.ESB.Resolver.XPATH.dll**。 这会实现 XPATH 冲突解决程序。  
  
- **Microsoft.Practices.ESB.Resolver.Schemas.dll**。 这包含冲突解决程序架构。  
  
- **Microsoft.Practices.ESB.Adapter.dll**。 这会实现适配器管理器。  
  
- **Microsoft.Practices.ESB.Adapter.FTP.dll**。 这会实现 FTP 适配器提供程序。  
  
- **Microsoft.Practices.ESB.Adapter.FILE.dll**。 这会实现文件适配器提供程序。  
  
- **Microsoft.Practices.ESB.Adapter.MQSeries.dll**。 这会实现 MQSeries 适配器提供程序。  
  
- **Microsoft.Practices.ESB.Adapter.WcfBasicHttp.dll**。 这将实现 WCF BasicHttp 适配器提供程序。  
  
- **Microsoft.Practices.ESB.Adapter.WcfWSHttp.dll**。 这会实现 Wcf-wshttp 适配器提供程序。  
  
  动态解析示例也是依赖于前面的冲突解决程序和适配器的正确配置。 请确保安装中所述完成配置，这些过程[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。  
  
  本节包含下列主题：  
  
- [安装动态解析示例](../esb-toolkit/installing-the-dynamic-resolution-sample.md)  
  
- [运行动态解析示例](../esb-toolkit/running-the-dynamic-resolution-sample.md)
