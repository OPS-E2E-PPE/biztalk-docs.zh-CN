---
title: 如何修改 Orchestration 内存限制设置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Bts10.settings.HostInstanceOrchestration
ms.assetid: f6953c68-7809-4518-87ec-e75c98884af3
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c48f1ec5e74ae577a7c1d130e22f3b4a1b53874c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-modify-orchestration-memory-throttling-settings"></a>如何修改内存阻止设置业务流程
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 主机实例内存阻止机制会连续监控阻止条件，计算阻止条件的严重性，并根据计算出的严重性以渐进方式应用主机实例内存阻止。 本主题提供了使用设置仪表板修改这些设置的分步过程。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此操作，则必须以 BizTalk Server Administrators 组成员的身份登录。  
  
### <a name="to-modify-the-orchestration-memory-throttling-settings-of-a-host-instance"></a>修改主机实例的业务流程内存阻止设置  
  
1.  在**BizTalk Server 管理控制台**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击**BizTalk 组**，然后单击**设置**。  
  
2.  在**BizTalk 设置仪表板**对话框中，在**主机实例**页上，单击**Orchestration 内存限制**选项卡。  
  
3.  执行以下操作，并依次**应用**应用修改再转到另一个选项卡。或单击**确定**应用进行修改并退出设置仪表板。  
  
    |使用此选项|执行的操作|边界值|默认值|  
    |--------------|----------------|---------------------|-------------------|  
    |**主机实例**|从下拉框中，在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时计算机上选择正在运行的主机实例。|-|-|  
  
     **物理**  
  
    |使用此选项|执行的操作|边界值|默认值|  
    |--------------|----------------|---------------------|-------------------|  
    |**最佳使用**|指定冻结阻止生效的物理内存使用率的百分比。 这是用于主机实例的物理内存的最佳百分比。|[0 – 100]|70|  
    |**最大限度地使用情况**|指定冻结阻止最大的物理内存使用率百分比。 这是用于主机实例的物理内存的最大百分比。<br /><br /> 最小值**最大限度地使用**应**最佳使用**。|（ 最佳使用量 – 100]<br /><br /> 都为 0 或都为 100 时除外。|85|  
  
     **虚拟**  
  
    |使用此选项|执行的操作|边界值|默认值|  
    |--------------|----------------|---------------------|-------------------|  
    |**最佳使用**|指定冻结阻止生效的虚拟内存使用率的百分比。<br /><br /> 此时， **TestThreshold**具有值**MaxThreshold**和任何内存使用率大于**OptimalUsage**导致**TestThreshold**要小于**MaxThreshold**。|[0 – 100]|65|  
    |**最大限度地使用情况**|指定冻结阻止最大的虚拟内存使用率百分比。<br /><br /> 此时， **TestThreshold**具有值**MinThreshold**和任何内存使用率小于**MaximalUsage**导致**TestThreshold**晚于**MinThreshold**。|（ 最佳使用量 – 100]<br /><br /> 都为 0 或都为 100 时除外。|85|  
  
    > [!NOTE]
    >  若要还原默认设置，请单击**还原为默认值**。  
  
## <a name="see-also"></a>另请参阅  
 [如何修改主机实例设置](../core/how-to-modify-host-instance-settings.md)