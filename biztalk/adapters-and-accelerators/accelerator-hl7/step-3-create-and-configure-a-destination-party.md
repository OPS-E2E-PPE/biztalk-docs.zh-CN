---
title: 步骤 3：创建并配置目标参与方 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8746f115-9f69-4593-9943-9ccda45cd900
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80dff125e13ffb12acaeb98664957ed4e681ffa3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288895"
---
# <a name="step-3-create-and-configure-a-destination-party"></a><span data-ttu-id="7e42c-102">步骤 3：创建并配置目标参与方</span><span class="sxs-lookup"><span data-stu-id="7e42c-102">Step 3: Create and Configure a Destination Party</span></span>
<span data-ttu-id="7e42c-103">此步骤中，创建并配置创建 Batch 方案的目标参与方。</span><span class="sxs-lookup"><span data-stu-id="7e42c-103">In this step, you create and configure a destination party for the Create-Batch scenario.</span></span> <span data-ttu-id="7e42c-104">你还选择的消息的[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]批处理和批处理计划，为该参与方定义的一样。</span><span class="sxs-lookup"><span data-stu-id="7e42c-104">You also select the messages that [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] batches and the batch schedules, as defined for that party.</span></span> <span data-ttu-id="7e42c-105">您计划为一小时后将文件复制到文件夹中的批发送时间。</span><span class="sxs-lookup"><span data-stu-id="7e42c-105">You schedule the batch send time as one hour after copying the files into the folder.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="7e42c-106">频率为一小时之后收到任何消息进行批处理。</span><span class="sxs-lookup"><span data-stu-id="7e42c-106">batches any messages received thereafter with a frequency of one hour.</span></span>  
  
### <a name="to-create-and-configure-a-destination-party"></a><span data-ttu-id="7e42c-107">若要创建和配置目标参与方</span><span class="sxs-lookup"><span data-stu-id="7e42c-107">To create and configure a destination party</span></span>  
  
1. <span data-ttu-id="7e42c-108">在 BizTalk Server 管理控制台中，右键单击**参与方**，依次指向**新建**，然后单击**参与方**。</span><span class="sxs-lookup"><span data-stu-id="7e42c-108">In the BizTalk Server Administration Console, right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
2. <span data-ttu-id="7e42c-109">在参与方属性对话框中，在**名称**框中，键入**Tutorial_BatchDest**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7e42c-109">In the Party Properties dialog box, in the **Name** box, type **Tutorial_BatchDest**, and then click **OK**.</span></span>  
  
3. <span data-ttu-id="7e42c-110">单击**启动**，依次指向**所有程序**，指向**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后单击**BTAHL7 配置资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="7e42c-110">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
4. <span data-ttu-id="7e42c-111">BTAHL7 配置资源管理器中上**参与方**选项卡上的控制台树中，单击**Tutorial_BatchDest**。</span><span class="sxs-lookup"><span data-stu-id="7e42c-111">In BTAHL7 Configuration Explorer, on the **Parties** tab in the console tree, click **Tutorial_BatchDest**.</span></span>  
  
5. <span data-ttu-id="7e42c-112">单击**确认**详细信息窗格中的选项卡。</span><span class="sxs-lookup"><span data-stu-id="7e42c-112">Click the **Acknowledgment** tab in the Details pane.</span></span> <span data-ttu-id="7e42c-113">确认**确认类型**是**None**。</span><span class="sxs-lookup"><span data-stu-id="7e42c-113">Verify that the **Acknowledgment type** is **None**.</span></span>  
  
6. <span data-ttu-id="7e42c-114">单击**批定义**选项卡。在中**可用消息**窗格中，选择**BTAHL7Schemas.ADT_A03_231_GLO_DEF**。</span><span class="sxs-lookup"><span data-stu-id="7e42c-114">Click the **Batch Definition** tab. In the **Available Messages** pane, select **BTAHL7Schemas.ADT_A03_231_GLO_DEF**.</span></span> <span data-ttu-id="7e42c-115">单击向右箭头 (**>>**) 添加到此架构**选择消息**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="7e42c-115">Click the Move to the right arrow (**>>**) to add this schema to **Selected Messages**, and then click **Save**.</span></span>  
  
7. <span data-ttu-id="7e42c-116">单击**批处理计划**选项卡。在中**重复执行批处理后**部分中，验证**小时**已选中，然后键入**1**中**小时**框。</span><span class="sxs-lookup"><span data-stu-id="7e42c-116">Click the **Batch Schedule** tab. In the **Repeat Batch After** section, verify that **Hours** is selected, and then type **1** in the **Hours** box.</span></span> <span data-ttu-id="7e42c-117">在中**小时之后第一批,** 框中，键入**1**，然后单击**开始计划**。</span><span class="sxs-lookup"><span data-stu-id="7e42c-117">In the **Hours before first batch** box, type **1**, and then click **Start Schedule**.</span></span>  
  
   <span data-ttu-id="7e42c-118">请继续执行[步骤 4:配置源参与方创建批处理方案](../../adapters-and-accelerators/accelerator-hl7/step-4-configure-the-source-party-for-the-create-batch-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="7e42c-118">Proceed to [Step 4: Configure the Source Party for the Create-Batch Scenario](../../adapters-and-accelerators/accelerator-hl7/step-4-configure-the-source-party-for-the-create-batch-scenario.md).</span></span>