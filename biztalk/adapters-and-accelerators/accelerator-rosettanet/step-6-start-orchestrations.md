---
title: 步骤 6： 启动业务流程 |Microsoft Docs
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
ms.openlocfilehash: 973d0c5e8628d2363e8192c7faffeaebcc6d63b6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993182"
---
# <a name="step-6-start-orchestrations"></a><span data-ttu-id="7f068-102">步骤 6： 启动业务流程</span><span class="sxs-lookup"><span data-stu-id="7f068-102">Step 6: Start Orchestrations</span></span>
<span data-ttu-id="7f068-103">在此步骤中，使用 Microsoft[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]启动 microsoft 业务流程[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7f068-103">In this step, you use Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to start the orchestrations for Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span>  
  
### <a name="to-start-the-btarn-orchestrations-using-visual-studio"></a><span data-ttu-id="7f068-104">使用 Visual Studio 启动 BTARN 业务流程</span><span class="sxs-lookup"><span data-stu-id="7f068-104">To start the BTARN orchestrations using Visual Studio</span></span>  
  
1.  <span data-ttu-id="7f068-105">在中**BTARN**管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，和然后展开**BizTalk Application 1**。</span><span class="sxs-lookup"><span data-stu-id="7f068-105">In the **BTARN** Management Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
2.  <span data-ttu-id="7f068-106">单击**发送端口**，然后启动**PrivateInitiator_To_LOB**并**PrivateResponder_To_LOB**发送端口。</span><span class="sxs-lookup"><span data-stu-id="7f068-106">Click **Send Ports**, and then start **PrivateInitiator_To_LOB** and **PrivateResponder_To_LOB** send ports.</span></span>  
  
3.  <span data-ttu-id="7f068-107">单击**接收位置**，然后启用**LOB_To_PrivateInitiator**， **LOB_To_PrivateResponder**， **Async_Http_Receive**，并**Sync_Http_Receive**接收位置。</span><span class="sxs-lookup"><span data-stu-id="7f068-107">Click **Receive Locations**, and then enable **LOB_To_PrivateInitiator**, **LOB_To_PrivateResponder**, **Async_Http_Receive**, and **Sync_Http_Receive** receive locations.</span></span>  
  
4.  <span data-ttu-id="7f068-108">单击**业务流程**，并启动所有**BTARN 业务流程**。</span><span class="sxs-lookup"><span data-stu-id="7f068-108">Click **Orchestrations**, and start all **BTARN orchestrations**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f068-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="7f068-109">See Also</span></span>  
 <span data-ttu-id="7f068-110">[步骤 7： 创建示例 LOB 消息](../../adapters-and-accelerators/accelerator-rosettanet/step-7-create-a-sample-lob-message.md) </span><span class="sxs-lookup"><span data-stu-id="7f068-110">[Step 7: Create a Sample LOB Message](../../adapters-and-accelerators/accelerator-rosettanet/step-7-create-a-sample-lob-message.md) </span></span>  
 [<span data-ttu-id="7f068-111">以编程方式停止和启动业务流程、发送端口和接收位置</span><span class="sxs-lookup"><span data-stu-id="7f068-111">Stopping and Starting Orchestrations, Send Ports, and Receive Locations Programmatically</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/code-to-stop-and-start-orchestrations-send-ports-and-receive-locations.md)