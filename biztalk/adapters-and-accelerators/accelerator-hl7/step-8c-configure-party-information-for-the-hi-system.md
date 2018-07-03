---
title: 步骤 8c： 配置 HI 系统的参与方信息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ac5c113-7ee7-4009-8ca3-d263f74c7a8d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aba42674a78bbed850c0994ec23c477c36b29c2b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970822"
---
# <a name="step-8c-configure-party-information-for-the-hi-system"></a>步骤 8c： 配置 HI 系统的参与方信息
在此步骤中，你可以配置 HI 系统的参与方信息。  

### <a name="to-configure-the-hi-system-party-information"></a>若要配置 HI 系统的参与方信息  

1. 在 BizTalk Server 管理控制台中，右键单击**参与方**，依次指向**新建**，然后单击**参与方**。  

2. 在参与方属性对话框中，在**名称**框中，键入**Tutorial_HISystem**。  

3. 在控制台树中，单击**发送端口**。  

4. 在发送端口窗格中，单击中的空白字段**名称**列中，选择**Tutorial_MllpSend**，然后单击**确定**。  

5. 单击**启动**，依次指向**程序**，指向**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后单击**BTAHL7 配置资源管理器**。  

6. BTAHL7 配置资源管理器中选择**MSH 映射**选项卡，然后再执行以下操作：  


   | 使用此选项  |                                             执行的操作                                             |
   |-----------|----------------------------------------------------------------------------------------------------|
   | **MSH3**  | 类型**BTAHL7**， **IE**，并**UUID**在第一个，第二、 第三个消息和框中，分别。 |
   | **MSH5**  | 类型**HI**，**系统**，并**GUID**在第一个，第二、 第三个消息和框中，分别。 |
   | **MSH9**  |           类型**ADT**并**A04**中第一个和第二个消息框中，分别。            |
   | **MSH12** |                                           类型**2.4**。                                            |
   | **MSH15** |         选择**SU**后要将发送确认的消息成功传输。          |
   | **MSH16** |                            选择**NE**永远不会发送确认。                            |


7. 单击**保存**，然后关闭 BTAHL7 配置资源管理器。  

   > [!NOTE]
   >  您不需要创建参与方信息 BTAHL7 接口引擎系统，因为不需要此方案的配置信息。  

   请继续执行[步骤 9： 重启 BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server.md)。