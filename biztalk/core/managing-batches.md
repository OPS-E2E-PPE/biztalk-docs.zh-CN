---
title: 管理批处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82755840-4e00-4fed-80e0-1a22b248c0bf
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af801bd6ec61c883d81e7ea6fd15e92f2186b777
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021524"
---
# <a name="managing-batches"></a><span data-ttu-id="2fdb8-102">管理批</span><span class="sxs-lookup"><span data-stu-id="2fdb8-102">Managing Batches</span></span>
<span data-ttu-id="2fdb8-103">如何手动控制版本的批处理交换，在顶部使用的控件**批配置**页的单向协议选项卡**协议属性**对话框 (在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台) X12 和 EDIFACT 编码的。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-103">How to control manually the release of batched interchanges, using the controls at the top of the **Batch Configuration** page of the one-way agreement tab of the **Agreement Properties** dialog box (in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console) for both X12 and EDIFACT encoding.</span></span> <span data-ttu-id="2fdb8-104">其中包括下列控件：</span><span class="sxs-lookup"><span data-stu-id="2fdb8-104">This involves the following controls:</span></span>  
  
- <span data-ttu-id="2fdb8-105">**启动批**。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-105">**Starting a batch**.</span></span> <span data-ttu-id="2fdb8-106">激活批处理业务流程的实例。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-106">Activates an instance of the batching orchestration.</span></span> <span data-ttu-id="2fdb8-107">选择后**启动**按钮时，批处理元素将收集实例在激活范围内时。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-107">After you select the **Start** button, batching elements are collected when the instance is within the activation range.</span></span>  
  
- <span data-ttu-id="2fdb8-108">**重写批**。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-108">**Overriding a batch**.</span></span> <span data-ttu-id="2fdb8-109">创建使用现有元素一个批并立即发送它。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-109">Creates a batch using existing elements and immediately sends it.</span></span> <span data-ttu-id="2fdb8-110">发送批之后，批处理业务流程将根据已建立的设置，继续进行批处理。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-110">After the batch is sent, the batching orchestration resumes batch processing according to the established settings.</span></span>  
  
- <span data-ttu-id="2fdb8-111">**停止批**。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-111">**Stopping a batch**.</span></span> <span data-ttu-id="2fdb8-112">停用批处理业务流程的激活的实例。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-112">Deactivates an activated instance of the batching orchestration.</span></span> <span data-ttu-id="2fdb8-113">选择后**停止**按钮，该业务流程基于现有批元素创建批，将交换传送给 EDI 发送管道，并且将终止。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-113">After you select the **Stop** button, the orchestration creates a batch from existing batch elements, delivers the interchange to the EDI send pipeline, and terminates.</span></span>  
  
  <span data-ttu-id="2fdb8-114">控件对单个批配置进行操作。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-114">The controls act upon a single batch configuration.</span></span>  
  
  <span data-ttu-id="2fdb8-115">按下时，BizTalk 采取的操作**启动**取决于按钮**筛选器**条件**版本**条件，和**激活**上的范围设置**批配置**页。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-115">The actions that BizTalk takes when you press the **Start** button depend upon the **Filter** criteria, **Release** criteria, and **Activation** range settings on the **Batch Configuration** page.</span></span> <span data-ttu-id="2fdb8-116">筛选条件确定将对哪些消息进行批处理。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-116">The filter criteria determine which messages are batched.</span></span> <span data-ttu-id="2fdb8-117">发布条件确定何时发布批。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-117">The release criteria determine when batches are released.</span></span> <span data-ttu-id="2fdb8-118">“激活范围”属性确定批处理业务流程的激活实例是否将收集批处理元素。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-118">The activation range properties determine whether an activated instance of the batching orchestration will collect elements for batching.</span></span> <span data-ttu-id="2fdb8-119">有关这些设置的详细信息，请参阅[配置传出批](../core/configuring-an-outgoing-batch.md)。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-119">For more information about these settings, see [Configuring an Outgoing Batch](../core/configuring-an-outgoing-batch.md).</span></span>  

<span data-ttu-id="2fdb8-120">本主题演示如何启动、 停止、 重写，以及删除批。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-120">This topic shows you how to start, stop, override, and delete batches.</span></span>  

> [!NOTE]
>  <span data-ttu-id="2fdb8-121">有关如何配置批处理的说明，请参阅[配置 X12 批处理](../core/configuring-batching-x12.md)或[配置 EDIFACT 批处理](../core/configuring-batching-edifact.md)。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-121">For instructions on how to configure batches, see [Configuring X12 Batching](../core/configuring-batching-x12.md) or [Configuring EDIFACT Batching](../core/configuring-batching-edifact.md).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="2fdb8-122">必要條件</span><span class="sxs-lookup"><span data-stu-id="2fdb8-122">Prerequisites</span></span>  
 <span data-ttu-id="2fdb8-123">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-123">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2fdb8-124">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员可以启动、停止或重写批，但不能更改与批处理相关的任何配置设置。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-124">A member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group can start, stop, or override a batch, but cannot change any configuration setting related to batching.</span></span> <span data-ttu-id="2fdb8-125">必须是 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组的成员才能更改批配置。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-125">You must be a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group to change batch configuration.</span></span>  
  
## <a name="start-stop-and-override-batches"></a><span data-ttu-id="2fdb8-126">启动、 停止和重写批</span><span class="sxs-lookup"><span data-stu-id="2fdb8-126">Start, stop, and override batches</span></span>  
  
1. <span data-ttu-id="2fdb8-127">打开**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理**、 BizTalk 组，然后选择**方**。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-127">Open **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration**, expand the BizTalk group, and select **Parties**.</span></span>  
  
2. <span data-ttu-id="2fdb8-128">在中**参与方和业务配置文件**页面上，在**协议**部分中，右键单击你想要启动、 停止或重写其批配置的协议。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-128">In the **Parties and Business Profiles** page, under the **Agreements** section, right-click the agreement with the batch configuration that you want to start, stop, or override.</span></span>  
  
3. <span data-ttu-id="2fdb8-129">在单向协议选项卡中的**协议属性**，选择**批配置**页。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-129">In the one-way agreement tab of the **Agreement Properties**, select the **Batch Configuration** page.</span></span>  
  
4. <span data-ttu-id="2fdb8-130">上**批配置**页上，选择你想要启动、 停止或重写批的选项卡。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-130">On the **Batch Configuration** page, select the tab for the batch that you want to start, stop, or override.</span></span>  
  
5. <span data-ttu-id="2fdb8-131">验证筛选条件、发布条件和激活范围属性是否使用其应当使用的值。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-131">Verify that the filter criteria, release criteria, and activation range properties are as they should be.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="2fdb8-132">如果您的成员[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]操作员组，但不是[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组，可以启动、 停止、 或重写批。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-132">If you are a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators group, but not the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group, you can start, stop, or override batches.</span></span> <span data-ttu-id="2fdb8-133">但是，不能更改批配置设置。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-133">But, you cannot change batch configuration settings.</span></span> <span data-ttu-id="2fdb8-134">设置都可见，但是如果更改了设置，然后选择**确定**，出现权限错误。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-134">The settings are visible to you, but if you change a setting, and then select **OK**, you get a permissions error.</span></span>  
  
6. <span data-ttu-id="2fdb8-135">如果尚未激活批处理业务流程的实例，请选择**启动**激活实例。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-135">If an instance of the batching orchestration has not been activated, select **Start** to activate an instance.</span></span>  
  
   > [!NOTE]
   >  - <span data-ttu-id="2fdb8-136">则可以确定是否批处理业务流程的实例未被激活**启动**启用按钮，并**激活批处理**下显示**开始**控件。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-136">You can tell that an instance of the batching orchestration has not been activated if the **Start** button is enabled, and **Batching is not activated** is displayed just beneath the **Start** control.</span></span>  
   >  - <span data-ttu-id="2fdb8-137">如果已单击**启动**按钮，并已激活批处理业务流程实例，但为批收集任何元素，然后验证中的日期时间**激活**文本框中已发生的情况。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-137">If you have clicked the **Start** button, and an instance of the batching orchestration has been activated, but no elements are being collected for the batch, then verify that the datetime in the **Activation** text box has transpired.</span></span> <span data-ttu-id="2fdb8-138">如果没有，则**激活**日期必须设置为当前日期或更早版本。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-138">If not, the **Activation** date must be set to the current date or earlier.</span></span>  
  
7. <span data-ttu-id="2fdb8-139">当不满足发布条件时发送批处理的交换，请选择**重写**。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-139">To send a batched interchange when the release criteria have not been met, select **Override**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="2fdb8-140">选择**重写**导致批处理的交换发送，但不会影响批处理业务流程实例、 激活条件或发布条件的激活状态。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-140">Selecting **Override** results in a batched interchange being sent, but does not affect the activation status of the batching orchestration instance, the activation criteria, or the release criteria.</span></span>  
  
8. <span data-ttu-id="2fdb8-141">若要停用批处理业务流程的实例，请选择**停止**。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-141">To deactivate the instance of the batching orchestration, select **Stop**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="2fdb8-142">选择**停止**导致批处理的交换发送，并正在终止批处理业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-142">Selecting **Stop** results in a batched interchange being sent, and the batching orchestration instance being terminated.</span></span>  
  
9. <span data-ttu-id="2fdb8-143">选择**确定**或**取消**以关闭**协议属性**。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-143">Select **OK** or **Cancel** to close the **Agreement Properties**.</span></span>  

## <a name="delete-batches"></a><span data-ttu-id="2fdb8-144">删除批</span><span class="sxs-lookup"><span data-stu-id="2fdb8-144">Delete batches</span></span>  
  
1. <span data-ttu-id="2fdb8-145">在中**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理**，选择**方**。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-145">In **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration**, select **Parties**.</span></span>  
  
2. <span data-ttu-id="2fdb8-146">在中**参与方和业务配置文件**页面上，在**协议**部分中，右键单击你想要删除的批配置的协议。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-146">In the **Parties and Business Profiles** page, under the **Agreements** section, right-click the agreement with the batch configuration that you want to delete.</span></span>  
  
3. <span data-ttu-id="2fdb8-147">在单向协议选项卡中的**协议属性**对话框中，选择**批配置**页。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-147">In the one-way agreement tab of the **Agreement Properties** dialog box, select the **Batch Configuration** page.</span></span>  
  
4. <span data-ttu-id="2fdb8-148">上**批配置**页上，选择你想要删除的批的选项卡。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-148">On the **Batch Configuration** page, select the tab for the batch that you want to delete.</span></span>  
  
5. <span data-ttu-id="2fdb8-149">在右下角的选项卡页上选择**删除**。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-149">On the right-hand corner of the tab page, select **Delete**.</span></span>  
  
6. <span data-ttu-id="2fdb8-150">选择**确定**以关闭**协议属性**。</span><span class="sxs-lookup"><span data-stu-id="2fdb8-150">Select **OK** to close the **Agreement Properties**.</span></span>  

  
## <a name="see-also"></a><span data-ttu-id="2fdb8-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="2fdb8-151">See Also</span></span>  
 [<span data-ttu-id="2fdb8-152">配置传出批</span><span class="sxs-lookup"><span data-stu-id="2fdb8-152">Configuring an Outgoing Batch</span></span>](../core/configuring-an-outgoing-batch.md)  
 [<span data-ttu-id="2fdb8-153">管理 EDI 和 AS2 解决方案</span><span class="sxs-lookup"><span data-stu-id="2fdb8-153">Managing EDI and AS2 Solutions</span></span>](../core/managing-edi-and-as2-solutions.md)