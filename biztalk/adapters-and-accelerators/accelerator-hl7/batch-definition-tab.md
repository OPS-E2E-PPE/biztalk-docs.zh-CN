---
title: 批处理定义选项卡 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- btahl7.configurationexplorer.tab.batchdefinition
helpviewer_keywords:
- Batch Definition tab [Configuration Explorer]
- batching, configuring
- configuring, batching
ms.assetid: fe8685ef-5de5-4337-8691-8e4094056ace
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2270625a6e4512f2a99bea7a06812b601b48d44c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204509"
---
# <a name="batch-definition-tab"></a>批处理定义选项卡
你使用**批定义**选项卡以启用中的入站批处理，批处理 / 批处理出批处理，并选择可用架构的出站批处理。  
  
 在**BTAHL7 配置资源管理器**对话框中，在**批定义**选项卡上，执行以下操作：  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**所需的碎片**|选择以下选项之一：<br /><br /> -   **是**。 若要启用碎片。<br />-   **不**。 若要禁用碎片。 **注意：** 为新的当事方，**所需的碎片**默认为**否**。|  
|**所需的可恢复的交换支持**|选择以下选项之一：<br /><br /> -   **True**。 若要启用可恢复的交换的支持。<br />-   **FALSE**。 若要禁用可恢复的交换支持。 **注意：** 为新的当事方，**所需的碎片**默认为**FALSE**和才会启用的值**所需的碎片**是**否**。|  
|**选择消息**|选择你想要从可用消息窗口作为批处理发送，然后单击右箭头转向的消息类型 (**>>**)。<br /><br /> 若要批处理传入 ACK 消息，必须添加 ACK 消息类型。 你做到这一点部署 ACK 消息架构。|  
|**选择消息确认**|选择要为其的消息类型[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]从可用的消息确认窗口中，作为批处理发送确认，然后单击右箭头转向 (**>>**)。|