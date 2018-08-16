---
title: 运行预定义的路线接入点示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4400193-20ac-479a-8bf9-b1c99eb35231
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e428a9106582e5bad3408cfb6643cc5da21ac74
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996582"
---
# <a name="run-a-predefined-itinerary-on-ramp-sample"></a>运行预定义的路线接入点示例
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括可以执行的 20 预定义的路线用例。 有关这些列表的用例，请参阅[示例路线方案](../esb-toolkit/the-sample-itinerary-scenarios.md)。  
  
> [!NOTE]
>  在运行任何示例之前，您必须手动导入相应的路线的绑定文件从 \Source\Samples\Itinerary\Install\Binding 文件夹到 GlobalBank.ESB BizTalk 应用程序。 此绑定文件将重置两个动态发送端口上的属性。 导入名为 GlobalBank.ESB.Itinerary_Bindings.xml 的绑定文件。  
  
### <a name="to-run-one-of-the-pre-defined-itinerary-on-ramp-samples"></a>若要运行其中一个预定义路线接入点示例  
  
1. 如果尚未运行 GlobalBank.ESB 应用程序，使用 BizTalk 管理控制台来启动它。  
  
2. 在 Windows 资源管理器中，打开子文件夹 \Source\Samples\Itinerary\Source\ESB。Itinerary.Test\bin\Debug 其中您安装了 BizTalk ESB 工具包示例中，然后再开始应用程序名为 Esb.Itinerary.Test.exe。  
  
3. 单击**LoadItinerary**按钮，并选择示例路线名为 TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml \Source\Samples\Itinerary\Itineraries 文件夹中。  
  
4. 在中**Web 服务选项**部分中，选择**双向服务**复选框。 这会指示测试客户端来执行请求-响应路线服务操作。  
  
5. （可选）选择**使用 WCF 服务**复选框，如果你想要使用 OnRamp.Itinerary.Response.WCF 的应用程序接收位置而不是默认 OnRamp.Itinerary.Response.SOAP 接收位置。  
  
6. 单击**LoadMessage**按钮，并从 \Source\Samples\Itinerary\Test\Data 文件夹选择 NAOrderDoc.xml 示例消息。  
  
7. 单击**SubmitRequest**按钮以将请求发送到路线接入点服务。 图 1 显示的结果。  
  
   ![在负载增加路线](../esb-toolkit/media/ch6-itineraryonramp.gif "Ch6-ItineraryOnRamp")  
  
   **图 1**  
  
   **运行路线接入点示例之一的路线接入点客户端应用程序**  
  
   路线的定义中指定的服务的名称直接对应于**ServiceName**示例订阅的服务的属性。 在上一过程 (TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml) 中执行路线示例中，执行的第一个服务是基于业务流程的服务，执行的转换。 路线的以下节指定此服务。  
  
```  
<Service uuid="" beginTime="" completeTime=""   
    name="Microsoft.Practices.ESB.Services.Transform"  
    type="Orchestration" state="Pending" isRequestResponse="false"  
    position="0" serviceInstanceId="" />  
```  
  
 在此业务流程服务**\<服务\>** 元素指定了图 2 所示的筛选器属性的直接绑定业务流程。 请注意，业务流程订阅仅向具有的值的消息**Microsoft.Practices.ESB.Services.Transform**有关**ServiceName**上下文属性、 值**挂起**有关**ServiceState**上下文属性和值的业务流程用于**ServiceType**上下文属性。  
  
 ![筛选表达式](../esb-toolkit/media/ch6-filterexpression.gif "Ch6-FilterExpression")  
  
 **图 2**  
  
 **路线接入点示例中使用直接绑定业务流程筛选器表达式**