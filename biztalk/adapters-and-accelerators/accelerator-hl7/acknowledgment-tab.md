---
title: "确认选项卡 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: btahl7.configurationexplorer.tab.acknowledgement
helpviewer_keywords:
- acknowledgements, configuring
- Acknowledgement tab [Configuration Explorer]
- configuring, acknowledgements
ms.assetid: f00d698c-1a33-4885-853f-c6b58d49d937
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28dcf3d0faee6ebf37a827f3773f33b955ce5447
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="acknowledgment-tab"></a>确认选项卡
你使用**确认**选项卡来指定入站和生成的确认的确认属性。  
  
 在**BTAHL7 配置资源管理器**对话框中，在**确认**选项卡上，执行以下操作：  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**确认类型**|从下列选项中进行选择：<br /><br /> -   **None**。 如果你不想要配置任何确认，请选择此选项。<br />-   **OriginalMode**。 选择此选项以配置**MSH1 – 字段分隔符**， **MSH2 – 编码的字符**，和**MSH8 – 安全**仅选项。<br />-   **EnhancedMode**。 选择此选项以配置所有可用确认选项。<br />-   **DeferredMode**。 选择此选项以配置**MSH1 – 字段分隔符**， **MSH2 – 编码的字符**，和**MSH8 – 安全**仅选项。<br />-   **StaticMode**。 选择此选项以配置**成功**和**失败**确认选项。|  
|**MSH 15 接受确认类型**|从下列选项中进行选择：<br /><br /> -   **AL**。 如果你始终希望能够发送，请选择此选项接受确认。<br />-   **NE**。 如果你永远不会想要发送，请选择此选项接受确认。<br />-   **SU**。 如果你想要发送，请选择此选项接受后成功的消息传输的确认。<br />-   **ER**。 如果你想要发送，请选择此选项仅发生错误时接受确认。|  
|**MSH 16 的应用程序确认类型**|从下列选项中进行选择：<br /><br /> -   **AL**。 如果你始终希望能够发送应用程序确认，请选择此选项。<br />-   **NE**。 如果你永远不会想要发送应用程序确认，请选择此选项。<br />-   **SU**。 如果你想要将应用程序确认发送成功的消息传输后，请选择此选项。<br />-   **ER**。 如果你想要仅发生错误时发送应用程序确认，请选择此选项。|  
|**MSH1 – 字段分隔符**|类型的唯一字符作为字段分隔符。 默认值是**&#124;**，和允许的最大字符数是一个字符。 请注意，是否你需要修改 MSH1，则必须使用适当的值的 MSH1 写入你 HL7 消息上下文业务流程。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]序列化程序上下文中读取值，并在序列化的消息中使用它。|  
|**MSH2 – 编码的字符**|键入根据 HL7 规范的编码字符有关的唯一字符。 编码的字符都是默认 ^，~， \\，和 （& a)。 所需的最小字符都是两个字符，和允许的最大为 4 个字符。 请注意，如果 MSH2_3 或 MSH2_4 （转义和子组件动态分隔符） 中未指定原始消息，确认消息将自动填充这些字段。 例如，如果原始消息 MSH 段为`MSH&#124;^~&#124;`，其中指定，仅组件和重复分隔符，则 ACK 消息自动填充该字段，以便包括作为第三个和第四个组件`MSH&#124;^~\&`如果这些在确认部分中没有配置值[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。|  
|**MSH 3**|键入生成确认中为发送应用程序的字段值。 允许的最大长度统称为 180 个字符。<br /><br /> 如果未配置，生成的确认包含传入**MSH5**消息值。 **注意：**此选项仅适用于 2.X 消息。 **注意：**若要覆盖现有值为 null，请键入 **\\** 。|  
|**MSH 5**|键入生成确认中为目标应用程序的字段值。 允许的最大长度统称为 180 个字符。<br /><br /> 如果未配置，生成的确认包含传入**MSH3**消息值。 **注意：**此选项仅适用于 2.X 消息。 **注意：**若要覆盖现有值为 null，请键入 **\\** 。|  
|**MSH8 – 安全**|键入一个可选的安全字符。|  
|**MSH 9**|键入生成的确认消息类型的字段值。<br /><br /> 如果未配置，生成的确认包含传入**MSH9**消息值。 **注意：**此选项仅适用于 2.X 消息。 **注意：**若要覆盖现有值为 null，请键入 **\\** 。|  
|**MSH15 – 接受确认类型**|选择接受确认类型的以下选项：<br /><br /> -   **AL**。 如果你始终希望能够发送，请选择此选项接受确认。<br />-   **NE**。 如果你永远不会想要发送，请选择此选项接受确认。<br />-   **SU**。 如果你想要发送，请选择此选项接受后成功的消息传输的确认。<br />-   **ER**。 如果你想要发送，请选择此选项仅发生错误时接受确认。|  
|**如果成功**|键入用于成功的消息传递一个静态确认的文本。|  
|**失败**|键入不成功的消息传送静态确认的文本。|  
|**将确认发送请求-响应管道路由到发送端口**|选择此选项可将同步的 ACK 消息发送到源 LOB 应用程序。 在请求-响应发送端口上，此选项才可用。<br /><br /> 如果不选择此选项，接收管道将生成基于确认设置 ACK 消息。|