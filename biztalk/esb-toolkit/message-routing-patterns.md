---
title: 消息路由模式 |Microsoft Docs
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
ms.openlocfilehash: 7233c5d5f5a3669cf23931afc29dfaac8548dc3d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022083"
---
# <a name="message-routing-patterns"></a>消息路由模式
消息路由模式定义消息路由到其目标终结点的经验证的准则。 路由可以是静态配置的结果，也可以将它动态地配置基于许多条件和使用多种方法。  
  
## <a name="message-router"></a>消息路由器  
 消息路由器模式确定基于一组条件的消息的收件人。 此模式的详细说明，请参阅[消息路由器](http://go.microsoft.com/fwlink/?LinkId=186844)([http://go.microsoft.com/fwlink/?LinkId=186844](http://go.microsoft.com/fwlink/?LinkId=186844)) 企业集成模式站点上。  
  
 在路线设计器中此模式的实现是一系列[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线的路由服务和单个基于内容的解析程序。 路线的路由服务是消息的负责升级 Microsoft BizTalk 消息上下文中的消息路由属性或显式路由。  
  
 可以选择路线的路由服务提供的[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，如下所示：  
  
- 定义路线的路由服务使用消息传送的扩展程序，以在使用路线设计器的 BizTalk 管道中执行。  
  
- 定义与业务流程扩展程序以使用路线设计器执行路由使用 BizTalk 发送端口业务流程执行路线的路由服务。  
  
  与路线的路由服务相关联的冲突解决程序确定基于消息内容的消息接收的方。 您可以选择从解析程序，支持基于内容的路由提供[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，也可以实现您自己的解析程序。  
  
  有关实现此模式中的示例[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，请参阅以下资源：  
  
- [如何：使用 UDDI 绑定密钥搜索解析服务终结点](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-binding-key-search.md)  
  
- [如何：使用 UDDI 类别搜索解析服务终结点](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-category-search.md)  
  
## <a name="content-based-router"></a>基于内容的路由器  
 基于内容的路由器模式确定基于消息内容的消息接收的方。 此模式的详细说明，请参阅[基于内容的路由器](http://go.microsoft.com/fwlink/?LinkId=186839)([http://go.microsoft.com/fwlink/?LinkId=186839](http://go.microsoft.com/fwlink/?LinkId=186839)) 企业集成模式站点上。  
  
 在路线设计器中此模式的实现是一系列[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线的路由服务和单个基于内容的解析程序。 路线的路由服务是负责升级 BizTalk 消息上下文中的消息路由属性或显式将消息路由。  
  
 可以选择路线的路由服务提供的[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，如下所示：  
  
- 定义具有消息传送的扩展程序，以在使用路线设计器的 BizTalk 管道中执行的路线的路由服务。  
  
- 定义与业务流程扩展程序以使用路线设计器中，后者将执行路由使用 BizTalk 发送端口业务流程执行路线路由服务。  
  
- 定义具有一个 broker 消息传递扩展程序以使用路线设计器的 BizTalk 管道中执行的路线 broker 服务。  
  
  与路线的路由服务相关联的冲突解决程序确定基于消息内容的消息接收的方。 您可以选择从以下冲突解决程序，支持基于内容的路由提供[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]:  
  
- **XPATH 冲突解决程序**。 通过使用此解析程序，你可以使用 XPATH 查询的消息内容进行路由。  
  
- **BRE 冲突解决程序**。 通过使用此解析程序，可以从使用 BizTalk 规则引擎的消息内容来检索路由信息。  
  
- **消息上下文冲突解决程序**。 通过使用此解析程序，可以检索一条消息的内容从 BizTalk 消息上下文时与关联[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线 broker 服务。  
  
  > [!NOTE]
  >  除了前面的实现方案中，可以作为基于消息传送或业务流程基于服务开发的自定义基于内容的解析程序和路线的路由解决方案。 在这种情况下，您可能需要实现的扩展器[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线设计器与进行互操作的冲突解决程序和路线服务。  
  
  有关示例的此实现中，请参阅以下资源：  
  
- [安装和运行路线接入点示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)  
  
- [如何：使用已知消息类型的业务规则策略实现基于内容的路由](../esb-toolkit/apply-content-based-routing-using-business-rules-policy-for-known-message-type.md)  
  
- [如何：使用业务规则策略动态路由基于消息上下文的消息](../esb-toolkit/dynamically-route-messages-based-on-message-context-using-business-rules-policy.md)  
  
## <a name="routing-slip"></a>传送名单  
 传送名单模式描述了一条消息必须路由通过一系列中预定义的顺序，不可能在设计时已知的组件的方案。 此模式的详细说明，请参阅[传送名单](http://go.microsoft.com/fwlink/?LinkId=186840)([http://go.microsoft.com/fwlink/?LinkId=186840](http://go.microsoft.com/fwlink/?LinkId=186840)) 企业集成模式站点上。  
  
 此模式的实现提供通过[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]; 其实现取决于提交的消息以基于路线的处理的客户端应用程序的类型：  
  
- **服务代理**。 使用此类型的应用程序，配置[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线选择器管道组件与负载增加并将关联的路线的冲突解决程序选择相应[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线。 路线属性可以配置为静态属性使用路线冲突解决程序，或它们可以配置为使用 BizTalk 规则引擎和 BRI 冲突解决程序的动态属性。  
  
- **高级客户端**。 使用此类型的应用程序，配置[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]接入点的路线选择器管道组件和路线静态解析程序。 客户端应用程序发送一个路线引用标头，其中包含路线名称、 版本和跟踪标识符的消息。  
  
- **自适应客户端**。 使用此类型的应用程序，客户端应用程序调用解析程序服务，这反过来，通过将作为请求消息传递客户端状态标识路线的引用。 路线得到解决后，客户端应用程序将使用路线引用消息提交如上述的高级客户端方案中所示相同的方式。  
  
  有关实现此模式的详细信息，请参阅以下资源：  
  
- [如何：使用业务规则策略选择路线](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
- [如何：转换消息并使用路线传送名单将生成的消息路由至文件位置](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
  > [!NOTE]
  >  除了前面的方案中，可以开发自定义路线的冲突解决程序和路线的路由服务。 你可以考虑在路线设计器中创建用于自定义路线服务的设计器扩展器。  
  
## <a name="scatter-gather"></a>散播-聚集  
 散播-聚集模式可以使信息发送到多个收件人，并聚合其响应;这会导致一条消息。 此模式的详细说明，请参阅[散播-聚集](http://go.microsoft.com/fwlink/?LinkId=186841)([http://go.microsoft.com/fwlink/?LinkId=186841](http://go.microsoft.com/fwlink/?LinkId=186841)) 企业集成模式站点上。  
  
 有关实现此模式的示例，请参阅[安装和运行分散-集中示例](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md)示例。  
  
## <a name="recipient-list"></a>收件人列表  
 收件人列表模式向一个或多个收件人地址中的路由消息的解决方案。 收件人列表可以是以静态方式定义 （这意味着它具有的固定的列表的收件人） 或动态。 此模式的详细说明，请参阅[收件人列表](http://go.microsoft.com/fwlink/?LinkId=186842)([http://go.microsoft.com/fwlink/?LinkId=186842](http://go.microsoft.com/fwlink/?LinkId=186842)) 企业集成模式站点上。  
  
 在路线设计器中此模式的实现是一系列[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线的路由服务和多个冲突解决程序。 路线的路由服务负责克隆一条消息，然后使用其 BizTalk 消息上下文属性显式将消息路由。  
  
 可以选择路线的路由服务提供的[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，如下所示：  
  
- 定义路线的路由服务使用消息传送的扩展程序，以使用路线设计器在 BizTalk 管道中执行。  
  
- 定义与消息传送的扩展程序，以使用路线设计器中，后者将执行路由使用 BizTalk 发送端口业务流程作为执行路线的路由服务。  
  
  与路线的路由服务相关联的冲突解决程序确定基于消息内容的消息接收的方。 可以选择冲突解决程序所提供的一套[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]要实现此方案。 有关实现此模式的详细信息，请参阅以下资源：  
  
- [如何：使用路线传送名单将单条消息路由至多个收件人](../esb-toolkit/route-a-single-message-to-multiple-recipients-using-an-itinerary-routing-slip.md)  
  
## <a name="splitter"></a>拆分器  
 拆分器模式在单个消息需要进行拆分为多个消息时解决问题。 此模式的详细说明，请参阅[Splitter](http://go.microsoft.com/fwlink/?LinkId=186843) ([http://go.microsoft.com/fwlink/?LinkId=186843](http://go.microsoft.com/fwlink/?LinkId=186843)) 企业集成模式站点上。 有关实现此模式的详细信息，请参阅以下资源：  
  
-   [如何：拆分交换并使用不同的路线将生成的消息路由至多个文件位置](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md)