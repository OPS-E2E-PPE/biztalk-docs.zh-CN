---
title: "步骤 8 C： 配置 HI 系统的当事方信息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4ac5c113-7ee7-4009-8ca3-d263f74c7a8d
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f0b9e1538ea667eab2299a1a02021c1237bc985
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-8c-configure-party-information-for-the-hi-system"></a>步骤 8 C： 配置 HI 系统的当事方信息
在此步骤中，你可以配置 HI 系统的方信息。  
  
### <a name="to-configure-the-hi-system-party-information"></a>若要配置的 HI 系统方信息  
  
1.  在 BizTalk Server 管理控制台中，右键单击**方**，指向**新建**，然后单击**方**。  
  
2.  在参与方属性对话框中，在**名称**框中，键入**Tutorial_HISystem**。  
  
3.  在控制台树中，单击**发送端口**。  
  
4.  在发送端口窗格中，单击中的空白字段**名称**列中，选择**Tutorial_MllpSend**，然后单击**确定**。  
  
5.  单击**启动**，指向**程序**，指向**Microsoft BizTalk\<版本 > Accelerator for HL7**，然后单击**BTAHL7配置资源管理器**。  
  
6.  在 BTAHL7 配置资源管理器中，选择**MSH 映射**选项卡，然后执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**MSH3**|类型**BTAHL7**， **IE**，和**UUID**中第一个，第二周、 和第三个消息框中，分别。|  
    |**MSH5**|类型**HI**，**系统**，和**GUID**中第一个，第二周、 和第三个消息框中，分别。|  
    |**MSH9**|类型**ADT**和**A04**在第一个和第二个消息框中，分别。|  
    |**MSH12**|类型**2.4**。|  
    |**MSH15**|选择**SU**后要将发送确认成功的消息传输。|  
    |**MSH16**|选择**NE**永远不会发送确认。|  
  
7.  单击**保存**，然后关闭 BTAHL7 配置资源管理器。  
  
    > [!NOTE]
    >  你不需要创建方信息对于 BTAHL7 接口引擎系统，因为不需要这种情况下配置信息。  
  
 继续执行[步骤 9： 重新启动 BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server.md)。