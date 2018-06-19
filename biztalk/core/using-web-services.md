---
title: 使用 Web 服务 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services
- Web services, about Web services
- orchestrations, Web services
- Web services, orchestrations
ms.assetid: a54261e3-d8ef-4770-8d9a-147685846051
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 236acb42c010effe5c3d45cde1daaf9a7097ede5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288253"
---
# <a name="using-web-services"></a>使用 Web 服务
Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]为 Web 服务提供内置支持。 BizTalk Server 支持所有现有 Web Services 在业务流程中的重用和聚合。 你还可以将业务流程发布（公开）为 Web Services，以将 Web Services 逻辑与业务流程逻辑分开。  
  
 BizTalk Server 实现了对 Web Services 中的本机适配器的支持。 本机适配器支持为 Web Services 提供了可伸缩性、容错功能和跟踪功能，且无需为此编写代码。 有关 SOAP 适配器的信息，请参阅[SOAP 适配器](../core/soap-adapter.md)。  
  
 BizTalk Server 中的 Web 服务支持划分为两个类别： 使用或调用 Web 服务和发布或创建 Web 服务。  
  
 使用或发布 Web 服务之前，你应会在 ASP.NET 中的 XML Web 服务的了解。 XML Web 服务的基础知识的信息，请参阅文章"XML Web Services 基础知识"在[http://go.microsoft.com/fwlink/?LinkId=193057](http://go.microsoft.com/fwlink/?LinkId=193057)。  
  
 **使用 Web 服务**  
  
 可以从业务流程中使用（调用）Web Services。 可以将若干 Web Services 聚合成单个业务流程以完成整个业务流程。  
  
 **发布 Web 服务**  
  
 可以使用 Web Services 发布向导发布 Web Services。 业务流程和发送适配器可以使用这些已发布 Web Services。  
  
 **使用 SOAP 标头**  
  
 BizTalk Server 支持已定义的和未知的 SOAP 标头。 BizTalk Server 为 Web Services 中的每个已定义的 SOAP 标头创建一个上下文属性。  
  
 **Web 服务标准**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应使用任何 Web Services 标准发送和接收。 并非所有的标准都进行了测试。 通常情况下，WCF 支持的标准也受 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 支持。 示例标准包括：  
  
-   WS-ReliableMessaging  
  
-   WS-安全性  
  
-   WS-SecureConversation  
  
-   WS-Trust  
  
-   WS 联合身份验证  
  
-   WS-Addressing  
  
-   WS-Policy  
  
-   WS-MetadataExchange  
  
-   WS-Coordination  
  
-   WS-Atomic  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用 Web 服务](../core/consuming-web-services.md)  
  
-   [发布 Web 服务](../core/publishing-web-services.md)  
  
-   [使用 SOAP 标头](../core/using-soap-headers.md)