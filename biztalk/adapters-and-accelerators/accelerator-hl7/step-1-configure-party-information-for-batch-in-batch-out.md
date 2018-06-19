---
title: 步骤 1： 配置为批处理中批处理的当事方信息 |Microsoft 文档
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
ms.openlocfilehash: 4cb67fb2e1a232894a0e936bc7827270ca79e6f8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25960507"
---
# <a name="step-1-configure-party-information-for-batch-inbatch-out"></a><span data-ttu-id="f1443-102">步骤 1： 配置对批次中的当事方信息/批处理出</span><span class="sxs-lookup"><span data-stu-id="f1443-102">Step 1: Configure Party Information for Batch In/Batch Out</span></span>
<span data-ttu-id="f1443-103">在此步骤中，你将关闭批处理用于当事方，启用批处理的碎片中 / 批处理出方案。</span><span class="sxs-lookup"><span data-stu-id="f1443-103">In this step, you turn off fragmentation of batching for the party, enabling the Batch In/Batch Out scenario.</span></span> <span data-ttu-id="f1443-104">然后重新启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]若要启用配置更改才能生效。</span><span class="sxs-lookup"><span data-stu-id="f1443-104">You then restart [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] to enable the configuration change to take effect.</span></span>  
  
### <a name="to-turn-off-fragmentation-of-batching-for-the-party"></a><span data-ttu-id="f1443-105">若要关闭的当事方批处理的碎片</span><span class="sxs-lookup"><span data-stu-id="f1443-105">To turn off fragmentation of batching for the party</span></span>  
  
1.  <span data-ttu-id="f1443-106">单击**启动**，指向**所有程序**，指向**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后单击**BTAHL7 配置资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="f1443-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
2.  <span data-ttu-id="f1443-107">在 BTAHL7 配置资源管理器，在**方**选项卡上的左窗格中，单击**Tutorial_BatchSource**。</span><span class="sxs-lookup"><span data-stu-id="f1443-107">In BTAHL7 Configuration Explorer, on the **Parties** tab in the left-hand pane, click **Tutorial_BatchSource**.</span></span>  
  
3.  <span data-ttu-id="f1443-108">单击**批定义**选项卡。</span><span class="sxs-lookup"><span data-stu-id="f1443-108">Click the **Batch Definition** tab.</span></span>  
  
4.  <span data-ttu-id="f1443-109">选择**否**为**所需的碎片**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="f1443-109">Select **No** for **Fragmentation required**, and then click **Save**.</span></span>  
  
5.  <span data-ttu-id="f1443-110">请确保在**交换可恢复的支持，所需**下拉列表**False**选择。</span><span class="sxs-lookup"><span data-stu-id="f1443-110">Make sure that in **Recoverable Interchange Support Required** dropdown list **False** is selected.</span></span>  
  
 <span data-ttu-id="f1443-111">继续执行[步骤 2： 修改或创建发送方和接收端口](../../adapters-and-accelerators/accelerator-hl7/step-2-modify-or-create-the-send-and-receive-ports.md)。</span><span class="sxs-lookup"><span data-stu-id="f1443-111">Proceed to [Step 2: Modify or Create the Send and Receive Ports](../../adapters-and-accelerators/accelerator-hl7/step-2-modify-or-create-the-send-and-receive-ports.md).</span></span>