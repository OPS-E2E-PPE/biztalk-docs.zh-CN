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
ms.openlocfilehash: 0d314e032030f7db644f8f0e180f92d963127752
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386977"
---
# <a name="how-to-configure-a-biztalk-host-as-a-cluster-resource"></a>如何将 BizTalk 主机配置为群集资源
本主题介绍将 BizTalk 主机配置为群集资源时必须遵循的步骤。 若要完成本主题中的步骤，你必须已配置至少两台 BizTalk Server 在 BizTalk 组中为 Windows Server 群集的成员。 有关配置 Windows Server 群集的详细信息，请参阅 Windows Server 联机帮助。  
  
## <a name="prerequisites"></a>先决条件  
 您必须为要群集或取消群集主机的 BizTalk Administrators 组的成员身份登录。  
  
## <a name="considerations-and-known-issues"></a>注意事项和已知的问题  
  
- 可以在 BizTalk Server 上运行的群集的 BizTalk 主机实例之前，必须为 Windows Server 故障转移群集的节点配置 BizTalk Server。 有关在服务器群集中配置的群集节点的详细信息，请参阅 Windows Server 联机帮助。  
  
- 无法故障转移群集的 BizTalk 主机到主机实例，可以选择**禁用主机实例启动**设置。 确保群集 BizTalk 主机的所有主机实例都没有启用此选项。 在 BizTalk Server 管理控制台上设置此选项**主机实例属性**页。  
  
- 在群集 BizTalk 主机时, 指定的群集资源组中创建相应的群集资源。 创建群集资源时，在群集的每个可用节点添加为群集资源的可能的所有者。 由于群集资源可以故障转移到的可能所有者列表中的任何节点中，应在群集 BizTalk 主机之前添加到所有可用的群集节点主机的实例。 尝试进行故障转移到群集的 BizTalk 主机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不包含主机的实例的计算机将会失败。  
  
  > [!NOTE]
  >  如果你想要阻止群集的 BizTalk 主机上运行或故障转移到特定群集节点中，从在群集 BizTalk 主机时创建的群集资源的可能所有者列表中删除节点。 您可以修改使用 Windows Server 故障转移群集管理接口的群集资源的可能所有者列表。  
  
- 群集 BizTalk 主机时，请确保要添加到主机的群集组中，群集的服务或应用程序包含网络名称和 IP 地址资源。 如果目标群集组包含网络名称和 IP 地址资源，然后网络名称资源已添加为依赖项到群集的 BizTalk 主机。 如果这些资源不可用，则 BizTalk 主机将不正常的群集资源。  
  
- 如果您取消对作为群集 BizTalk 主机的可能所有者列出的 BizTalk 服务器/群集节点，主机实例的群集资源是在 Windows 群集中脱机使用。 如果您需要取消对[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机作为群集 BizTalk 主机的可能所有者列出没有使主机实例的群集资源脱机，请执行以下步骤：  
  
  - 在 Windows Server 故障转移群集管理界面中，故障转移群集的主机，对[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以外的其他计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将取消配置的计算机。  
  
  - 在 BizTalk Server 管理控制台中，选择对应的群集 BizTalk 主机实例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将成为计算机未配置。  
  
  - 删除主机实例。 如果出现错误提示您选择的选项强制删除该主机实例。  
  
  - 取消对[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
- 当 BizTalk 主机配置为群集主机时，在群集上指定的群集资源组中创建相应的群集资源。  
  
   默认情况下，群集的 BizTalk 主机资源配置 Windows Server 故障转移群集上的以下重新启动值，位于**策略**选项卡**属性**对话框群集资源：  
  
  |Option|ReplTest1|  
  |------------|-----------|  
  |如果资源失败，请尝试重新启动当前节点上。|**True** <br />群集服务将尝试重新启动该资源，如果该操作失败。|  
  |重新启动 (mm: ss) 的时段：|**15:00** <br />指定的时间段期间的重新启动尝试次数进行计数。|  
  |在指定时间段内的最大重新启动：|**1** <br />指定重新启动尝试期间允许的最大数**重新启动 (mm: ss) 的时段**。|  
  |如果重新启动不成功，故障转移此服务或应用程序中的所有资源。|**True** <br />群集服务将尝试重启资源通过故障转移到另一个群集节点的整个资源组。|  
  |如果所有重新启动尝试都失败，开始指定时间段 (hh: mm) 之后再次重新启动：|**1:00** <br />指定群集服务将在其后开始另一系列的重新启动尝试延长的等待时间。|  
  |挂起超时 (mm: ss):|**3:00** <br />指定资源可能需要先更改之间联机和脱机状态，然后在群集服务使资源处于失败状态的时间的长度。|  
  
   默认值重新启动值规定 Windows Server 故障转移群集将尝试重新启动群集 BizTalk 主机的失败的实例实例 15 分钟的时间范围内最多进行 1 次。 由于**重新启动不成功，如果故障转移此服务或应用程序中的所有资源**值设置为**True**，任何重新启动尝试也将故障转移到另一个群集的群集资源组节点。 如果指定次数的尝试在指定的时间段内无法重新启动群集 BizTalk 主机的失败的实例，则群集的 BizTalk 主机将假定的状态**失败**在故障转移群集管理接口。 如果群集的 BizTalk 主机呈现的状态**失败**则必须手动启动故障转移群集管理中。  
  
   默认情况下，群集的 BizTalk 主机资源配置服务器群集上的以下重新启动值，位于**高级**选项卡**属性**群集对话框资源：  
  
  |**选项**|**ReplTest1**|  
  |----------------|---------------|  
  |重新启动|**True**<br /><br /> 群集服务将尝试重新启动该资源，如果该操作失败。|  
  |影响组|**True**<br /><br /> 群集服务将尝试重启资源通过故障转移到另一个群集节点的整个资源组。|  
  |重新启动阈值|**3**<br /><br /> 指定重新启动尝试期间允许的最大数**Restart Period**。 如果重新启动尝试次数超过**Restart Threshold**期间**Restart Period**群集资源将会呈现的状态，然后**失败**和群集服务不会尝试任何重新启动。|  
  |重新启动期间|**900 秒**<br /><br /> 指定的时间段期间的重新启动尝试次数进行计数。 **Restart Period**时第一次重新启动尝试初始化。 重新启动尝试计数会重置为零**Restart Threshold**持续时间内未超过**Restart Period**。|  
  
   默认值重新启动值规定 Windows Server 群集将尝试重新启动群集 BizTalk 主机实例的失败的实例最多 3 次 900 秒的时间范围内。 由于**影响组**值设置为**True**，任何重新启动尝试也将故障转移到另一个群集节点的群集资源组。 如果指定次数的尝试在指定的时间段中，无法重新启动群集 BizTalk 主机的失败的实例，则群集的 BizTalk 主机将假定的状态**失败**在群集管理器。 如果群集的 BizTalk 主机呈现的状态**失败**，则它必须手动启动群集管理器中。  
  
## <a name="procedures"></a>过程  
  
#### <a name="to-configure-a-biztalk-host-as-a-cluster-resource"></a>若要将 BizTalk 主机配置为群集资源  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击以展开**BizTalk Server 管理**，单击此项可展开**BizTalk 组 [\<servername\>:\<管理数据库\>]**，单击此项可展开**平台设置**，然后单击以展开**主机**。 主机列表将显示在文件夹下。  
  
2. 右键单击你想要的群集，然后选择该主机**群集**。  
  
   > [!NOTE]
   >  请确保在所有成员节点的群集组的可能所有者添加到该群集组的 BizTalk 主机之前创建的主机的实例。  
  
3. 选择你想要从下拉列表中可用的群集组的运行中的主机的群集组。  
  
   > [!NOTE]
   >  一旦群集了主机，它将进入联机状态并将开始处理文档的任何适配器处理程序或配置为在主机中运行的业务流程。  
  
#### <a name="to-uncluster-a-clustered-biztalk-host"></a>若要对群集的 BizTalk 主机取消群集  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击以展开**BizTalk Server 管理**，单击此项可展开**BizTalk 组 [\<servername\>:\<管理数据库\>]**，单击此项可展开**平台设置**，然后单击以展开**主机**。 主机列表将显示在文件夹下。  
  
2. 右键单击你想要对其取消群集，并选择该群集的主机**取消群集**。  
  
   > [!NOTE]
   >  非群集的群集的主机时，与该群集主机相关联的任何主机实例都将停止，且该主机将停止处理的任何适配器处理程序或配置为在主机中运行的业务流程的文档。