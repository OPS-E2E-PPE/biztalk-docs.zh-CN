---
title: MSH 映射选项卡 |Microsoft Docs
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
ms.openlocfilehash: e8e534011f75adc13ad14708c008cd7e18233662
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65290306"
---
# <a name="msh-map-tab"></a>MSH 映射选项卡
您使用**MSH 映射**选项卡以启用对入站消息的消息标头转换。  
  
 在中**BTAHL7 配置资源管理器**对话框中，在**MSH 映射**选项卡上，执行以下操作：  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**MSH.3**|为此消息标头替代类型消息字段。 **注意：** 若要覆盖现有值设置为 null，请键入**\\**。|  
|**MSH.4**|为此消息标头替代类型消息字段。 **注意：** 若要覆盖现有值设置为 null，请键入**\\**。|  
|**MSH.5**|为此消息标头替代类型消息字段。 **注意：** 若要覆盖现有值设置为 null，请键入**\\**。|  
|**MSH.6**|为此消息标头替代类型消息字段。 **注意：** 若要覆盖现有值设置为 null，请键入**\\**。|  
|**MSH.8**|为此消息标头替代类型消息字段。 **注意：** 若要覆盖现有值设置为 null，请键入**\\**。|  
|**MSH.9**|为此消息标头替代类型消息字段。 **注意：** 若要覆盖现有值设置为 null，请键入**\\**。|  
|**MSH.12**|为此消息标头替代类型消息字段。 **注意：** 若要覆盖现有值设置为 null，请键入**\\**。|  
|**MSH.15**|从接受确认类型为确认替代以下选项中选择：<br /><br /> -   **AL**。 如果始终想要发送，请选择此选项接受确认。<br />-   **NE**。 选择此选项，如果永远不会想要发送接受确认。<br />-   **SU**。 如果你想要发送，请选择此选项后的消息传输成功接受确认。<br />-   **ER**。 如果你想要发送，请选择此选项仅当出现错误时，接受确认。|  
|**MSH.16**|从应用程序确认类型为确认替代以下选项中选择：<br /><br /> -   **AL**。 如果始终想要发送应用程序确认，请选择此选项。<br />-   **NE**。 如果你永远不会想要发送应用程序确认，请选择此选项。<br />-   **SU**。 如果你想要将应用程序确认发送成功传输消息后，请选择此选项。<br />-   **ER**。 如果你想要发送应用程序确认仅发生错误时，请选择此选项。|