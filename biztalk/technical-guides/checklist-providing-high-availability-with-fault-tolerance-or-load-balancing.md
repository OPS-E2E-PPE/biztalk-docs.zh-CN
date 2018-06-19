---
title: 清单： 容错或负载平衡提供高可用性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c93cfc3-05b2-43ad-b0a9-b7f0d2596113
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72976dba4ed30ad6747d2d6175702110fe9730a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299605"
---
# <a name="checklist-providing-high-availability-with-fault-tolerance-or-load-balancing"></a>清单： 会提供高可用性容错或负载平衡
本主题列出为配置容错能力和/或负载平衡的生产型的组件，应完成的步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境，以提供高可用性。 这些组件的容错功能的配置将允许系统以特定组件失败时继续操作。  
  
|步骤|参考|  
|-----------|---------------|  
|创建多个 BizTalk 主机实例，并实现主机群集的这些适配器需要它的支持。|[BizTalk 主机的高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)|  
|配置跟踪以实现高可用性的主机。|[BizTalk 主机的高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)|  
|配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上聚集数据库[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Windows server 群集实例上的。|[数据库的高可用性](../technical-guides/high-availability-for-databases.md)|  
|配置跟踪以实现高可用性的主机。 验证有与启用其中 N 是 BizTalk 组中的 MessageBox 数据库数目跟踪至少 N + 1 个主机实例。|若要启用跟踪的主机，请选择该选项以**允许主机跟踪**上**主机属性**对话框可从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 有关设置主机属性的详细信息，请参阅主题[如何修改主机属性](http://go.microsoft.com/fwlink/?LinkId=154359)(http://go.microsoft.com/fwlink/?LinkId=154359)。|  
|练习定期执行，以确保故障转移功能的数据库故障转移。|应直接分配这一职责，以确保这在以一致的方式上完成。|  
|验证是否有足够的处理能力和被动群集节点上的内存，若要启用多个[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例同时运行在故障转移方案中。|如果两个 SQL 实例定期使用超过 50%的各个群集节点上的资源，然后在时两个实例的故障转移到单个节点，每个实例将会遇到性能下降。 因此，测试应该进行以确保单个群集节点将能够处理负载，直到出现故障的节点重新联机。 如果单个节点不能处理的两个 SQL 实例负载请考虑添加其他群集节点，以实现主动/主动/被动群集拓扑。|  
|实现存储区域网络 (SAN) 到内部[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。 **注意：** 如果可能，请配置 SAN 磁盘使用 RAID 1 + 0 （带区的镜像集） 的最大的性能和高可用性的拓扑。|在["BizTalk Server 数据库优化白皮书"](http://go.microsoft.com/fwlink/?linkid=104427) (http://go.microsoft.com/fwlink/?linkid=104427)，请参阅"性能优化"下的"磁盘基础结构"部分。|  
|使用 Windows 群集群集企业单一登录 (SSO) 主密钥服务器。|[主密钥服务器的高可用性](../technical-guides/high-availability-for-the-master-secret-server.md)**注意：** 运行的计算机上未群集 SSO 服务[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]除非您的群集实现 SSO 和相同的群集组中的 BizTalk 主机。 有关群集 SSO 服务的详细信息和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机相同的群集组中看到[如何群集 SSO 和相同的群集组中的 BizTalk 主机](http://go.microsoft.com/fwlink/?LinkId=154367)(http://go.microsoft.com/fwlink/?LinkId=154367)。|  
|备份企业单一登录 (SSO) 主密钥。|请参阅[如何备份主密钥](http://go.microsoft.com/fwlink/?LinkID=151395)(http://go.microsoft.com/fwlink/?LinkID=151395)。|  
|配置 Internet Information Services (IIS) Web 服务器隔离的主机实例和 BAM 门户 Web 页后，可以将高度可用的使用网络负载平衡 (NLB) 或其他负载平衡设备。|**对于 Windows Server 2008**： 请参阅[网络负载平衡部署指南](http://go.microsoft.com/fwlink/?LinkId=153139)(http://go.microsoft.com/fwlink/?LinkId=153139)。|  
  
## <a name="see-also"></a>另请参阅  
 [提供高可用性](../technical-guides/providing-high-availability.md)