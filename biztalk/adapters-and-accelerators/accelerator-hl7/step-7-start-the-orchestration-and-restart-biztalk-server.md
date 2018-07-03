---
title: 步骤 7： 启动业务流程和重启 BizTalk Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa5168b0-4642-4842-a57a-ed7fa35fe161
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7bf1541edcd5341461a2ff948ef82839c623ea51
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006486"
---
# <a name="step-7-start-the-orchestration-and-restart-biztalk-server"></a>步骤 7： 启动业务流程和重启 BizTalk Server
在此步骤中，将启动业务流程，然后重新启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，以便在本教程中所做的更改将生效。  
  
### <a name="to-start-the-orchestration-and-restart-biztalk-server"></a>若要启动该业务流程和重新启动 BizTalk Server  
  
1. 在 BizTalk 管理控制台中，单击**业务流程**，右键单击**BatchOrchestration.Orchestration_1**，然后单击**启动**。  
  
2. 展开**平台设置**，然后单击**主机实例**。 右键单击**BizTalkServerApplication**，然后单击**重新启动**。 验证状态是否**已停止**，然后**运行**。  
  
   请继续执行[步骤 8： 测试 Create-batch 方案](../../adapters-and-accelerators/accelerator-hl7/step-8-test-the-create-batch-scenario.md)。