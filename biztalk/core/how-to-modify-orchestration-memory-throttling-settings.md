---
title: 如何修改业务流程内存阻止设置 |Microsoft Docs
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
ms.openlocfilehash: 839ef9d8d97e06c85192c3d8fee049029942fb99
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336053"
---
# <a name="how-to-modify-orchestration-memory-throttling-settings"></a>如何修改业务流程内存阻止设置
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机实例内存阻止机制会连续监控阻止条件，计算阻止条件的严重性和应用主机实例内存阻止以渐进方式具体取决于计算严重级别。 本主题提供了使用设置仪表板修改这些设置的分步过程。  

## <a name="prerequisites"></a>先决条件  
 若要执行此操作，必须以 BizTalk Server Administrators 组的成员的身份登录。  

### <a name="to-modify-the-orchestration-memory-throttling-settings-of-a-host-instance"></a>若要修改业务流程内存阻止设置的主机实例  

1. 在中**BizTalk Server 管理控制台**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击**BizTalk 组**，然后单击**设置**。  

2. 在中**BizTalk 设置仪表板**对话框中，在**主机实例**页上，单击**业务流程内存阻止**选项卡。  

3. 执行以下操作，然后依次**应用**以应用修改并转到另一个选项卡。或单击**确定**应用所做的修改并退出设置仪表板。  


   |     使用此选项      |                                                                                执行的操作                                                                                | 边界值 | 默认值 |
   |-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|---------------|
   | **主机实例** | 从下拉列表框中，选择正在运行的主机实例上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时计算机。 |        -        |       -       |

    **物理**  

   |使用此选项|执行的操作|边界值|默认值|  
   |--------------|----------------|---------------------|-------------------|  
   |**最佳使用率**|指定的冻结阻止生效的物理内存使用率的百分比。 这是用于主机实例的物理内存的最佳百分比。|[0 – 100]|70|  
   |**最大使用率**|指定冻结阻止处于最大物理内存使用率的百分比。 这是用于主机实例的物理内存的最大百分比。<br /><br /> 最小值**最大使用率**应**最佳使用率**。|（最佳使用量 – 100]<br /><br /> 两者都是 0 或 100 时除外。|85|  

    **Virtual**  

   |使用此选项|执行的操作|边界值|默认值|  
   |--------------|----------------|---------------------|-------------------|  
   |**最佳使用率**|指定冻结阻止生效的虚拟内存使用率的百分比。<br /><br /> 在此情况下， **TestThreshold**具有值**MaxThreshold** ，大于任何内存使用量**OptimalUsage**会导致**TestThreshold**为小于**MaxThreshold**。|[0 – 100]|65|  
   |**最大使用率**|指定冻结阻止处于最大虚拟内存使用率的百分比。<br /><br /> 在此情况下， **TestThreshold**具有值**MinThreshold** ，任何内存使用量小于**MaximalUsage**会导致**TestThreshold**大于**MinThreshold**。|（最佳使用量 – 100]<br /><br /> 两者都是 0 或 100 时除外。|85|  

   > [!NOTE]
   >  若要还原默认设置，请单击**还原为默认值**。  

## <a name="see-also"></a>请参阅  
 [如何修改主机实例设置](../core/how-to-modify-host-instance-settings.md)