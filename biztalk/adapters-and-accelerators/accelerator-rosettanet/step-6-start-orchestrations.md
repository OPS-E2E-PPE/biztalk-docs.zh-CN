---
title: 步骤 6： 启动业务流程 |Microsoft 文档
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
ms.openlocfilehash: 7ef08b7c0db08d527df4943aa25650d81231e703
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209509"
---
# <a name="step-6-start-orchestrations"></a>步骤 6： 启动业务流程
在此步骤中，你使用[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]启动的业务流程[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]。  
  
### <a name="to-start-the-btarn-orchestrations-using-visual-studio"></a>使用 Visual Studio 启动 BTARN 业务流程  
  
1.  在**BTARN**管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，和然后展开**BizTalk 应用程序 1**。  
  
2.  单击**发送端口**，然后启动**PrivateInitiator_To_LOB**和**PrivateResponder_To_LOB**发送端口。  
  
3.  单击**接收位置**，然后启用**LOB_To_PrivateInitiator**， **LOB_To_PrivateResponder**， **Async_Http_Receive**，和**Sync_Http_Receive**接收位置。  
  
4.  单击**业务流程**，并启动所有**BTARN 业务流程**。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 7： 创建示例 LOB 消息](../../adapters-and-accelerators/accelerator-rosettanet/step-7-create-a-sample-lob-message.md)   
 [停止和启动业务流程，发送端口，并以编程方式接收位置](../../adapters-and-accelerators/accelerator-rosettanet/code-to-stop-and-start-orchestrations-send-ports-and-receive-locations.md)