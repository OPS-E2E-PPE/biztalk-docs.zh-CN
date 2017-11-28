---
title: "管理批处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82755840-4e00-4fed-80e0-1a22b248c0bf
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4903cf2722f1938ceb1df92c2a3ac2a88fe6d61e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="managing-batches"></a><span data-ttu-id="69c03-102">管理批</span><span class="sxs-lookup"><span data-stu-id="69c03-102">Managing Batches</span></span>
<span data-ttu-id="69c03-103">如何手动控制版本的批处理的交换，在顶部使用的控件**批配置**的单向协议选项卡页**协议属性**对话框中 (在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台) 的 X12 和 EDIFACT 编码。</span><span class="sxs-lookup"><span data-stu-id="69c03-103">How to control manually the release of batched interchanges, using the controls at the top of the **Batch Configuration** page of the one-way agreement tab of the **Agreement Properties** dialog box (in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console) for both X12 and EDIFACT encoding.</span></span> <span data-ttu-id="69c03-104">其中包括下列控件：</span><span class="sxs-lookup"><span data-stu-id="69c03-104">This involves the following controls:</span></span>  
  
-   <span data-ttu-id="69c03-105">**开始一批**。</span><span class="sxs-lookup"><span data-stu-id="69c03-105">**Starting a batch**.</span></span> <span data-ttu-id="69c03-106">激活批处理的业务流程的实例。</span><span class="sxs-lookup"><span data-stu-id="69c03-106">Activates an instance of the batching orchestration.</span></span> <span data-ttu-id="69c03-107">选择后**启动**按钮，批处理元素将收集实例激活范围内时。</span><span class="sxs-lookup"><span data-stu-id="69c03-107">After you select the **Start** button, batching elements are collected when the instance is within the activation range.</span></span>  
  
-   <span data-ttu-id="69c03-108">**重写一批**。</span><span class="sxs-lookup"><span data-stu-id="69c03-108">**Overriding a batch**.</span></span> <span data-ttu-id="69c03-109">创建使用现有元素一批并立即将其发送。</span><span class="sxs-lookup"><span data-stu-id="69c03-109">Creates a batch using existing elements and immediately sends it.</span></span> <span data-ttu-id="69c03-110">发送批之后，批处理业务流程将根据已建立的设置，继续进行批处理。</span><span class="sxs-lookup"><span data-stu-id="69c03-110">After the batch is sent, the batching orchestration resumes batch processing according to the established settings.</span></span>  
  
-   <span data-ttu-id="69c03-111">**停止一批**。</span><span class="sxs-lookup"><span data-stu-id="69c03-111">**Stopping a batch**.</span></span> <span data-ttu-id="69c03-112">停用激活批处理的业务流程的实例。</span><span class="sxs-lookup"><span data-stu-id="69c03-112">Deactivates an activated instance of the batching orchestration.</span></span> <span data-ttu-id="69c03-113">选择后**停止**按钮，业务流程将创建一批从现有的批处理元素，将交换传递到 EDI 发送管道，并终止。</span><span class="sxs-lookup"><span data-stu-id="69c03-113">After you select the **Stop** button, the orchestration creates a batch from existing batch elements, delivers the interchange to the EDI send pipeline, and terminates.</span></span>  
  
 <span data-ttu-id="69c03-114">控件对单个批配置进行操作。</span><span class="sxs-lookup"><span data-stu-id="69c03-114">The controls act upon a single batch configuration.</span></span>  
  
 <span data-ttu-id="69c03-115">当你按下时，BizTalk 所执行的操作**启动**取决于按钮**筛选器**条件，**版本**条件，和**激活**上范围设置**批配置**页。</span><span class="sxs-lookup"><span data-stu-id="69c03-115">The actions that BizTalk takes when you press the **Start** button depend upon the **Filter** criteria, **Release** criteria, and **Activation** range settings on the **Batch Configuration** page.</span></span> <span data-ttu-id="69c03-116">筛选条件确定将对哪些消息进行批处理。</span><span class="sxs-lookup"><span data-stu-id="69c03-116">The filter criteria determine which messages are batched.</span></span> <span data-ttu-id="69c03-117">发布条件确定何时发布批。</span><span class="sxs-lookup"><span data-stu-id="69c03-117">The release criteria determine when batches are released.</span></span> <span data-ttu-id="69c03-118">“激活范围”属性确定批处理业务流程的激活实例是否将收集批处理元素。</span><span class="sxs-lookup"><span data-stu-id="69c03-118">The activation range properties determine whether an activated instance of the batching orchestration will collect elements for batching.</span></span> <span data-ttu-id="69c03-119">有关这些设置的详细信息，请参阅[配置传出批处理](../core/configuring-an-outgoing-batch.md)。</span><span class="sxs-lookup"><span data-stu-id="69c03-119">For more information about these settings, see [Configuring an Outgoing Batch](../core/configuring-an-outgoing-batch.md).</span></span>  

<span data-ttu-id="69c03-120">本主题演示如何启动、 停止、 重写，并删除批次。</span><span class="sxs-lookup"><span data-stu-id="69c03-120">This topic shows you how to start, stop, override, and delete batches.</span></span>  

> [!NOTE]
>  <span data-ttu-id="69c03-121">有关如何配置批说明，请参阅[配置 X12 批处理](../core/configuring-batching-x12.md)或[配置 EDIFACT 批处理](../core/configuring-batching-edifact.md)。</span><span class="sxs-lookup"><span data-stu-id="69c03-121">For instructions on how to configure batches, see [Configuring X12 Batching](../core/configuring-batching-x12.md) or [Configuring EDIFACT Batching](../core/configuring-batching-edifact.md).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="69c03-122">先决条件</span><span class="sxs-lookup"><span data-stu-id="69c03-122">Prerequisites</span></span>  
 <span data-ttu-id="69c03-123">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="69c03-123">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69c03-124">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员可以启动、停止或重写批，但不能更改与批处理相关的任何配置设置。</span><span class="sxs-lookup"><span data-stu-id="69c03-124">A member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group can start, stop, or override a batch, but cannot change any configuration setting related to batching.</span></span> <span data-ttu-id="69c03-125">必须是 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组的成员才能更改批配置。</span><span class="sxs-lookup"><span data-stu-id="69c03-125">You must be a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group to change batch configuration.</span></span>  
  
## <a name="start-stop-and-override-batches"></a><span data-ttu-id="69c03-126">启动、 停止和重写批处理</span><span class="sxs-lookup"><span data-stu-id="69c03-126">Start, stop, and override batches</span></span>  
  
1.  <span data-ttu-id="69c03-127">打开**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理**，展开 BizTalk 组中，然后选择**方**。</span><span class="sxs-lookup"><span data-stu-id="69c03-127">Open **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration**, expand the BizTalk group, and select **Parties**.</span></span>  
  
2.  <span data-ttu-id="69c03-128">在**方和业务配置文件**页上，在**协议**部分中，右键单击与你想要启动、 停止或重写的批处理配置的协议。</span><span class="sxs-lookup"><span data-stu-id="69c03-128">In the **Parties and Business Profiles** page, under the **Agreements** section, right-click the agreement with the batch configuration that you want to start, stop, or override.</span></span>  
  
3.  <span data-ttu-id="69c03-129">单向协议选项卡中**协议属性**，选择**批配置**页。</span><span class="sxs-lookup"><span data-stu-id="69c03-129">In the one-way agreement tab of the **Agreement Properties**, select the **Batch Configuration** page.</span></span>  
  
4.  <span data-ttu-id="69c03-130">上**批配置**页上，选择你想要启动、 停止或重写的批处理的选项卡。</span><span class="sxs-lookup"><span data-stu-id="69c03-130">On the **Batch Configuration** page, select the tab for the batch that you want to start, stop, or override.</span></span>  
  
5.  <span data-ttu-id="69c03-131">验证筛选条件、发布条件和激活范围属性是否使用其应当使用的值。</span><span class="sxs-lookup"><span data-stu-id="69c03-131">Verify that the filter criteria, release criteria, and activation range properties are as they should be.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="69c03-132">如果你是的成员[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Operators 组，但不是[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组，可以启动、 停止、 或替代批处理。</span><span class="sxs-lookup"><span data-stu-id="69c03-132">If you are a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators group, but not the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group, you can start, stop, or override batches.</span></span> <span data-ttu-id="69c03-133">但是，你不能更改批处理配置设置。</span><span class="sxs-lookup"><span data-stu-id="69c03-133">But, you cannot change batch configuration settings.</span></span> <span data-ttu-id="69c03-134">设置是否可见，但如果你更改设置，然后选择**确定**，则会收到权限错误。</span><span class="sxs-lookup"><span data-stu-id="69c03-134">The settings are visible to you, but if you change a setting, and then select **OK**, you get a permissions error.</span></span>  
  
6.  <span data-ttu-id="69c03-135">如果尚未激活批处理的业务流程的实例，则选择**启动**激活实例。</span><span class="sxs-lookup"><span data-stu-id="69c03-135">If an instance of the batching orchestration has not been activated, select **Start** to activate an instance.</span></span>  
  
    > [!NOTE]
    >  - <span data-ttu-id="69c03-136">你可以判断，批处理的业务流程的实例尚未激活是否**启动**启用按钮，和**未激活批处理**下方只显示**启动**控件。</span><span class="sxs-lookup"><span data-stu-id="69c03-136">You can tell that an instance of the batching orchestration has not been activated if the **Start** button is enabled, and **Batching is not activated** is displayed just beneath the **Start** control.</span></span>  
    >  - <span data-ttu-id="69c03-137">如果您在单击**启动**按钮，批处理的业务流程的实例已激活，但为批处理正在收集任何元素，然后验证中的 datetime**激活**文本框中已发生的情况。</span><span class="sxs-lookup"><span data-stu-id="69c03-137">If you have clicked the **Start** button, and an instance of the batching orchestration has been activated, but no elements are being collected for the batch, then verify that the datetime in the **Activation** text box has transpired.</span></span> <span data-ttu-id="69c03-138">如果没有，则**激活**日期必须设置为当前日期或更早版本。</span><span class="sxs-lookup"><span data-stu-id="69c03-138">If not, the **Activation** date must be set to the current date or earlier.</span></span>  
  
7.  <span data-ttu-id="69c03-139">若要释放条件未满足时，请发送批处理的交换，请选择**重写**。</span><span class="sxs-lookup"><span data-stu-id="69c03-139">To send a batched interchange when the release criteria have not been met, select **Override**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="69c03-140">选择**重写**导致批处理的交换发送，但不会影响的批处理的业务流程实例、 激活条件或释放条件的激活状态。</span><span class="sxs-lookup"><span data-stu-id="69c03-140">Selecting **Override** results in a batched interchange being sent, but does not affect the activation status of the batching orchestration instance, the activation criteria, or the release criteria.</span></span>  
  
8.  <span data-ttu-id="69c03-141">若要停用批处理的业务流程的实例，请选择**停止**。</span><span class="sxs-lookup"><span data-stu-id="69c03-141">To deactivate the instance of the batching orchestration, select **Stop**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="69c03-142">选择**停止**会导致批处理的交换正在发送的数据和批处理的业务流程实例正在终止。</span><span class="sxs-lookup"><span data-stu-id="69c03-142">Selecting **Stop** results in a batched interchange being sent, and the batching orchestration instance being terminated.</span></span>  
  
9. <span data-ttu-id="69c03-143">选择**确定**或**取消**关闭**协议属性**。</span><span class="sxs-lookup"><span data-stu-id="69c03-143">Select **OK** or **Cancel** to close the **Agreement Properties**.</span></span>  

## <a name="delete-batches"></a><span data-ttu-id="69c03-144">删除批次</span><span class="sxs-lookup"><span data-stu-id="69c03-144">Delete batches</span></span>  
  
1.  <span data-ttu-id="69c03-145">在**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理**，选择**方**。</span><span class="sxs-lookup"><span data-stu-id="69c03-145">In **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration**, select **Parties**.</span></span>  
  
2.  <span data-ttu-id="69c03-146">在**方和业务配置文件**页上，在**协议**部分中，右键单击与你想要删除的批处理配置的协议。</span><span class="sxs-lookup"><span data-stu-id="69c03-146">In the **Parties and Business Profiles** page, under the **Agreements** section, right-click the agreement with the batch configuration that you want to delete.</span></span>  
  
3.  <span data-ttu-id="69c03-147">单向协议选项卡中**协议属性**对话框中，选择**批配置**页。</span><span class="sxs-lookup"><span data-stu-id="69c03-147">In the one-way agreement tab of the **Agreement Properties** dialog box, select the **Batch Configuration** page.</span></span>  
  
4.  <span data-ttu-id="69c03-148">上**批配置**页上，选择你想要删除的批处理的选项卡。</span><span class="sxs-lookup"><span data-stu-id="69c03-148">On the **Batch Configuration** page, select the tab for the batch that you want to delete.</span></span>  
  
5.  <span data-ttu-id="69c03-149">在选项卡页右上角，选择**删除**。</span><span class="sxs-lookup"><span data-stu-id="69c03-149">On the right-hand corner of the tab page, select **Delete**.</span></span>  
  
6.  <span data-ttu-id="69c03-150">选择**确定**关闭**协议属性**。</span><span class="sxs-lookup"><span data-stu-id="69c03-150">Select **OK** to close the **Agreement Properties**.</span></span>  

  
## <a name="see-also"></a><span data-ttu-id="69c03-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69c03-151">See Also</span></span>  
 [<span data-ttu-id="69c03-152">配置传出批处理</span><span class="sxs-lookup"><span data-stu-id="69c03-152">Configuring an Outgoing Batch</span></span>](../core/configuring-an-outgoing-batch.md)  
 [<span data-ttu-id="69c03-153">管理 EDI 和 AS2 解决方案</span><span class="sxs-lookup"><span data-stu-id="69c03-153">Managing EDI and AS2 Solutions</span></span>](../core/managing-edi-and-as2-solutions.md)