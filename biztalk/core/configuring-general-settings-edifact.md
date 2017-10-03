---
title: "配置常规设置 (EDIFACT) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e18892d3-c1a4-41c8-98c2-a116ce2805ba
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a05fab2501c0c3a71c27e22f2138c7a189193c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-general-settings-edifact"></a><span data-ttu-id="25b06-102">配置常规设置 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="25b06-102">Configuring General Settings (EDIFACT)</span></span>
<span data-ttu-id="25b06-103">作为常规设置的一部分，指定协议名称、将使用的协议（X12 或 EDIFACT）、之间存在协议的参与方和配置文件以及是否为通过协议处理的所有消息启用报告。</span><span class="sxs-lookup"><span data-stu-id="25b06-103">As part of the general settings, you specify agreement name, the protocol it will use (X12 or EDIFACT), the parties and profiles that the agreement is between, and whether to have reporting enabled for all messages processed through the agreement.</span></span> <span data-ttu-id="25b06-104">作为协议的一部分，还可以指定参与方联系信息。</span><span class="sxs-lookup"><span data-stu-id="25b06-104">You can also specify the party contact information as part of the agreement.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="25b06-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="25b06-105">Prerequisites</span></span>  
 <span data-ttu-id="25b06-106">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="25b06-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-general-agreement-settings"></a><span data-ttu-id="25b06-107">若要配置常规协议设置，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="25b06-107">To configure general agreement settings</span></span>  
  
1.  <span data-ttu-id="25b06-108">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**在控制台树中，然后在**方和业务配置文件**页上，右键单击业务配置文件，必须为协议的一部分，要创建，指向**新建**，然后单击**协议**。</span><span class="sxs-lookup"><span data-stu-id="25b06-108">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, click **Parties** in the console tree, and in the **Parties and Business Profiles** page, right-click a business profile that must be part of the agreement that you are creating, point to **New**, and then click **Agreement**.</span></span>  
  
2.  <span data-ttu-id="25b06-109">下表列出了不同的属性以及要为中的属性指定的值**常规属性**页。</span><span class="sxs-lookup"><span data-stu-id="25b06-109">The following tables list the different properties and the values to be specified for the properties in the **General Properties** page.</span></span>  
  
    1.  <span data-ttu-id="25b06-110">在**协议参数**部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="25b06-110">In the **Agreement Parameters** section, do the following:</span></span>  
  
        |<span data-ttu-id="25b06-111">使用此选项</span><span class="sxs-lookup"><span data-stu-id="25b06-111">Use this</span></span>|<span data-ttu-id="25b06-112">执行的操作</span><span class="sxs-lookup"><span data-stu-id="25b06-112">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="25b06-113">**名称**</span><span class="sxs-lookup"><span data-stu-id="25b06-113">**Name**</span></span>|<span data-ttu-id="25b06-114">指定此协议的名称</span><span class="sxs-lookup"><span data-stu-id="25b06-114">Specify a name for the agreement</span></span>|  
        |<span data-ttu-id="25b06-115">**ID**</span><span class="sxs-lookup"><span data-stu-id="25b06-115">**ID**</span></span>|<span data-ttu-id="25b06-116">列出该协议的唯一标识。</span><span class="sxs-lookup"><span data-stu-id="25b06-116">Lists unique identification for the agreement.</span></span> <span data-ttu-id="25b06-117">此文本框不可编辑，并在您单击后将显示协议 ID**应用**接受的第一个时间和设置。</span><span class="sxs-lookup"><span data-stu-id="25b06-117">This text box is not editable and will display the agreement ID after you click **Apply** for the first time and settings are accepted.</span></span>|  
        |<span data-ttu-id="25b06-118">**状态**</span><span class="sxs-lookup"><span data-stu-id="25b06-118">**Status**</span></span>|<span data-ttu-id="25b06-119">指定协议的状态。</span><span class="sxs-lookup"><span data-stu-id="25b06-119">Specifies the status of the agreement.</span></span> <span data-ttu-id="25b06-120">默认情况下，在创建协议**Active**状态。</span><span class="sxs-lookup"><span data-stu-id="25b06-120">By default, an agreement is created in an **Active** state.</span></span> <span data-ttu-id="25b06-121">如果你想协议时首先创建，选择要禁用**禁用**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="25b06-121">If you want the agreement to be disabled when it is first created, select **Disabled** from the drop-down list.</span></span>|  
        |<span data-ttu-id="25b06-122">**协议**</span><span class="sxs-lookup"><span data-stu-id="25b06-122">**Protocol**</span></span>|<span data-ttu-id="25b06-123">指定该协议的协议。</span><span class="sxs-lookup"><span data-stu-id="25b06-123">Specifies the protocol for the agreement.</span></span> <span data-ttu-id="25b06-124">对于一种编码 EDIFACT 协议，选择**EDIFACT**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="25b06-124">For an EDIFACT encoding protocol, select **EDIFACT** from the drop-down list.</span></span>|  
  
    2.  <span data-ttu-id="25b06-125">在**第一个合作伙伴**部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="25b06-125">In the **First Partner** section, do the following:</span></span>  
  
        |<span data-ttu-id="25b06-126">使用此选项</span><span class="sxs-lookup"><span data-stu-id="25b06-126">Use this</span></span>|<span data-ttu-id="25b06-127">执行的操作</span><span class="sxs-lookup"><span data-stu-id="25b06-127">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="25b06-128">**名称**</span><span class="sxs-lookup"><span data-stu-id="25b06-128">**Name**</span></span>|<span data-ttu-id="25b06-129">显示具有要为其创建协议的业务配置文件的合作伙伴名称。</span><span class="sxs-lookup"><span data-stu-id="25b06-129">Displays the partner name that has the business profile for which you are creating the agreement.</span></span> <span data-ttu-id="25b06-130">此文本框不可编辑。</span><span class="sxs-lookup"><span data-stu-id="25b06-130">This text box is not editable.</span></span>|  
        |<span data-ttu-id="25b06-131">**配置文件**</span><span class="sxs-lookup"><span data-stu-id="25b06-131">**Profile**</span></span>|<span data-ttu-id="25b06-132">显示要为其创建协议的配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="25b06-132">Displays the name of the profile for which you are creating the agreement.</span></span> <span data-ttu-id="25b06-133">此文本框不可编辑。</span><span class="sxs-lookup"><span data-stu-id="25b06-133">This text box is not editable.</span></span>|  
        |<span data-ttu-id="25b06-134">**协议设置**</span><span class="sxs-lookup"><span data-stu-id="25b06-134">**Protocol Set**</span></span>|<span data-ttu-id="25b06-135">如果您创建了一个作为业务配置文件一部分的 EDIFACT 协议集，您便可从下拉列表中选择该协议集。</span><span class="sxs-lookup"><span data-stu-id="25b06-135">If you created an EDIFACT protocol set as part of the business profile, you can select that from the drop-down list.</span></span> <span data-ttu-id="25b06-136">如果您未创建作为业务配置文件一部分的 EDIFACT 协议集，则可将其留空。</span><span class="sxs-lookup"><span data-stu-id="25b06-136">If you did not create an EDIFACT protocol set as part of the business profile, you can leave this empty.</span></span>|  
  
    3.  <span data-ttu-id="25b06-137">在**第二个合作伙伴**部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="25b06-137">In the **Second Partner** section, do the following:</span></span>  
  
        |<span data-ttu-id="25b06-138">使用此选项</span><span class="sxs-lookup"><span data-stu-id="25b06-138">Use this</span></span>|<span data-ttu-id="25b06-139">执行的操作</span><span class="sxs-lookup"><span data-stu-id="25b06-139">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="25b06-140">**名称**</span><span class="sxs-lookup"><span data-stu-id="25b06-140">**Name**</span></span>|<span data-ttu-id="25b06-141">从下拉列表中选择具有您希望用其创建协议的业务配置文件的参与方。</span><span class="sxs-lookup"><span data-stu-id="25b06-141">From the drop-down select a party that has the business profile with which you want to create an agreement.</span></span>|  
        |<span data-ttu-id="25b06-142">**配置文件**</span><span class="sxs-lookup"><span data-stu-id="25b06-142">**Profile**</span></span>|<span data-ttu-id="25b06-143">从下拉列表中选择您要通过其创建协议的简介。</span><span class="sxs-lookup"><span data-stu-id="25b06-143">From the drop-down select a profile with which you want to create an agreement.</span></span>|  
        |<span data-ttu-id="25b06-144">**协议设置**</span><span class="sxs-lookup"><span data-stu-id="25b06-144">**Protocol Set**</span></span>|<span data-ttu-id="25b06-145">如果您创建了一个作为业务配置文件一部分的 EDIFACT 协议集，您便可从下拉列表中选择该协议集。</span><span class="sxs-lookup"><span data-stu-id="25b06-145">If you created an EDIFACT protocol set as part of the business profile, you can select that from the drop-down list.</span></span> <span data-ttu-id="25b06-146">如果您未创建作为业务配置文件一部分的 EDIFACT 协议集，则可将其留空。</span><span class="sxs-lookup"><span data-stu-id="25b06-146">If you did not create an EDIFACT protocol set as part of the business profile, you can leave this empty.</span></span>|  
  
        > [!TIP]
        >  <span data-ttu-id="25b06-147">按`CTRL`，选择将为协议的一部分，右键单击任一业务配置文件，指向的业务配置文件**新建**，然后单击**协议**。</span><span class="sxs-lookup"><span data-stu-id="25b06-147">Press `CTRL`, select the business profiles that will be part of the agreement, right-click either business profile, point to **New**, and then click **Agreement**.</span></span> <span data-ttu-id="25b06-148">值的合作伙伴名称，这两个合作伙伴的业务配置文件将自动填充在**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="25b06-148">The values for partner name and business profiles for both the partners will be automatically populated in the **Agreement Properties** dialog box.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="25b06-149">一旦你选择的其他配置文件，添加两个选项卡旁边**常规**选项卡。每个选项卡都代表两个参与方之间的一个单向 EDIFACT 协议。</span><span class="sxs-lookup"><span data-stu-id="25b06-149">As soon as you select the other profile, two tabs are added next to the **General** tab. Each tab represents a one-way EDIFACT agreement between the two parties.</span></span> <span data-ttu-id="25b06-150">您可以使用这些选项卡来指定选项卡中的与交换和事务集相关的设置。</span><span class="sxs-lookup"><span data-stu-id="25b06-150">You use the tabs to specify interchange and transaction set related settings in the tabs.</span></span> <span data-ttu-id="25b06-151">有关详细信息，请参阅[配置交换设置 (X12)](../core/configuring-interchange-settings-x12.md)和[配置事务集设置 (X12)](../core/configuring-transaction-set-settings-x12.md)。</span><span class="sxs-lookup"><span data-stu-id="25b06-151">For more information, see [Configuring Interchange Settings (X12)](../core/configuring-interchange-settings-x12.md) and [Configuring Transaction Set Settings (X12)](../core/configuring-transaction-set-settings-x12.md).</span></span>  
  
    4.  <span data-ttu-id="25b06-152">选择**启用协议**复选框以启用该协议并执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="25b06-152">Select the **Enable Agreement** check box to enable the agreement and do the following:</span></span>  
  
        |<span data-ttu-id="25b06-153">使用此选项</span><span class="sxs-lookup"><span data-stu-id="25b06-153">Use this</span></span>|<span data-ttu-id="25b06-154">执行的操作</span><span class="sxs-lookup"><span data-stu-id="25b06-154">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="25b06-155">**From**</span><span class="sxs-lookup"><span data-stu-id="25b06-155">**From**</span></span>|<span data-ttu-id="25b06-156">选址协议的有效期起始日期和时间。</span><span class="sxs-lookup"><span data-stu-id="25b06-156">Select the date and time from which the agreement will be valid.</span></span>|  
        |<span data-ttu-id="25b06-157">**无结束日期**</span><span class="sxs-lookup"><span data-stu-id="25b06-157">**No End Date**</span></span>|<span data-ttu-id="25b06-158">如果您不希望设置禁用协议的结束日期，则选择该选项。</span><span class="sxs-lookup"><span data-stu-id="25b06-158">Select this option if you do not want to set an end date when the agreement is disabled.</span></span>|  
        |<span data-ttu-id="25b06-159">**结束日期**</span><span class="sxs-lookup"><span data-stu-id="25b06-159">**End By**</span></span>|<span data-ttu-id="25b06-160">选择该选项并指定协议有效的结束日期和时间。</span><span class="sxs-lookup"><span data-stu-id="25b06-160">Select this option and specify the date and time until which the agreement will be valid.</span></span>|  
  
    5.  <span data-ttu-id="25b06-161">在**常见主机设置**部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="25b06-161">In the **Common Host Settings** section, do the following:</span></span>  
  
        |<span data-ttu-id="25b06-162">使用此选项</span><span class="sxs-lookup"><span data-stu-id="25b06-162">Use this</span></span>|<span data-ttu-id="25b06-163">执行的操作</span><span class="sxs-lookup"><span data-stu-id="25b06-163">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="25b06-164">**错误记录到事件日志**</span><span class="sxs-lookup"><span data-stu-id="25b06-164">**Log errors to event log**</span></span>|<span data-ttu-id="25b06-165">如果要将 EDI 引擎（EDI 管道、批处理业务流程、路由业务流程等）生成的任何错误以及上下文信息记录到 Windows 事件查看器中，则选择此选项。</span><span class="sxs-lookup"><span data-stu-id="25b06-165">Select this option if you want to log any errors generated by the EDI engine (EDI pipelines, batching orchestration, routing orchestration, etc.), with contextual information, to the Windows Event Viewer.</span></span>|  
        |<span data-ttu-id="25b06-166">**日志警告记录到事件日志**</span><span class="sxs-lookup"><span data-stu-id="25b06-166">**Log warnings to event log**</span></span>|<span data-ttu-id="25b06-167">如果要将 EDI 引擎（EDI 管道、批处理业务流程、路由业务流程等）生成的任何警告以及上下文信息记录到 Windows 事件查看器中，则选择此选项。</span><span class="sxs-lookup"><span data-stu-id="25b06-167">Select this option if you want to log any warnings generated by the EDI engine (EDI pipelines, batching orchestration, routing orchestration, etc.), with contextual information, to the Windows Event Viewer.</span></span>|  
        |<span data-ttu-id="25b06-168">**打开报表**</span><span class="sxs-lookup"><span data-stu-id="25b06-168">**Turn ON reporting**</span></span>|<span data-ttu-id="25b06-169">选择此选项以显示所有 EDI 消息 （传入和传出） 的状态条目上**EDI 交换和关联 ACK 状态**选项卡**组概述**页面[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="25b06-169">Select this option to display status entries for all EDI messages (incoming and outgoing) on the **EDI Interchange and Correlated ACK Status** tab of the **Group Overview** page in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="25b06-170">如果取消选中此选项，则不会显示任何状态条目。</span><span class="sxs-lookup"><span data-stu-id="25b06-170">If unchecked, no status entries will be displayed.</span></span>|  
        |<span data-ttu-id="25b06-171">**存储用于报告的消息有效负载**</span><span class="sxs-lookup"><span data-stu-id="25b06-171">**Store message payload for reporting**</span></span>|<span data-ttu-id="25b06-172">如果你选择**打开 reporting**，选择此选项以存储事务设置中的跟踪 (BizTalkDTADb) 数据库的 EDI 表。</span><span class="sxs-lookup"><span data-stu-id="25b06-172">If you selected **Turn ON reporting**, select this option to store transaction sets in the EDI tables of the tracking (BizTalkDTADb) database.</span></span>|  
  
3.  <span data-ttu-id="25b06-173">在**常规**选项卡上，在**联系人信息**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="25b06-173">In the **General** tab, on the **Contact Information** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="25b06-174">在**Contact1**选项卡上，输入要与其创建协议的参与方的配置文件的联系信息。</span><span class="sxs-lookup"><span data-stu-id="25b06-174">In the **Contact1** tab, enter the contact information for the party’s profile with which you are creating an agreement.</span></span> <span data-ttu-id="25b06-175">此数据仅供参考；BizTalk 运行时不会使用此数据。</span><span class="sxs-lookup"><span data-stu-id="25b06-175">This data is for information purposes only; it will not be used by the BizTalk Runtime.</span></span>  
  
    2.  <span data-ttu-id="25b06-176">若要添加的联系人的另一个选项卡，单击**新联系人**选项卡。</span><span class="sxs-lookup"><span data-stu-id="25b06-176">To add another tab for contact, click the **New Contact** tab.</span></span>  
  
    3.  <span data-ttu-id="25b06-177">若要删除的联系人的选项卡，单击**删除**从选项卡页右上角。</span><span class="sxs-lookup"><span data-stu-id="25b06-177">To delete a contact tab, click **Delete** from the top right corner of the tab page.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="25b06-178">无法删除**Contact1**选项卡。只能删除您添加的新选项卡。</span><span class="sxs-lookup"><span data-stu-id="25b06-178">You cannot delete the **Contact1** tab. You can only delete the new tabs that you add.</span></span>  
  
4.  <span data-ttu-id="25b06-179">在**常规**选项卡上，在**其他属性**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="25b06-179">In the **General** tab, on the **Additional Properties** page, do the following:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="25b06-180">BizTalk Server 未使用此页上指定的信息进行任何处理；此数据仅供参考。</span><span class="sxs-lookup"><span data-stu-id="25b06-180">The information you specify on this page is not used by the BizTalk Server for any processing; this data is for information purposes only.</span></span>  
  
    1.  <span data-ttu-id="25b06-181">在**其他属性**网格中，输入你想要添加的任何信息相关的方或协议的名称-值对。</span><span class="sxs-lookup"><span data-stu-id="25b06-181">In the **Additional Properties** grid, enter name-value pairs for any information that you want to add related to the party or agreement.</span></span>  <span data-ttu-id="25b06-182">输入一个名称/值对以存储有关参与方的任何信息。</span><span class="sxs-lookup"><span data-stu-id="25b06-182">Enter a name-value pair to store any information about the party.</span></span> <span data-ttu-id="25b06-183">可以根据需要添加任意数量的名称/值对。</span><span class="sxs-lookup"><span data-stu-id="25b06-183">You can add as many name-value pairs as you want.</span></span>  
  
         <span data-ttu-id="25b06-184">若要删除的名称-值对，选择行，然后单击**删除**从右上角。</span><span class="sxs-lookup"><span data-stu-id="25b06-184">To delete a name-value pair, select the row and click **Delete** from the top-right corner.</span></span>  
  
    2.  <span data-ttu-id="25b06-185">在**文本 1**，**文本 2**，和**协议**文本框中，输入关于与方协议的信息。</span><span class="sxs-lookup"><span data-stu-id="25b06-185">In the **Text 1**, **Text 2**, and **Agreement** text boxes, enter information about the agreement with a party.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="25b06-186">如果你单击**确定**或**应用**此页中提供的所有值列出后，你将收到错误。</span><span class="sxs-lookup"><span data-stu-id="25b06-186">If you click **OK** or **Apply** after providing all the values listed in this page, you will get an error.</span></span> <span data-ttu-id="25b06-187">这是因为还未提供创建协议的必需值。</span><span class="sxs-lookup"><span data-stu-id="25b06-187">That is because the mandatory values to create an agreement are not yet provided.</span></span> <span data-ttu-id="25b06-188">这些选项位于 UNB2 和 UNB3 值**标识符**的每个单向协议选项卡页。</span><span class="sxs-lookup"><span data-stu-id="25b06-188">These are UNB2 and UNB3 values on the **Identifiers** page of each one-way agreement tab.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="25b06-189">后续步骤</span><span class="sxs-lookup"><span data-stu-id="25b06-189">Next Steps</span></span>  
 <span data-ttu-id="25b06-190">现在，您必须为协议配置交换或事务集设置。</span><span class="sxs-lookup"><span data-stu-id="25b06-190">You must now configure the interchange or transaction set settings for the agreement.</span></span> <span data-ttu-id="25b06-191">有关说明，请参阅[配置交换设置 (EDIFACT)](../core/configuring-interchange-settings-edifact.md)或[配置事务集设置 (EDIFACT)](../core/configuring-transaction-set-settings-edifact.md)。</span><span class="sxs-lookup"><span data-stu-id="25b06-191">For instructions see [Configuring Interchange Settings (EDIFACT)](../core/configuring-interchange-settings-edifact.md) or [Configuring Transaction Set Settings (EDIFACT)](../core/configuring-transaction-set-settings-edifact.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25b06-192">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25b06-192">See Also</span></span>  
 [<span data-ttu-id="25b06-193">配置 EDIFACT 特定协议属性</span><span class="sxs-lookup"><span data-stu-id="25b06-193">Configuring EDIFACT-Specific Agreement Properties</span></span>](../core/configuring-edifact-specific-agreement-properties.md)