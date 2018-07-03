---
title: 步骤 8B： 配置 RX 系统的参与方信息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b0b34ec9-220d-4a6b-9712-54c8099b663b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2ed8dfaeb333c1b35ea64a5d52a53ebce509729
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008398"
---
# <a name="step-8b-configure-party-information-for-the-rx-system"></a>步骤 8B： 配置 RX 系统的参与方信息
在此步骤中，你可以配置 RX 系统的参与方信息。  

### <a name="to-configure-the-rx-system-party-information"></a>若要配置 RX 系统参与方信息  

1. 在 BizTalk Server 管理控制台中，右键单击**参与方**，依次指向**新建**，然后单击**参与方**。  

2. 在参与方属性对话框中，在**名称**框中，键入**Tutorial_RXSystem**。  

3. 在控制台树中，单击**发送端口**。  

4. 在发送端口窗格中，单击中的空白字段**名称**列中，选择**Tutorial_sendMsg_RX**，然后单击**确定**。  

5. 单击**启动**，依次指向**程序**，指向**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后单击**BTAHL7 配置资源管理器**。  

6. 在 BTAHL7 配置资源管理器中，选择**MSH 映射**选项卡，然后再执行以下操作：  


   | 使用此选项 |                    执行的操作                    |
   |----------|--------------------------------------------------|
   | **MSH3** |      类型**BTAHL7**左侧的文本框中。       |
   | **MSH5** | 类型**Tutorial_RXSystem**左侧的文本框中。 |


7. 单击**保存**，然后关闭 BTAHL7 配置资源管理器。  

   请继续执行[步骤 8c： 配置 HI 系统的参与方信息](../../adapters-and-accelerators/accelerator-hl7/step-8c-configure-party-information-for-the-hi-system.md)。