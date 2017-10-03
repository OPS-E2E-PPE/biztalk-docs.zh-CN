---
title: "运行预定义的路线上负载增加示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b4400193-20ac-479a-8bf9-b1c99eb35231
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 167d18f0eba624d62b03b3b0a5386fcac04e5b18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="run-a-predefined-itinerary-on-ramp-sample"></a>运行预定义的路线上负载增加示例
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括预定义的 20 路线用例可以执行。 有关这些列表用例，请参阅[示例路线方案](../esb-toolkit/the-sample-itinerary-scenarios.md)。  
  
> [!NOTE]
>  在运行任何示例之前，你必须手动从导入合适的路线绑定文件 \Source\Samples\Itinerary\Install\Binding 文件夹到 GlobalBank.ESB BizTalk 应用程序。 此绑定文件将重置两个动态发送端口上的属性。 导入名为 GlobalBank.ESB.Itinerary_Bindings.xml 的绑定文件。  
  
### <a name="to-run-one-of-the-pre-defined-itinerary-on-ramp-samples"></a>若要运行的预定义的路线入口示例之一  
  
1.  如果 GlobalBank.ESB 应用程序尚未运行，使用 BizTalk 管理控制台来启动它。  
  
2.  在 Windows 资源管理器，打开子文件夹 \Source\Samples\Itinerary\Source\ESB。Itinerary.Test\bin\Debug 其中您安装了 BizTalk ESB 工具包示例中，然后再开始应用程序名为 Esb.Itinerary.Test.exe。  
  
3.  单击**LoadItinerary**按钮，，然后选择名为双向-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml \Source\Samples\Itinerary\Itineraries 文件夹中的示例路线。  
  
4.  在**Web 服务选项**部分中，选择**双向服务**复选框。 这会指示测试客户端来执行的请求-响应路线服务操作。  
  
5.  （可选）选择**使用 WCF 服务**复选框，如果你想要使用 OnRamp.Itinerary.Response.WCF 的应用程序接收位置而非默认 OnRamp.Itinerary.Response.SOAP 接收位置。  
  
6.  单击**LoadMessage**按钮，然后从 \Source\Samples\Itinerary\Test\Data 文件夹然后选择 NAOrderDoc.xml 示例消息。  
  
7.  单击**SubmitRequest**按钮以将请求发送到路线提升服务。 图 1 显示的结果。  
  
 ![在负载增加路线](../esb-toolkit/media/ch6-itineraryonramp.gif "Ch6 ItineraryOnRamp")  
  
 **图 1**  
  
 **运行路线入口示例之一的路线负载技术增加客户端应用程序**  
  
 路线的定义中指定的服务名称直接对应**ServiceName**示例订阅的服务的属性。 在前面的过程 (双向-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml) 中执行路线示例中，执行第一个服务是一种基于业务流程的服务执行转换。 路线的以下节指定此服务。  
  
```  
<Service uuid="" beginTime="" completeTime=""   
    name="Microsoft.Practices.ESB.Services.Transform"  
    type="Orchestration" state="Pending" isRequestResponse="false"  
    position="0" serviceInstanceId="" />  
```  
  
 在此业务流程服务**\<服务 >**元素指定直接绑定业务流程具有图 2 所示的筛选器属性。 请注意业务流程订阅仅对具有值的消息**Microsoft.Practices.ESB.Services.Transform**为**ServiceName**上下文属性、 值**挂起**为**ServiceState**上下文属性和值业务流程的**ServiceType**上下文属性。  
  
 ![筛选器表达式](../esb-toolkit/media/ch6-filterexpression.gif "Ch6 FilterExpression")  
  
 **图 2**  
  
 **直接绑定业务流程路线入口示例中使用筛选器表达式**