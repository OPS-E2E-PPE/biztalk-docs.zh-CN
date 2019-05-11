---
title: 示例体系结构：基本 BizTalk Server |Microsoft Docs
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
ms.openlocfilehash: c4db442ec29ac9185bd1479219db795a9398073f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393961"
---
# <a name="sample-architecture-base-biztalk-server"></a>示例体系结构：基本 BizTalk Server
本主题讨论基本示例结构。 它介绍了是独立于适配器的 BizTalk Server 部署中的组件。 我们建议所有 BizTalk Server 部署都有至少包含这些组件。  
  
 下图显示的基本 BizTalk Server 组件的示例体系结构。 这些组件将出现在我们在后面的章节中介绍的所有特定于适配器的 BizTalk Server 结构。  
  
 **图 1 基本结构组件**  
  
 ![基本结构组件](../core/media/tdi-sec-refarch.gif "TDI_Sec_RefArch_")  
  
 此示例结构包含以下各节所述的项。  
  
## <a name="perimeter-networkinternet"></a>外围网络 ― internet  
  
-   此外围网络 （也称为 DMZ、 外围安全区域和外围子网） 包含提供 Internet 相关服务的服务器。 有没有 BizTalk Server、 BizTalk 在这个域中接收位置或企业单一登录服务器。  
  
## <a name="perimeter-networkintranet"></a>外围网络 ― intranet  
 此外围网络包含提供 intranet 相关服务的服务器。 它提供了额外的 intranet （例如，公司网络） 和运行应用程序的服务器之间的安全性。 Internet 外围网络，如 intranet 外围网络不包含 BizTalk Server、 BizTalk 接收位置或企业单一登录服务器。  
  
## <a name="e-business-domain"></a>电子商务域  
 此域包含的所有基础结构和使用您的 BizTalk Server 实施的应用程序。 此域中的服务器是：  
  
-   **BizTalk Server.** 此服务器已安装了 BizTalk Server 运行时和各种 BizTalk 主机的实例。 在环境中的 BizTalk 服务器数量取决于它们运行的主机和性能需求的类型。 根据性能需求的增加，您可以添加更多 BizTalk Server 对您的环境的处理主机的主机实例。  
  
-   **主密钥服务器。** 此服务器是企业单一登录 (SSO) 主密钥服务器。 它包含主密钥 （加密密钥） SSO 系统用来加密 SSO 数据库中的数据。  
  
-   **SQL Server。** 此服务器包含 BizTalk 数据库。  
  
    > [!IMPORTANT]
    >  对于故障转移保护，我们建议您群集每个 BizTalk 数据库。 有关 Microsoft SQL Server 故障转移群集的详细信息，请参阅 Microsoft MSDN 网站上的[ http://go.microsoft.com/fwlink/?LinkID=190216 ](http://go.microsoft.com/fwlink/?LinkID=190216)。  
  
    > [!NOTE]
    >  根据性能需求，可能需要分离到多台计算机运行 SQL Server 的 BizTalk 数据库。  
  
-   **域控制器。** 此服务器托管的电子商务 Active Directory 域。 它包含有关所有组和个人帐户需要访问 BizTalk Server 的信息。  
  
-   **管理工具。** 在这个域中的服务器之一承载管理工具：BizTalk 管理控制台和企业单一登录 (SSO) 管理实用程序。  
  
## <a name="firewalls-and-domains"></a>防火墙和域  
 在图 1 中，Forefront Threat Management Gateway (TMG) 2010年服务器充当软件防火墙，以帮助保护和包含每个域。 此外，电子商务域具有其自己的域控制器，并且此域不信任其他任何域。 有关如何为域和信任关系配置防火墙的详细信息，请参阅 Microsoft 帮助和支持网站上的[ http://go.microsoft.com/fwlink/?LinkId=25230 ](http://go.microsoft.com/fwlink/?LinkId=25230)。  
  
 示例体系结构具有两个防火墙：  
  
- **防火墙 1。** 此防火墙具有三个网络接口：它将从 Internet、 intranet 和外围网络的流量路由。  
  
- **防火墙 2。** 此防火墙是双宿主：它将路由来自外围网络 （Internet 和 intranet） 和电子商务域的流量。  
  
  外围网络中的计算机不是任何域的成员，它们不会彼此进行通信。  
  
## <a name="ipsec"></a>IPsec  
 我们建议使用 Internet 协议安全 (IPSec) 来帮助保护电子商务域中的所有服务器之间的通信。 IPsec 规则如下所示：  
  
- 允许 BizTalk Server 与域控制器之间经过验证的通信。  
  
- 允许 BizTalk Server 管理工具服务器之间经过身份验证的流量。  
  
- 允许 BizTalk Server 与主密钥服务器之间经过验证的通信。  
  
- 允许 BizTalk Server 和 SQL Server 之间经过验证的通信。  
  
- 允许主密钥服务器和域控制器之间经过验证的通信。  
  
- 允许主密钥服务器与 BizTalk Server （独立、 处理、 在进程和跟踪主机。） 之间经过验证的通信  
  
- 允许主密钥服务器和 SQL Server （SSO 数据库） 之间经过验证的通信。  
  
- 允许域控制器和域中的所有服务器之间经过验证的通信。  
  
- 允许管理工具服务器和域中的所有服务器之间经过验证的通信。  
  
  如果你有其他域中的应用程序不需要访问 BizTalk Server、 SQL Server、 主密钥服务器或管理工具服务器阻止这些应用程序与通信的相应服务器。  
  
## <a name="see-also"></a>请参阅  
 [规划安全性](../core/planning-for-security.md)   
 [对于小型和中型公司的示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md)   
 [威胁模型分析的示例方案](../core/sample-scenarios-for-threat-model-analysis.md)