---
title: 步骤 7： 创建和配置源参与方 |Microsoft Docs
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
ms.openlocfilehash: 4708a682047ced4fa33ae34781fd88d379c5e70b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968926"
---
# <a name="step-7-create-and-configure-a-source-party"></a><span data-ttu-id="34721-102">步骤 7： 创建和配置源参与方</span><span class="sxs-lookup"><span data-stu-id="34721-102">Step 7: Create and Configure a Source Party</span></span>
<span data-ttu-id="34721-103">在此步骤中，创建并配置源参与方，并分配要启用消息标头转换为传出消息的发送端口。</span><span class="sxs-lookup"><span data-stu-id="34721-103">In this step, you create and configure a source party, and assign send ports to enable message header transformations for the outgoing message.</span></span>  
  
### <a name="to-create-and-configure-a-source-party"></a><span data-ttu-id="34721-104">若要创建和配置源参与方</span><span class="sxs-lookup"><span data-stu-id="34721-104">To create and configure a source party</span></span>  
  
1. <span data-ttu-id="34721-105">在 BizTalk 管理控制台中，右键单击**参与方**，依次指向**新建**，然后单击**参与方**。</span><span class="sxs-lookup"><span data-stu-id="34721-105">In the BizTalk Administration Console, right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
2. <span data-ttu-id="34721-106">在中**参与方属性**对话框中，在名称字段中，类型**Tutorial_BatchSource**。</span><span class="sxs-lookup"><span data-stu-id="34721-106">In the **Party Properties** dialog box, in the Name field, type **Tutorial_BatchSource**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="34721-107">在此框中键入的值是从原始 FHS3.1[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]批处理的消息，FragmentedInboundBatch.txt。</span><span class="sxs-lookup"><span data-stu-id="34721-107">The value that you type in this box is from FHS3.1 of the original [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] batched message, FragmentedInboundBatch.txt.</span></span>  
  
3. <span data-ttu-id="34721-108">在控制台树中，单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="34721-108">In the console tree, click **Send Ports**.</span></span>  
  
4. <span data-ttu-id="34721-109">在发送端口窗格的名称字段中，选择**Tutorial_2wayAck**。</span><span class="sxs-lookup"><span data-stu-id="34721-109">In the Send Ports pane, for the Name field, select **Tutorial_2wayAck**.</span></span>  
  
5. <span data-ttu-id="34721-110">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="34721-110">Click **OK**.</span></span>  
  
6. <span data-ttu-id="34721-111">单击**启动**，依次指向**所有程序**，指向**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后单击**BTAHL7 配置资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="34721-111">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
7. <span data-ttu-id="34721-112">BTAHL7 配置资源管理器中上**参与方**选项卡上，单击**Tutorial_BatchSource**。</span><span class="sxs-lookup"><span data-stu-id="34721-112">In BTAHL7 Configuration Explorer, on the **Parties** tab, click **Tutorial_BatchSource**.</span></span>  
  
8. <span data-ttu-id="34721-113">选择**批定义**BTAHL7 配置资源管理器选项卡。</span><span class="sxs-lookup"><span data-stu-id="34721-113">Select the **Batch Definition** tab of BTAHL7 Configuration Explorer.</span></span> <span data-ttu-id="34721-114">选择**是**有关**所需的碎片**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="34721-114">Select **Yes** for **Fragmentation Required**, and then click **Save**.</span></span>  
  
9. <span data-ttu-id="34721-115">选择**确认**选项卡。有关**确认类型**，选择**OriginalMode**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="34721-115">Select the **Acknowledgment** tab. For **Acknowledgment Type**, select **OriginalMode**, and then click **Save**.</span></span>  
  
   <span data-ttu-id="34721-116">请继续执行[步骤 8： 重启 BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-8-restart-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="34721-116">Proceed to [Step 8: Restart BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-8-restart-biztalk-server.md).</span></span>