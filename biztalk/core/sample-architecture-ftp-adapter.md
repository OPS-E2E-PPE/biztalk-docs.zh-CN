---
title: 示例体系结构：FTP 适配器 |Microsoft Docs
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
- independent software vendor (ISV)
- security, examples
- security, architecture
- examples, architecture
- architecture, security
- FTP adapters, security
- FTP adapters, architecture examples
ms.assetid: 13fc1086-6acc-483c-be83-4ff6a60cd2bc
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baa9a9514d7e1524cd277e3e822f7b15a2904d7d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393944"
---
# <a name="sample-architecture-ftp-adapter"></a>示例体系结构：FTP 适配器
使用 FTP 适配器发送和接收消息时，本主题介绍对示例结构。  
  
 使用 FTP 适配器时下, 图显示的 BizTalk Server 组件的示例体系结构。  
  
 **图 1 显示了 FTP 适配器的示例结构**  
  
 ![示例 FTP 适配器的体系结构](../core/media/tdi-sec-refarch-ftp.gif "TDI_Sec_RefArch_FTP")  
  
 此示例结构包含的组件，如以下各节中所述。  
  
## <a name="perimeter-networkinternet"></a>外围网络 ― internet  
 当使用 FTP 适配器时，Internet 外围网络没有 FTP 服务器。  
  
> [!NOTE]
>  FTP 服务器也可能位于你的环境之外，在合作伙伴的网络中，或由第三方独立软件供应商 (ISV) 托管。  
  
## <a name="perimeter-networkintranet"></a>外围网络 ― intranet  
 公司通常使用 FTP 协议进行基于 Internet 的通信，并因此不需要支持此方案在 intranet 外围网络中的任何服务器。  
  
## <a name="e-business-domain"></a>电子商务域  
 此域中的服务器是：  
  
-   **BizTalk Server （处理、 FTP 适配器和跟踪主机）。** 此服务器安装了 BizTalk Server 运行时，并具有包含 BizTalk 业务流程、 管道、 业务规则引擎和其他业务流程主机实例。 这是其中 BizTalk Server 端口、 接收位置、 管道、 映射、 架构和程序集位于要接收、 路由、 处理和发送消息。 此服务器还具有支持跟踪运行状况监视和业务监视数据的主机的主机实例。 此外，此主机包含运行 FTP 发送主机的实例和接收适配器。  
  
    > [!NOTE]
    >  根据性能需求的增加，您可以添加更多 BizTalk Server 对您的环境的处理主机的主机实例。 有关如何配置 BizTalk Server 的高可用性的详细信息，请参阅[以实现高可用性规划](../core/planning-for-high-availability3.md)。  
  
-   **主密钥服务器。** 中的相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
-   **SQL Server。** 与相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
-   **域控制器。** 与以下主题中的相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
-   **管理工具。** 中的相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
## <a name="see-also"></a>请参阅  
 [对于小型和中型公司的示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md)   
 [威胁模型分析的示例方案](../core/sample-scenarios-for-threat-model-analysis.md)