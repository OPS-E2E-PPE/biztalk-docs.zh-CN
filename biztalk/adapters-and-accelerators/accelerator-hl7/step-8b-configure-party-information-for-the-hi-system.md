---
title: 单步 8B： 配置 HI 系统的当事方信息 |Microsoft 文档
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
ms.openlocfilehash: 460840cf3bbbd6556b1684b25851a16778be92b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206309"
---
# <a name="step-8b-configure-party-information-for-the-hi-system"></a>单步 8B： 配置 HI 系统的当事方信息
在此步骤中，你可以配置 HI 系统的方信息。  
  
### <a name="to-configure-the-hi-system-party-information"></a>若要配置的 HI 系统方信息  
  
1.  在 BizTalk 管理控制台中，右键单击**方**，指向**新建**，然后单击**方**。  
  
2.  在参与方属性对话框中，在**名称**字段中，键入**HIS**。 （在此框中键入的值应匹配原始 HL7 消息实例，QRY^Q01.txt MSH5。）  
  
3.  在控制台树中，单击**发送端口**。  
  
4.  在**发送端口**窗格中，为**名称**在第一行中，选择**HIS_Send**，然后单击**确定**。  
  
 继续执行[步骤 9： 重新启动 BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server-hl7-main.md)。