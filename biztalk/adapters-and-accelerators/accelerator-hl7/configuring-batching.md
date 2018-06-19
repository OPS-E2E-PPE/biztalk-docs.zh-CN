---
title: 配置批处理 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, configuring
- configuring, batching
ms.assetid: 33c72d5e-31dd-44a8-8418-1faab3239e8e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9ab9ead01273e54826db670e7e6d6a2e9af6200
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204565"
---
# <a name="configuring-batching"></a><span data-ttu-id="142b3-102">配置批处理</span><span class="sxs-lookup"><span data-stu-id="142b3-102">Configuring Batching</span></span>
<span data-ttu-id="142b3-103">你使用[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]配置资源管理器来创建批处理，批处理中 / 批处理出批处理，并选择可用架构的出站批处理。</span><span class="sxs-lookup"><span data-stu-id="142b3-103">You use [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Configuration Explorer to create batch, batch in/batch out batching, and to select available schemas for outbound batching.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="142b3-104">你必须配置贸易合作伙伴使用 BizTalk 资源管理器，然后才能配置消息批处理。</span><span class="sxs-lookup"><span data-stu-id="142b3-104">You must configure trading partners using BizTalk Explorer before you can configure message batching.</span></span>  
  
 <span data-ttu-id="142b3-105">下图显示[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器**批定义**选项卡。</span><span class="sxs-lookup"><span data-stu-id="142b3-105">The following figure shows the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer **Batch Definition** tab.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-batchdef.gif "hl7_ops_batchdef")  
  
 <span data-ttu-id="142b3-106">使用以下过程来打开[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器和配置批处理。</span><span class="sxs-lookup"><span data-stu-id="142b3-106">Use the following procedures to open [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer and configure batching.</span></span>  
  
### <a name="to-enable-message-batching-for-outbound-batching-create-batch"></a><span data-ttu-id="142b3-107">若要启用消息批处理用于出站批处理 （创建批处理）</span><span class="sxs-lookup"><span data-stu-id="142b3-107">To enable message batching for outbound batching (Create Batch)</span></span>  
  
1.  <span data-ttu-id="142b3-108">在**启动**菜单上，打开**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="142b3-108">In the **Start** menu, open **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="142b3-109">在管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk应用程序 1**。</span><span class="sxs-lookup"><span data-stu-id="142b3-109">In the Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
3.  <span data-ttu-id="142b3-110">单击**业务流程**，右键单击**BatchOrchestration.Orchestration_1**，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="142b3-110">Click **Orchestrations**, right-click **BatchOrchestration.Orchestration_1**, and then select **Properties**.</span></span>  
  
4.  <span data-ttu-id="142b3-111">在业务流程属性对话框中，单击**绑定**在控制台树中。</span><span class="sxs-lookup"><span data-stu-id="142b3-111">In the Orchestration Properties dialog box, click **Bindings** in the console tree.</span></span>  
  
5.  <span data-ttu-id="142b3-112">在**绑定**窗格中，选择适当的主机的**主机**。</span><span class="sxs-lookup"><span data-stu-id="142b3-112">In the **Bindings** pane, select the appropriate host for **Host**.</span></span> <span data-ttu-id="142b3-113">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="142b3-113">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="142b3-114">右键单击**BatchOrchestration.Orchestration_1**，然后选择**Enlist**。</span><span class="sxs-lookup"><span data-stu-id="142b3-114">Right-click **BatchOrchestration.Orchestration_1**, and then select **Enlist**.</span></span>  
  
7.  <span data-ttu-id="142b3-115">右键单击**BatchOrchestration.Orchestration_1**，然后选择**启动**。</span><span class="sxs-lookup"><span data-stu-id="142b3-115">Right-click **BatchOrchestration.Orchestration_1**, and then select **Start**.</span></span>  
  
### <a name="to-run-btahl7-configuration-explorer"></a><span data-ttu-id="142b3-116">若要运行 BTAHL7 配置资源管理器</span><span class="sxs-lookup"><span data-stu-id="142b3-116">To run BTAHL7 Configuration Explorer</span></span>  
  
-   <span data-ttu-id="142b3-117">在**启动**菜单上，打开**Microsoft BizTalk Accelerator for HL7** ，然后单击**BTAHL7 配置资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="142b3-117">In the **Start** menu, open **Microsoft BizTalk Accelerator for HL7** , and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
### <a name="to-configure-batching"></a><span data-ttu-id="142b3-118">若要配置批处理</span><span class="sxs-lookup"><span data-stu-id="142b3-118">To configure batching</span></span>  
  
-   <span data-ttu-id="142b3-119">在[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器，请在**BTAHL7 配置资源管理器**对话框中，在**方**选项卡上，选择你想要配置，的方，然后在**批处理定义**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="142b3-119">In [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer, in the **BTAHL7 Configuration Explorer** dialog box, on the **Parties** tab, select the party you want to configure, and then on the **Batch Definition** tab, do the following:</span></span>  
  
    |<span data-ttu-id="142b3-120">使用此选项</span><span class="sxs-lookup"><span data-stu-id="142b3-120">Use this</span></span>|<span data-ttu-id="142b3-121">执行的操作</span><span class="sxs-lookup"><span data-stu-id="142b3-121">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="142b3-122">**所需的碎片**</span><span class="sxs-lookup"><span data-stu-id="142b3-122">**Fragmentation required**</span></span>|<span data-ttu-id="142b3-123">选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="142b3-123">Select one of the following options:</span></span><br /><br /> <span data-ttu-id="142b3-124">-   **是**。</span><span class="sxs-lookup"><span data-stu-id="142b3-124">-   **Yes**.</span></span> <span data-ttu-id="142b3-125">若要启用碎片。</span><span class="sxs-lookup"><span data-stu-id="142b3-125">To enable fragmentation.</span></span><br /><span data-ttu-id="142b3-126">-   **不**。</span><span class="sxs-lookup"><span data-stu-id="142b3-126">-   **No**.</span></span> <span data-ttu-id="142b3-127">若要禁用碎片。</span><span class="sxs-lookup"><span data-stu-id="142b3-127">To disable fragmentation.</span></span> <span data-ttu-id="142b3-128">**注意：** 为新的当事方，**所需的碎片**默认为**否**。</span><span class="sxs-lookup"><span data-stu-id="142b3-128">**Note:**  For a new party, **Fragmentation Required** defaults to **No**.</span></span>|  
    |<span data-ttu-id="142b3-129">**选择消息**</span><span class="sxs-lookup"><span data-stu-id="142b3-129">**Select Messages**</span></span>|<span data-ttu-id="142b3-130">选择你想要将作为从一批发送的消息类型**可用消息**窗口中，然后单击右箭头转向 (**>>**)。</span><span class="sxs-lookup"><span data-stu-id="142b3-130">Select the message types you want to send as a batch from the **Available Messages** window, and then click the Move to the right arrow (**>>**).</span></span>|  
    |<span data-ttu-id="142b3-131">**选择消息确认**</span><span class="sxs-lookup"><span data-stu-id="142b3-131">**Select Message Acknowledgments**</span></span>|<span data-ttu-id="142b3-132">选择要为其以从一批的形式发送的确认的消息类型**可用消息确认**窗口中，然后单击向右移动 (**>>**)。</span><span class="sxs-lookup"><span data-stu-id="142b3-132">Select the message types for which you want the acknowledgments to send as a batch from the **Available Message Acks** window, and then click the Move to the right (**>>**).</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="142b3-133">你可能看不到架构添加到你在[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]项目中时，在[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器正在运行。</span><span class="sxs-lookup"><span data-stu-id="142b3-133">You may not see schemas that you add to your In [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] project while In [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer is running.</span></span> <span data-ttu-id="142b3-134">若要查看这些文件，你可能需要在重新启动[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。</span><span class="sxs-lookup"><span data-stu-id="142b3-134">In order to view these files, you may need to restart In [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="142b3-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="142b3-135">See Also</span></span>  
 [<span data-ttu-id="142b3-136">计划批处理</span><span class="sxs-lookup"><span data-stu-id="142b3-136">Scheduling Batching</span></span>](../../adapters-and-accelerators/accelerator-hl7/scheduling-batching.md)