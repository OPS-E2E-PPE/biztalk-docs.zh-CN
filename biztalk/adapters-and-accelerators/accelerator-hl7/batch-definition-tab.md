---
title: 批处理定义选项卡 |Microsoft Docs
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
ms.openlocfilehash: 70d06bb7832d42264d90d0edd63faf5d747bf849
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247672"
---
# <a name="batch-definition-tab"></a>批处理定义选项卡
您使用**批定义**选项卡以启用中的入站批处理，批处理 / 出站批处理，批处理并选择可用架构以供出站批处理。  

 在中**BTAHL7 配置资源管理器**对话框中，在**批定义**选项卡上，执行以下操作：  


|                   使用此选项                   |                                                                                                                                                            执行的操作                                                                                                                                                            |
|----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|          **所需的碎片**          |                                                           选择以下选项之一：<br /><br /> -   **是**。 若要启用碎片。<br />-   **不**。 若要禁用碎片。 **注意：** 对于新的参与方，**所需的碎片**默认值为**否**。                                                           |
| **所需的可恢复的交换支持** | 选择以下选项之一：<br /><br /> -   **True**。 若要启用可恢复的交换的支持。<br />-   **FALSE**。 若要禁用可恢复的交换的支持。 **注意：** 对于新的参与方，**所需的碎片**默认值为**FALSE**才会启用和的值**所需的碎片**是**否**。 |
|             **选择消息**              |                              选择你想要从可用消息窗口中作为一个批发送，然后单击向右箭头移动的消息类型 (**>>**)。<br /><br /> 若要传入的确认消息进行批处理，必须添加 ACK 消息类型。 您为此部署的 ACK 消息架构。                              |
|      **选择消息确认**      |                               选择为其所需的消息类型[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]从可用的消息确认窗口中，作为批处理发送确认，然后单击向右箭头 (**>>**)。                                |

