---
title: MSH 映射选项卡 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- btahl7.configurationexplorer.tab.mshmap
helpviewer_keywords:
- MSH Map tab [Configuration Explorer]
- messages, message headers
ms.assetid: 2c9d81bd-1abc-463d-87d7-0bea77182432
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d667c26abb66a5e5be007503e759820ad8f1040
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="msh-map-tab"></a>MSH 映射选项卡
你使用**MSH 映射**选项卡以启用入站消息的消息标头转换。  
  
 在**BTAHL7 配置资源管理器**对话框中，在**MSH 映射**选项卡上，执行以下操作：  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**MSH.3**|为此消息头替代类型消息字段。 **注意：**若要覆盖现有值为 null，请键入 **\\** 。|  
|**MSH.4**|为此消息头替代类型消息字段。 **注意：**若要覆盖现有值为 null，请键入 **\\** 。|  
|**MSH.5**|为此消息头替代类型消息字段。 **注意：**若要覆盖现有值为 null，请键入 **\\** 。|  
|**MSH.6**|为此消息头替代类型消息字段。 **注意：**若要覆盖现有值为 null，请键入 **\\** 。|  
|**MSH.8**|为此消息头替代类型消息字段。 **注意：**若要覆盖现有值为 null，请键入 **\\** 。|  
|**MSH.9**|为此消息头替代类型消息字段。 **注意：**若要覆盖现有值为 null，请键入 **\\** 。|  
|**MSH.12**|为此消息头替代类型消息字段。 **注意：**若要覆盖现有值为 null，请键入 **\\** 。|  
|**MSH.15**|选择接受确认类型的确认替代的以下选项：<br /><br /> -   **AL**。 如果你始终希望能够发送，请选择此选项接受确认。<br />-   **NE**。 如果你永远不会想要发送，请选择此选项接受确认。<br />-   **SU**。 如果你想要发送，请选择此选项接受后成功的消息传输的确认。<br />-   **ER**。 如果你想要发送，请选择此选项仅发生错误时接受确认。|  
|**MSH.16**|选择从以下选项中进行的应用程序的确认类型的确认替代：<br /><br /> -   **AL**。 如果你始终希望能够发送应用程序确认，请选择此选项。<br />-   **NE**。 如果你永远不会想要发送应用程序确认，请选择此选项。<br />-   **SU**。 如果你想要将应用程序确认发送成功的消息传输后，请选择此选项。<br />-   **ER**。 如果你想要仅发生错误时发送应用程序确认，请选择此选项。|