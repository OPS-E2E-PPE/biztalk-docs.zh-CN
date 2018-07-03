---
title: 步骤 5： 创建镜像协议 |Microsoft Docs
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
ms.openlocfilehash: 9fde79b9ee5cdbb5cd34440aa59e79e842f79b0b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006462"
---
# <a name="step-5-create-a-mirror-agreement"></a><span data-ttu-id="c4a1d-102">步骤 5： 创建镜像协议</span><span class="sxs-lookup"><span data-stu-id="c4a1d-102">Step 5: Create a Mirror Agreement</span></span>
<span data-ttu-id="c4a1d-103">在此步骤中，将使用 Loopback 实用工具在你配置了本组织的计算机上创建模拟贸易合作伙伴的镜像协议。</span><span class="sxs-lookup"><span data-stu-id="c4a1d-103">In this step, you use the Loopback utility to create a mirror agreement simulating the trading partner on the same computer on which you configured the home organization.</span></span> <span data-ttu-id="c4a1d-104">Loopback 实用工具是一个命令行工具。</span><span class="sxs-lookup"><span data-stu-id="c4a1d-104">The Loopback utility is a command-line tool.</span></span>  
  
### <a name="to-create-a-mirror-agreement-using-the-loopback-utility"></a><span data-ttu-id="c4a1d-105">使用 Loopback 实用工具创建镜像协议</span><span class="sxs-lookup"><span data-stu-id="c4a1d-105">To create a mirror agreement using the Loopback utility</span></span>  
  
1. <span data-ttu-id="c4a1d-106">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="c4a1d-106">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="c4a1d-107">在命令提示符处，转到\<*驱动器*\>: \Program 文件 (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK。</span><span class="sxs-lookup"><span data-stu-id="c4a1d-107">At the command prompt, move to \<*drive*\>:\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK.</span></span> <span data-ttu-id="c4a1d-108">键入以下命令，然后按**Enter**:</span><span class="sxs-lookup"><span data-stu-id="c4a1d-108">Type the following command and then press **Enter**:</span></span>  
  
   ```  
   Loopback /enable HOME  
   ```  
  
3. <span data-ttu-id="c4a1d-109">在步骤 2 中执行的命令完成后，在命令提示符处，键入以下命令，然后按**Enter**:</span><span class="sxs-lookup"><span data-stu-id="c4a1d-109">After the command executed in step 2 has completed, type the following command in the command prompt, and then press **Enter**:</span></span>  
  
   ```  
   Loopback /mirror "Trade Agreement"   
   ```  
  
   <span data-ttu-id="c4a1d-110">Loopback 实用工具会为本组织（发起方）自动创建发送端口，并为合作伙伴组织自动创建镜像贸易协议。</span><span class="sxs-lookup"><span data-stu-id="c4a1d-110">The Loopback utility automatically creates send ports for the home organization (initiator) and a mirror trade agreement for the partner organization.</span></span> <span data-ttu-id="c4a1d-111">合作伙伴使用两个新的发送端口与本组织进行通信。</span><span class="sxs-lookup"><span data-stu-id="c4a1d-111">The partner uses the two new send ports to communicate with the home organization.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4a1d-112">在每次更新原始贸易协议时，都必须重新反映贸易协议。</span><span class="sxs-lookup"><span data-stu-id="c4a1d-112">You must re-mirror the trade agreement whenever you update the original trade agreement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4a1d-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4a1d-113">See Also</span></span>  
 [<span data-ttu-id="c4a1d-114">步骤 6：启动业务流程</span><span class="sxs-lookup"><span data-stu-id="c4a1d-114">Step 6: Start Orchestrations</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-6-start-orchestrations.md)
