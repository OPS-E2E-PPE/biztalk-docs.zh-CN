---
title: 步骤 6：启动业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, starting
- loopback tutorial, starting orchestratrations
ms.assetid: f16a4a77-04fe-4e73-8517-556668174eb9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a79ac73ef2b275cd5b3740f6dccd32918f43b493
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280637"
---
# <a name="step-6-start-orchestrations"></a>步骤 6：启动业务流程
在此步骤中，使用 Microsoft[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]启动 microsoft 业务流程[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]。  
  
### <a name="to-start-the-btarn-orchestrations-using-visual-studio"></a>启动 BTARN 业务流程使用 Visual Studio  
  
1.  在中**BTARN**管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，和然后展开**BizTalk Application 1**。  
  
2.  单击**发送端口**，然后启动**PrivateInitiator_To_LOB**并**PrivateResponder_To_LOB**发送端口。  
  
3.  单击**接收位置**，然后启用**LOB_To_PrivateInitiator**， **LOB_To_PrivateResponder**， **Async_Http_Receive**，并**Sync_Http_Receive**接收位置。  
  
4.  单击**业务流程**，并启动所有**BTARN 业务流程**。  
  
## <a name="see-also"></a>请参阅  
 [步骤 7：创建示例 LOB 消息](../../adapters-and-accelerators/accelerator-rosettanet/step-7-create-a-sample-lob-message.md)   
 [以编程方式停止和启动业务流程、发送端口和接收位置](../../adapters-and-accelerators/accelerator-rosettanet/code-to-stop-and-start-orchestrations-send-ports-and-receive-locations.md)