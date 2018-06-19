---
title: 创建高度可用的 BizTalk Server 环境 |Microsoft 文档
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
ms.openlocfilehash: 87044102248d371ea19ed07d676a0e7a0861296e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239397"
---
# <a name="creating-a-highly-available-biztalk-server-environment"></a>创建高度可用的 BizTalk Server 环境
本部分介绍如何为数据和 Microsoft 中的通信提供高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]集成不同系统和应用程序时。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]从处理的数据，使你能够解决可用性问题通过缩放数据库和承载独立的主机的数据区分开来。  
  
## <a name="demonstrating-high-availability"></a>证实高可用性  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的高可用性着重于恢复在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 部署中可能出现可用性问题的功能组件。  
  
 为了演示中的高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，你必须应用失败，并度量恢复中的产品的有效性。 高度可用的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 部署在发生错误和故障时对外部应用程序和系统几乎没有什么影响，能够确保所有服务继续正常工作，最大程度地减少中断时间。  
  
## <a name="designing-for-high-availability"></a>针对高可用性进行设计  
 设计[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供高可用性的部署涉及到实现冗余，以便在应用程序集成或业务过程集成方案涉及每个功能组件。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]从概念上讲从处理的数据的主机分离数据，从而简化了这些方案的实现。 因此，确保 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 具备高可用性将涉及运行多个主机实例并群集 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库，如下所述：  
  
-   **BizTalk 主机的体系结构**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以单独的主机并运行多个主机实例以提供高可用性的关键功能，如接收消息，处理业务流程，并将发送消息。 这些主机不需要任何其他群集或负载平衡机制因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]自动通过主机实例的多台计算机间分配工作负荷。 但是，运行 HTTP 适配器和 SOAP 适配器的接收处理程序的主机则需要如网络负载平衡 (NLB) 之类的负载平衡机制来确保高可用性。  
  
-   **BizTalk Server 数据库的体系结构**的高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库通常包含在主动/被动服务器群集配置中配置的两个或多个数据库计算机。 这些计算机共享一个公共的磁盘资源（如 RAID5 SCSI 磁盘阵列或存储区域网络），并使用 Windows 群集提供备份冗余和容错功能。  
  
> [!NOTE]
>  高度可用的环境实际上就是多计算机环境。 配置时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在多台计算机环境中，你必须使用域用户组和帐户。  
  
 由于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 建立在 Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 或 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] 以及 Microsoft SQL Server 2008 的基础之上，请确保在配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的主机前部署这些产品并确保其具备高可用性。 以下链接包括有关确保这些基础产品的高可用性的信息：  
  
-   **高可用性 – 始终在技术**、 在可用[http://go.microsoft.com/fwlink/?LinkId=130376](http://go.microsoft.com/fwlink/?LinkId=130376)。  
  
     此白皮书描述 SQL Server 2008 提供的高可用性功能。  
  
-   **高可用性解决方案概述**、 在可用[http://go.microsoft.com/fwlink/?LinkId=130377](http://go.microsoft.com/fwlink/?LinkId=130377)。  
  
     介绍了 SQL Server 2008 中若干改善服务器或数据库可用性的高可用性解决方案。  
  
-   **Windows 部署服务循序渐进指南**、 在可用[http://go.microsoft.com/fwlink/?LinkId=130379](http://go.microsoft.com/fwlink/?LinkId=130379)。  
  
     包含有关如何在 Windows Server 2008 中使用 Windows 部署服务角色的循序渐进指南。  
  
-   **Windows Server 2003 部署工具包： 规划服务器部署**、 在可用[http://go.microsoft.com/fwlink/?LinkId=24433](http://go.microsoft.com/fwlink/?LinkId=24433)。  
  
     本书介绍了有关规划服务器存储的信息，以及有关设计和部署大、中型组织中的文件服务器、打印服务器和终端服务器的信息。  
  
-   **为 BizTalk Server 增加可用性**、 在可用[http://go.microsoft.com/fwlink/?LinkId=130457](http://go.microsoft.com/fwlink/?LinkId=130457)。  
  
     部分[BizTalk Server 操作指南](http://go.microsoft.com/fwlink/?LinkId=130458)描述你可以增加的可用性的方式你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [为 BizTalk 主机提供高可用性](../core/providing-high-availability-for-biztalk-hosts.md)  
  
-   [为 BizTalk Server 数据库提供高可用性](../core/providing-high-availability-for-biztalk-server-databases.md)  
  
## <a name="see-also"></a>另请参阅  
 [示例 BizTalk Server 高可用性方案](../core/sample-biztalk-server-high-availability-scenarios.md)   
 [Windows Server 群集用于 BizTalk Server Hosts2 为提供高可用性](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)