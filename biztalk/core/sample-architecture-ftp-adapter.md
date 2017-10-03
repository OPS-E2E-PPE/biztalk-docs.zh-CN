---
title: "示例体系结构： FTP 适配器 |Microsoft 文档"
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
- independent software vendor (ISV)
- security, examples
- security, architecture
- examples, architecture
- architecture, security
- FTP adapters, security
- FTP adapters, architecture examples
ms.assetid: 13fc1086-6acc-483c-be83-4ff6a60cd2bc
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bed15e06027bec5e73c19cf73548674bc51ce68a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sample-architecture-ftp-adapter"></a>示例体系结构： FTP 适配器
本主题将介绍使用 FTP 适配器发送和接收消息时的示例结构。  
  
 下图显示了使用 FTP 适配器时 BizTalk Server 示例结构的组件：  
  
 **显示 FTP 适配器的图 1 示例体系结构**  
  
 ![示例体系结构为 FTP 适配器](../core/media/tdi-sec-refarch-ftp.gif "TDI_Sec_RefArch_FTP")  
  
 此示例体系结构包含的组件，如以下各节所述。  
  
## <a name="perimeter-networkinternet"></a>外围网络 ― Internet  
 使用 FTP 适配器时，Internet 外围网络中需要存在 FTP 服务器。  
  
> [!NOTE]
>  FTP 服务器也可以位于您的网络环境之外（例如位于合作伙伴网络中），也可使用第三方独立软件供应商 (ISV) 作为宿主。  
  
## <a name="perimeter-networkintranet"></a>外围网络 ― Intranet  
 公司通常使用 FTP 协议进行基于 Internet 的通信，因此，在 Intranet 外围网络中不需要任何服务器就可以支持此方案。  
  
## <a name="e-business-domain"></a>电子商务域  
 此域中的服务器如下：  
  
-   **BizTalk Server （处理、 FTP 适配器和跟踪主机）。** 此服务器安装有 BizTalk Server 运行时，并具有包含 BizTalk 业务流程、管道、业务规则引擎以及其他业务程序的主机实例。 BizTalk Server 端口、接收位置、管道、映射、架构以及程序集均在此服务器上接收、路由、处理和发送消息。 此服务器还具有支持的运行状况监视和监视数据的业务的跟踪的主机的主机实例。 此外，此主机包含运行 FTP 发送和接收适配器的主机实例。  
  
    > [!NOTE]
    >  当需要提高性能时，你可向处理主机的实例环境添加更多的 BizTalk Server。 有关如何配置 BizTalk Server 的高可用性的详细信息，请参阅[高可用性规划](../core/planning-for-high-availability3.md)。  
  
-   **主密钥服务器。** 作为中相同[示例体系结构： 基 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
-   **SQL Server。** 与相同[示例体系结构： 基 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
-   **域控制器。** 如下所示中的相同相同[示例体系结构： 基 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
-   **管理工具。** 作为中相同[示例体系结构： 基 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。  
  
## <a name="see-also"></a>另请参阅  
 [对于小型和中型公司示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md)   
 [威胁模型分析的示例方案](../core/sample-scenarios-for-threat-model-analysis.md)