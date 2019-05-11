---
title: WCF 适配器常见问题解答：WCF 终结点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccc94b7d-b8a6-4c24-907e-922fd885b874
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e56e1e7b657b0c365675e3b7f308d7960c12968f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393570"
---
# <a name="wcf-adapter-faq-wcf-endpoints"></a>WCF 适配器常见问题解答：WCF 终结点
## <a name="what-are-two-endpoints-options-can-be-created-by-the-biztalk-wcf-service-publishing-wizard"></a>可以通过 BizTalk WCF 服务发布向导创建两个终结点选项是什么？  
 运行 BizTalk WCF 服务发布向导时，你可以选择创建 WCF 服务终结点或 WCF 仅元数据终结点 (MEX)。  
  
 服务终结点创建公开实际 WCF 服务的功能的 IIS 中承载的实际 Web 位置。 仅在独立的适配器 （Wcf-wshttp、 Wcf-basichttp 和 Wcf-customisolated） 可用于服务终结点。 此类型的终结点的功能由业务流程或架构发布为 WCF 服务的实现。  
  
 仅元数据终结点是一个通过 BizTalk 实现其功能接收位置。  这将使用 IIS 和进程内 WCF 接收适配器，而不是公开的业务流程或实际 WCF 服务代码。 使用向导生成仅元数据终结点公开更简单的方法提供了有关集成信息接收位置使用比手动使用 svcutil.exe 的进程内 WCF 适配器。 使用 svcutil.exe 可强制您查找将元数据转发到你的服务的使用者，使其可以调用的方法。  
  
## <a name="why-would-i-use-a-metadata-only-endpoint-in-biztalk-server"></a>为什么要使用 BizTalk Server 中的仅元数据终结点？  
 使用仅元数据终结点，服务实现一个实际的 WCF 服务中不存在。 功能而不是，实现在 BizTalk 接收位置，只是作为 WCF 服务与服务终结点调用。 例如，可能有两个架构和一个映射，以便执行一条消息中的字段并将其转换为全部大写。 在这种情况下服务元数据中发布为"ConvertToUpper"。 但在接收位置并不是在代码或通过业务流程实现的服务的功能。  
  
 WCF 终结点由地址、 绑定和协定组成。 当向导创建仅元数据终结点时，它获取的地址和绑定详细信息，从现有接收位置。 协定信息定义的架构可以存在于 BizTalk 业务流程，也可以创建手动使用该向导。 如果愿意**BizTalk 业务流程发布为 WCF 服务**，仅元数据终结点使用从业务流程的程序集中的消息和端口类型定义的协定。  
  
 如果愿意**将架构发布为 WCF 服务**，该向导，可通过使用现有的输入和输出架构中指定服务和操作名称来定义服务定义。 该向导创建一个.svc 文件和 IIS 虚拟目录，因此发布后，可以浏览元数据。 BizTalk WCF 服务发布向导还会创建一个 web.config 文件与其 httpGetEnabled 属性\<serviceMetadata\>元素设置为 true。 这将发布用于浏览元数据。 如果你选择 BizTalk 接收位置发布服务元数据，可以通过使用 HTTP 访问通过 GET 请求该数据`?wsdl`服务的 URL 的末尾。  
  
## <a name="are-service-endpoints-hosted-in-iis-and-why"></a>在 IIS 中承载的服务终结点和原因？  
 是的使用三个独立适配器之一的 IIS 中承载的服务终结点：  
  
- WCF-WsHttp  
  
- WCF-BasicHttp  
  
- WCF-CustomIsolated  
  
  服务终结点与仅元数据终结点在于可以直接作为 WCF 服务调用其功能。 使用 BizTalk WCF 服务发布向导在新创建的服务终结点结果中指定的 BizTalk 应用程序接收位置。 它定义在其中可以通过 IIS 访问业务流程的 URI。  
  
## <a name="when-creating-a-service-endpoint-why-would-i-select-to-publish-schemas-as-a-wcf-service"></a>在创建服务终结点时，为什么选择"将架构发布为 WCF 服务"？  
 选择要将架构发布为 WCF 接收位置的 WCF 服务是使用 BizTalk 消息仅传送的 BizTalk 应用程序的一部分。 这意味着没有业务流程使用，并且所有功能将公开通过接收位置和发送端口。 发布架构以指定的协定信息。 获取此信息可以从架构程序集，或甚至从业务流程程序集 （尽管业务流程可能不用于此终结点）。