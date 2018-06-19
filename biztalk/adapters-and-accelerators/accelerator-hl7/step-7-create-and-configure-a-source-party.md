---
title: 步骤 7： 创建并配置源方 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d8788a9c-ae6f-461b-82e5-f4276d1d5e0c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ba84bd9a0ab8c6f7d5ccd24b27e90ef9c441b93
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25960747"
---
# <a name="step-7-create-and-configure-a-source-party"></a><span data-ttu-id="d7201-102">步骤 7： 创建并配置源方</span><span class="sxs-lookup"><span data-stu-id="d7201-102">Step 7: Create and Configure a Source Party</span></span>
<span data-ttu-id="d7201-103">在此步骤中，你将创建并配置源方，并分配发送端口以便允许传出消息的消息标头转换。</span><span class="sxs-lookup"><span data-stu-id="d7201-103">In this step, you create and configure a source party, and assign send ports to enable message header transformations for the outgoing message.</span></span>  
  
### <a name="to-create-and-configure-a-source-party"></a><span data-ttu-id="d7201-104">若要创建和配置源方</span><span class="sxs-lookup"><span data-stu-id="d7201-104">To create and configure a source party</span></span>  
  
1.  <span data-ttu-id="d7201-105">在 BizTalk 管理控制台中，右键单击**方**，指向**新建**，然后单击**方**。</span><span class="sxs-lookup"><span data-stu-id="d7201-105">In the BizTalk Administration Console, right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="d7201-106">在**参与方属性**对话框中，在名称字段中，类型**Tutorial_BatchSource**。</span><span class="sxs-lookup"><span data-stu-id="d7201-106">In the **Party Properties** dialog box, in the Name field, type **Tutorial_BatchSource**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d7201-107">在此框中键入的值是从原始 FHS3.1[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]消息的批处理，FragmentedInboundBatch.txt。</span><span class="sxs-lookup"><span data-stu-id="d7201-107">The value that you type in this box is from FHS3.1 of the original [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] batched message, FragmentedInboundBatch.txt.</span></span>  
  
3.  <span data-ttu-id="d7201-108">在控制台树中，单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="d7201-108">In the console tree, click **Send Ports**.</span></span>  
  
4.  <span data-ttu-id="d7201-109">在发送端口窗格中的名称字段中，选择**Tutorial_2wayAck**。</span><span class="sxs-lookup"><span data-stu-id="d7201-109">In the Send Ports pane, for the Name field, select **Tutorial_2wayAck**.</span></span>  
  
5.  <span data-ttu-id="d7201-110">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="d7201-110">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="d7201-111">单击**启动**，指向**所有程序**，指向**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后单击**BTAHL7 配置资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="d7201-111">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
7.  <span data-ttu-id="d7201-112">在 BTAHL7 配置资源管理器，在**方**选项卡上，单击**Tutorial_BatchSource**。</span><span class="sxs-lookup"><span data-stu-id="d7201-112">In BTAHL7 Configuration Explorer, on the **Parties** tab, click **Tutorial_BatchSource**.</span></span>  
  
8.  <span data-ttu-id="d7201-113">选择**批定义**BTAHL7 配置浏览器选项卡。</span><span class="sxs-lookup"><span data-stu-id="d7201-113">Select the **Batch Definition** tab of BTAHL7 Configuration Explorer.</span></span> <span data-ttu-id="d7201-114">选择**是**为**所需的碎片**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="d7201-114">Select **Yes** for **Fragmentation Required**, and then click **Save**.</span></span>  
  
9. <span data-ttu-id="d7201-115">选择**确认**选项卡。有关**确认类型**，选择**OriginalMode**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="d7201-115">Select the **Acknowledgment** tab. For **Acknowledgment Type**, select **OriginalMode**, and then click **Save**.</span></span>  
  
 <span data-ttu-id="d7201-116">继续执行[步骤 8： 重新启动 BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-8-restart-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="d7201-116">Proceed to [Step 8: Restart BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-8-restart-biztalk-server.md).</span></span>