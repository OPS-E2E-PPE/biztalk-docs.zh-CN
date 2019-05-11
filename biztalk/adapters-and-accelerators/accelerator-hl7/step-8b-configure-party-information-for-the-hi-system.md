---
title: 步骤 8B:配置 HI 系统的参与方信息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 96338c05-1440-416e-a56a-6f5b19b55a60
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd7afd025337d10e5f18fad03ded58544ce07ff0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286592"
---
# <a name="step-8b-configure-party-information-for-the-hi-system"></a>步骤 8B:配置 HI 系统的参与方信息
在此步骤中，你可以配置 HI 系统的参与方信息。  
  
### <a name="to-configure-the-hi-system-party-information"></a>若要配置 HI 系统的参与方信息  
  
1. 在 BizTalk 管理控制台中，右键单击**参与方**，依次指向**新建**，然后单击**参与方**。  
  
2. 在参与方属性对话框中，在**名称**字段中，键入**HIS**。 （在此框中键入的值应匹配原始 HL7 消息实例，QRY^Q01.txt MSH5。）  
  
3. 在控制台树中，单击**发送端口**。  
  
4. 在中**发送端口**窗格中，对于**名称**在第一行中，选择**HIS_Send**，然后单击**确定**。  
  
   请继续执行[步骤 9:重启 BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server-hl7-main.md)。