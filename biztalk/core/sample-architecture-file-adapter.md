---
title: "示例体系结构： 文件适配器 |Microsoft 文档"
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
- File adapters, security
- security, examples
- security, architecture
- examples, architecture
- architecture, security
- File adapters, architecture examples
ms.assetid: fdcbba0c-e301-46ce-8940-d617232cafbd
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11884786f743ece21a8009ea339a251b107420c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sample-architecture-file-adapter"></a>示例体系结构： 文件适配器
本主题将介绍使用文件适配器发送和接收消息时的示例结构。  
  
## <a name="file-adapter-components"></a>文件适配器组件  
 下图显示使用文件适配器时 BizTalk Server 示例结构的组件。  
  
> [!NOTE]
>  如果使用 EDI 适配器，此示例结构同样适用。  
  
 **显示文件适配器的图 1 示例体系结构**  
  
 ![示例文件适配器的体系结构](../core/media/tdi-sec-refarch-file.gif "TDI_Sec_RefArch_File")  
  
 此示例结构包含以下部分中介绍的组件。  
  
## <a name="perimeter-network-internet"></a>外围网络 - Internet  
 公司通常将文件协议用于基于 Intranet 的通信，因此，在 Internet 外围网络中您不需要任何服务器以支持此方案。  
  
## <a name="perimeter-network-intranet"></a>外围网络 - Intranet  
 如果您使用文件适配器，则在 Intranet 外围网络中需要存在文件服务器。 您的合作伙伴在此服务器上存放其消息，而且 BizTalk 文件接收适配器从此服务器中提取消息。  
  
## <a name="e-business-domain"></a>电子商务域  
 此域中的服务器如下：  
  
-   **BizTalk Server （处理、 文件适配器和跟踪主机）。** 此服务器安装有 BizTalk Server 运行时，并具有包含 BizTalk 业务流程、管道、业务规则引擎以及其他业务程序的主机实例。 BizTalk Server 端口、接收位置、管道、映射、架构以及程序集均在此服务器上接收、路由、处理和发送消息。 此服务器还具有支持的运行状况监视和监视数据的业务的跟踪的主机的主机实例。 此外，此主机包含运行文件发送和接收适配器的主机的实例。  
  
    > [!NOTE]
    >  当需要提高性能时，你可向处理主机的实例环境添加更多的 BizTalk Server。 有关如何配置 BizTalk Server 的高可用性的详细信息，请参阅[高可用性规划](../core/planning-for-high-availability3.md)。  
  
-   **主密钥服务器。** 作为中相同[示例体系结构： 基 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
-   **SQL Server。** 作为中相同[示例体系结构： 基 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
-   **域控制器。** 作为中相同[示例体系结构： 基 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
-   **管理工具。** 作为中相同[示例体系结构： 基 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
## <a name="see-also"></a>另请参阅  
 [对于小型和中型公司示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md)   
 [威胁模型分析的示例方案](../core/sample-scenarios-for-threat-model-analysis.md)