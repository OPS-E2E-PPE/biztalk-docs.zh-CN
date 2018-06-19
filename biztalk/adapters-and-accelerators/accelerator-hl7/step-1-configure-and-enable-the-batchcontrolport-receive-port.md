---
title: 步骤 1： 配置和启用 BatchControlPort 接收端口 |Microsoft 文档
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
ms.openlocfilehash: d50289924062268db078844f2b3d2eaaccda23a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206141"
---
# <a name="step-1-configure-and-enable-the-batchcontrolport-receive-port"></a>步骤 1： 配置和启用 BatchControlPort 接收端口
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 安装程序创建接收端口，批处理控制端口，以处理的消息的批处理业务流程用于启动，请停止，和时间的批次。 这些消息包括批处理激活、 批处理终止和计时器消息进行批处理。 在此步骤中，你可以配置批处理控制端口，接收管道，启用端口。  
  
### <a name="to-configure-and-enable-batchcontrolport"></a>若要配置并启用 BatchControlPort  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**， **BizTalk 组**，**应用程序**，和**BizTalk 应用程序1**。 单击**接收位置**。  
  
3.  右键单击**BatchControlLocation**，然后单击**禁用**。  
  
4.  右键单击**BatchControlLocation**，然后单击**属性**。  
  
5.  在接收位置属性对话框中，为**接收管道**，选择**BTAHL72XPipelines.BTAHL72XReceivePipeline**。单击**确定**。  
  
6.  在 BizTalk 管理控制台中，右键单击**BatchControlLocation**，然后单击**启用**。  
  
 继续执行[步骤 2： 启用批处理业务流程](../../adapters-and-accelerators/accelerator-hl7/step-2-enable-the-batch-orchestration.md)。