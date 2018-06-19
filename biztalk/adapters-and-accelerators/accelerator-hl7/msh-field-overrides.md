---
title: MSH 字段将覆盖 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- headers, overriding
- MSH Map tab [Configuration Explorer]
- headers, MSH Map tab
- messages, message headers
ms.assetid: f5b2c820-57e7-4a56-9d9f-713563bd7335
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7303de4a8054cfe9f7140bd6eb548c228248777c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961019"
---
# <a name="msh-field-overrides"></a>MSH 字段将覆盖
每个 HL7 消息具有一个消息头。 使用[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]，你可以重写基于你的业务需求的任何消息标头值。 你使用[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器**MSH 映射**选项卡以手动覆盖消息标头值而不使用任何映射或业务流程。  
  
## <a name="configuring-msh-field-overrides"></a>配置 MSH 字段重写  
 你使用**MSH 映射**选项卡中[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器 (在高级下**方**选项卡) 来配置 MSH 字段重写。 使用此选项卡，此值替代 MSH 字段输入的值在出站 HL7 中的现有 MSH 值消息时，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将发送到所选的当事方。 你可以键入新值 MSH 的多个字段，或从 MSH15 和 MSH16 字段的下拉列表中选择值。  
  
 下图显示[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器**MSH 映射**选项卡。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-msh.gif "hl7_ops_msh")  
  
 使用以下过程来打开[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器并配置 MSH 字段重写。  
  
#### <a name="to-open-btahl7-configuration-explorer"></a>若要打开 BTAHL7 配置资源管理器  
  
-   单击**启动**，单击**程序**，单击**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后单击**BTAHL7 配置资源管理器**。  
  
#### <a name="to-configure-msh-field-overrides"></a>若要配置 MSH 字段重写  
  
1.  在 BTAHL7 配置资源管理器，在**MSH 映射**选项卡上，执行以下操作：  
  
    > [!NOTE]
    >  若要覆盖现有值为 null，请键入 **\\** 。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**MSH.3**|为此消息头替代类型消息字段。|  
    |**MSH.4**|为此消息头替代类型消息字段。|  
    |**MSH.5**|为此消息头替代类型消息字段。|  
    |**MSH.6**|为此消息头替代类型消息字段。|  
    |**MSH.8**|为此消息头替代类型消息字段。|  
    |**MSH.9**|此消息头的替代类型消息字段|  
    |**MSH.12**|为此消息头替代类型消息字段。|  
    |**MSH.15**|选择接受确认类型的确认替代的以下选项：<br /><br /> -   **AL**。 如果你始终希望能够发送，请选择此选项接受确认。<br />-   **NE**。 如果你永远不会想要发送，请选择此选项接受确认。<br />-   **SU**。 如果你想要发送，请选择此选项接受后成功的消息传输的确认。<br />-   **ER**。 如果你想要发送，请选择此选项仅发生错误时接受确认。|  
    |**MSH.16**|选择从以下选项中进行的应用程序的确认类型的确认替代：<br /><br /> -   **AL**。 如果你始终希望能够发送应用程序确认，请选择此选项。<br />-   **NE**。 如果你永远不会想要发送应用程序确认，请选择此选项。<br />-   **SU**。 如果你想要将应用程序确认发送成功的消息传输后，请选择此选项。<br />-   **ER**。 如果你想要仅发生错误时发送应用程序确认，请选择此选项。|  
  
2.  单击 **“保存”**。  
  
## <a name="see-also"></a>另请参阅  
 [日志记录配置](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md)   
 [消息批处理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)   
[运行日志记录、消息批处理、验证和确认设置](../../adapters-and-accelerators/accelerator-hl7/operational-logging-message-batching-validation-and-asknowledgment-settings.md)