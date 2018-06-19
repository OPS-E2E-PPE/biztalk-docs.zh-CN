---
title: 消息路由模式 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d95c5ba0-122f-4793-bfce-a95830dfe094
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a332a8ab942363ff5224f34149b345c9c7d40698
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22296885"
---
# <a name="message-routing-patterns"></a>消息路由模式
消息路由模式定义消息路由到其目标终结点的经验证的准则。 路由可以是静态配置的结果，也可以将它动态配置基于许多条件和使用多种方法。  
  
## <a name="message-router"></a>消息路由器  
 消息路由器模式确定基于一组条件的消息的接收方。 有关此模式的详细说明，请参阅[消息路由器](http://go.microsoft.com/fwlink/?LinkId=186844)([http://go.microsoft.com/fwlink/?LinkId=186844](http://go.microsoft.com/fwlink/?LinkId=186844)) 上的企业集成模式站点。  
  
 此模式在路线设计器中的实现是的组合[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线路由服务和单个基于内容的解析程序。 路线路由服务是消息的负责将提升 Microsoft BizTalk 消息的上下文中的消息路由属性或显式路由。  
  
 你可以选择提供的路线路由服务[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，如下所示：  
  
-   定义一个要在 BizTalk 管道中使用路线设计器执行的消息传送的扩展程序添加的路线路由服务。  
  
-   定义要作为使用路线设计器执行路由使用 BizTalk 发送端口业务流程执行业务流程扩展程序的路线路由服务。  
  
 与路线路由服务关联的冲突解决程序确定基于消息内容消息接收的方。 你可以选择冲突解决程序从该支持基于内容的路由提供[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，或者你可以实现你自己的解析程序。  
  
 有关实现此模式中的示例[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，请参阅以下资源：  
  
-   [如何： 解决使用绑定密钥搜索 UDDI 服务终结点](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-binding-key-search.md)  
  
-   [如何： 解决使用 UDDI 类别搜索的服务终结点](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-category-search.md)  
  
## <a name="content-based-router"></a>基于内容的路由器  
 基于内容的路由器模式确定基于消息内容的消息的接收方。 有关此模式的详细说明，请参阅[基于内容的路由器](http://go.microsoft.com/fwlink/?LinkId=186839)([http://go.microsoft.com/fwlink/?LinkId=186839](http://go.microsoft.com/fwlink/?LinkId=186839)) 上的企业集成模式站点。  
  
 此模式在路线设计器中的实现是的组合[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线路由服务和单个基于内容的解析程序。 路线路由服务是负责将提升 BizTalk 消息上下文中的消息路由属性或显式路由消息。  
  
 你可以选择提供的路线路由服务[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，如下所示：  
  
-   定义具有一个要在 BizTalk 管道中使用路线设计器执行的消息传送的扩展程序添加的路线路由服务。  
  
-   定义具有 orchestration 扩展程序作为使用路线设计器中，后者将执行路由使用 BizTalk 发送端口业务流程执行的路线路由服务。  
  
-   定义具有 broker 消息扩展，程序在使用路线设计器的 BizTalk 管道中执行的路线 broker 服务。  
  
 与路线路由服务关联的冲突解决程序确定基于消息内容的消息的接收方。 你可以选择从以下冲突解决程序该支持基于内容的路由提供[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]:  
  
-   **XPATH 冲突解决程序**。 通过使用此解析程序，你可以使用 XPATH 查询的消息内容进行路由。  
  
-   **BRE 冲突解决程序**。 通过使用此解析程序，你可以从使用 BizTalk 规则引擎的消息内容检索路由信息。  
  
-   **消息上下文冲突解决程序**。 通过使用此解析程序，你可以一条消息的内容从 BizTalk 消息上下文时检索与之关联[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线 broker 服务。  
  
    > [!NOTE]
    >  除了前面的实现方案中，你可以开发自定义基于内容的解析程序和路线路由解决方案作为基于消息的或基于业务流程的服务。 在这种情况下，你可能需要实现的扩展器[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]解析器和路线与路线设计器进行互操作的服务。  
  
 有关示例的此实现中，请参阅以下资源：  
  
-   [安装和运行路线上负载增加示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)  
  
-   [如何： 实现基于内容的路由使用业务规则的一个已知的消息类型的策略](../esb-toolkit/apply-content-based-routing-using-business-rules-policy-for-known-message-type.md)  
  
-   [如何： 动态路由基于消息上下文使用业务规则策略在一条消息](../esb-toolkit/dynamically-route-messages-based-on-message-context-using-business-rules-policy.md)  
  
## <a name="routing-slip"></a>路由滑动  
 路由滑动模式描述中的消息必须路由通过一系列中预定义的顺序，不可能在设计时已知的组件的方案。 有关此模式的详细说明，请参阅[路由滑动](http://go.microsoft.com/fwlink/?LinkId=186840)([http://go.microsoft.com/fwlink/?LinkId=186840](http://go.microsoft.com/fwlink/?LinkId=186840)) 上的企业集成模式站点。  
  
 此模式的实现提供通过[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]; 其实现取决于提交邮件以进行基于路线的处理的客户端应用程序的类型：  
  
-   **服务代理**。 使用此类型的应用程序，配置[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线选择器管道组件与负载增加并将关联一个路线冲突解决程序选择相应[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线。 路线属性可能配置为使用路线冲突解决程序的静态属性或可以将它们配置为使用 BizTalk 规则引擎和 BRI 冲突解决程序的动态属性。  
  
-   **高级客户端**。 使用此类型的应用程序，配置[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线静态解析程序路线选择器管道组件与负载增加。 客户端应用程序发送一条消息有路线引用标头，其中包含路线名称、 版本和跟踪标识符。  
  
-   **自适应客户端**。 使用此类型的应用程序，客户端应用程序时，将调用解析程序服务，这反过来，通过将作为请求消息传递客户端状态标识路线的引用。 如果被解析路线，客户端应用程序将在上述情景中高级客户端与相同的方式提交路线引用的消息。  
  
 有关实现此模式的详细信息，请参阅以下资源：  
  
-   [如何： 选择使用业务规则策略路线](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [如何： 转换一条消息，并将生成的消息路由到使用路线的路由滑动某个文件位置](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
    > [!NOTE]
    >  除了前面的方案中，你可以开发自定义的路线解析程序和路线路由服务。 你可以考虑在路线设计器中创建用于自定义路线服务的设计器扩展器。  
  
## <a name="scatter-gather"></a>散播-聚集  
 散播-聚集模式使消息发送到多个收件人并聚合其响应中;这会导致单个消息。 有关此模式的详细说明，请参阅[散播-聚集](http://go.microsoft.com/fwlink/?LinkId=186841)([http://go.microsoft.com/fwlink/?LinkId=186841](http://go.microsoft.com/fwlink/?LinkId=186841)) 上的企业集成模式站点。  
  
 有关实现此模式的示例，请参阅[安装和运行散播-聚集示例](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md)示例。  
  
## <a name="recipient-list"></a>收件人列表  
 收件人列表模式对一个或多个收件人地址方案解决方案中的路由消息。 收件人列表可以是静态定义 （这意味着它具有的固定的列表的收件人） 或动态。 有关此模式的详细说明，请参阅[收件人列表](http://go.microsoft.com/fwlink/?LinkId=186842)([http://go.microsoft.com/fwlink/?LinkId=186842](http://go.microsoft.com/fwlink/?LinkId=186842)) 上的企业集成模式站点。  
  
 此模式在路线设计器中的实现是的组合[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线路由服务和多个冲突解决程序。 路线路由服务负责克隆一条消息，然后使用其 BizTalk 消息上下文属性来显式将消息路由。  
  
 你可以选择提供的路线路由服务[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，如下所示：  
  
-   定义一个要在 BizTalk 管道使用路线设计器中执行的消息传送的扩展程序添加的路线路由服务。  
  
-   定义一个作为使用路线设计器中，后者将执行路由使用 BizTalk 发送端口业务流程执行的消息传送的扩展程序添加的路线路由服务。  
  
 与路线路由服务关联的冲突解决程序确定基于消息内容的消息的接收方。 你可以选择冲突解决程序提供的一套[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]为了实现此方案。 有关实现此模式的详细信息，请参阅以下资源：  
  
-   [如何： 将一条消息路由到多个收件人使用路线路由的滑动](../esb-toolkit/route-a-single-message-to-multiple-recipients-using-an-itinerary-routing-slip.md)  
  
## <a name="splitter"></a>拆分器  
 拆分模式解决了问题，一条消息需要拆分为多个消息时。 有关此模式的详细说明，请参阅[拆分器](http://go.microsoft.com/fwlink/?LinkId=186843)([http://go.microsoft.com/fwlink/?LinkId=186843](http://go.microsoft.com/fwlink/?LinkId=186843)) 上的企业集成模式站点。 有关实现此模式的详细信息，请参阅以下资源：  
  
-   [如何： 拆分将交换，并将生成的消息路由到多个使用不同路线的文件位置](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md)