---
title: 示例体系结构： 基 BizTalk Server |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, examples
- IPSec
- BizTalk Server, examples
- security, examples
- security, architecture
- IPSec, about IPSec
- BizTalk Server, architecture
- architecture, security
ms.assetid: 7ccc1ef3-670f-423f-b6ca-3d56b9bbeabf
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea815c0165f58c28cea8ce7cae35fd6ed7437323
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271189"
---
# <a name="sample-architecture-base-biztalk-server"></a>示例结构：基本 BizTalk Server
本主题将介绍基本示例结构。 其中介绍了 BizTalk Server 部署中与适配器无关的组件。 建议所有 BizTalk Server 部署都至少包含这些组件。  
  
 下图显示了 BizTalk Server 基本示例结构的组件。 所有针对适配器的 BizTalk Server 结构中都包含这些组件，我们将在稍后部分中讨论这些结构。  
  
 **图 1 基本体系结构组件**  
  
 ![基本体系结构组件](../core/media/tdi-sec-refarch.gif "TDI_Sec_RefArch_")  
  
 此示例结构包含以下部分中介绍的各项。  
  
## <a name="perimeter-networkinternet"></a>外围 network―internet  
  
-   此外围网络（也称为 DMZ、外围安全区域和外围子网）包含提供 Internet 相关服务的服务器。 此域中没有 BizTalk Server、BizTalk 接收位置或企业单一登录服务器。  
  
## <a name="perimeter-networkintranet"></a>外围网络 ― Intranet  
 此外围网络包含提供 Intranet 相关服务的服务器。 该网络在 Intranet（例如公司网络）与运行应用程序的服务器之间提供附加的安全防护层。 与 Internet 外围网络一样，Intranet 外围网络不包含 BizTalk Server、BizTalk 接收位置或企业单一登录服务器。  
  
## <a name="e-business-domain"></a>电子商务域  
 此域包含 BizTalk Server 实现使用的所有基础结构和应用程序。 此域中的服务器如下：  
  
-   **BizTalk Server。** 此服务器安装有 BizTalk Server 运行时以及各种 BizTalk 主机的实例。 环境中 BizTalk Server 的数目取决于其运行的主机类型和所需的性能。 当需要提高性能时，你可向处理主机的实例环境添加更多的 BizTalk Server。  
  
-   **主密钥服务器。** 此服务器是企业单一登录 (SSO) 主密钥服务器。 该服务器保存有 SSO 系统用于对 SSO 数据库中的数据进行加密的主密钥（加密密钥）。  
  
-   **SQL Server。** 此服务器包含 BizTalk 数据库。  
  
    > [!IMPORTANT]
    >  为了进行故障转移保护，建议你对每个 BizTalk 数据库进行群集。 有关 Microsoft SQL Server 故障转移群集的详细信息，请参阅 Microsoft MSDN 网站在[http://go.microsoft.com/fwlink/?LinkID=190216](http://go.microsoft.com/fwlink/?LinkID=190216)。  
  
    > [!NOTE]
    >  根据所需的性能，你可能必须将 BizTalk 数据库分别放在多台运行 SQL Server 的计算机上。  
  
-   **域控制器。** 此服务器用作电子商务 Active Directory 域的宿主。 其中包含有关需要访问 BizTalk Server 的所有组帐户和个人帐户的信息。  
  
-   **管理工具。** 在这个域中的服务器之一承载管理工具： BizTalk 管理控制台和企业单一登录 (SSO) 管理实用程序。  
  
## <a name="firewalls-and-domains"></a>防火墙和域  
 图 1 中，Forefront Threat Management Gateway (TMG) 2010 服务器用作软件防火墙，以保护和包含每个域。 此外，电子商务域具有自己的域控制器，并且此域不信任其他任何域。 有关如何为域和信任关系配置防火墙的详细信息，请参阅以下 Microsoft 帮助和支持 Web 站点[http://go.microsoft.com/fwlink/?LinkId=25230](http://go.microsoft.com/fwlink/?LinkId=25230)。  
  
 该示例结构具有两个防火墙：  
  
-   **防火墙 1。** 此防火墙具有三个网络接口： 它将路由从 Internet、 intranet 和外围网络的流量。  
  
-   **防火墙 2。** 此防火墙是双宿主： 它将路由从外围网络 （Internet 和 intranet） 和电子商务域的流量。  
  
 外围网络中的计算机不是任何域的成员，并且这些计算机互不通信。  
  
## <a name="ipsec"></a>IPsec  
 建议你使用 Internet 协议安全性 (IPSec) 来帮助确保电子商务域中所有服务器之间通信的安全。 IPsec 规则如下所述：  
  
-   允许 BizTalk Server 与域控制器之间经过验证的通信。  
  
-   允许 BizTalk Server 与管理工具服务器之间经过验证的通信。  
  
-   允许 BizTalk Server 与主密钥服务器之间经过验证的通信。  
  
-   允许 BizTalk Server 与 SQL Server 之间经过验证的通信。  
  
-   允许主密钥服务器与域控制器之间经过验证的通信。  
  
-   允许主密钥服务器与 BizTalk Server（独立、处理、进程内和跟踪主机）之间经过验证的通信。  
  
-   允许主密钥服务器与 SQL Server（SSO 数据库）之间经过验证的通信。  
  
-   允许域控制器与域中所有服务器之间经过验证的通信。  
  
-   允许管理工具服务器与域中所有服务器之间经过验证的通信。  
  
 如果域中存在不需要访问 BizTalk Server、SQL Server、主密钥服务器或管理工具服务器的其他应用程序，则阻止这些应用程序与相应服务器之间的通信。  
  
## <a name="see-also"></a>另请参阅  
 [规划安全性](../core/planning-for-security.md)   
 [对于小型和中型公司示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md)   
 [威胁模型分析的示例方案](../core/sample-scenarios-for-threat-model-analysis.md)