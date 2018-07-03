---
title: 步骤 8A： 配置 ADT system_hl7_main 的参与方信息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 693fda8b-9a99-4a6e-89b7-294f84676350
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f407f549404744d76eccdfe1af47f12cbb64ef82
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971158"
---
# <a name="step-8a-configure-party-information-for-the-adt-systemhl7main"></a>步骤 8A： 配置 ADT system_hl7_main 的参与方信息
在此步骤中，你可以配置 ADT 系统的参与方信息。  
  
### <a name="to-configure-the-adt-system-party-information"></a>若要配置 ADT 系统参与方信息  
  
1. 在 BizTalk 管理控制台中，展开**BizTalk Server 管理**，然后展开**BizTalk 组**。 右键单击**参与方**，依次指向**新建**，然后单击**参与方**。  
  
2. 在参与方属性对话框中，在**名称**字段中，键入**ADT**。 （在此框中键入的值应匹配原始 HL7 消息实例，QRY^Q01.txt MSH3。）  
  
3. 在控制台树中，单击**发送端口**。  
  
4. 在中**发送端口**窗格中，对于**名称**在第一行中，选择**ADT_Send**，然后单击**确定**。  
  
5. 单击**启动**，依次指向**程序**，指向**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后单击**BTAHL7 配置资源管理器**。  
  
6. BTAHL7 配置资源管理器中单击**确认**选项卡。有关**确认类型**，选择**EnhancedMode**。  
  
7. Inboiund 消息窗格中的确认属性中的**MSH15-接受确认类型**，选择**AL**。  
  
8. 在确认属性窗格中的**MSH16-应用程序确认类型**，选择**NE**。  
  
9. 单击**保存**，然后关闭 BTAHL7 配置资源管理器。  
  
   请继续执行[步骤 8B： 配置 HI 系统的参与方信息](../../adapters-and-accelerators/accelerator-hl7/step-8b-configure-party-information-for-the-hi-system.md)。