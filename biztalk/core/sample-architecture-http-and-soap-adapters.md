---
title: 示例体系结构：HTTP 和 SOAP 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77b7d8557564cfa94bbfb243447e5e85d4b6865d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65271072"
---
# <a name="sample-architecture-http-and-soap-adapters"></a>示例体系结构：HTTP 和 SOAP 适配器
使用 HTTP 和 SOAP 适配器发送和接收消息时，本主题介绍对示例结构。  
  
 使用 HTTP 或 SOAP 适配器时下, 图显示的 BizTalk Server 组件的示例体系结构。  
  
 **图 1 显示了 HTTP 或 SOAP 适配器的示例结构**  
  
 ![示例 HTTP 或 SOAP 适配器的体系结构](../core/media/tdi-sec-refarch-http.gif "TDI_Sec_RefArch_HTTP")  
  
 此示例结构包含的组件，如以下各节中所述。  
  
## <a name="perimeter-networkinternet"></a>外围网络 ― internet  
 当使用 SOAP 和 HTTP 适配器时，我们建议使用反向代理规则 （TMG 服务器实施被称为 Web 发布），中继将消息从面向 Internet 的防火墙 (防火墙 1) 到防火墙帮助保护电子商务域 (防火墙 2)，并从此防火墙到运行独立主机的 BizTalk 服务器。 有关 Web 发布规则的详细信息，请参阅 Microsoft 网站[ http://go.microsoft.com/fwlink/?LinkID=205340 ](http://go.microsoft.com/fwlink/?LinkID=205340) (http://go.microsoft.com/fwlink/?LinkID=205340)。  
  
> [!NOTE]
>  当使用反向代理时，您不需要外围网络中的 Web 服务器。  
  
## <a name="perimeter-networkintranet"></a>外围网络 ― intranet  
 公司通常使用 HTTP 和 SOAP 协议进行基于 Internet 的通信，并因此不需要支持此方案在 intranet 外围网络中的任何服务器。 如果必须通过 HTTP 或 SOAP 协议与 BizTalk Server 集成在 intranet 中的内部应用程序，则应遵循针对 Internet 外围网络的建议。  
  
## <a name="e-business-domain"></a>电子商务域  
 此域包含的所有基础结构和使用您的 BizTalk Server 实施的应用程序。 此域中的服务器是：  
  
-   **BizTalk Server （处理和跟踪主机）。** 此服务器安装了 BizTalk Server 运行时，并具有包含 BizTalk 业务流程、 管道、 业务规则引擎和其他业务流程主机实例。 此服务器还具有支持跟踪运行状况监视和业务监视数据的主机的主机实例。  
  
    > [!NOTE]
    >  根据性能需求的增加，您可以添加更多 BizTalk Server 对您的环境的处理主机的主机实例。  
  
-   **BizTalk Server （SOAP 和 HTTP 适配器的独立主机）。** 此服务器安装了 BizTalk Server 运行时，并具有仅包含 HTTP 和 SOAP 适配器主机实例。 这些主机运行在单独的服务器由于这些适配器要求你在计算机上安装 Internet 信息服务 (IIS) 运行它们。  
  
    > [!NOTE]
    >  根据性能需求的增加，您可以添加更多 BizTalk Server 环境 HTTP 和 SOAP 适配器主机的主机实例。 当执行此操作时，还必须配置网络负载平衡 (NLB)。 有关如何配置 BizTalk Server 的高可用性的详细信息，请参阅[以实现高可用性规划](../core/planning-for-high-availability3.md)。  
  
-   **主密钥服务器。** 中的相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
-   **SQL Server。** 中的相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
-   **域控制器。** 中的相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
-   **管理工具。** 中的相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
## <a name="see-also"></a>请参阅  
 [对于小型和中型公司的示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md)   
 [威胁模型分析的示例方案](../core/sample-scenarios-for-threat-model-analysis.md)