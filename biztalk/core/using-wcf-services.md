---
title: 使用 WCF 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF services
- Windows Communication Foundation (WCF)
ms.assetid: 34fe5e4c-6a92-4627-b2aa-e8b58a708320
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81082cacafb1f04d54920648d8f588a4b2ccc50a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396738"
---
# <a name="using-wcf-services"></a>使用 WCF 服务
Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供内置支持为 Windows Communication Foundation (WCF)。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使您可以重用和聚合业务流程中的所有现有 WCF 服务。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 此外实现 WCF 服务中的本地适配器的支持。 本机适配器支持提供了可伸缩性、 容错能力和跟踪功能为 WCF 服务，而无需编写代码。 有关 WCF 适配器的信息，请参阅[WCF 适配器](../core/wcf-adapters.md)。  
  
 WCF 中的服务支持[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]划分为两个类别： 发布或创建 WCF 服务时，或调用或使用 WCF 服务。  
  
 **发布 WCF 服务**  
  
 您可以发布 （公开） 您的业务流程和架构作为 WCF 服务与 WCF 适配器，以便单独的 WCF 服务逻辑与业务流程逻辑。 对于独立 WCF 适配器，可以使用 BizTalk WCF 服务发布向导创建独立 WCF 接收位置由运行在 Internet 信息服务 (IIS) Web 应用程序承载。 对于进程内 WCF 适配器，可以将发布为 BizTalk WCF 服务发布向导与任何 WCF 位置的服务元数据。  元数据的发布允许使用 svcutil.exe 实用程序的客户端代码的创建。  
  
 **使用 WCF 服务**  
  
 可以使用 BizTalk WCF 服务使用向导生成 BizTalk 项目，如 BizTalk 业务流程和类型，以便使用基于 WCF 服务的元数据文档的 WCF 服务。 元数据，用于访问外部服务作为客户端的发送端口。 元数据纯粹用于描述终结点地址、 绑定和协定。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [发布 WCF 服务](../core/publishing-wcf-services.md)  
  
-   [使用 WCF 服务](../core/consuming-wcf-services.md)  
  
-   [指定 WCF 适配器的消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)  
  
-   [WCF 适配器演练](../core/wcf-adapter-walkthroughs.md)