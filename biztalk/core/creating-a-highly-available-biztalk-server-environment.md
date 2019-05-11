---
title: 创建高度可用的 BizTalk Server 环境 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, high availability
- architecture, databases
- databases, architecture
- performance
- hosts, multiple
- hosts, architecture
- architecture, hosts
- databases, clustering
- high availability, designing
- BizTalk Server, architecture
- installation, planning
- clustering, databases
- installation, availability
ms.assetid: 758eb3bd-a25b-4863-a4ca-d7a1635f7542
caps.latest.revision: 54
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dad0587f02d0307140e5208043eb16735bb6f03e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354172"
---
# <a name="creating-a-highly-available-biztalk-server-environment"></a>创建高度可用的 BizTalk Server 环境
本部分介绍如何为数据和 Microsoft 中的通信提供高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]集成分散的系统和应用程序时。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 分隔数据与处理数据，使您能够解决可用性问题通过扩展数据库和承载独立的主机。  
  
## <a name="demonstrating-high-availability"></a>证实高可用性  
 高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]着重于恢复可能会中断中的可用性的功能组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署。  
  
 为了演示中的高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，您必须发生故障并度量恢复中的产品的有效性。 高度可用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署使错误和失败对外部应用程序和系统中，透明并可确保所有服务都继续正常工作中断降至最低。  
  
## <a name="designing-for-high-availability"></a>为实现高可用性设计  
 设计[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供高可用性部署涉及到实现冗余，以便应用程序集成或业务流程集成方案中所涉及的每个功能组件。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 通过将数据从概念上讲分离与处理数据的主机，简化了这些方案的实现。 因此，确保具备高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]涉及运行多个主机实例并群集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，按如下所示：  
  
- **为 BizTalk 主机的体系结构**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]允许您分隔不同的主机并运行多个主机实例以提供高可用性，如接收消息、 处理业务流程和发送消息的关键功能。 这些主机不需要任何其他群集或负载平衡机制因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]会自动将工作负荷分散到主机实例的多台计算机。 但是，运行 HTTP 和 SOAP 适配器的接收处理程序的主机需要负载平衡机制如网络负载平衡 (NLB) 来提供高可用性。  
  
- **BizTalk Server 数据库的体系结构**的高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库通常包含在主动/被动服务器群集配置中配置的两个或多个数据库计算机。 这些计算机共享公共的磁盘资源 （例如 RAID5 SCSI 磁盘阵列或存储区域网络），并使用 Windows 群集提供备份冗余和容错功能。  
  
> [!NOTE]
>  高度可用环境的性质，多计算机环境的不同而不同。 配置时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在多计算机环境中，您必须使用域用户组和帐户。  
  
 因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]基于 Microsoft[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]，和 Microsoft SQL Server 2008，请确保配置的主机前，具有高可用性部署这些产品[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 以下链接包括有关为这些基础产品提供高可用性的信息：  
  
- **高可用性 – Always On Technologies**，可在[ http://go.microsoft.com/fwlink/?LinkId=130376 ](http://go.microsoft.com/fwlink/?LinkId=130376)。  
  
   本白皮书介绍了适用于 SQL Server 2008 的高可用性功能。  
  
- **高可用性解决方案概述**，可在[ http://go.microsoft.com/fwlink/?LinkId=130377 ](http://go.microsoft.com/fwlink/?LinkId=130377)。  
  
   为提高可用性的服务器或数据库的 SQL Server 2008 引入了多个高可用性解决方案。  
  
- **Windows 部署服务循序渐进指南**，可在[ http://go.microsoft.com/fwlink/?LinkId=130379 ](http://go.microsoft.com/fwlink/?LinkId=130379)。  
  
   包含有关如何在 Windows Server 2008 中使用 Windows 部署服务角色循序渐进指南。  
  
- **Windows Server 2003 部署工具包：规划服务器部署**，可在[ http://go.microsoft.com/fwlink/?LinkId=24433 ](http://go.microsoft.com/fwlink/?LinkId=24433)。  
  
   本书提供了有关设计和部署文件服务器、 打印服务器和中型和大型组织中的终端服务器的规划服务器存储和信息有关的信息。  
  
- **BizTalk Server 提供高可用性**，可在[ http://go.microsoft.com/fwlink/?LinkId=130457 ](http://go.microsoft.com/fwlink/?LinkId=130457)。  
  
   部分[BizTalk Server 操作指南](http://go.microsoft.com/fwlink/?LinkId=130458)描述的方式可以提高可用性的你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [为 BizTalk 主机提供高可用性](../core/providing-high-availability-for-biztalk-hosts.md)  
  
-   [为 BizTalk Server 数据库提供高可用性](../core/providing-high-availability-for-biztalk-server-databases.md)  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 高可用性示例方案](../core/sample-biztalk-server-high-availability-scenarios.md)   
 [使用 Windows Server 群集为 BizTalk Server 主机 2 提供高可用性](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)