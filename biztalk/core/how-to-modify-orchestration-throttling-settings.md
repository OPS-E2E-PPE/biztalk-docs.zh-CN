---
title: 如何修改限制设置的业务流程 |Microsoft 文档
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
ms.openlocfilehash: f868c0b6d686871211410e8861acbdec118ac302
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254621"
---
# <a name="how-to-modify-orchestration-throttling-settings"></a>如何修改业务流程阻止设置
使用 BizTalk 设置仪表板，可以在 BizTalk 组中修改给定主机的业务流程阻止配置设置。 这些设置将应用于分配到给定主机的所有主机实例。 本主题提供了修改这些设置的分步过程。  
  
 业务流程限制中指定的设置**btsntsvc.exe.config**文件中，阻止从通过限制它可具有未完成的消息数消耗太多内存的业务流程。 所有消息都继续传递到 MessageBox;但是，排队的消息不会传递到业务流程直到它处理某些其未完成的消息。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此操作，则必须以 BizTalk Server Administrators 组成员的身份登录。  
  
### <a name="to-modify-the-orchestrations-throttling-settings-of-a-host"></a>修改主机的业务流程阻止设置  
  
1.  在**BizTalk Server 管理控制台**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击**BizTalk 组**，然后单击**设置**。  
  
2.  在**BizTalk 设置仪表板**对话框中，在**主机**选项卡上，单击**业务流程限制**选项卡。  
  
3.  执行以下操作，并依次**应用**应用修改再转到另一个选项卡。或单击**确定**应用进行修改并退出设置仪表板。  
  
    |使用此选项|执行的操作|边界值|默认值|升级逻辑|  
    |--------------|----------------|---------------------|-------------------|-------------------|  
    |**主机**|从下拉列表中，选择代表 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时实例的主机。|-|-|-|  
    |**冻结行为**|选择业务流程 (XLANG) 引擎的冻结行为。 请注意只有在选中“自定义”情况下，其他 XLANG 设置才可以编辑。<br /><br /> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用这些冻结属性来确定何时对业务流程冻结和解除冻结。 在正常的负载下，默认冻结值就足够了，但如果运行在较高的负载下，并且希望改变性能特征，应优化值。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的冻结行为完全取决于有多少内存可用，以及有多少内存正在使用中。|始终<br /><br /> 从不<br /><br /> 自定义|自定义|-|  
  
     **基于时间**  
  
    |使用此选项|执行的操作|边界值|默认值|升级逻辑|  
    |--------------|----------------|---------------------|-------------------|-------------------|  
    |**最大阈值**|指定业务流程实例无法阻止的冻结之前的最大空闲时间。|(MinThreshold – 整型的最大值]|1800 秒|-|  
    |**最小阈值**|指定在冻结之前阻止业务流程实例的最短空闲时间。|[1 – 整型的最大值 ）|1 秒|-|  
    |**订阅**|选中此选项以手动设置订阅的“暂停点”和“继续点”值。 默认状态下，系统在运行时处理订阅。|打开、 关闭|Off|-|  
    |**在暂停**|指定希望订阅存储的最大消息数。<br /><br /> 当订阅具有大约或等于指定数量的等待使用的消息时，消息将不会发送到订阅实例。 消息的最小数量将是“继续点”值。<br /><br /> 例如，如果你设置**处暂停**值为 100，这意味着一个业务流程有 100 个未完成的消息和消息框将停止发送其他消息。|(ResumeAt – 整数类型的最大值]。<br /><br /> 除非都 0 时。|Off|-|  
    |**在恢复**|指定你想 MessageBox 继续将消息发送到订阅的消息数。<br /><br /> 例如，设置**恢复在**值为 50。 下 50 业务流程的邮件数时，它指定消息框可以恢复发送消息。|[0 – 整数类型的最大值)|Off|-|  
  
    > [!NOTE]
    >  若要还原默认设置，请单击**还原为默认值**。  
  
## <a name="see-also"></a>另请参阅  
 [如何修改主机设置](../core/how-to-modify-host-settings.md)