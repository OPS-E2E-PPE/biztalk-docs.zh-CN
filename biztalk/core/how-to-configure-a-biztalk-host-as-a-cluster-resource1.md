---
title: 如何将 BizTalk 主机配置为群集 Resource1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 36
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53df974ec3b0fdf93b4e1cd59c9144b5b33af424
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981982"
---
# <a name="how-to-configure-a-biztalk-host-as-a-cluster-resource"></a>将 BizTalk 主机配置为群集资源
本主题将讨论要将 BizTalk 主机配置为群集资源所必须遵循的步骤。 若要完成本主题中的步骤，必须已经在 BizTalk 组中将至少两个 BizTalk 服务器配置为 Windows Server 群集的成员。 有关配置 Windows Server 群集的详细信息，请参阅 Windows Server 联机帮助。  
  
## <a name="prerequisites"></a>必要條件  
 必须以 BizTalk Administrators 组成员的身份登录才能对主机进行群集或取消群集。  
  
## <a name="considerations-and-known-issues"></a>注意事项和已知问题  
  
- 在 BizTalk Server 上运行群集 BizTalk 主机的实例之前，必须将 BizTalk Server 配置为 Windows Server 故障转移群集中的一个节点。 有关在服务器群集中配置群集节点的详细信息，请参阅 Windows Server 联机帮助。  
  
- 无法故障转移群集的 BizTalk 主机到主机实例，可以选择**禁用主机实例启动**设置。 确保群集 BizTalk 主机的所有主机实例都没有启用此选项。 在 BizTalk Server 管理控制台上设置此选项**主机实例属性**页。  
  
- 在群集 BizTalk 主机时，会在指定群集资源组中创建相应的群集资源。 在创建群集资源时，该群集的每个可用节点都作为群集资源的可能所有者进行添加。 由于可以将群集资源故障转移给可能所有者列表中的任何节点，因此应该在群集 BizTalk 主机之前向所有可用的群集节点添加一个主机实例。 将群集的 BizTalk 主机故障转移给不包含该主机实例的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机的尝试将会失败。  
  
  > [!NOTE]
  >  如果要阻止一个群集的 BizTalk 主机在特定群集节点上运行或故障转移给该群集节点，请从在群集 BizTalk 主机时创建的群集资源的可能所有者列表中删除该节点。 使用 Windows Server 故障转移群集管理接口可以修改群集资源的可能所有者列表。  
  
- 群集 BizTalk 主机时，确保要向其中添加主机的群集组、群集服务或应用程序包含网络名称和 IP 地址资源。 如果目标群集组包含网络名称和 IP 地址资源，则网络名称资源将会作为依存关系添加到群集的 BizTalk 主机。 如果这些资源不可用，则 BizTalk 主机将不能正常地起到群集资源的作用。  
  
- 如果您取消对作为群集 BizTalk 主机的可能所有者列出的 BizTalk 服务器/群集节点，主机实例的群集资源是在 Windows 群集中脱机使用。 如果需要取消对作为群集 BizTalk 主机的可能所有者列出的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机的配置，但不希望该主机实例的群集资源变为脱机状态，请按照以下步骤操作：  
  
  - 在 Windows Server 故障转移群集管理接口中，将群集主机故障转移到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机上，而非转移到将取消配置的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机。  
  
  - 在 BizTalk Server 管理控制台中，选择对应的群集 BizTalk 主机实例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将成为计算机未配置。  
  
  - 删除该主机实例。 如果出现错误提示，则选择相应选项以强制删除该主机实例。  
  
  - 取消配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
- 在将 BizTalk 主机配置为群集主机时，会在群集上指定的群集资源组中创建相应的群集资源。  
  
   默认情况下，群集的 BizTalk 主机资源配置 Windows Server 故障转移群集上的以下重新启动值，位于**策略**选项卡**属性**对话框群集资源：  
  
  |选项|ReplTest1|  
  |------------|-----------|  
  |如果资源失败，请尝试在当前节点上重新启动。|**True** <br />如果资源失败，群集服务将尝试重新启动该资源。|  
  |重新启动的时段(mm:ss):|**15:00** <br />指定时间期限，在此期间内，会对重新启动尝试计数。|  
  |指定时间段内的最大重新启动次数:|**1** <br />指定重新启动尝试期间允许的最大数**重新启动 (mm: ss) 的时段**。|  
  |如果重新启动不成功，故障转移此服务或应用程序中的所有资源。|**True** <br />群集服务将尝试通过将整个资源组故障转移至其他群集节点来重新启动该资源。|  
  |如果所有重新启动尝试都失败，则在指定时间段 (hh:mm) 之后再次开始重新启动:|**1:00** <br />指定群集服务将在其后开始另一系列的重新启动尝试延长的等待时间。|  
  |挂起超时(mm:ss):|**3:00** <br />指定资源可能需要先更改之间联机和脱机状态，然后在群集服务使资源处于失败状态的时间的长度。|  
  
   默认的重新启动值规定 Windows Server 故障转移群集在 15 分钟的时间范围内对群集 BizTalk 主机实例的失败实例最多进行 1 次重新启动。 由于**重新启动不成功，如果故障转移此服务或应用程序中的所有资源**值设置为**True**，任何重新启动尝试也将故障转移到另一个群集的群集资源组节点。 如果指定次数的尝试在指定的时间段内无法重新启动群集 BizTalk 主机的失败的实例，则群集的 BizTalk 主机将假定的状态**失败**在故障转移群集管理接口。 如果群集的 BizTalk 主机呈现的状态**失败**则必须手动启动故障转移群集管理中。  
  
   默认情况下，群集的 BizTalk 主机资源配置服务器群集上的以下重新启动值，位于**高级**选项卡**属性**群集对话框资源：  
  
  |**选项**|**ReplTest1**|  
  |----------------|---------------|  
  |重新启动|**True**<br /><br /> 如果资源失败，群集服务将尝试重新启动该资源。|  
  |Affect the group|**True**<br /><br /> 群集服务将尝试通过将整个资源组故障转移至其他群集节点来重新启动该资源。|  
  |Restart Threshold|**3**<br /><br /> 指定重新启动尝试期间允许的最大数**Restart Period**。 如果重新启动尝试次数超过**Restart Threshold**期间**Restart Period**群集资源将会呈现的状态，然后**失败**和群集服务不会尝试任何重新启动。|  
  |Restart Period|**900 秒**<br /><br /> 指定时间期限，在此期间内，会对重新启动尝试计数。 **Restart Period**时第一次重新启动尝试初始化。 重新启动尝试计数会重置为零**Restart Threshold**持续时间内未超过**Restart Period**。|  
  
   默认的重新启动值规定 Windows Server 群集在 900 秒的时间范围内对群集 BizTalk 主机实例的失败实例最多进行 3 次重新启动。 由于**影响组**值设置为**True**，任何重新启动尝试也将故障转移到另一个群集节点的群集资源组。 如果指定次数的尝试在指定的时间段中，无法重新启动群集 BizTalk 主机的失败的实例，则群集的 BizTalk 主机将假定的状态**失败**在群集管理器。 如果群集的 BizTalk 主机呈现的状态**失败**，则它必须手动启动群集管理器中。  
  
## <a name="procedures"></a>过程  
  
#### <a name="to-configure-a-biztalk-host-as-a-cluster-resource"></a>若要将 BizTalk 主机配置为群集资源  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击以展开**BizTalk Server 管理**，单击此项可展开**BizTalk 组 [\<servername\>:\<管理数据库\>]**，单击此项可展开**平台设置**，然后单击以展开**主机**。 主机列表将显示在该文件夹下。  
  
2. 右键单击你想要的群集，然后选择该主机**群集**。  
  
   > [!NOTE]
   >  在将 BizTalk 主机添加到群集组前，确保已经在作为该群集组的可能所有者的所有成员节点上创建了该主机的一个实例。  
  
3. 从可用群集组的下拉列表中选择要在其中运行该主机的群集组。  
  
   > [!NOTE]
   >  一旦群集了主机，该主机就会变为联机状态，并将开始处理配置为要在该主机中运行的任何适配器处理程序或业务流程的文档。  
  
#### <a name="to-uncluster-a-clustered-biztalk-host"></a>若要对群集的 BizTalk 主机取消群集  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击以展开**BizTalk Server 管理**，单击此项可展开**BizTalk 组 [\<servername\>:\<管理数据库\>]**，单击此项可展开**平台设置**，然后单击以展开**主机**。 主机列表将显示在该文件夹下。  
  
2. 右键单击你想要对其取消群集，并选择该群集的主机**取消群集**。  
  
   > [!NOTE]
   >  在对群集的主机取消群集后，与该群集主机相关联的所有主机实例都将停止，并且该主机将停止处理配置为要在该主机中运行的任何适配器处理程序或业务流程的文档。