---
title: "使用 WCF 服务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF services
- Windows Communication Foundation (WCF)
ms.assetid: 34fe5e4c-6a92-4627-b2aa-e8b58a708320
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29b984bcda798796565113739c6088af6d569f7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-wcf-services"></a>使用 WCF 服务
Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供内置支持 Windows Communication Foundation (WCF)。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可重复使用和聚合你业务流程中的所有现有 WCF 服务。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在 WCF 服务还实现对本机适配器的支持。 本地适配器支持为 WCF 服务提供了可伸缩性、容错功能和跟踪功能，且用户无需为此编写代码。 有关 WCF 适配器的信息，请参阅[WCF 适配器](../core/wcf-adapters.md)。  
  
 WCF 服务中的支持[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]划分为两个类别： 发布或创建 WCF 服务，或调用或使用 WCF 服务。  
  
 **发布的 WCF 服务**  
  
 您可以使用 WCF 适配器将您的业务流程和架构发布（公开）为 WCF 服务，以便将 WCF 服务逻辑与业务流程逻辑分开。 对于独立 WCF 适配器来说，您可以使用 BizTalk WCF 服务发布向导创建在 Internet 信息服务 (IIS) 中运行的 Web 应用程序承载的独立 WCF 接收位置。 对于进程内 WCF 适配器来说，您可以使用 BizTalk WCF 服务发布向导为任何 WCF 位置发布服务元数据。  发布元数据将允许使用 svcutil.exe 实用程序创建客户端代码。  
  
 **使用 WCF 服务**  
  
 您可以使用 BizTalk WCF 服务使用向导生成 BizTalk 项目（如 BizTalk 业务流程和类型），以便根据 WCF 服务的元数据文档使用 WCF 服务。 元数据允许发送端口以客户端身份访问外部服务。 元数据仅用于对终结点地址、绑定和协议进行描述。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [发布的 WCF 服务](../core/publishing-wcf-services.md)  
  
-   [使用 WCF 服务](../core/consuming-wcf-services.md)  
  
-   [为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)  
  
-   [WCF 适配器演练](../core/wcf-adapter-walkthroughs.md)