---
title: "配置批处理确认 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching, acknowledgements
- acknowledgements, batching
ms.assetid: f3529638-e036-4270-ae6d-1bdc3ef98727
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60e6c9b3a6fadfcc0407c1b4fa206d0f966fa7dd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="configuring-batching-acknowledgments"></a>配置批处理确认
你使用[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]配置资源管理器来指定入站和生成的确认的确认属性。  
  
### <a name="to-run-btahl7-configuration-explorer"></a>若要运行 BTAHL7 配置资源管理器  
  
-   单击**启动**，指向**程序**，指向**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后单击**BTAHL7 配置资源管理器**。  
  
### <a name="to-configure-message-batching-acknowledgments"></a>若要配置批处理确认的消息  
  
-   在 BTAHL7 配置资源管理器，在**BTAHL7 配置资源管理器**对话框中，在**方**选项卡上，选择你想要配置，的方，然后在**确认**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**确认类型**|选择下列选项之一：<br /><br /> -   **None**。 如果不希望配置任何确认，请选择此选项。<br />-   **OriginalMode**。 选择此项可配置**MSH1 – 字段分隔符**， **MSH2 – 编码的字符**，和**MSH8 – 安全**仅选项。<br />-   **EnhancedMode**。 选择此选项，可以配置所有可用确认选项。<br />-   **DeferredMode**。 选择此项可配置**MSH1 – 字段分隔符**， **MSH2 – 编码的字符**，和**MSH8 – 安全**仅选项。<br />-   **StaticMode**。 选择此项可配置**成功**和**失败**确认选项。|  
    |**MSH 15 接受确认类型**|选择下列选项之一：<br /><br /> -   **AL**。 选择要始终发送接受确认。<br />-   **NE**。 永远不会发送到选择接受确认。<br />-   **SU**。 选择要发送接受后成功的消息传输的确认。<br />-   **ER**。 选择要发送仅发生错误时接受确认。|  
    |**MSH 15 的应用程序确认类型**|选择下列选项之一：<br /><br /> -   **AL**。 选择此项可始终发送应用程序确认。<br />-   **NE**。 选择永远不会发送应用程序确认。<br />-   **SU**。 选择后要将发送应用程序确认成功的消息传输。<br />-   **ER**。 选择此项可仅发生错误时发送应用程序确认。|  
    |**MSH1 – 字段分隔符**|类型的唯一字符作为字段分隔符。 默认值是一个管道字符 (**&#124;**)，和允许的最大字符数是一个字符。 请注意，是否你需要修改 MSH1，则必须使用适当的值的 MSH1 写入你 HL7 消息上下文业务流程。 BTAHL7 序列化程序上下文中读取值，并使用它在序列化的消息。|  
    |**MSH2 – 编码的字符**|键入作为根据 HL7 标准编码字符的唯一字符。 编码的字符都是默认 ^，~， \\，和 （& a)。 所需的最小字符都是两个字符，和允许的最大为 4 个字符。 请注意，如果 MSH2_3 或 MSH2_4 （转义和子组件动态分隔符） 中未指定原始消息，确认 (ACK) 消息自动填充这些字段。 例如，如果原始消息 MSH 段为`MSH&#124;^~&#124;`，其中指定，仅组件和重复分隔符，则 ACK 消息自动填充该字段，以便包括作为第三个和第四个组件`MSH&#124;^~\&`、 提供字段值必须不已配置在 BTAHL7 配置资源管理器的确认部分中。|  
    |**MSH3**|键入生成确认中为发送应用程序的字段值。 允许的最大长度统称为 180 个字符。<br /><br /> 如果未配置，生成的确认包含传入**MSH5**消息值。 **注意：**此选项仅适用于 2.X 消息。 **注意：**若要覆盖现有值为 null，请键入 **\\** 。|  
    |**MSH5**|键入生成确认中为目标应用程序的字段值。 允许的最大长度统称为 180 个字符。<br /><br /> 如果未配置，生成的确认包含传入**MSH3**消息值。 **注意：**此选项仅适用于 2.X 消息。 **注意：**若要覆盖现有值为 null，请键入 **\\** 。|  
    |**MSH8 – 安全**|键入一个可选的安全字符。|  
    |**MSH15 – 接受确认类型**|选择接受确认类型的以下选项：<br /><br /> -   **AL**。 如果你想要始终发送选择接受确认。<br />-   **NE**。 如果你永远不会想要发送选择接受确认。<br />-   **SU**。 如果你想要发送，请选择此选项接受后成功的消息传输的确认。<br />-   **ER**。 如果你想要发送，请选择此选项仅发生错误时接受确认。|  
    |**如果成功**|键入静态确认时成功的消息传递的文本。|  
    |**失败**|键入静态确认时不成功的消息传递的文本。|  
    |**将确认发送请求-响应管道路由到发送端口**|选择此选项可将同步的 ACK 消息发送到源 LOB 应用程序。 在请求-响应发送端口上，此选项才可用。<br /><br /> 如果不选择此选项，接收管道将生成基于确认设置 ACK 消息。|  
  
    > [!NOTE]
    >  确认使用关闭的碎片生成批处理消息将包含与值 2.4 MSH12.1。 通过应用发送管道中的映射，可以手动修改的版本号。 有关详细信息，请参阅[创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)。  
  
## <a name="see-also"></a>另请参阅  
 [配置批处理](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)