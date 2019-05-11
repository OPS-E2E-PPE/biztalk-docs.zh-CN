---
title: 大型分布式体系结构 |Microsoft Docs
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
ms.openlocfilehash: 8e4af265827890b3dafd242028fb481044799519
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329816"
---
# <a name="large-distributed-architecture"></a>大型分布式体系结构
有关完整信息的系统体系结构[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署，请参阅[Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)。  
  
 本部分中介绍的体系结构适用于生产环境。 它不包括开发或测试环境中或管理网络环境的建议。 有关暂存配置从开发到测试环境中，并从测试到生产环境的详细信息，请参阅[部署 BizTalk 应用程序](../core/deploying-biztalk-applications.md)。  
  
 下图显示了高度分布式[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]采用深度防御的体系结构。  
  
 ![大型分布式体系结构](../core/media/06c5ae00-17aa-42f5-88d1-487bf7720183.gif "06c5ae00-17aa-42f5-88d1-487bf7720183")  
分布式 BizTalk Server 安全体系结构  
  
 此体系结构包含以下五个域：  
  
 **外围网络。** 外围网络 （也称为 DMZ、 外围安全区域和外围子网） 包含提供有关企业与 Internet 相关服务的服务器。 此域可包含的服务器的物理位置的面向 Internet 的传输发送和接收消息，与主[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 有没有 BizTalk Server、 BizTalk 在这个域中接收位置或企业单一登录服务器。 如果使用 SOAP 或 HTTP 适配器，可以使用反向代理规则 （Forefront Threat Management Gateway (TMG) 2010年服务器实施被称为 Web 发布），将消息从面向 Internet 的防火墙 (FW4) 中继到保护服务的防火墙接口域 (FW3)。 有关 Web 发布规则的详细信息，请参阅 Microsoft 网站[ http://go.microsoft.com/fwlink/?LinkID=205340 ](http://go.microsoft.com/fwlink/?LinkID=205340) (<http://go.microsoft.com/fwlink/?LinkID=205340>)。  
  
 在上图中，外围网络中的服务器表示位于外部的某个域中的服务器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。 因此，其中部分服务器也可位于远程位置。 例如，文件传输协议 (FTP) 服务器可以位于远程位置;简单邮件传输协议 (SMTP) 服务器可以用作公司电子邮件服务器、 Internet 服务提供商 (ISP) 服务器或远程 SMTP 服务器。  
  
 **服务接口域。** 这是启动消息处理的域。 此域包含带有 BizTalk 接收和发送处理程序的服务器。 这就是[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]端口、 接收位置、 管道、 映射、 架构和程序集位于接收、 路由和发送消息。 在这个域中的 BizTalk Server 的数目取决于主机和主机实例所需的公司的性能要求的数量。  
  
 **服务域。** 此域包含的服务器中的服务接口域信任和需要处理的消息已成功，但这需要加强防范来自外围网络，例如处理服务器具有的攻击的服务BizTalk 业务流程、 管道、 企业单一登录 (SSO) 服务、 业务规则引擎和其他业务流程。  
  
 此域还包含公司域需要访问，但仍需保护其免受外部威胁的服务。 在这个域中的服务器之一承载管理工具：BizTalk 管理控制台和企业单一登录 (SSO) 管理实用工具。 此域还包含 SSO 主密钥服务器，其中包含主密钥 （加密密钥） SSO 系统用来加密 SSO 数据库中的数据。 在这个域中的服务器必须支持跟踪运行状况监视和业务监视数据的主机的主机实例。  
  
> [!NOTE]
>  在企业单一登录系统中，某些处理服务器可能没有 BizTalk Server 组件与包含只有 SSO 服务。 有关详细信息，请参阅[为企业单一登录的高可用性](../core/high-availability-for-enterprise-single-sign-on.md)。  
  
 **数据域。** 因为它包含存储重要业务数据和处理数据的 SQL Server 数据库，并且不信任其他任何域数据域最远离 Internet，。 虽然可将每个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库在不同服务器上运行 SQL Server，我们建议将基于的处理的主要类型的数据库 （主要是读取操作，基本上为写入操作，还是两者）：  
  
- 每个 MessageBox 数据库的 SQL Server。 您可以添加用于负载平衡的多个 MessageBox 数据库。 它们是读取和写入密集型数据库。  
  
- SSO 数据库的 SQL Server。 BizTalk Server 主要读取此数据库中的操作。 此数据库存放敏感数据，且需要限制最严格的访问权限。  
  
- BizTalk 管理和业务规则引擎数据库为一个 SQL Server。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 主要读取这些数据库中的操作。 此服务器还包含跟踪数据库，这是一个写密集型数据库。  
  
- 分析服务器跟踪数据库的 SQL Server。  
  
- Microsoft Operations Manager (MOM) 数据库的 SQL Server。  
  
- SQL Server 日志传送的目标系统  
  
> [!IMPORTANT]
>  对于故障转移保护，我们建议您群集每个 BizTalk 数据库。 有关 SQL Server 故障转移群集的详细信息，请参阅 Microsoft MSDN 网站上[ http://go.microsoft.com/fwlink/?LinkId=131016 ](http://go.microsoft.com/fwlink/?LinkId=131016)。  
  
> [!NOTE]
>  有关日志传送的目标系统的详细信息，请参阅[备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-the-biztalk-server-databases.md)。  
  
 在上图中，Forefront Threat Management Gateway (TMG) 2010年服务器充当软件防火墙，以保护和包含每个域。 此外，每个域，该域包含到面向外部的服务器 （外围网络和公司域） 的关键服务器 （数据域） 建立了信任关系具有其自己的域控制器，并且服务器只能访问中的服务它们需要连接到其他域。 没有一个防火墙从服务接口和服务域 (FW1) 将流量限制到数据域。 同样，没有一个防火墙 （FW2) 将流量限制到服务域中，从服务接口和操作的域。  
  
 **公司域。** 这是一个 intranet 域，而且它包含你的公司或部门中的所有台式计算机，向你的公司内信息工作者提供服务的所有服务器。 有两个不同的逻辑容器，此域中：  
  
- **Intranet 服务。** 此容器包含接收和发送消息的 SQL 和文件适配器与内部合作伙伴之间的服务器。 这是一个 intranet，而是不同于其中大多数用户都拥有他们的帐户和服务的公司网络。 类似于在外围网络图中，某些此容器中的服务器可以位于其他位置。 例如，发送和接收位置 （文件夹），可将 SQL 适配器在服务接口域中运行 SQL Server 服务器时，文件适配器可以是服务接口域之外的任意层中。  
  
- **操作。** 此容器包含终端服务客户端 IT 专业人员使用远程管理、 维护和监视性能和的环境中的所有服务器运行状况。 通过使用终端服务，IT 专业人员连接到服务域中的管理服务器，并从该处执行管理任务的环境中的所有服务器。  
  
  尽管公司域中，可能有开发计算机，这些计算机的配置不在本文的讨论范围内。  
  
  有关 BizTalk Server 体系结构包括信息工作者服务的详细信息，请参阅[具有信息工作者服务的大型分布式结构](../core/large-distributed-architecture-with-information-worker-services.md)。  
  
  在域间信任是按如下所示：  
  
- 数据域不信任其他任何域。  
  
- 服务接口域信任数据域。  
  
- 服务域信任数据域。  
  
- 公司域信任服务域。  
  
  有关为域和信任关系配置防火墙的详细信息，请参阅 Microsoft 帮助和支持网站上的[ http://go.microsoft.com/fwlink/?LinkId=25230 ](http://go.microsoft.com/fwlink/?LinkId=25230)。  
  
  尽管上图中重点介绍安全，还可以扩展了网络负载平衡 (NLB) 和群集服务的可用性和性能体系结构。  
  
  有关高可用性的详细信息，请参阅[以实现高可用性规划](../core/planning-for-high-availability3.md)。  
  
  有关性能的详细信息，请参阅[规划可持续性能](../core/planning-for-sustained-performance.md)。  
  
  下表总结了可以配置使用网络负载平衡 (NLB) 要实现服务级别协议 (SLA) 具体取决于服务器的类型：  
  
|“属性”|类型|域|  
|----------|----------|------------|  
|HTTP (Rec)|Internet Information Services|外围网络|  
|接收处理程序 （独立）|Internet Information Services|服务接口域|  
|BAM 门户|Internet Information Services|服务接口域|  
  
 下表总结了可以群集要实现服务级别协议 (SLA) 具体取决于服务器的类型：  
  
|“属性”|类型|域|  
|----------|----------|------------|  
|Exchange （发送）|Exchange Server|外围网络|  
|对于 FTP 和 POP3 适配器接收处理程序 （进程内主机）|BizTalk Server|服务接口域<br /><br /> Corporate Domain|  
|主密钥服务器|BizTalk Server|服务域|  
|所有 SQL Server|SQL Server|数据域|  
  
 有关 BizTalk Server 体系结构包括信息工作者服务的详细信息，请参阅[具有信息工作者服务的大型分布式结构](../core/large-distributed-architecture-with-information-worker-services.md)。  
  
## <a name="see-also"></a>请参阅  
 [示例 BizTalk Server 体系结构](../core/sample-biztalk-server-architectures.md)   
 [缩减的体系结构](../core/scaled-down-architecture.md)