---
title: 示例 BizTalk Server 高可用性方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, small distributions
- examples, high availability
- architecture, examples
- high availability, examples
- examples, architecture
- databases, clustering
- architecture, medium distributions
- scaling
- architecture, large distributions
ms.assetid: ad9e3f57-1a23-41c2-82c9-dc8e1b29ed4d
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff4db96e89dc91ee96aaf5f0b60f0de34ce83425
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271661"
---
# <a name="sample-biztalk-server-high-availability-scenarios"></a>BizTalk Server 高可用性示例方案
本主题介绍了 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中通过对主机的各层进行扩展提供高可用性的方案。 分隔各个区域的功能分为不同的主机和中的层[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，管理员可以为每个主机提供冗余和缩放它们独立于其他主机。 若要为每个功能区域提供高可用性，应创建单独的主机，为每个主函数-接收、 处理、 发送和跟踪-和群集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库和企业单一登录的主密钥服务器。  
  
## <a name="small-biztalk-server-deployments"></a>小型 BizTalk Server 部署  
 为 SQL Server 和 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供高可用性的最小 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 部署是由两台具有 SQL Server 的主动/主动群集配置的计算机组成。 这两台计算机包含了该环境中所有 BizTalk 主机的实例。 如果其中一台计算机失败或遇到错误，另一台计算机将同时维护 SQL Server 和 BizTalk Server 的服务可用性。 此配置并不具有高可用性，因为由于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 主机实例将不会在群集企业单一登录资源处于被动的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机上启动，从而它不会提供群集的主密钥服务器。 有关群集的主密钥服务器的详细信息，请参阅[为企业单一登录的高可用性](../core/high-availability-for-enterprise-single-sign-on.md)。  
  
 对于小型[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包含少于 5 台计算机的部署，我们建议，在包含 BizTalk Server 数据库的 SQL Server 群集运行单独的计算机上从 BizTalk Server 计算机。 BizTalk Server 计算机可以运行所有 BizTalk 主机（接收、处理和发送）。 为确保此部署高度可用，请群集 SQL Server 和企业单一登录主密钥服务器，并使用两个 BizTalk Server，分别用来在您的环境中运行每个主机的实例。  
  
 下图显示了高度可用的小型 BizTalk Server 部署：  
  
 ![Small BizTalk Server 部署](../core/media/tdi-highava-smalldepl.gif "TDI_HighAva_SmallDepl")  
  
## <a name="medium-sized-biztalk-server-deployments"></a>中型 BizTalk Server 部署  
 对于包含五台至十台计算机的中型部署，建议您对包含 BizTalk Server 数据库的 SQL Server 和企业单一登录主密钥服务器进行群集。 如果您的方案需要进行大量接收，您可能希望将两台 BizTalk Server 专用于运行接收主机实例，以便提供高度可用的解决方案。 然后，您就可以具有两台以上既运行处理主机实例又运行发送主机实例的计算机。 为确保此部署高度可用，请在两台 BizTalk Server 上创建处理主机和发送主机的实例。 同样，如果您的方案需要进行大量处理，您可能希望将两台 BizTalk Server 专用于运行处理主机实例，并使用其余两台 BizTalk Server 运行接收主机和发送主机的实例。  
  
 下图显示了高度可用的中型 BizTalk Server 部署，其中包含两台专用于接收操作的 BizTalk Server：  
  
 ![中等 &#45;大小 BizTalk Server 部署](../core/media/tdi-highava-meddepl.gif "TDI_HighAva_MedDepl")  
  
 为企业单一登录高可用性的详细信息，请参阅[为企业单一登录的高可用性](../core/high-availability-for-enterprise-single-sign-on.md)。  
  
## <a name="large-scale-biztalk-server-deployments"></a>大规模 BizTalk Server 部署  
 对于包含十台或更多台计算机的大型部署，请将单独的 BizTalk Server 计算机分别专用于接收、处理和发送功能。 此外，如果组中具有多台 BizTalk Server 计算机，您可以包括其他 MessageBox 数据库计算机以提高性能。 在这种情况下，群集 MessageBox 数据库和主密钥服务器可确保高可用性。  
  
 此类分布式的配置演示的灵活性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]因为这样可以评估和确定特定部署中的故障点，然后从战略角度将分配资源以减少系统中的这些时间点。 当今瞬息万变的业务环境需要这种灵活性以应对工作负荷波动和业务需求的日常变化。  
  
 您可以将资源从资源使用量较少的计算机中移至需要大量资源的计算机中，从而使用现有资源来实现高可用性，而不用另外花费资金进行升级或采购新硬件。  
  
 下图显示了大规模[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署。  
  
 ![大型 &#45;缩放 BizTalk Server 部署](../core/media/tdi-highava-largedepl.gif "TDI_HighAva_LargeDepl")  
  
 为企业单一登录高可用性的详细信息，请参阅[为企业单一登录的高可用性](../core/high-availability-for-enterprise-single-sign-on.md)。  
  
## <a name="providing-high-availability-using-hyper-v-and-failover-clustering"></a>使用 Hyper-V 和故障转移群集提供高可用性  
 Windows® Server 2008 Hyper-V 角色和 Windows Server 2008 故障转移群集功能可以一起用来为虚拟化的服务器计算环境提供高可用性。 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 部署中使用的 BizTalk Server 计算机和 SQL Server 计算机可以安装在 Hyper-V 虚拟化环境中，然后通过故障转移群集使其具有高可用性。 由于在 Hyper-V 上运行来宾操作系统涉及到系统资源成本，因此建议在将此解决方案部署到生产之前执行详细性能测试。 有关使用 HYPER-V 和故障转移群集在一起的详细信息来为虚拟机提供高可用性，请参阅"HYPER-V 分步指南:: HYPER-V 和故障转移群集"在[http://go.microsoft.com/fwlink/?LinkID=129113](http://go.microsoft.com/fwlink/?LinkID=129113)。 有关部署的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到 HYPER-V 虚拟化环境中，请参阅 BizTalk Server HYPER-V 指南下载[http://go.microsoft.com/fwlink/?LinkId=189706](http://go.microsoft.com/fwlink/?LinkId=189706)。  
  
## <a name="see-also"></a>另请参阅  
 [为 BizTalk 主机提供高可用性](../core/providing-high-availability-for-biztalk-hosts.md)   
 [为 BizTalk Server 数据库提供高可用性](../core/providing-high-availability-for-biztalk-server-databases.md)   
 [为企业单一登录的高可用性](../core/high-availability-for-enterprise-single-sign-on.md)