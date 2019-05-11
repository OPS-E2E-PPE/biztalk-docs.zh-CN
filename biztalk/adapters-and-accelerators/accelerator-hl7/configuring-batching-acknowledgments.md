---
title: 配置批处理确认 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, acknowledgements
- acknowledgements, batching
ms.assetid: f3529638-e036-4270-ae6d-1bdc3ef98727
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88b892fb7d525a567662956501b15e3414c17967
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251394"
---
# <a name="configuring-batching-acknowledgments"></a>配置批处理确认
您使用[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]配置资源管理器来指定入站和生成确认的确认属性。  
  
### <a name="to-run-btahl7-configuration-explorer"></a>若要运行 BTAHL7 配置资源管理器  
  
-   单击**启动**，依次指向**程序**，指向**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后单击**BTAHL7 配置资源管理器**。  
  
### <a name="to-configure-message-batching-acknowledgments"></a>若要配置批处理确认的消息  
  
-   在 BTAHL7 配置资源管理器中**BTAHL7 配置资源管理器**对话框中，在**方**选项卡上，选择你想要配置，该参与的方，然后在**确认**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**确认类型**|选择下列选项之一：<br /><br /> -   **None**。 如果不想配置任何确认，请选择此选项。<br />-   **OriginalMode**。 选择此选项可以配置**MSH1 – 字段分隔符**， **MSH2 – 编码的字符**，并**MSH8 – 安全**仅选项。<br />-   **EnhancedMode**。 选择此选项可以配置所有可用确认选项。<br />-   **DeferredMode**。 选择此选项可以配置**MSH1 – 字段分隔符**， **MSH2 – 编码的字符**，并**MSH8 – 安全**仅选项。<br />-   **StaticMode**。 选择此选项可以配置**成功**并**失败**确认选项。|  
    |**MSH 15 接受确认类型**|选择下列选项之一：<br /><br /> -   **AL**。 选择将始终发送接受确认。<br />-   **NE**。 选择到永远不会发送接受确认。<br />-   **SU**。 选择要发送成功传输消息之后接受确认。<br />-   **ER**。 选择要发送接受确认仅发生错误。|  
    |**MSH 15 应用程序确认类型**|选择下列选项之一：<br /><br /> -   **AL**。 选中此选项始终发送应用程序确认。<br />-   **NE**。 选择此选项可以永远不会发送应用程序确认。<br />-   **SU**。 选中此选项后成功发送一条消息的发送应用程序确认。<br />-   **ER**。 选择此选项可以仅发生错误时发送应用程序确认。|  
    |**MSH1 – 字段分隔符**|键入唯一的字符作为字段分隔符。 默认值是管道字符 (**&#124;**)，和允许的最大字符数是 1 个字符。 请注意，是否您需要修改 MSH1，则必须使用相应的 MSH1 值写入到 HL7 消息上下文中的业务流程。 BTAHL7 序列化程序上下文中读取值，并使用它在序列化的消息。|  
    |**MSH2 – 编码的字符**|为根据 HL7 标准编码字符键入唯一的字符。 默认编码的字符为 ^，~， \\，和 （& a)。 所需最少字符数为两个字符，并允许的最大为 4 个字符。 请注意，如果 MSH2_3 或 MSH2_4 （转义和子组件动态分隔符） 中未指定在原始消息的确认 (ACK) 消息会自动填充这些字段。 例如，如果在原始消息 MSH 段`MSH&#124;^~&#124;`，其中指定了仅的组件和重复分隔符，然后确认消息自动填充该字段，以便包含第三个和第四个组件作为`MSH&#124;^~\&`，同时提供字段值必须尚未配置 BTAHL7 配置资源管理器中的确认部分。|  
    |**MSH3**|键入生成确认中为发送应用程序的字段值。 允许的最大长度统称为 180 个字符。<br /><br /> 如果未配置，生成的确认包含传入**MSH5**消息值。 **注意：** 此选项仅适用于 2.X 消息。 **注意：** 若要覆盖现有值设置为 null，请键入**\\**。|  
    |**MSH5**|键入生成确认中为目标应用程序的字段值。 允许的最大长度统称为 180 个字符。<br /><br /> 如果未配置，生成的确认包含传入**MSH3**消息值。 **注意：** 此选项仅适用于 2.X 消息。 **注意：** 若要覆盖现有值设置为 null，请键入**\\**。|  
    |**MSH8-安全**|键入可选的安全字符。|  
    |**MSH15 – 接受确认类型**|从接受确认类型的以下选项中选择：<br /><br /> -   **AL**。 如果你想要始终发送，接受确认选择。<br />-   **NE**。 选择希望永远不会发送接受确认。<br />-   **SU**。 如果你想要发送，请选择此选项后的消息传输成功接受确认。<br />-   **ER**。 如果你想要发送，请选择此选项仅当出现错误时，接受确认。|  
    |**如果成功**|键入静态确认成功的消息传递的文本。|  
    |**在失败**|键入静态确认不成功的消息传递的文本。|  
    |**将确认请求-响应发送管道路由到发送端口**|选择此选项可将同步的确认消息发送到源 LOB 应用程序。 要求响应发送端口上，此选项才可用。<br /><br /> 如果未选择此选项，接收管道会生成基于你的确认设置的确认消息。|  
  
    > [!NOTE]
    >  为批处理消息碎片关闭与生成的确认将包含 MSH12.1 值 2.4。 通过应用发送管道中的地图，您可以手动修改的版本号。 有关详细信息，请参阅[创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)。  
  
## <a name="see-also"></a>请参阅  
 [配置批处理](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)