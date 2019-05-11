---
title: 第 1 步：配置批处理批中扩展的参与方信息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a93d774b-1282-40d9-836f-44abeb65f78e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 188b7cae45ac9cae0076ed129e92147f276a79d6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289070"
---
# <a name="step-1-configure-party-information-for-batch-inbatch-out"></a><span data-ttu-id="6665f-102">第 1 步：配置参与方信息中的批处理/出站批处理</span><span class="sxs-lookup"><span data-stu-id="6665f-102">Step 1: Configure Party Information for Batch In/Batch Out</span></span>
<span data-ttu-id="6665f-103">在此步骤中，你将关闭碎片的参与方启用批处理的批处理中 / 出站批处理方案。</span><span class="sxs-lookup"><span data-stu-id="6665f-103">In this step, you turn off fragmentation of batching for the party, enabling the Batch In/Batch Out scenario.</span></span> <span data-ttu-id="6665f-104">然后重新启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]若要启用配置更改才能生效。</span><span class="sxs-lookup"><span data-stu-id="6665f-104">You then restart [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] to enable the configuration change to take effect.</span></span>  
  
### <a name="to-turn-off-fragmentation-of-batching-for-the-party"></a><span data-ttu-id="6665f-105">若要关闭的批处理的参与方的碎片</span><span class="sxs-lookup"><span data-stu-id="6665f-105">To turn off fragmentation of batching for the party</span></span>  
  
1. <span data-ttu-id="6665f-106">单击**启动**，依次指向**所有程序**，指向**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后单击**BTAHL7 配置资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="6665f-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
2. <span data-ttu-id="6665f-107">BTAHL7 配置资源管理器中上**参与方**选项卡上的左窗格中，单击**Tutorial_BatchSource**。</span><span class="sxs-lookup"><span data-stu-id="6665f-107">In BTAHL7 Configuration Explorer, on the **Parties** tab in the left-hand pane, click **Tutorial_BatchSource**.</span></span>  
  
3. <span data-ttu-id="6665f-108">单击**批定义**选项卡。</span><span class="sxs-lookup"><span data-stu-id="6665f-108">Click the **Batch Definition** tab.</span></span>  
  
4. <span data-ttu-id="6665f-109">选择**否**有关**所需的碎片**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="6665f-109">Select **No** for **Fragmentation required**, and then click **Save**.</span></span>  
  
5. <span data-ttu-id="6665f-110">请确保考虑到这**可恢复交换支持必需**下拉列表中**False**处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="6665f-110">Make sure that in **Recoverable Interchange Support Required** dropdown list **False** is selected.</span></span>  
  
   <span data-ttu-id="6665f-111">请继续执行[步骤 2:修改或创建发送和接收端口](../../adapters-and-accelerators/accelerator-hl7/step-2-modify-or-create-the-send-and-receive-ports.md)。</span><span class="sxs-lookup"><span data-stu-id="6665f-111">Proceed to [Step 2: Modify or Create the Send and Receive Ports](../../adapters-and-accelerators/accelerator-hl7/step-2-modify-or-create-the-send-and-receive-ports.md).</span></span>