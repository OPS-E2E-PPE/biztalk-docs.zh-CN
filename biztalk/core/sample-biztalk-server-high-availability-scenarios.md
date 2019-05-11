---
title: 示例 BizTalk Server 高可用性方案 |Microsoft Docs
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
ms.openlocfilehash: 950f82a57c1f0be599fa9fbcceb4b6a590a0576e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393919"
---
# <a name="sample-biztalk-server-high-availability-scenarios"></a>BizTalk Server 高可用性示例方案
本主题介绍 Microsoft 中的方案[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供通过向外扩展的主机的各层的高可用性。 通过分隔到不同的主机的功能和层中的区域[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，管理员可以为每个主机提供冗余和缩放其独立于其他主机。 若要为每个功能区域中提供高可用性，请创建单独的主机的每个主要功能 — 接收、 处理、 发送和跟踪，以及群集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库和企业单一登录主密钥服务器。  
  
## <a name="small-biztalk-server-deployments"></a>小型 BizTalk Server 部署  
 最小[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署为这两个 SQL Server 提供高可用性和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]具有适用于 SQL Server 的主动/被动群集配置的两台计算机组成。 这两台计算机包含在环境中的所有 BizTalk 主机的实例。 如果一台计算机失败或遇到错误，另一台计算机维护服务可用性的 SQL Server 和 BizTalk Server。 此配置不具有高可用性，因为它不适用于聚类分析主密钥服务器，因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机实例将不会启动上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]被动群集的企业单一登录资源的计算机。 有关群集主密钥服务器的详细信息，请参阅[为企业单一登录的高可用性](../core/high-availability-for-enterprise-single-sign-on.md)。  
  
 对于小型[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包含少于五台计算机的部署，我们建议，包含 BizTalk Server 数据库的 SQL Server 群集运行单独的计算机上从 BizTalk Server 计算机。 BizTalk Server 计算机可以运行所有 BizTalk 主机 （接收、 处理和发送）。 若要使此部署高度可用，群集 SQL Server 和企业单一登录主密钥服务器，并有两个 BizTalk 服务器，每个环境中运行的每个主机实例。  
  
 下图显示了高度可用的小型 BizTalk Server 部署。  
  
 ![小型 BizTalk Server 部署](../core/media/tdi-highava-smalldepl.gif "TDI_HighAva_SmallDepl")  
  
## <a name="medium-sized-biztalk-server-deployments"></a>中型 BizTalk Server 部署  
 对于包含五到十台计算机的中型部署，我们建议您群集包含 BizTalk Server 数据库的 SQL 服务器和企业单一登录主密钥服务器。 如果你的方案是接收密集型的可能想要将专用两台 BizTalk Server 运行接收主机实例以提供高度可用的解决方案。 然后，您可以运行这两个处理和发送主机实例的两个多个计算机。 若要使此高度可用的部署，创建的这两个处理主机实例并发送两台 BizTalk 服务器上的主机。 同样，如果您有一个需要进行大量处理的方案，你可能想要将两个 BizTalk Server 运行处理主机实例，并有剩余的两个 BizTalk Server 正在运行的实例的两个接收和发送主机专用于。  
  
 下图显示了高度可用中型 BizTalk Server 部署具有两个 BizTalk 服务器专用于接收操作。  
  
 ![中等&#45;调整大小的 BizTalk Server 部署](../core/media/tdi-highava-meddepl.gif "TDI_HighAva_MedDepl")  
  
 企业单一登录的高可用性的详细信息，请参阅[为企业单一登录的高可用性](../core/high-availability-for-enterprise-single-sign-on.md)。  
  
## <a name="large-scale-biztalk-server-deployments"></a>大型 BizTalk Server 部署  
 对于包含 10 个或多台计算机的大规模部署，将专用于接收、 处理和发送功能不同的 BizTalk Server 计算机。 此外，如果您有很多 BizTalk Server 计算机组中，可以包括其他 MessageBox 数据库计算机以提高性能。 在这种情况下，群集 MessageBox 数据库和主密钥服务器以提供高可用性。  
  
 此类分布式的配置展示的灵活性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]因为它允许您评估和确定你的部署中的失败的特定点并然后策略性地分配资源，以减少系统中的这些时间点。 当今业务环境需要这种灵活性，因为工作负荷波动和业务要求可以每日更改。  
  
 而不是不用另外花费资金进行升级或采购新硬件，您可以使用现有资源来通过将资源从资源使用量较少的是占用大量资源的计算机的计算机实现高可用性。  
  
 下图显示了大规模[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署。  
  
 ![大型&#45;BizTalk Server 部署规模](../core/media/tdi-highava-largedepl.gif "TDI_HighAva_LargeDepl")  
  
 企业单一登录的高可用性的详细信息，请参阅[为企业单一登录的高可用性](../core/high-availability-for-enterprise-single-sign-on.md)。  
  
## <a name="providing-high-availability-using-hyper-v-and-failover-clustering"></a>提供使用 HYPER-V 和故障转移群集实现高可用性  
 Windows® Server 2008 HYPER-V 角色和 Windows Server 2008 故障转移群集功能可一起为虚拟化的服务器计算环境提供高可用性。 BizTalk Server 计算机中使用的 SQL Server 计算机和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以安装在 HYPER-V 虚拟化环境中部署，然后进行故障转移群集在高度可用。 由于没有与 HYPER-V 上运行来宾操作系统相关的系统资源成本，我们建议，此解决方案部署到生产环境之前执行详细性能测试。 有关使用 HYPER-V 和故障转移群集的详细信息一起若要为虚拟机提供高可用性，请参阅"HYPER-V 循序渐进指南：HYPER-V 和故障转移群集"处[ http://go.microsoft.com/fwlink/?LinkID=129113 ](http://go.microsoft.com/fwlink/?LinkID=129113)。 有关部署的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到 HYPER-V 虚拟化环境中，请参阅 BizTalk Server HYPER-V 指南下载[ http://go.microsoft.com/fwlink/?LinkId=189706 ](http://go.microsoft.com/fwlink/?LinkId=189706)。  
  
## <a name="see-also"></a>请参阅  
 [为 BizTalk 主机提供高可用性](../core/providing-high-availability-for-biztalk-hosts.md)   
 [为 BizTalk Server 数据库提供高可用性](../core/providing-high-availability-for-biztalk-server-databases.md)   
 [企业单一登录的高可用性](../core/high-availability-for-enterprise-single-sign-on.md)