---
title: 步骤 8A:配置 ADT 系统的参与方信息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0d750c2-a3c6-4571-a4e1-0d0aaaa4d400
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5abeb65ac140bfcbc96c5c925960f38b539eeabf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65287890"
---
# <a name="step-8a-configure-party-information-for-the-adt-system"></a>步骤 8A:配置 ADT 系统的参与方信息
在此步骤中，你可以配置 ADT 系统的参与方信息。  
  
### <a name="to-configure-the-adt-system-party-information"></a>若要配置 ADT 系统参与方信息  
  
1. 在 BizTalk Server 管理控制台中，右键单击**参与方**，依次指向**新建**，然后单击**参与方**。  
  
2. 在参与方属性对话框中，在**名称**框中，键入**Tutorial_ADTSystem**。 （在此框中键入的值是从原始 HL7 消息实例，ADT^A03.txt MSH3。）  
  
3. 在控制台树中，单击**发送端口**。  
  
4. 在发送端口窗格中，单击中的空白字段**名称**列中，选择**Tutorial_sendAck_ADT**，然后单击**确定**。  
  
5. 单击**启动**，依次指向**程序**，指向**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后单击**BTAHL7 配置资源管理器**。  
  
6. 在 BTAHL7 配置资源管理器中，选择**确认**选项卡。有关**确认类型**，选择**EnhancedMode**。  
  
7. 单击**保存**，然后关闭 BTAHL7 配置资源管理器。  
  
   请继续执行[步骤 8B:配置 RX 系统的参与方信息](../../adapters-and-accelerators/accelerator-hl7/step-8b-configure-party-information-for-the-rx-system.md)。