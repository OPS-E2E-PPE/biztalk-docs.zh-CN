---
title: "如何将 BizTalk 主机配置为群集 Resource1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- installation, high availability
- clustering, servers
- hosts, multiple
- hosts, high availability
- Windows Server cluster
- databases, clustering
- clustering, fail-overs
- Windows Server cluster, about Windows Server cluster
- installation, planning
- clustering, databases
- clustering, best practices
- clustering, unclustering
- clustering, configuring
- installation, clustering
ms.assetid: bcd656d2-8dd6-49fc-9c42-ef5c884e52c4
caps.latest.revision: "36"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9704dbdf2bcf3549e23f1875e85a49f0ee051b2f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-a-biztalk-host-as-a-cluster-resource"></a>将 BizTalk 主机配置为群集资源
本主题将讨论要将 BizTalk 主机配置为群集资源所必须遵循的步骤。 若要完成本主题中的步骤，必须已经在 BizTalk 组中将至少两个 BizTalk 服务器配置为 Windows Server 群集的成员。 有关配置 Windows Server 群集的详细信息，请参阅 Windows Server 联机帮助。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 BizTalk Administrators 组成员的身份登录才能对主机进行群集或取消群集。  
  
## <a name="considerations-and-known-issues"></a>注意事项和已知问题  
  
-   在 BizTalk Server 上运行群集 BizTalk 主机的实例之前，必须将 BizTalk Server 配置为 Windows Server 故障转移群集中的一个节点。 有关在服务器群集中配置群集节点的详细信息，请参阅 Windows Server 联机帮助。  
  
-   无法故障转移群集的 BizTalk 主机，也可以选择的主机实例对**禁用主机启动的新实例**设置。 确保所有主机群集的 BizTalk 主机实例都没有启用此选项。 在 BizTalk Server 管理控制台中上设置此选项**主机实例属性**页。  
  
-   在群集 BizTalk 主机时，会在指定群集资源组中创建相应的群集资源。 在创建群集资源时，该群集的每个可用节点都作为群集资源的可能所有者进行添加。 由于可以将群集资源故障转移给可能所有者列表中的任何节点，因此应该在群集 BizTalk 主机之前向所有可用的群集节点添加一个主机实例。 将群集的 BizTalk 主机故障转移给不包含该主机实例的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机的尝试将会失败。  
  
    > [!NOTE]
    >  如果要阻止一个群集的 BizTalk 主机在特定群集节点上运行或故障转移给该群集节点，请从在群集 BizTalk 主机时创建的群集资源的可能所有者列表中删除该节点。 使用 Windows Server 故障转移群集管理接口可以修改群集资源的可能所有者列表。  
  
-   群集 BizTalk 主机时，确保要向其中添加主机的群集组、群集服务或应用程序包含网络名称和 IP 地址资源。 如果目标群集组包含网络名称和 IP 地址资源，则网络名称资源将会作为依存关系添加到群集的 BizTalk 主机。 如果这些资源不可用，则 BizTalk 主机将不能正常地起到群集资源的作用。  
  
-   如果你取消配置为群集的 BizTalk 主机的可能的所有者列出的 BizTalk server/群集节点，主机实例的群集资源脱机 Windows 群集中。 如果需要取消对作为群集 BizTalk 主机的可能所有者列出的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机的配置，但不希望该主机实例的群集资源变为脱机状态，请按照以下步骤操作：  
  
    -   在 Windows Server 故障转移群集管理接口中，将群集主机故障转移到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机上，而非转移到将取消配置的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机。  
  
    -   在 BizTalk Server 管理控制台中，选择对应于群集 BizTalk 主机实例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机将成为未配置。  
  
    -   删除该主机实例。 如果出现错误提示，则选择相应选项以强制删除该主机实例。  
  
    -   取消配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
-   在将 BizTalk 主机配置为群集主机时，会在群集上指定的群集资源组中创建相应的群集资源。  
  
     默认情况下，群集的 BizTalk 主机资源配置 Windows Server 故障转移群集上的以下重新启动值，都位于**策略**选项卡**属性**对话框群集资源：  
  
    |选项|值|  
    |------------|-----------|  
    |如果资源失败，请尝试在当前节点上重新启动。|**True** <br />如果资源失败，群集服务将尝试重新启动该资源。|  
    |重新启动的时段(mm:ss):|**15:00** <br />指定时间期限，在此期间内，会对重新启动尝试计数。|  
    |指定时间段内的最大重新启动次数:|**1** <br />指定重新启动尝试期间允许的最大数**期间重新启动 (mm: ss)** 。|  
    |如果重新启动失败，故障转移此服务或应用程序中的所有资源。|**True** <br />群集服务将尝试通过将整个资源组故障转移至其他群集节点来重新启动该资源。|  
    |如果所有重新启动尝试都失败，则在指定时间段 (hh:mm) 之后再次开始重新启动:|**1:00** <br />指定在其后群集服务将开始另一系列的重新启动次数延长的等待时间。|  
    |挂起超时(mm:ss):|**3:00** <br />指定资源可以采取用来更改联机和脱机之间的状态之前在群集服务使资源处于失败状态, 的时间的长度。|  
  
     默认的重新启动值规定 Windows Server 故障转移群集在 15 分钟的时间范围内对群集 BizTalk 主机实例的失败实例最多进行 1 次重新启动。 由于**如果重新启动失败，故障转移此服务或应用程序中的所有资源**值设置为**True**，任何重新启动尝试也将故障转移到另一个群集的群集资源组节点。 如果在指定的期间指定的时间段的尝试次数，无法重新启动失败的群集的 BizTalk 主机实例，则群集的 BizTalk 主机将采用的状态**失败**在故障转移群集管理接口。 如果群集的 BizTalk 主机假定的状态**失败**则在故障转移群集管理必须手动启动。  
  
     默认情况下，群集的 BizTalk 主机资源配置的服务器群集上的以下重新启动值，都位于**高级**选项卡**属性**群集的对话框资源：  
  
    |**选项**|**值**|  
    |----------------|---------------|  
    |重新启动|**True**<br /><br /> 如果资源失败，群集服务将尝试重新启动该资源。|  
    |Affect the group|**True**<br /><br /> 群集服务将尝试通过将整个资源组故障转移至其他群集节点来重新启动该资源。|  
    |Restart Threshold|**3**<br /><br /> 指定重新启动尝试期间允许的最大数**重新启动周期**。 如果重新启动尝试次数超过**重新启动阈值**期间**重新启动周期**群集资源假定的状态，然后**失败**和群集服务不会尝试任何更多的重启。|  
    |Restart Period|**900 秒**<br /><br /> 指定时间期限，在此期间内，会对重新启动尝试计数。 **重新启动周期**后第一次重新启动尝试初始化。 重新启动尝试计数重置为零如果**重新启动阈值**的持续时间不超出**重新启动周期**。|  
  
     默认的重新启动值规定 Windows Server 群集在 900 秒的时间范围内对群集 BizTalk 主机实例的失败实例最多进行 3 次重新启动。 由于**影响组**值设置为**True**，任何重新启动尝试也将故障转移到另一个群集节点的群集资源组。 如果在指定的期间指定的时间段的尝试次数，无法重新启动失败的群集的 BizTalk 主机实例，则群集的 BizTalk 主机将采用的状态**失败**在群集管理器。 如果群集的 BizTalk 主机假定的状态**失败**，则它必须手动启动在群集管理器。  
  
## <a name="procedures"></a>过程  
  
#### <a name="to-configure-a-biztalk-host-as-a-cluster-resource"></a>若要配置 BizTalk 主机作为群集资源  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台，单击以展开**BizTalk Server 管理**，单击以展开**BizTalk 组 [\<servername >:\<管理数据库 >]**，单击以展开**平台设置**，然后单击以展开**主机**。 主机列表将显示在该文件夹下。  
  
2.  右键单击你想要群集，，然后选择的主机**群集**。  
  
    > [!NOTE]
    >  在将 BizTalk 主机添加到群集组前，确保已经在作为该群集组的可能所有者的所有成员节点上创建了该主机的一个实例。  
  
3.  从可用群集组的下拉列表中选择要在其中运行该主机的群集组。  
  
    > [!NOTE]
    >  一旦群集了主机，该主机就会变为联机状态，并将开始处理配置为要在该主机中运行的任何适配器处理程序或业务流程的文档。  
  
#### <a name="to-uncluster-a-clustered-biztalk-host"></a>若要对其取消群集的 BizTalk 主机群集  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台，单击以展开**BizTalk Server 管理**，单击以展开**BizTalk 组 [\<servername >:\<管理数据库 >]**，单击以展开**平台设置**，然后单击以展开**主机**。 主机列表将显示在该文件夹下。  
  
2.  右键单击你想要对其取消群集，，然后选择的群集的主机**Uncluster**。  
  
    > [!NOTE]
    >  在对群集的主机取消群集后，与该群集主机相关联的所有主机实例都将停止，并且该主机将停止处理配置为要在该主机中运行的任何适配器处理程序或业务流程的文档。