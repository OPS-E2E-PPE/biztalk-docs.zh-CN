---
title: 步骤 5：创建镜像协议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, mirror agreements
- loopback tutorial, creating mirror agreements
- agreements, mirror agreements
ms.assetid: 6aa70b1e-7d38-49f7-9d5f-f008cbe3df66
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79cc7fb9d8eb54e45f2e4e86b36b12017ebf3c57
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280902"
---
# <a name="step-5-create-a-mirror-agreement"></a><span data-ttu-id="11bd6-102">步骤 5：创建镜像协议</span><span class="sxs-lookup"><span data-stu-id="11bd6-102">Step 5: Create a Mirror Agreement</span></span>
<span data-ttu-id="11bd6-103">在此步骤中，使用 Loopback 实用工具创建镜像协议模拟贸易合作伙伴在其配置本组织在同一计算机上。</span><span class="sxs-lookup"><span data-stu-id="11bd6-103">In this step, you use the Loopback utility to create a mirror agreement simulating the trading partner on the same computer on which you configured the home organization.</span></span> <span data-ttu-id="11bd6-104">Loopback 实用工具是一个命令行工具。</span><span class="sxs-lookup"><span data-stu-id="11bd6-104">The Loopback utility is a command-line tool.</span></span>  
  
### <a name="to-create-a-mirror-agreement-using-the-loopback-utility"></a><span data-ttu-id="11bd6-105">若要创建镜像协议使用 Loopback 实用工具</span><span class="sxs-lookup"><span data-stu-id="11bd6-105">To create a mirror agreement using the Loopback utility</span></span>  
  
1. <span data-ttu-id="11bd6-106">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="11bd6-106">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="11bd6-107">在命令提示符处，转到\<*驱动器*\>: \Program 文件 (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK。</span><span class="sxs-lookup"><span data-stu-id="11bd6-107">At the command prompt, move to \<*drive*\>:\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK.</span></span> <span data-ttu-id="11bd6-108">键入以下命令，然后按**Enter**:</span><span class="sxs-lookup"><span data-stu-id="11bd6-108">Type the following command and then press **Enter**:</span></span>  
  
   ```  
   Loopback /enable HOME  
   ```  
  
3. <span data-ttu-id="11bd6-109">在步骤 2 中执行的命令完成后，在命令提示符处，键入以下命令，然后按**Enter**:</span><span class="sxs-lookup"><span data-stu-id="11bd6-109">After the command executed in step 2 has completed, type the following command in the command prompt, and then press **Enter**:</span></span>  
  
   ```  
   Loopback /mirror "Trade Agreement"   
   ```  
  
   <span data-ttu-id="11bd6-110">Loopback 实用工具会自动创建本组织 （发起方） 发送端口和合作伙伴组织的镜像贸易协议。</span><span class="sxs-lookup"><span data-stu-id="11bd6-110">The Loopback utility automatically creates send ports for the home organization (initiator) and a mirror trade agreement for the partner organization.</span></span> <span data-ttu-id="11bd6-111">合作伙伴使用两个新发送端口与本组织进行通信。</span><span class="sxs-lookup"><span data-stu-id="11bd6-111">The partner uses the two new send ports to communicate with the home organization.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11bd6-112">每当你更新原始贸易协议时，必须重新反映贸易协议。</span><span class="sxs-lookup"><span data-stu-id="11bd6-112">You must re-mirror the trade agreement whenever you update the original trade agreement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11bd6-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="11bd6-113">See Also</span></span>  
 [<span data-ttu-id="11bd6-114">步骤 6：启动业务流程</span><span class="sxs-lookup"><span data-stu-id="11bd6-114">Step 6: Start Orchestrations</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-6-start-orchestrations.md)
