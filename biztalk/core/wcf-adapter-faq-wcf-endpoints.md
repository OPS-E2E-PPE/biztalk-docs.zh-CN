---
title: "WCF 适配器常见问题： WCF 终结点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ccc94b7d-b8a6-4c24-907e-922fd885b874
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90c59c586f0d7f1d02ad406baec694cf4e22ff24
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="wcf-adapter-faq-wcf-endpoints"></a>WCF 适配器常见问题： WCF 终结点
## <a name="what-are-two-endpoints-options-can-be-created-by-the-biztalk-wcf-service-publishing-wizard"></a>BizTalk WCF 服务发布向导可以创建的两个终结点选项是什么？  
 运行 BizTalk WCF 服务发布向导时，您可以选择创建 WCF 服务终结点或 WCF 仅元数据终结点 (MEX)。  
  
 服务终结点可创建 IIS 承载的实际 Web 位置（用于公开实际 WCF 服务的功能）。 仅独立的适配器（WCF-WsHttp、WCF-BasicHttp 和 WCF-CustomIsolated）才能用于服务终结点。 此类型终结点的功能由发布为 WCF 服务的业务流程或架构实现。  
  
 仅元数据终结点是一个通过 BizTalk 接收位置实现其功能的终结点。  其使用 IIS 和进程内 WCF 接收适配器，而非公开的业务流程或实际 WCF 服务代码。 使用向导生成仅包含元数据终结点公开更简单的方法为提供集成的信息接收位置使用进程内 WCF 适配器比手动使用 svcutil.exe。 使用 svcutil.exe 将强制你找到转发给你的服务的使用者的元数据，使其可以调用的方法。  
  
## <a name="why-would-i-use-a-metadata-only-endpoint-in-biztalk-server"></a>为什么在 BizTalk Server 中使用仅元数据终结点？  
 使用仅元数据终结点，实际 WCF 服务中则不存在服务实现， 而是在 BizTalk 接收位置实现功能，这称为具有服务终结点的 WCF 服务。 例如，您可能将两个架构和一个映射填入消息域中，并将其转换为全部大写。 在这种情况下，元数据中的服务发布为“ConvertToUpper”。 但是服务功能是在接收位置实现，而不是在代码中或通过业务流程实现的。  
  
 WCF 终结点由地址、绑定和约定组成。 向导创建仅元数据终结点后，将从现有接收位置获得地址和绑定详细信息。 约定信息由 BizTalk 业务流程中存在的架构定义，或者您可以使用向导进行手动创建。 如果你选择**作为 WCF 服务发布 BizTalk 业务流程**，仅包含元数据终结点将使用从业务流程的程序集中的消息和端口类型定义的协定。  
  
 如果你选择**将架构作为 WCF 服务发布**，该向导允许你通过使用现有的输入和输出架构中指定服务和操作名称来定义服务定义。 向导将创建一个 .svc 文件和一个 IIS 虚拟目录，以便发布元数据之后可对其进行浏览。 BizTalk WCF 服务发布向导还会创建 web.config 文件的与其 httpGetEnabled 属性\<serviceMetadata\>元素设置为 true。 这样可以发布元数据以供浏览。 如果你选择 BizTalk 接收位置发布服务元数据，该数据可以通过 GET 请求通过 HTTP 使用`?wsdl`服务的 URL 的末尾。  
  
## <a name="are-service-endpoints-hosted-in-iis-and-why"></a>服务终结点是否承载于 IIS 中，为什么？  
 是的，服务终结点通过以下三个独立适配器的其中之一承载于 IIS 中：  
  
-   WCF-WsHttp  
  
-   WCF-BasicHttp  
  
-   WCF-CustomIsolated  
  
 服务终结点与仅元数据终结点不同，后者的功能可作为 WCF 服务直接调用。 使用 BizTalk WCF 服务发布向导创建服务终结点会导致指定的 BizTalk 应用程序中生成新的接收位置。 它定义了可通过 IIS 访问的业务流程的 URI。  
  
## <a name="when-creating-a-service-endpoint-why-would-i-select-to-publish-schemas-as-a-wcf-service"></a>创建服务终结点时，为什么选择“将架构发布为 WCF 服务”？  
 如果 WCF 接收位置是仅使用 BizTalk 消息的 BizTalk 应用程序的一部分，则选择“将架构发布为 WCF 服务”。 这意味着不使用业务流程，并且将通过接收位置和发送端口公开所有功能。 发布架构以指定约定信息。 可从架构程序集或业务流程程序集获取（尽管业务流程可能未用于此终结点）此信息。