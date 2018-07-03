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
ms.openlocfilehash: 444f0a53827f99bda3eeb2389c555e614c44fe04
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022155"
---
# <a name="how-to-modify-orchestration-memory-throttling-settings"></a>如何修改内存阻止设置业务流程
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 主机实例内存阻止机制会连续监控阻止条件，计算阻止条件的严重性，并根据计算出的严重性以渐进方式应用主机实例内存阻止。 本主题提供了使用设置仪表板修改这些设置的分步过程。  

## <a name="prerequisites"></a>必要條件  
 若要执行此操作，则必须以 BizTalk Server Administrators 组成员的身份登录。  

### <a name="to-modify-the-orchestration-memory-throttling-settings-of-a-host-instance"></a>修改主机实例的业务流程内存阻止设置  

1. 在中**BizTalk Server 管理控制台**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击**BizTalk 组**，然后单击**设置**。  

2. 在中**BizTalk 设置仪表板**对话框中，在**主机实例**页上，单击**业务流程内存阻止**选项卡。  

3. 执行以下操作，然后依次**应用**以应用修改并转到另一个选项卡。或单击**确定**应用所做的修改并退出设置仪表板。  


   |     使用此选项      |                                                                                执行的操作                                                                                | 边界值 | 默认值 |
   |-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|---------------|
   | **主机实例** | 从下拉框中，在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时计算机上选择正在运行的主机实例。 |        -        |       -       |

    **物理**  

   |使用此选项|执行的操作|边界值|默认值|  
   |--------------|----------------|---------------------|-------------------|  
   |**最佳使用率**|指定冻结阻止生效的物理内存使用率的百分比。 这是用于主机实例的物理内存的最佳百分比。|[0 – 100]|70|  
   |**最大使用率**|指定冻结阻止最大的物理内存使用率百分比。 这是用于主机实例的物理内存的最大百分比。<br /><br /> 最小值**最大使用率**应**最佳使用率**。|（ 最佳使用量 – 100]<br /><br /> 都为 0 或都为 100 时除外。|85|  

    **虚拟**  

   |使用此选项|执行的操作|边界值|默认值|  
   |--------------|----------------|---------------------|-------------------|  
   |**最佳使用率**|指定冻结阻止生效的虚拟内存使用率的百分比。<br /><br /> 在此情况下， **TestThreshold**具有值**MaxThreshold** ，大于任何内存使用量**OptimalUsage**会导致**TestThreshold**为小于**MaxThreshold**。|[0 – 100]|65|  
   |**最大使用率**|指定冻结阻止最大的虚拟内存使用率百分比。<br /><br /> 在此情况下， **TestThreshold**具有值**MinThreshold** ，任何内存使用量小于**MaximalUsage**会导致**TestThreshold**大于**MinThreshold**。|（ 最佳使用量 – 100]<br /><br /> 都为 0 或都为 100 时除外。|85|  

   > [!NOTE]
   >  若要还原默认设置，请单击**还原为默认值**。  

## <a name="see-also"></a>请参阅  
 [如何修改主机实例设置](../core/how-to-modify-host-instance-settings.md)