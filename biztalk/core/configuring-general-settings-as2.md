---
title: "配置常规设置 (AS2) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8592c52e-5156-418c-9c49-7478f73c372e
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23ff62f90f14238f7834312ab909a137d49bcbab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-general-settings-as2"></a><span data-ttu-id="86fef-102">配置常规设置（AS2）</span><span class="sxs-lookup"><span data-stu-id="86fef-102">Configuring General Settings (AS2)</span></span>
<span data-ttu-id="86fef-103">作为常规设置的一部分，您可以指定协议名称、将使用的协议 (AS2)、协议的参与方和配置文件，以及是否为所有通过此协议处理的消息启用报告功能。 </span><span class="sxs-lookup"><span data-stu-id="86fef-103">As part of the general settings, you specify agreement name, the protocol it will use (AS2), the parties and profiles that the agreement is between, and whether to have reporting enabled for all messages processed through the agreement.</span></span> <span data-ttu-id="86fef-104">作为协议的一部分，还可以指定参与方联系信息。</span><span class="sxs-lookup"><span data-stu-id="86fef-104">You can also specify the party contact information as part of the agreement.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="86fef-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="86fef-105">Prerequisites</span></span>  
 <span data-ttu-id="86fef-106">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="86fef-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-general-agreement-settings"></a><span data-ttu-id="86fef-107">若要配置常规协议设置，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="86fef-107">To configure general agreement settings</span></span>  
  
1.  <span data-ttu-id="86fef-108">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**在控制台树中，然后在**方和业务配置文件**页上，右键单击业务配置文件，必须为协议的一部分，要创建，指向**新建**，然后单击**协议**。</span><span class="sxs-lookup"><span data-stu-id="86fef-108">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, click **Parties** in the console tree, and in the **Parties and Business Profiles** page, right-click a business profile that must be part of the agreement that you are creating, point to **New**, and then click **Agreement**.</span></span>  
  
2.  <span data-ttu-id="86fef-109">下表列出了不同的属性以及要为中的属性指定的值**常规属性**页。</span><span class="sxs-lookup"><span data-stu-id="86fef-109">The following tables list the different properties and the values to be specified for the properties in the **General Properties** page.</span></span>  
  
    1.  <span data-ttu-id="86fef-110">在**协议参数**部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="86fef-110">In the **Agreement Parameters** section, do the following:</span></span>  
  
        |<span data-ttu-id="86fef-111">使用此选项</span><span class="sxs-lookup"><span data-stu-id="86fef-111">Use this</span></span>|<span data-ttu-id="86fef-112">执行的操作</span><span class="sxs-lookup"><span data-stu-id="86fef-112">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="86fef-113">**名称**</span><span class="sxs-lookup"><span data-stu-id="86fef-113">**Name**</span></span>|<span data-ttu-id="86fef-114">指定此协议的名称</span><span class="sxs-lookup"><span data-stu-id="86fef-114">Specify a name for the agreement</span></span>|  
        |<span data-ttu-id="86fef-115">**ID**</span><span class="sxs-lookup"><span data-stu-id="86fef-115">**ID**</span></span>|<span data-ttu-id="86fef-116">列出该协议的唯一标识。</span><span class="sxs-lookup"><span data-stu-id="86fef-116">Lists unique identification for the agreement.</span></span> <span data-ttu-id="86fef-117">此文本框不可编辑，并在您单击后将显示协议 ID**应用**接受的第一个时间和设置。</span><span class="sxs-lookup"><span data-stu-id="86fef-117">This text box is not editable and will display the agreement ID after you click **Apply** for the first time and settings are accepted.</span></span>|  
        |<span data-ttu-id="86fef-118">**状态**</span><span class="sxs-lookup"><span data-stu-id="86fef-118">**Status**</span></span>|<span data-ttu-id="86fef-119">指定协议的状态。</span><span class="sxs-lookup"><span data-stu-id="86fef-119">Specifies the status of the agreement.</span></span> <span data-ttu-id="86fef-120">默认情况下，在创建协议**Active**状态。</span><span class="sxs-lookup"><span data-stu-id="86fef-120">By default, an agreement is created in an **Active** state.</span></span> <span data-ttu-id="86fef-121">如果你想协议时首先创建，选择要禁用**禁用**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="86fef-121">If you want the agreement to be disabled when it is first created, select **Disabled** from the drop-down list.</span></span>|  
        |<span data-ttu-id="86fef-122">**协议**</span><span class="sxs-lookup"><span data-stu-id="86fef-122">**Protocol**</span></span>|<span data-ttu-id="86fef-123">指定该协议的协议。</span><span class="sxs-lookup"><span data-stu-id="86fef-123">Specifies the protocol for the agreement.</span></span> <span data-ttu-id="86fef-124">对于 AS2 传输协议，选择**AS2**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="86fef-124">For an AS2 transport protocol, select **AS2** from the drop-down list.</span></span>|  
  
    2.  <span data-ttu-id="86fef-125">在**第一个合作伙伴**部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="86fef-125">In the **First Partner** section, do the following:</span></span>  
  
        |<span data-ttu-id="86fef-126">使用此选项</span><span class="sxs-lookup"><span data-stu-id="86fef-126">Use this</span></span>|<span data-ttu-id="86fef-127">执行的操作</span><span class="sxs-lookup"><span data-stu-id="86fef-127">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="86fef-128">**名称**</span><span class="sxs-lookup"><span data-stu-id="86fef-128">**Name**</span></span>|<span data-ttu-id="86fef-129">显示具有要为其创建协议的业务配置文件的合作伙伴名称。</span><span class="sxs-lookup"><span data-stu-id="86fef-129">Displays the partner name that has the business profile for which you are creating the agreement.</span></span> <span data-ttu-id="86fef-130">此文本框不可编辑。</span><span class="sxs-lookup"><span data-stu-id="86fef-130">This text box is not editable.</span></span>|  
        |<span data-ttu-id="86fef-131">**配置文件**</span><span class="sxs-lookup"><span data-stu-id="86fef-131">**Profile**</span></span>|<span data-ttu-id="86fef-132">显示要为其创建协议的配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="86fef-132">Displays the name of the profile for which you are creating the agreement.</span></span> <span data-ttu-id="86fef-133">此文本框不可编辑。</span><span class="sxs-lookup"><span data-stu-id="86fef-133">This text box is not editable.</span></span>|  
        |<span data-ttu-id="86fef-134">**协议设置**</span><span class="sxs-lookup"><span data-stu-id="86fef-134">**Protocol Set**</span></span>|<span data-ttu-id="86fef-135">如果您创建了一个 AS2 协议集作为业务配置文件的一部分，则可从下拉列表中选择该协议集。</span><span class="sxs-lookup"><span data-stu-id="86fef-135">If you created an AS2 protocol set as part of the business profile, you can select that from the drop-down list.</span></span> <span data-ttu-id="86fef-136">如果未创建 AS2 协议集作为业务配置文件的一部分，则可保留为空白。</span><span class="sxs-lookup"><span data-stu-id="86fef-136">If you did not create an AS2 protocol set as part of the business profile, you can leave this empty.</span></span>|  
  
    3.  <span data-ttu-id="86fef-137">在**第二个合作伙伴**部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="86fef-137">In the **Second Partner** section, do the following:</span></span>  
  
        |<span data-ttu-id="86fef-138">使用此选项</span><span class="sxs-lookup"><span data-stu-id="86fef-138">Use this</span></span>|<span data-ttu-id="86fef-139">执行的操作</span><span class="sxs-lookup"><span data-stu-id="86fef-139">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="86fef-140">**名称**</span><span class="sxs-lookup"><span data-stu-id="86fef-140">**Name**</span></span>|<span data-ttu-id="86fef-141">从下拉列表中选择具有您希望用其创建协议的业务配置文件的参与方。</span><span class="sxs-lookup"><span data-stu-id="86fef-141">From the drop-down select a party that has the business profile with which you want to create an agreement.</span></span>|  
        |<span data-ttu-id="86fef-142">**配置文件**</span><span class="sxs-lookup"><span data-stu-id="86fef-142">**Profile**</span></span>|<span data-ttu-id="86fef-143">从下拉列表中选择您要通过其创建协议的简介。</span><span class="sxs-lookup"><span data-stu-id="86fef-143">From the drop-down select a profile with which you want to create an agreement.</span></span>|  
        |<span data-ttu-id="86fef-144">**协议设置**</span><span class="sxs-lookup"><span data-stu-id="86fef-144">**Protocol Set**</span></span>|<span data-ttu-id="86fef-145">如果您创建了一个 AS2 协议集作为业务配置文件的一部分，则可从下拉列表中选择该协议集。</span><span class="sxs-lookup"><span data-stu-id="86fef-145">If you created an AS2 protocol set as part of the business profile, you can select that from the drop-down list.</span></span> <span data-ttu-id="86fef-146">如果未创建 AS2 协议集作为业务配置文件的一部分，则可保留为空白。</span><span class="sxs-lookup"><span data-stu-id="86fef-146">If you did not create an AS2 protocol set as part of the business profile, you can leave this empty.</span></span>|  
  
        > [!TIP]
        >  <span data-ttu-id="86fef-147">按`CTRL`，选择将为协议的一部分，右键单击任一业务配置文件，指向的业务配置文件**新建**，然后单击**协议**。</span><span class="sxs-lookup"><span data-stu-id="86fef-147">Press `CTRL`, select the business profiles that will be part of the agreement, right-click either business profile, point to **New**, and then click **Agreement**.</span></span> <span data-ttu-id="86fef-148">值的合作伙伴名称，这两个合作伙伴的业务配置文件将自动填充在**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="86fef-148">The values for partner name and business profiles for both the partners will be automatically populated in the **Agreement Properties** dialog box.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="86fef-149">一旦你选择的其他配置文件，添加两个选项卡旁边**常规**选项卡。每个选项卡都代表参与双方之间的一个单向 AS2 协议。</span><span class="sxs-lookup"><span data-stu-id="86fef-149">As soon as you select the other profile, two tabs are added next to the **General** tab. Each tab represents a one-way AS2 agreement between the two parties.</span></span> <span data-ttu-id="86fef-150">您可以使用这些选项卡来指定选项卡中的与交换和事务集相关的设置。</span><span class="sxs-lookup"><span data-stu-id="86fef-150">You use the tabs to specify interchange and transaction set related settings in the tabs.</span></span>  
  
    4.  <span data-ttu-id="86fef-151">选择**启用协议**复选框以启用该协议并执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="86fef-151">Select the **Enable Agreement** check box to enable the agreement and do the following:</span></span>  
  
        |<span data-ttu-id="86fef-152">使用此选项</span><span class="sxs-lookup"><span data-stu-id="86fef-152">Use this</span></span>|<span data-ttu-id="86fef-153">执行的操作</span><span class="sxs-lookup"><span data-stu-id="86fef-153">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="86fef-154">**From**</span><span class="sxs-lookup"><span data-stu-id="86fef-154">**From**</span></span>|<span data-ttu-id="86fef-155">选址协议的有效期起始日期和时间。</span><span class="sxs-lookup"><span data-stu-id="86fef-155">Select the date and time from which the agreement will be valid.</span></span>|  
        |<span data-ttu-id="86fef-156">**无结束日期**</span><span class="sxs-lookup"><span data-stu-id="86fef-156">**No End Date**</span></span>|<span data-ttu-id="86fef-157">如果您不希望设置禁用协议的结束日期，则选择该选项。</span><span class="sxs-lookup"><span data-stu-id="86fef-157">Select this option if you do not want to set an end date when the agreement is disabled.</span></span>|  
        |<span data-ttu-id="86fef-158">**结束日期**</span><span class="sxs-lookup"><span data-stu-id="86fef-158">**End By**</span></span>|<span data-ttu-id="86fef-159">选择该选项并指定协议有效的结束日期和时间。</span><span class="sxs-lookup"><span data-stu-id="86fef-159">Select this option and specify the date and time until which the agreement will be valid.</span></span>|  
  
    5.  <span data-ttu-id="86fef-160">在**常见主机设置**部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="86fef-160">In the **Common Host Settings** section, do the following:</span></span>  
  
        |<span data-ttu-id="86fef-161">使用此选项</span><span class="sxs-lookup"><span data-stu-id="86fef-161">Use this</span></span>|<span data-ttu-id="86fef-162">执行的操作</span><span class="sxs-lookup"><span data-stu-id="86fef-162">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="86fef-163">**打开报表**</span><span class="sxs-lookup"><span data-stu-id="86fef-163">**Turn ON reporting**</span></span>|<span data-ttu-id="86fef-164">若要显示中的所有 AS2 消息 （传入和传出） 的状态条目**AS2 消息和相关 MDN 状态**选项卡**组概述**窗格中的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="86fef-164">to display status entries for all AS2 messages (incoming and outgoing) in the **AS2 Message and Correlated MDN Status** tab of the **Group Overview** pane in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="86fef-165">如果清除此项，则不会显示任何状态项</span><span class="sxs-lookup"><span data-stu-id="86fef-165">If cleared, no status entries will be displayed</span></span>|  
  
3.  <span data-ttu-id="86fef-166">在**常规**选项卡上，在**联系人信息**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="86fef-166">In the **General** tab, on the **Contact Information** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="86fef-167">在**Contact1**选项卡上，输入要与其创建协议的参与方的配置文件的联系信息。</span><span class="sxs-lookup"><span data-stu-id="86fef-167">In the **Contact1** tab, enter the contact information for the party’s profile with which you are creating an agreement.</span></span> <span data-ttu-id="86fef-168">此数据仅供参考；BizTalk 运行时不会使用此数据。</span><span class="sxs-lookup"><span data-stu-id="86fef-168">This data is for information purposes only; it will not be used by the BizTalk Runtime.</span></span>  
  
    2.  <span data-ttu-id="86fef-169">若要添加的联系人的另一个选项卡，单击**新联系人**选项卡。</span><span class="sxs-lookup"><span data-stu-id="86fef-169">To add another tab for contact, click the **New Contact** tab.</span></span>  
  
    3.  <span data-ttu-id="86fef-170">若要删除的联系人的选项卡，单击**删除**从选项卡页右上角。</span><span class="sxs-lookup"><span data-stu-id="86fef-170">To delete a contact tab, click **Delete** from the top right corner of the tab page.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="86fef-171">无法删除**Contact1**选项卡。只能删除您添加的新选项卡。</span><span class="sxs-lookup"><span data-stu-id="86fef-171">You cannot delete the **Contact1** tab. You can only delete the new tabs that you add.</span></span>  
  
4.  <span data-ttu-id="86fef-172">在**常规**选项卡上，在**其他属性**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="86fef-172">In the **General** tab, on the **Additional Properties** page, do the following:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="86fef-173">BizTalk Server 未使用此页上指定的信息进行任何处理；此数据仅供参考。</span><span class="sxs-lookup"><span data-stu-id="86fef-173">The information you specify on this page is not used by the BizTalk Server for any processing; this data is for information purposes only.</span></span>  
  
    1.  <span data-ttu-id="86fef-174">在**其他属性**网格中，输入你想要添加的任何信息相关的方或协议的名称-值对。</span><span class="sxs-lookup"><span data-stu-id="86fef-174">In the **Additional Properties** grid, enter name-value pairs for any information that you want to add related to the party or agreement.</span></span>  <span data-ttu-id="86fef-175">输入一个名称/值对以存储有关参与方的任何信息。</span><span class="sxs-lookup"><span data-stu-id="86fef-175">Enter a name-value pair to store any information about the party.</span></span> <span data-ttu-id="86fef-176">可以根据需要添加任意数量的名称/值对。</span><span class="sxs-lookup"><span data-stu-id="86fef-176">You can add as many name-value pairs as you want.</span></span>  
  
         <span data-ttu-id="86fef-177">若要删除的名称-值对，选择行，然后单击**删除**从右上角。</span><span class="sxs-lookup"><span data-stu-id="86fef-177">To delete a name-value pair, select the row and click **Delete** from the top-right corner.</span></span>  
  
    2.  <span data-ttu-id="86fef-178">在**文本 1**，**文本 2**，和**协议**文本框中，输入关于与方协议的信息。</span><span class="sxs-lookup"><span data-stu-id="86fef-178">In the **Text 1**, **Text 2**, and **Agreement** text boxes, enter information about the agreement with a party.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="86fef-179">如果你单击**确定**或**应用**此页中提供的所有值列出后，你将收到错误。</span><span class="sxs-lookup"><span data-stu-id="86fef-179">If you click **OK** or **Apply** after providing all the values listed in this page, you will get an error.</span></span> <span data-ttu-id="86fef-180">这是因为还未提供创建协议的必需值。</span><span class="sxs-lookup"><span data-stu-id="86fef-180">That is because the mandatory values to create an agreement are not yet provided.</span></span> <span data-ttu-id="86fef-181">这些是 AS2-从到 AS2-上的值**标识符**的每个单向协议选项卡页。</span><span class="sxs-lookup"><span data-stu-id="86fef-181">These are AS2-From to AS2-To values on the **Identifiers** page of each one-way agreement tab.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="86fef-182">后续步骤</span><span class="sxs-lookup"><span data-stu-id="86fef-182">Next Steps</span></span>  
 <span data-ttu-id="86fef-183">现在您必须为协议配置标识符设置。</span><span class="sxs-lookup"><span data-stu-id="86fef-183">You must now configure the identifier settings for the agreement.</span></span> <span data-ttu-id="86fef-184">有关说明，请参阅[配置标识符 (AS2)](../core/configuring-identifiers-as2.md)。</span><span class="sxs-lookup"><span data-stu-id="86fef-184">For instructions see [Configuring Identifiers (AS2)](../core/configuring-identifiers-as2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86fef-185">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86fef-185">See Also</span></span>  
 [<span data-ttu-id="86fef-186">配置 AS2 协议属性</span><span class="sxs-lookup"><span data-stu-id="86fef-186">Configuring AS2 Agreement Properties</span></span>](../core/configuring-as2-agreement-properties.md)