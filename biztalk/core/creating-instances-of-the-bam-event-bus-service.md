---
title: 创建的 BAM 事件总线服务实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 454bdde7-45a6-41ab-9196-f662273f0f2b
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba406ca55a4d317284c450262f96c06412bf8edd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389935"
---
# <a name="creating-instances-of-the-bam-event-bus-service"></a>创建 BAM 事件总线服务的实例
在 BizTalk 应用程序主机中运行 BAM 事件总线服务。 您可以使用默认主机来承载 BAM 事件总线服务，或者可以创建新的主机。 如果某个主机作为 BAM 事件总线服务，你也创建为该主机的任何新实例将承载服务。  
  
 有关默认主机的信息，请参阅[主机](../core/hosts.md)。  
  
 有关创建主机的信息，请参阅[如何创建新的主机](../core/how-to-create-a-new-host.md)。  
  
 有关创建主机实例的信息，请参阅[如何将主机实例添加](../core/how-to-add-a-host-instance.md)。  
  
 有关创建和配置主机和主机实例的信息，请参阅[管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md)。  
  
### <a name="to-create-the-host-that-hosts-the-bam-event-bus-service"></a>若要创建承载 BAM 事件总线服务主机  
  
1. 单击**启动**，依次指向**所有程序**，单击**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在 BizTalk 管理控制台窗口中，展开**BizTalk Server 管理**节点，展开**Biztalk 组**节点，展开**平台设置**节点用鼠标右键单击**主机**节点中，选择**新建**，然后单击**主机**。  
  
3. 在中**主机属性**对话框中**名称**框中，键入主机的描述性名称。  
  
4. 上**常规**选项卡上，选择**允许主机跟踪**复选框。  
  
    新的子节点下显示**主机**与新主机的名称的节点。  
  
5. 在中**Windows 组**框中，键入要分配此主机，然后单击 Windows 组的名称**确定**。  
  
    新的子节点下显示**主机**与新主机的名称的节点。  
  
### <a name="to-create-a-new-host-instance-of-the-host"></a>若要创建新的主机实例的主机  
  
1.  右键单击**主机实例**节点中，选择**新建**，然后单击**主机实例**。  
  
2.  选择的服务器位置的主机实例将运行，然后依次**确定**。  
  
### <a name="to-add-hosting-tracking-to-the-host"></a>若要向主机添加主机跟踪  
  
1.  右键单击你想要重新配置，然后单击的主机**属性**。  
  
2.  上**常规**选项卡上，选择**允许主机跟踪**，然后单击**确定**。  
  
3.  重新启动该主机的所有实例。  
  
### <a name="to-remove-hosting-tracking-from-the-host"></a>若要从主机删除主机跟踪  
  
1.  右键单击你想要删除主机跟踪，的主机，然后单击**属性**。  
  
2.  清除**允许主机跟踪**复选框，然后依次**确定**。  
  
3.  重新启动该主机的实例。  
  
## <a name="see-also"></a>请参阅  
 [管理 BAM 事件总线服务](../core/managing-the-bam-event-bus-service.md)   
 [BAM 安全建议](../core/bam-security-recommendations.md)   
 [业务活动监视 (BAM)](../core/business-activity-monitoring-bam.md)