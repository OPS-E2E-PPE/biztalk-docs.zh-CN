---
title: 第 1 步：配置和启用 BatchControlPort 接收端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be248a05-e740-497a-b112-8ba3a57b020b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fdc4260109769fd025b33e6b14d8fd3465d4e0e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289115"
---
# <a name="step-1-configure-and-enable-the-batchcontrolport-receive-port"></a>第 1 步：配置和启用 BatchControlPort 接收端口
Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 安装程序将创建接收端口，批处理控制端口，若要处理的消息的批处理业务流程使用来启动，请停止，和时间的批次。 这些消息包括批处理激活、 批处理终止和计时器消息进行批处理。 在此步骤中，将批处理控制端口，将接收管道配置和启用端口。  
  
### <a name="to-configure-and-enable-batchcontrolport"></a>若要配置和启用 BatchControlPort  
  
1. 启动**BizTalk Server 管理**。  
  
2. 在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**， **BizTalk 组**，**应用程序**，和**BizTalk 应用程序1**。 单击**接收位置**。  
  
3. 右键单击**BatchControlLocation**，然后单击**禁用**。  
  
4. 右键单击**BatchControlLocation**，然后单击**属性**。  
  
5. 在接收位置属性对话框中，对于**接收管道**，选择**BTAHL72XPipelines.BTAHL72XReceivePipeline**。单击**确定**。  
  
6. 在 BizTalk 管理控制台中，右键单击**BatchControlLocation**，然后单击**启用**。  
  
   请继续执行[步骤 2:启用批处理业务流程](../../adapters-and-accelerators/accelerator-hl7/step-2-enable-the-batch-orchestration.md)。