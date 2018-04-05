---
title: 管理协议 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.resultsobject.agreement
ms.assetid: e9c6cdd1-8c17-4b1e-a556-2b287593bb9d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 012a4a5032bd9f9e9a66b855d41a83b5dc5736d1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="managing-agreements"></a><span data-ttu-id="87990-102">管理协议</span><span class="sxs-lookup"><span data-stu-id="87990-102">Managing Agreements</span></span>
<span data-ttu-id="87990-103">贸易合作伙伴协议 (TPA) 将在两个贸易合作伙伴之间被定义为一个确定且具有约束力的协议，以便通过特定的 B2B 协议处理消息。</span><span class="sxs-lookup"><span data-stu-id="87990-103">A Trading Partner Agreement (TPA) is defined as a definitive and binding agreement between two trading partners for transacting messages over a specific B2B Protocol.</span></span> <span data-ttu-id="87990-104">请参阅[贸易合作伙伴协议](../core/trading-partner-agreement.md)。</span><span class="sxs-lookup"><span data-stu-id="87990-104">See [Trading Partner Agreement](../core/trading-partner-agreement.md).</span></span> 

<span data-ttu-id="87990-105">本主题演示如何创建、 查看、 编辑、 启用、 禁用或删除协议。</span><span class="sxs-lookup"><span data-stu-id="87990-105">This topics shows you how to create, view, edit, enable, disable, or delete an agreement.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="87990-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="87990-106">Prerequisites</span></span>  
 <span data-ttu-id="87990-107">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="87990-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
## <a name="create-an-agreement"></a><span data-ttu-id="87990-108">创建协议</span><span class="sxs-lookup"><span data-stu-id="87990-108">Create an agreement</span></span>  
  
1.  <span data-ttu-id="87990-109">打开**BizTalk Server 管理**，展开 BizTalk 组中，然后选择**方**。</span><span class="sxs-lookup"><span data-stu-id="87990-109">Open **BizTalk Server Administration**, expand the BizTalk group, and select **Parties**.</span></span> 
2. <span data-ttu-id="87990-110">在**方和业务配置文件**页上，右键单击你要创建的协议选择的一部分的业务配置文件**新建**，然后选择**协议**。</span><span class="sxs-lookup"><span data-stu-id="87990-110">In the **Parties and Business Profiles** page, right-click a business profile that is part of the agreement you are creating, select **New**, and then select **Agreement**.</span></span>  
  
3.  <span data-ttu-id="87990-111">在**常规属性**:</span><span class="sxs-lookup"><span data-stu-id="87990-111">In the **General Properties**:</span></span> 
  
    1.  <span data-ttu-id="87990-112">在**协议参数**部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="87990-112">In the **Agreement Parameters** section, do the following:</span></span>  
  
        |<span data-ttu-id="87990-113">使用此选项</span><span class="sxs-lookup"><span data-stu-id="87990-113">Use this</span></span>|<span data-ttu-id="87990-114">执行的操作</span><span class="sxs-lookup"><span data-stu-id="87990-114">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="87990-115">**名称**</span><span class="sxs-lookup"><span data-stu-id="87990-115">**Name**</span></span>|<span data-ttu-id="87990-116">输入协议的名称</span><span class="sxs-lookup"><span data-stu-id="87990-116">Enter a name for the agreement</span></span>|  
        |<span data-ttu-id="87990-117">**ID**</span><span class="sxs-lookup"><span data-stu-id="87990-117">**ID**</span></span>|<span data-ttu-id="87990-118">列出该协议的唯一标识。</span><span class="sxs-lookup"><span data-stu-id="87990-118">Lists unique identification for the agreement.</span></span> <span data-ttu-id="87990-119">此文本框中是只读的并选择后显示的协议 ID**应用**的第一个接受时间和设置。</span><span class="sxs-lookup"><span data-stu-id="87990-119">This text box is read-only, and display the agreement ID after you select **Apply** for the first time, and the settings are accepted.</span></span>|  
        |<span data-ttu-id="87990-120">**状态**</span><span class="sxs-lookup"><span data-stu-id="87990-120">**Status**</span></span>|<span data-ttu-id="87990-121">指定协议的状态。</span><span class="sxs-lookup"><span data-stu-id="87990-121">Specifies the status of the agreement.</span></span> <span data-ttu-id="87990-122">默认情况下，在创建协议**Active**状态。</span><span class="sxs-lookup"><span data-stu-id="87990-122">By default, an agreement is created in an **Active** state.</span></span> <span data-ttu-id="87990-123">如果你想协议时首先创建，选择要禁用**禁用**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="87990-123">If you want the agreement to be disabled when it is first created, select **Disabled** from the drop-down list.</span></span>|  
        |<span data-ttu-id="87990-124">**协议**</span><span class="sxs-lookup"><span data-stu-id="87990-124">**Protocol**</span></span>|<span data-ttu-id="87990-125">指定该协议的协议。</span><span class="sxs-lookup"><span data-stu-id="87990-125">Specifies the protocol for the agreement.</span></span><br /><br /> <span data-ttu-id="87990-126">-对于 X12 编码协议，选择**X12**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="87990-126">-   For an X12 encoding protocol, select **X12** from the drop-down list.</span></span> <span data-ttu-id="87990-127">请参阅[配置 X12 特定协议属性](../core/configuring-x12-specific-agreement-properties.md)</span><span class="sxs-lookup"><span data-stu-id="87990-127">See [Configuring X12-Specific Agreement Properties](../core/configuring-x12-specific-agreement-properties.md)</span></span><br /><span data-ttu-id="87990-128">-对于 EDIFACT 编码协议，选择**EDIFACT**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="87990-128">-   For an EDIFACT encoding protocol, select **EDIFACT** from the drop-down list.</span></span>  <span data-ttu-id="87990-129">请参阅[配置 EDIFACT 特定协议属性](../core/configuring-edifact-specific-agreement-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="87990-129">See [Configuring EDIFACT-Specific Agreement Properties](../core/configuring-edifact-specific-agreement-properties.md).</span></span><br /><span data-ttu-id="87990-130">-对于一种编码 AS2 协议，选择**AS2**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="87990-130">-   For an AS2 encoding protocol, select **AS2** from the drop-down list.</span></span> <span data-ttu-id="87990-131">请参阅[配置 AS2 协议属性](../core/configuring-as2-agreement-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="87990-131">See [Configuring AS2 Agreement Properties](../core/configuring-as2-agreement-properties.md).</span></span> <br/><br/><span data-ttu-id="87990-132">**注意**</span><span class="sxs-lookup"><span data-stu-id="87990-132">**Note**</span></span><br/>  <span data-ttu-id="87990-133">协议属性是在单向协议选项卡中提供的。</span><span class="sxs-lookup"><span data-stu-id="87990-133">The agreement properties are provided in the one-way agreement tabs.</span></span> <span data-ttu-id="87990-134">当您选择了将通过其创建协议的第二个简介之后，便会出现单向协议选项卡。</span><span class="sxs-lookup"><span data-stu-id="87990-134">The one-way agreement tabs appear after you have selected the second profile with which the agreement will be created.</span></span> <span data-ttu-id="87990-135">将在以下步骤中选择第二个合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="87990-135">You select the second partner in the following steps.</span></span>|  
  
    2.  <span data-ttu-id="87990-136">在**第一个合作伙伴**部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="87990-136">In the **First Partner** section, do the following:</span></span>  
  
        |<span data-ttu-id="87990-137">使用此选项</span><span class="sxs-lookup"><span data-stu-id="87990-137">Use this</span></span>|<span data-ttu-id="87990-138">执行的操作</span><span class="sxs-lookup"><span data-stu-id="87990-138">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="87990-139">**名称**</span><span class="sxs-lookup"><span data-stu-id="87990-139">**Name**</span></span>|<span data-ttu-id="87990-140">显示具有要为其创建协议的业务配置文件的合作伙伴名称。</span><span class="sxs-lookup"><span data-stu-id="87990-140">Displays the partner name that has the business profile for which you are creating the agreement.</span></span> <span data-ttu-id="87990-141">此文本框中是只读的。</span><span class="sxs-lookup"><span data-stu-id="87990-141">This text box is read-only.</span></span>|  
        |<span data-ttu-id="87990-142">**配置文件**</span><span class="sxs-lookup"><span data-stu-id="87990-142">**Profile**</span></span>|<span data-ttu-id="87990-143">显示要为其创建协议的配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="87990-143">Displays the name of the profile for which you are creating the agreement.</span></span> <span data-ttu-id="87990-144">此文本框中是只读的。</span><span class="sxs-lookup"><span data-stu-id="87990-144">This text box is read-only.</span></span>|  
        |<span data-ttu-id="87990-145">**协议设置**</span><span class="sxs-lookup"><span data-stu-id="87990-145">**Protocol Set**</span></span>|<span data-ttu-id="87990-146">如果您创建了一个 X12 协议集作为业务简介的一部分，则可以从下拉列表中选择该协议集。</span><span class="sxs-lookup"><span data-stu-id="87990-146">If you created an X12 protocol set as part of the business profile, you can select that from the drop-down list.</span></span> <span data-ttu-id="87990-147">如果您没有创建一个 X12 协议集作为业务简介的一部分，则可以保留它为空。</span><span class="sxs-lookup"><span data-stu-id="87990-147">If you did not create an X12 protocol set as part of the business profile, you can leave this empty.</span></span>|  
  
    3.  <span data-ttu-id="87990-148">在**第二个合作伙伴**部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="87990-148">In the **Second Partner** section, do the following:</span></span>  
  
        |<span data-ttu-id="87990-149">使用此选项</span><span class="sxs-lookup"><span data-stu-id="87990-149">Use this</span></span>|<span data-ttu-id="87990-150">执行的操作</span><span class="sxs-lookup"><span data-stu-id="87990-150">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="87990-151">**名称**</span><span class="sxs-lookup"><span data-stu-id="87990-151">**Name**</span></span>|<span data-ttu-id="87990-152">从下拉列表中选择具有您希望用其创建协议的业务配置文件的参与方。</span><span class="sxs-lookup"><span data-stu-id="87990-152">From the drop-down select a party that has the business profile with which you want to create an agreement.</span></span>|  
        |<span data-ttu-id="87990-153">**配置文件**</span><span class="sxs-lookup"><span data-stu-id="87990-153">**Profile**</span></span>|<span data-ttu-id="87990-154">从下拉列表中选择您要通过其创建协议的简介。</span><span class="sxs-lookup"><span data-stu-id="87990-154">From the drop-down select a profile with which you want to create an agreement.</span></span>|  
        |<span data-ttu-id="87990-155">**协议设置**</span><span class="sxs-lookup"><span data-stu-id="87990-155">**Protocol Set**</span></span>|<span data-ttu-id="87990-156">如果您创建了一个 X12 协议集作为业务简介的一部分，则可以从下拉列表中选择该协议集。</span><span class="sxs-lookup"><span data-stu-id="87990-156">If you created an X12 protocol set as part of the business profile, you can select that from the drop-down list.</span></span> <span data-ttu-id="87990-157">如果您没有创建一个 X12 协议集作为业务简介的一部分，则可以保留它为空。</span><span class="sxs-lookup"><span data-stu-id="87990-157">If you did not create an X12 protocol set as part of the business profile, you can leave this empty.</span></span>|  
  
        > [!TIP]
        >  <span data-ttu-id="87990-158">按`CTRL`，选择将为协议的一部分，右键单击任一业务配置文件，选择的业务配置文件**新建**，然后选择**协议**。</span><span class="sxs-lookup"><span data-stu-id="87990-158">Press `CTRL`, select the business profiles that will be part of the agreement, right-click either business profile, select **New**, and then select **Agreement**.</span></span> <span data-ttu-id="87990-159">值的合作伙伴名称和两个伙伴的业务配置文件中自动填充**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="87990-159">The values for partner name and business profiles for both the partners are automatically populated in the **Agreement Properties** dialog box.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="87990-160">一旦你选择的其他配置文件，添加两个选项卡旁边**常规**选项卡。每个选项卡代表双方之间的一个单向协议。</span><span class="sxs-lookup"><span data-stu-id="87990-160">As soon as you select the other profile, two tabs are added next to the **General** tab. Each tab represents a one-way agreement between the two parties.</span></span> <span data-ttu-id="87990-161">使用选项卡输入的协议属性。</span><span class="sxs-lookup"><span data-stu-id="87990-161">You use the tabs to enter the agreement properties.</span></span>  
  
    4.  <span data-ttu-id="87990-162">选择**启用协议**复选框以启用该协议，并执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="87990-162">Select the **Enable Agreement** check box to enable the agreement, and do the following:</span></span>  
  
        |<span data-ttu-id="87990-163">使用此选项</span><span class="sxs-lookup"><span data-stu-id="87990-163">Use this</span></span>|<span data-ttu-id="87990-164">执行的操作</span><span class="sxs-lookup"><span data-stu-id="87990-164">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="87990-165">**From**</span><span class="sxs-lookup"><span data-stu-id="87990-165">**From**</span></span>|<span data-ttu-id="87990-166">选择的日期和时间则协议的有效。</span><span class="sxs-lookup"><span data-stu-id="87990-166">Select the date and time from which the agreement is valid.</span></span>|  
        |<span data-ttu-id="87990-167">**无结束日期**</span><span class="sxs-lookup"><span data-stu-id="87990-167">**No End Date**</span></span>|<span data-ttu-id="87990-168">如果您不希望设置禁用协议的结束日期，则选择该选项。</span><span class="sxs-lookup"><span data-stu-id="87990-168">Select this option if you do not want to set an end date when the agreement is disabled.</span></span>|  
        |<span data-ttu-id="87990-169">**结束日期**</span><span class="sxs-lookup"><span data-stu-id="87990-169">**End By**</span></span>|<span data-ttu-id="87990-170">选择此选项可输入的日期和时间，直到协议无效。</span><span class="sxs-lookup"><span data-stu-id="87990-170">Select this option to enter the date and time until the agreement is valid.</span></span>|  
  
    5.  <span data-ttu-id="87990-171">在**常见主机设置**部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="87990-171">In the **Common Host Settings** section, do the following:</span></span>  
  
        |<span data-ttu-id="87990-172">使用此选项</span><span class="sxs-lookup"><span data-stu-id="87990-172">Use this</span></span>|<span data-ttu-id="87990-173">执行的操作</span><span class="sxs-lookup"><span data-stu-id="87990-173">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="87990-174">**错误记录到事件日志**</span><span class="sxs-lookup"><span data-stu-id="87990-174">**Log errors to event log**</span></span>|<span data-ttu-id="87990-175">如果要将 EDI 引擎（EDI 管道、批处理业务流程、路由业务流程等）生成的任何错误以及上下文信息记录到 Windows 事件查看器中，则选择此选项。</span><span class="sxs-lookup"><span data-stu-id="87990-175">Select this option if you want to log any errors generated by the EDI engine (EDI pipelines, batching orchestration, routing orchestration, etc.), with contextual information, to the Windows Event Viewer.</span></span><br/><br/><span data-ttu-id="87990-176">**请注意**： 不适用于 AS2 协议。</span><span class="sxs-lookup"><span data-stu-id="87990-176">**Note**:  Does not apply to AS2 agreements.</span></span>|  
        |<span data-ttu-id="87990-177">**日志警告记录到事件日志**</span><span class="sxs-lookup"><span data-stu-id="87990-177">**Log warnings to event log**</span></span>|<span data-ttu-id="87990-178">如果要将 EDI 引擎（EDI 管道、批处理业务流程、路由业务流程等）生成的任何警告以及上下文信息记录到 Windows 事件查看器中，则选择此选项。</span><span class="sxs-lookup"><span data-stu-id="87990-178">Select this option if you want to log any warnings generated by the EDI engine (EDI pipelines, batching orchestration, routing orchestration, etc.), with contextual information, to the Windows Event Viewer.</span></span> <br/><br/><span data-ttu-id="87990-179">**请注意**： 不适用于 AS2 协议。</span><span class="sxs-lookup"><span data-stu-id="87990-179">**Note**:  Does not apply to AS2 agreements.</span></span>|  
        |<span data-ttu-id="87990-180">**打开报表**</span><span class="sxs-lookup"><span data-stu-id="87990-180">**Turn ON reporting**</span></span>|<span data-ttu-id="87990-181">选择此选项以显示所有 EDI 消息 （传入和传出） 的状态条目上**EDI 交换和关联 ACK 状态**选项卡**组概述**页面[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="87990-181">Select this option to display status entries for all EDI messages (incoming and outgoing) on the **EDI Interchange and Correlated ACK Status** tab of the **Group Overview** page in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="87990-182">如果取消选中后，会不显示任何状态条目。</span><span class="sxs-lookup"><span data-stu-id="87990-182">If unchecked, no status entries are displayed.</span></span>|  
        |<span data-ttu-id="87990-183">**存储用于报告的消息有效负载**</span><span class="sxs-lookup"><span data-stu-id="87990-183">**Store message payload for reporting**</span></span>|<span data-ttu-id="87990-184">如果你选择**打开 reporting**，选择此选项以存储事务设置中的跟踪 (BizTalkDTADb) 数据库的 EDI 表。</span><span class="sxs-lookup"><span data-stu-id="87990-184">If you selected **Turn ON reporting**, select this option to store transaction sets in the EDI tables of the tracking (BizTalkDTADb) database.</span></span> <br/><br/><span data-ttu-id="87990-185">**请注意**： 不适用于 AS2 协议。</span><span class="sxs-lookup"><span data-stu-id="87990-185">**Note**:  Does not apply to AS2 agreements.</span></span>|  
  
4.  <span data-ttu-id="87990-186">在**常规**选项卡上，在**联系人信息**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="87990-186">In the **General** tab, on the **Contact Information** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="87990-187">在**Contact1**选项卡上，输入要与其创建协议的参与方的配置文件的联系信息。</span><span class="sxs-lookup"><span data-stu-id="87990-187">In the **Contact1** tab, enter the contact information for the party’s profile with which you are creating an agreement.</span></span> <span data-ttu-id="87990-188">此数据是仅; 用于信息由 BizTalk 运行时不使用它。</span><span class="sxs-lookup"><span data-stu-id="87990-188">This data is for information purposes only; it is not used by the BizTalk Runtime.</span></span>  
  
    2.  <span data-ttu-id="87990-189">若要添加的联系人的另一个选项卡，选择**新联系人**选项卡。</span><span class="sxs-lookup"><span data-stu-id="87990-189">To add another tab for contact, select the **New Contact** tab.</span></span>  
  
    3.  <span data-ttu-id="87990-190">若要删除的联系人的选项卡，选择**删除**从选项卡页右上角。</span><span class="sxs-lookup"><span data-stu-id="87990-190">To delete a contact tab, select **Delete** from the top right corner of the tab page.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="87990-191">无法删除**Contact1**选项卡。只能删除您添加的新选项卡。</span><span class="sxs-lookup"><span data-stu-id="87990-191">You cannot delete the **Contact1** tab. You can only delete the new tabs that you add.</span></span>  
  
5.  <span data-ttu-id="87990-192">在**常规**选项卡上，在**其他属性**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="87990-192">In the **General** tab, on the **Additional Properties** page, do the following:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="87990-193">BizTalk Server 不会将此页面输入的信息用于任何处理;此数据是仅供信息。</span><span class="sxs-lookup"><span data-stu-id="87990-193">The information you enter on this page is not used by the BizTalk Server for any processing; this data is for information purposes only.</span></span>  
  
    1.  <span data-ttu-id="87990-194">在**其他属性**网格中，输入你想要添加的任何信息相关的方或协议的名称-值对。</span><span class="sxs-lookup"><span data-stu-id="87990-194">In the **Additional Properties** grid, enter name-value pairs for any information that you want to add related to the party or agreement.</span></span>  <span data-ttu-id="87990-195">输入一个名称/值对以存储有关参与方的任何信息。</span><span class="sxs-lookup"><span data-stu-id="87990-195">Enter a name-value pair to store any information about the party.</span></span> <span data-ttu-id="87990-196">可以根据需要添加任意数量的名称/值对。</span><span class="sxs-lookup"><span data-stu-id="87990-196">You can add as many name-value pairs as you want.</span></span>  
  
         <span data-ttu-id="87990-197">要删除的名称-值对，选择行，然后选择**删除**从右上角。</span><span class="sxs-lookup"><span data-stu-id="87990-197">To delete a name-value pair, select the row, and select **Delete** from the top-right corner.</span></span>  
  
    2.  <span data-ttu-id="87990-198">在**文本 1**，**文本 2**，和**协议**文本框中，输入关于与方协议的信息。</span><span class="sxs-lookup"><span data-stu-id="87990-198">In the **Text 1**, **Text 2**, and **Agreement** text boxes, enter information about the agreement with a party.</span></span>  
  
    3.  <span data-ttu-id="87990-199">选择**应用**接受属性，或选择**确定**完成的配置设置。</span><span class="sxs-lookup"><span data-stu-id="87990-199">Select **Apply** to accept the properties, or select **OK** to complete the configuration setting.</span></span> <span data-ttu-id="87990-200">以上任一操作验证的设置。</span><span class="sxs-lookup"><span data-stu-id="87990-200">Either action validates the settings.</span></span>  

## <a name="view-or-change-an-agreement"></a><span data-ttu-id="87990-201">查看或更改协议</span><span class="sxs-lookup"><span data-stu-id="87990-201">View or change an agreement</span></span>  
  
1.  <span data-ttu-id="87990-202">在**BizTalk Server 管理**，选择**方**。</span><span class="sxs-lookup"><span data-stu-id="87990-202">In **BizTalk Server Administration**, select **Parties**.</span></span> 

2. <span data-ttu-id="87990-203">在**方和业务配置文件**页上，选择任何具有你想要查看或编辑协议的两个业务配置文件。</span><span class="sxs-lookup"><span data-stu-id="87990-203">In the **Parties and Business Profiles** page, select any of the two business profile that have the agreement that you want to view or edit.</span></span>  
  
3.  <span data-ttu-id="87990-204">在**协议**部分，右键单击该协议，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="87990-204">In the **Agreements** section, right-click the agreement, and then select **Properties**.</span></span>  
  
4.  <span data-ttu-id="87990-205">在**协议属性**、 查看或编辑该协议。</span><span class="sxs-lookup"><span data-stu-id="87990-205">In the **Agreement Properties**, view or edit the agreement.</span></span> <span data-ttu-id="87990-206">可以在不同的选项卡和中的页面上输入的值**协议属性**对话框框中，请参阅以下：</span><span class="sxs-lookup"><span data-stu-id="87990-206">For the values that can be entered on the different tabs and pages in the **Agreement Properties** dialog box, see the following:</span></span>  
  
    |<span data-ttu-id="87990-207">若要了解</span><span class="sxs-lookup"><span data-stu-id="87990-207">For this</span></span>|<span data-ttu-id="87990-208">请参阅此</span><span class="sxs-lookup"><span data-stu-id="87990-208">See this</span></span>|  
    |--------------|--------------|  
    |<span data-ttu-id="87990-209">x12 协议</span><span class="sxs-lookup"><span data-stu-id="87990-209">For X12 agreement</span></span>|[<span data-ttu-id="87990-210">配置 X12 特定协议属性</span><span class="sxs-lookup"><span data-stu-id="87990-210">Configuring X12-Specific Agreement Properties</span></span>](../core/configuring-x12-specific-agreement-properties.md)|  
    |<span data-ttu-id="87990-211">EDIFACT 协议</span><span class="sxs-lookup"><span data-stu-id="87990-211">For EDIFACT agreement</span></span>|[<span data-ttu-id="87990-212">配置 EDIFACT 特定协议属性</span><span class="sxs-lookup"><span data-stu-id="87990-212">Configuring EDIFACT-Specific Agreement Properties</span></span>](../core/configuring-edifact-specific-agreement-properties.md)|  
    |<span data-ttu-id="87990-213">AS2 协议</span><span class="sxs-lookup"><span data-stu-id="87990-213">For AS2 agreement</span></span>|[<span data-ttu-id="87990-214">配置 AS2 协议属性</span><span class="sxs-lookup"><span data-stu-id="87990-214">Configuring AS2 Agreement Properties</span></span>](../core/configuring-as2-agreement-properties.md)|  
  
5.  <span data-ttu-id="87990-215">选择**应用**接受属性，或选择**确定**完成的配置设置。</span><span class="sxs-lookup"><span data-stu-id="87990-215">Select **Apply** to accept the properties, or select **OK** to complete the configuration setting.</span></span> <span data-ttu-id="87990-216">以上任一操作验证的设置。</span><span class="sxs-lookup"><span data-stu-id="87990-216">Either action validates the settings.</span></span> 

## <a name="enable-or-disable-an-agreement"></a><span data-ttu-id="87990-217">启用或禁用协议</span><span class="sxs-lookup"><span data-stu-id="87990-217">Enable or disable an agreement</span></span>  
  
1.  <span data-ttu-id="87990-218">在**BizTalk Server 管理**，选择**方**。</span><span class="sxs-lookup"><span data-stu-id="87990-218">In **BizTalk Server Administration**, select **Parties**.</span></span> 

2. <span data-ttu-id="87990-219">在**方和业务配置文件**页上，选择任何具有你想要编辑的协议的两个业务配置文件。</span><span class="sxs-lookup"><span data-stu-id="87990-219">In the **Parties and Business Profiles** page, select any of the two business profile that have the agreement that you want to edit.</span></span>  
  
3.  <span data-ttu-id="87990-220">在**协议**部分，右键单击该协议，然后选择**启用**或**禁用**。</span><span class="sxs-lookup"><span data-stu-id="87990-220">In the **Agreements** section, right-click the agreement, and then select **Enable** or **Disable**.</span></span> 
  
    > [!NOTE]
    >  <span data-ttu-id="87990-221">当首次创建一个协议时，默认情况下将始终启用。</span><span class="sxs-lookup"><span data-stu-id="87990-221">When an agreement is first created, it is always enabled by default.</span></span> <span data-ttu-id="87990-222">**启用**选项仅在禁用协议时才可用。</span><span class="sxs-lookup"><span data-stu-id="87990-222">The **Enable** option is available only when the agreement is disabled.</span></span> <span data-ttu-id="87990-223">**禁用**选项仅在启用该协议时才可用。</span><span class="sxs-lookup"><span data-stu-id="87990-223">The **Disable** option is available only when the agreement is enabled.</span></span>  

## <a name="delete-an-agreement"></a><span data-ttu-id="87990-224">删除协议</span><span class="sxs-lookup"><span data-stu-id="87990-224">Delete an agreement</span></span>  
1.  <span data-ttu-id="87990-225">在**BizTalk Server 管理**，选择**方**。</span><span class="sxs-lookup"><span data-stu-id="87990-225">In **BizTalk Server Administration**, select **Parties**.</span></span> 
  
2.  <span data-ttu-id="87990-226">在**方和业务配置文件**页上，选择任何具有你想要删除的协议的两个业务配置文件。</span><span class="sxs-lookup"><span data-stu-id="87990-226">In the **Parties and Business Profiles** page, select any of the two business profile that have the agreement that you want to delete.</span></span>  
  
3.  <span data-ttu-id="87990-227">在**协议**部分中，右键单击你想要删除，然后选择协议**删除**。</span><span class="sxs-lookup"><span data-stu-id="87990-227">In the **Agreements** section, right-click the agreement that you want to delete, and then select **Delete**.</span></span>  
  
4.  <span data-ttu-id="87990-228">在**确认删除协议**对话框中，选择**是**若要删除的协议。</span><span class="sxs-lookup"><span data-stu-id="87990-228">In the **Confirm delete agreement** dialog box, select **Yes** to delete the agreement.</span></span>  

      
## <a name="see-also"></a><span data-ttu-id="87990-229">另请参阅</span><span class="sxs-lookup"><span data-stu-id="87990-229">See Also</span></span>  
 [<span data-ttu-id="87990-230">管理 EDI 和 AS2 解决方案</span><span class="sxs-lookup"><span data-stu-id="87990-230">Managing EDI and AS2 Solutions</span></span>](../core/managing-edi-and-as2-solutions.md)