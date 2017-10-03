---
title: "步骤 1： 配置为批处理中批处理的当事方信息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a93d774b-1282-40d9-836f-44abeb65f78e
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 982b17fe3826a0e5c5ee2a42030ba020b755ab70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-configure-party-information-for-batch-inbatch-out"></a>步骤 1： 配置对批次中的当事方信息/批处理出
在此步骤中，你将关闭批处理用于当事方，启用批处理的碎片中 / 批处理出方案。 然后重新启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]若要启用配置更改才能生效。  
  
### <a name="to-turn-off-fragmentation-of-batching-for-the-party"></a>若要关闭的当事方批处理的碎片  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft BizTalk\<版本 > Accelerator for HL7**，然后单击**BTAHL7配置资源管理器**。  
  
2.  在 BTAHL7 配置资源管理器，在**方**选项卡上的左窗格中，单击**Tutorial_BatchSource**。  
  
3.  单击**批定义**选项卡。  
  
4.  选择**否**为**所需的碎片**，然后单击**保存**。  
  
5.  请确保在**交换可恢复的支持，所需**下拉列表**False**选择。  
  
 继续执行[步骤 2： 修改或创建发送方和接收端口](../../adapters-and-accelerators/accelerator-hl7/step-2-modify-or-create-the-send-and-receive-ports.md)。