---
title: 大型分布式体系结构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, examples
- data, domains
- corporate domains
- networks
- domain types, service
- domain types, processing
- screened subnet
- service domains
- domain types, corporate
- domain types, data
- perimeter networks
- processing domains
- demilitarized zone
- architecture, large distributions
ms.assetid: 3cfc07c4-0b1d-489b-9a29-55187fde0539
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c29bda1c60b59db42fabacaa0c02175aed90bda
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264789"
---
# <a name="large-distributed-architecture"></a>大型分布式结构
有关系统体系结构的完整信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署，请参阅[示例 BizTalk 服务器体系结构](../core/sample-biztalk-server-architectures.md)。  
  
 本部分将介绍适用于生产环境的结构。 这不包括开发环境或测试环境，或对环境管理网络的建议。 有关暂存你从开发到测试环境中，并从测试到生产环境的配置的详细信息，请参阅[部署 BizTalk 应用程序](../core/deploying-biztalk-applications.md)。  
  
 下图显示了采用深度防御的高度分布式 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 体系结构。  
  
 ![大型分布式体系结构](../core/media/06c5ae00-17aa-42f5-88d1-487bf7720183.gif "06c5ae00-17aa-42f5-88d1-487bf7720183")  
分布式 BizTalk Server 安全结构  
  
 此结构包含以下五个域：  
  
 **外围网络。** 外围网络（也称为 DMZ、外围安全区域和外围子网）包含为企业提供 Internet 相关服务的服务器。 此域可包含作为特定物理位置宿主的服务器，面向 Internet 的传输通过这些物理位置收发与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 之间的消息。 此域中没有 BizTalk Server、BizTalk 接收位置或企业单一登录服务器。 如果你使用 SOAP 适配器或 HTTP 适配器，则可以使用反向代理规则（Forefront Threat Management Gateway (TMG) 2010 服务器实施被称为 Web 发布），将消息从面向 Internet 的防火墙 (FW4) 中继到保护服务接口域的防火墙 (FW3)。 有关 Web 发布规则的详细信息，请参阅 Microsoft 网站[http://go.microsoft.com/fwlink/?LinkID=205340](http://go.microsoft.com/fwlink/?LinkID=205340) (http://go.microsoft.com/fwlink/?LinkID=205340)。  
  
 在上图中，外围网络中的服务器表示位于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境外部的某个域中的服务器。 因此，其中部分服务器也可位于远程位置。 例如，可以将文件传输协议 (FTP) 服务器是在远程位置;简单邮件传输协议 (SMTP) 服务器可能是公司的电子邮件服务器，Internet 服务提供商的 (ISP) 服务器或远程的 SMTP 服务器。  
  
 **服务接口域。** 这是启动消息处理的域。 此域包含具有 BizTalk 接收和发送处理程序的服务器。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 端口、接收位置、管道、映射、架构以及程序集均在此域中接收、路由和发送消息。 此域中的 BizTalk Server 的数量取决于公司性能要求所需的主机数和主机实例数。  
  
 **服务域。** 此域包含服务接口域中的服务器成功处理消息所需的受信任服务，但这些服务需要加强防范来自外围网络的攻击，例如带有 BizTalk 业务流程、管道、企业单一登录 (SSO) 服务、业务规则引擎和其他业务程序的处理服务器。  
  
 此域还包含公司域需要访问的服务，但仍需保护其免受外部威胁。 在这个域中的服务器之一承载管理工具： BizTalk 管理控制台和企业单一登录 (SSO) 管理实用程序。 此域还包含 SSO 主密钥服务器，该服务器存放 SSO 系统用来加密 SSO 数据库中的数据的主密钥（加密密钥）。 此域中的一个服务器包含支持跟踪运行状况监视数据和业务监视数据的主机实例。  
  
> [!NOTE]
>  在企业单一登录系统中，某些处理服务器可能只包含 SSO 服务，而没有任何 BizTalk Server 组件。 有关详细信息，请参阅[为企业单一登录的高可用性](../core/high-availability-for-enterprise-single-sign-on.md)。  
  
 **数据域。** 数据域最远离 Internet，因为它包含存储重要业务数据和处理数据的 SQL Server 数据库，并且它不信任其他任何域。 虽然你可将每个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库存放在运行 SQL Server 的不同服务器上，但是建议你根据数据库的主要处理类型（主要是读取操作或写入操作，还是两者并重）集中存放数据库：  
  
-   为每个 MessageBox 数据库使用一个 SQL Server。 你可以添加更多的 MessageBox 数据库以平衡负载。 这些都是读写密集型数据库。  
  
-   为 SSO 数据库使用一个 SQL Server。 在此数据库中，BizTalk Server 主要执行读取操作。 此数据库存放敏感数据，其访问权限的限制性最高。  
  
-   用于 BizTalk 管理中和业务规则引擎数据库的 SQL 服务器。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]多数情况下未读这些数据库中的操作。 此服务器还包含跟踪数据库。这是一个写密集型数据库。  
  
-   为分析服务器跟踪数据库使用一个 SQL Server。  
  
-   为 Microsoft Operations Manager (MOM) 数据库使用一个 SQL Server。  
  
-   为用于日志传送的目标系统使用一个 SQL Server  
  
> [!IMPORTANT]
>  对于故障转移保护，我们建议您的群集的每个 BizTalk 数据库。 有关 SQL Server 故障转移群集的详细信息，请参阅 Microsoft MSDN 网站， [http://go.microsoft.com/fwlink/?LinkId=131016](http://go.microsoft.com/fwlink/?LinkId=131016)。  
  
> [!NOTE]
>  有关日志传送目标系统的详细信息，请参阅[备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-the-biztalk-server-databases.md)。  
  
 在上图中，Forefront Threat Management Gateway (TMG) 2010 服务器用作软件防火墙，以保护和包含每个域。 此外，每个域都有自己的域控制器，这些域控制器在包含重要服务器的域（数据域）和面向外部的服务器（外围网络和公司域）之间建立了信任关系，服务器只能访问它们需要连接的其他域中的服务。 从服务接口域和服务域到数据域之间都存在一个防火墙 (FW1)，用于限制传入数据域的通信。 同样，从服务接口域和操作域到服务域之间也都存在一个防火墙 (FW2)，用于限制传入服务域的通信。  
  
 **公司域。** 这是一个 Intranet 域，该域包含你的公司或部门中所有台式计算机，以及为公司内信息工作者提供服务的所有服务器。 这个域中有两个不同的逻辑容器：  
  
-   **Intranet 服务。** 此容器包含通过 SQL 适配器和文件适配器与内部合作伙伴之间收发消息的服务器。 尽管这是一个 Intranet，但它不同于公司网络，在公司网络中大多数用户都有自己的帐户和服务。 与图中的外围网络相类似，此容器中某些服务器可以位于其他位置。 例如，文件适配器的发送和接收位置（文件夹）可以位于服务接口域之外的任意层中，而运行用于 SQL 适配器的 SQL Server 的服务器也可以位于服务接口域中。  
  
-   **操作。** 此容器包含终端服务客户端，IT 专业人员利用这些客户端来远程管理、维护和监控环境中所有服务器的性能和运行状况。 通过终端服务，IT 专业人员可连接到服务域中的管理服务器，从那里对环境中的所有服务器执行管理任务。  
  
 尽管公司域中可能设有开发计算机，但是这些计算机的配置不在本文档讨论范围之内。  
  
 有关 BizTalk Server 体系结构包括的信息工作人员服务的详细信息，请参阅[大型分布式体系结构与信息辅助服务](../core/large-distributed-architecture-with-information-worker-services.md)。  
  
 这些域之间的信任关系如下：  
  
-   数据域不信任其他任何域。  
  
-   服务接口域信任数据域。  
  
-   服务域信任数据域。  
  
-   公司域信任服务域。  
  
 有关配置防火墙的域和信任关系的详细信息，请参阅 Microsoft 帮助和支持 Web 的网站，网址[http://go.microsoft.com/fwlink/?LinkId=25230](http://go.microsoft.com/fwlink/?LinkId=25230)。  
  
 上图主要介绍的是安全性，你还可以使用网络负载平衡 (NLB) 和群集服务对该结构进行扩展，以提高可用性和性能。  
  
 有关高可用性的详细信息，请参阅[高可用性规划](../core/planning-for-high-availability3.md)。  
  
 有关性能的详细信息，请参阅[持续性能规划](../core/planning-for-sustained-performance.md)。  
  
 下表概括列出了根据要实现的服务级别协议 (SLA) 可配置网络负载平衡 (NLB) 的服务器的类型：  
  
|Name|类型|域|  
|----------|----------|------------|  
|HTTP (Rec)|Internet Information Services|外围网络|  
|接收处理程序（独立）|Internet Information Services|服务接口域|  
|BAM 门户|Internet Information Services|服务接口域|  
  
 下表概括列出了根据要实现的服务级别协议 (SLA) 可群集的服务器的类型：  
  
|Name|类型|域|  
|----------|----------|------------|  
|Exchange（发送）|Exchange Server|外围网络|  
|FTP 和 POP3 适配器的接收处理程序（进程内主机）|BizTalk Server|服务接口域<br /><br /> 公司域|  
|主密钥服务器|BizTalk Server|服务域|  
|所有 SQL Server|SQL Server|数据域|  
  
 有关 BizTalk Server 体系结构包括的信息工作人员服务的详细信息，请参阅[大型分布式体系结构与信息辅助服务](../core/large-distributed-architecture-with-information-worker-services.md)。  
  
## <a name="see-also"></a>另请参阅  
 [示例 BizTalk Server 体系结构](../core/sample-biztalk-server-architectures.md)   
 [按比例缩小体系结构](../core/scaled-down-architecture.md)