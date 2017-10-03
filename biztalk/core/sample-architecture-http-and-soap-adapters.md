---
title: "示例体系结构： HTTP 和 SOAP 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, security
- architecture, examples
- SOAP adapters, security
- Web Publishing
- security, examples
- security, architecture
- SOAP adapters, architecture examples
- examples, architecture
- architecture, security
- HTTP adapters, architecture examples
- reverse proxy rules
- ISA Server implementation
- HTTP adapters, security
ms.assetid: 935197d0-5108-4970-b237-3c6d5b40c5e9
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dae8be185084a9a838876e3d50b605a63c161b66
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sample-architecture-http-and-soap-adapters"></a>示例结构：HTTP 和 SOAP 适配器
本主题将介绍使用 HTTP 和 SOAP 适配器发送和接收消息时的示例结构。  
  
 下图显示了使用 HTTP 或 SOAP 适配器时 BizTalk Server 示例结构的组件：  
  
 **显示 HTTP 或 SOAP 适配器的图 1 示例体系结构**  
  
 ![示例体系结构为 HTTP 或 SOAP 适配器](../core/media/tdi-sec-refarch-http.gif "TDI_Sec_RefArch_HTTP")  
  
 此示例结构包含以下各部分所讨论的组件。  
  
## <a name="perimeter-networkinternet"></a>外围网络 ― Internet  
 使用 SOAP 和 HTTP 适配器时，建议您使用反向代理规则（TMG 服务器实施被称为 Web 发布）将消息从面向 Internet 的防火墙（防火墙 1）中继到帮助保护电子商务域的防火墙（防火墙 2），并从此防火墙中继到运行独立主机的 BizTalk Server。 有关 Web 发布规则的详细信息，请参阅 Microsoft 网站[http://go.microsoft.com/fwlink/?LinkID=205340](http://go.microsoft.com/fwlink/?LinkID=205340) (http://go.microsoft.com/fwlink/?LinkID=205340)。  
  
> [!NOTE]
>  使用反向代理时，在外围网络中不需要 Web 服务器。  
  
## <a name="perimeter-networkintranet"></a>外围网络 ― Intranet  
 公司通常将 HTTP 和 SOAP 协议用于基于 Internet 的通信，因此，在 Intranet 外围网络中不需要任何服务器就可以支持此方案。 如果 Intranet 中存在通过 HTTP 或 SOAP 协议与 BizTalk Server 相集成的内部应用程序，则应遵循针对 Internet 外围网络的建议。  
  
## <a name="e-business-domain"></a>电子商务域  
 此域包含 BizTalk Server 实现使用的所有基础结构和应用程序。 此域中的服务器如下：  
  
-   **BizTalk Server （处理和跟踪主机）。** 此服务器安装有 BizTalk Server 运行时，并具有包含 BizTalk 业务流程、管道、业务规则引擎以及其他业务程序的主机实例。 此服务器还具有支持的运行状况监视和监视数据的业务的跟踪的主机的主机实例。  
  
    > [!NOTE]
    >  当需要提高性能时，你可向处理主机的实例环境添加更多的 BizTalk Server。  
  
-   **BizTalk Server （独立主机为 SOAP 和 HTTP 适配器）。** 此服务器安装有 BizTalk Server 运行时，并且只具有包含 HTTP 和 SOAP 适配器的主机的实例。 这些主机运行在单独的服务器中，因为这些适配器需要您在运行它们的计算机上安装 Internet 信息服务 (IIS)。  
  
    > [!NOTE]
    >  当需要提高性能时，您可向 HTTP 和 SOAP 适配器主机的实例环境添加更多的 BizTalk Server。 执行此操作后，还必须配置网络负载平衡 (NLB)。 有关如何配置 BizTalk Server 的高可用性的详细信息，请参阅[高可用性规划](../core/planning-for-high-availability3.md)。  
  
-   **主密钥服务器。** 作为中相同[示例体系结构： 基 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
-   **SQL Server。** 作为中相同[示例体系结构： 基 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
-   **域控制器。** 作为中相同[示例体系结构： 基 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
-   **管理工具。** 作为中相同[示例体系结构： 基 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
## <a name="see-also"></a>另请参阅  
 [对于小型和中型公司示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md)   
 [威胁模型分析的示例方案](../core/sample-scenarios-for-threat-model-analysis.md)