---
title: 如何修改业务流程阻止设置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Bts10.settings.HostOrchestration
ms.assetid: 30086994-cb55-4ff7-9940-df197e5e35ce
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4dd51b52aea9d38ba9f6f9911680ae27b069b58c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384582"
---
# <a name="how-to-modify-orchestration-throttling-settings"></a>如何修改业务流程阻止设置
使用 BizTalk 设置仪表板，可以修改的业务流程的给定主机的配置设置阻止跨 BizTalk 组。 这些设置适用于所有分配给给定主机的主机实例。 本主题提供了修改这些设置的分步过程。  

 限制设置中指定的业务流程**btsntsvc.exe.config**文件中，防止业务流程占用太多内存的限制可以具有的未处理消息的数量。 所有消息将都继续传送到 MessageBox 中;但是，排队的消息不会传递到业务流程直到它处理某些其未处理的消息。  

## <a name="prerequisites"></a>先决条件  
 若要执行此操作，必须以 BizTalk Server Administrators 组的成员的身份登录。  

### <a name="to-modify-the-orchestrations-throttling-settings-of-a-host"></a>若要修改的业务流程阻止主机设置  

1. 在中**BizTalk Server 管理控制台**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击**BizTalk 组**，然后单击**设置**。  

2. 在中**BizTalk 设置仪表板**对话框中，在**主机**选项卡上，单击**业务流程阻止**选项卡。  

3. 执行以下操作，然后依次**应用**以应用修改并转到另一个选项卡。或单击**确定**应用所做的修改并退出设置仪表板。  


   |         使用此选项         |                                                                                                                                                                                                                                                                                                                                                               执行的操作                                                                                                                                                                                                                                                                                                                                                                |               边界值               | 默认值 | 升级逻辑 |
   |--------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------|---------------|---------------|
   |         **主机**         |                                                                                                                                                                                                                                                                                     从下拉列表中，选择表示主机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时实例。                                                                                                                                                                                                                                                                                     |                      -                      |       -       |       -       |
   | **冻结行为** | 选择业务流程 (XLANG) 引擎的冻结行为。 请注意，仅当选择"自定义"可编辑其他 XLANG 设置。<br /><br /> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用冻结属性来确定何时冻结和解除冻结业务流程。 在正常负载时，默认冻结值就足够了，但如果在重负载下运行，并且希望改变性能特征，应优化值。 冻结行为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]完全取决于可用内存量是以及所使用的内存量。 | 始终<br /><br /> 从不<br /><br /> 自定义 |    自定义     |       -       |

    **基于时间**  

   |使用此选项|执行的操作|边界值|默认值|升级逻辑|  
   |--------------|----------------|---------------------|-------------------|-------------------|  
   |**最大阈值**|指定在冻结之前阻止业务流程实例的最大空闲时间。|(MinThreshold – 整型的最大值]|为 1800 秒|-|  
   |**最小阈值**|指定在冻结之前阻止业务流程实例的最小空闲时间。|[1 – 最大值类型为 Integer）|1 秒|-|  
   |**订阅**|选择此选项可手动设置的暂停点和继续点值的订阅。 默认情况下，系统将负责在运行时的订阅。|On、 Off|Off|-|  
   |**在暂停**|指定你想要存储的订阅的消息的最大数目。<br /><br /> 当订阅具有大于或等于指定数字的消息等待使用时，消息不传送到订阅实例。 消息的最小数量将是继续点值。<br /><br /> 例如，如果您设置**处暂停**值为 100，这意味着业务流程具有 100 个未完成的消息，并且 MessageBox 将停止发送其他消息。|(ResumeAt – 整数类型的最大值]。<br /><br /> 两者均为 0 时除外。|Off|-|  
   |**继续点**|指定您希望继续将消息发送到订阅 MessageBox 的消息数。<br /><br /> 例如，设置**继续点**为 50 的值。 未处理消息的业务流程的数量下降到 50 时，它指定 MessageBox 可以继续发送消息。|[0 – 整数类型的最大值)|Off|-|  

   > [!NOTE]
   >  若要还原默认设置，请单击**还原为默认值**。  

## <a name="see-also"></a>请参阅  
 [如何修改主机设置](../core/how-to-modify-host-settings.md)