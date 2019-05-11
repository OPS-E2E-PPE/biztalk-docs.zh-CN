---
title: 示例体系结构：文件适配器 |Microsoft Docs
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
- File adapters, security
- security, examples
- security, architecture
- examples, architecture
- architecture, security
- File adapters, architecture examples
ms.assetid: fdcbba0c-e301-46ce-8940-d617232cafbd
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 961c4e3f7820f88c4935e070c739aacaab5d1a63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65271151"
---
# <a name="sample-architecture-file-adapter"></a>示例体系结构：文件适配器
使用文件适配器发送和接收消息时，本主题介绍对示例结构。  
  
## <a name="file-adapter-components"></a>文件适配器组件  
 下图显示的 BizTalk Server 组件使用文件适配器时，此示例体系结构。  
  
> [!NOTE]
>  使用 EDI 适配器时，此示例结构化也适用。  
  
 **图 1 显示了文件适配器的示例结构**  
  
 ![示例文件适配器的体系结构](../core/media/tdi-sec-refarch-file.gif "TDI_Sec_RefArch_File")  
  
 此示例结构包含以下各节所述的组件。  
  
## <a name="perimeter-network-internet"></a>外围网络-Internet  
 公司通常使用文件协议用于基于 intranet 的通信，并因此不需要 Internet 外围网络以支持此方案中的任何服务器。  
  
## <a name="perimeter-network-intranet"></a>外围网络-intranet  
 当使用文件适配器时，intranet 外围网络没有的文件服务器。 这是指你的合作伙伴存放其消息，并 BizTalk 文件接收适配器从其中提取消息从该服务器。  
  
## <a name="e-business-domain"></a>电子商务域  
 此域中的服务器是：  
  
-   **BizTalk Server （处理、 文件适配器和跟踪主机）。** 此服务器安装了 BizTalk Server 运行时，并具有包含 BizTalk 业务流程、 管道、 业务规则引擎和其他业务流程主机实例。 这是其中 BizTalk Server 端口、 接收位置、 管道、 映射、 架构和程序集位于要接收、 路由、 处理和发送消息。 此服务器还具有支持跟踪运行状况监视和业务监视数据的主机的主机实例。 此外，此主机包含运行文件发送主机的实例和接收适配器。  
  
    > [!NOTE]
    >  根据性能需求的增加，您可以添加更多 BizTalk Server 对您的环境的处理主机的主机实例。 有关如何配置 BizTalk Server 的高可用性的详细信息，请参阅[以实现高可用性规划](../core/planning-for-high-availability3.md)。  
  
-   **主密钥服务器。** 中的相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
-   **SQL Server。** 中的相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
-   **域控制器。** 中的相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
-   **管理工具。** 中的相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
## <a name="see-also"></a>请参阅  
 [对于小型和中型公司的示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md)   
 [威胁模型分析的示例方案](../core/sample-scenarios-for-threat-model-analysis.md)