---
title: 使用 Web 服务 |Microsoft Docs
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
ms.openlocfilehash: 24af6961e888f8cda21e8d280451382160e2b5af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262119"
---
# <a name="using-web-services"></a>使用 Web 服务
Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]为 Web services 提供内置支持。 BizTalk Server，可以重用和聚合业务流程中的所有现有 Web 服务。 你还可以发布 （公开） 您的业务流程作为 Web 服务以单独的 Web 服务逻辑与业务流程逻辑。  
  
 BizTalk Server 实现 Web 服务中的本地适配器的支持。 本机适配器支持提供了可伸缩性、 容错能力和跟踪功能的 Web 服务，而无需编写一行代码。 有关 SOAP 适配器的信息，请参阅[SOAP 适配器](../core/soap-adapter.md)。  
  
 在 BizTalk Server 中的 Web services 支持分为两类： 使用或调用 Web 服务以及发布或创建 Web 服务。  
  
 在使用或发布 Web 服务之前，您应该了解 XML Web services 的 ASP.NET 中。 有关 XML Web services 的基础知识，请参阅文章"XML Web Services 基础"网址[ http://go.microsoft.com/fwlink/?LinkId=193057 ](http://go.microsoft.com/fwlink/?LinkId=193057)。  
  
 **使用 Web 服务**  
  
 您可以使用 （调用） Web 服务从业务流程中。 可以将若干 Web services 聚合成单个业务流程以完成整个业务流程。  
  
 **发布 Web services**  
  
 你可以发布 Web 服务使用 BizTalk Web Services 发布向导。 业务流程和发送适配器可以使用这些已发布的 Web 服务。  
  
 **使用 SOAP 标头**  
  
 BizTalk Server 定义的和未知的 SOAP 标头提供支持。 BizTalk Server Web 服务中创建每个定义的 SOAP 标头上下文属性。  
  
 **Web 服务标准**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应适用于任何 Web Services 标准发送和接收时。 并非所有的标准进行了测试。 通常情况下，WCF 支持的标准也受[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 示例标准包括：  
  
-   WS-ReliableMessaging  
  
-   WS-Security  
  
-   WS-SecureConversation  
  
-   WS-Trust  
  
-   WS-Federation  
  
-   WS-Addressing  
  
-   WS-Policy  
  
-   WS-MetadataExchange  
  
-   WS-Coordination  
  
-   WS-Atomic  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用 Web 服务](../core/consuming-web-services.md)  
  
-   [发布 Web 服务](../core/publishing-web-services.md)  
  
-   [使用 SOAP 标头](../core/using-soap-headers.md)