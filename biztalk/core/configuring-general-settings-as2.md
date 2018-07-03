---
title: 配置常规设置 (AS2) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8592c52e-5156-418c-9c49-7478f73c372e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20a0fa1ea7e9a3c6462f09eddee564850c4820dd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001446"
---
# <a name="configuring-general-settings-as2"></a><span data-ttu-id="3d963-102">配置常规设置（AS2）</span><span class="sxs-lookup"><span data-stu-id="3d963-102">Configuring General Settings (AS2)</span></span>
<span data-ttu-id="3d963-103">作为常规设置的一部分，您可以指定协议名称、将使用的协议 (AS2)、协议的参与方和配置文件，以及是否为所有通过此协议处理的消息启用报告功能。 </span><span class="sxs-lookup"><span data-stu-id="3d963-103">As part of the general settings, you specify agreement name, the protocol it will use (AS2), the parties and profiles that the agreement is between, and whether to have reporting enabled for all messages processed through the agreement.</span></span> <span data-ttu-id="3d963-104">作为协议的一部分，还可以指定参与方联系信息。</span><span class="sxs-lookup"><span data-stu-id="3d963-104">You can also specify the party contact information as part of the agreement.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="3d963-105">必要條件</span><span class="sxs-lookup"><span data-stu-id="3d963-105">Prerequisites</span></span>  
 <span data-ttu-id="3d963-106">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="3d963-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  

### <a name="to-configure-general-agreement-settings"></a><span data-ttu-id="3d963-107">若要配置常规协议设置，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3d963-107">To configure general agreement settings</span></span>  

1. <span data-ttu-id="3d963-108">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**在控制台树中，然后在**参与方和业务配置文件**页上，右键单击业务配置文件必须为协议的一部分，要创建、 指向**新建**，然后单击**协议**。</span><span class="sxs-lookup"><span data-stu-id="3d963-108">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, click **Parties** in the console tree, and in the **Parties and Business Profiles** page, right-click a business profile that must be part of the agreement that you are creating, point to **New**, and then click **Agreement**.</span></span>  

2. <span data-ttu-id="3d963-109">下表列出了不同的属性以及要为属性中指定的值**常规属性**页。</span><span class="sxs-lookup"><span data-stu-id="3d963-109">The following tables list the different properties and the values to be specified for the properties in the **General Properties** page.</span></span>  

   1. <span data-ttu-id="3d963-110">在中**协议参数**部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3d963-110">In the **Agreement Parameters** section, do the following:</span></span>  


      |   <span data-ttu-id="3d963-111">使用此选项</span><span class="sxs-lookup"><span data-stu-id="3d963-111">Use this</span></span>   |                                                                                                     <span data-ttu-id="3d963-112">执行的操作</span><span class="sxs-lookup"><span data-stu-id="3d963-112">To do this</span></span>                                                                                                     |
      |--------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
      |   <span data-ttu-id="3d963-113">**名称**</span><span class="sxs-lookup"><span data-stu-id="3d963-113">**Name**</span></span>   |                                                                                          <span data-ttu-id="3d963-114">指定此协议的名称</span><span class="sxs-lookup"><span data-stu-id="3d963-114">Specify a name for the agreement</span></span>                                                                                          |
      |    <span data-ttu-id="3d963-115">**ID**</span><span class="sxs-lookup"><span data-stu-id="3d963-115">**ID**</span></span>    |               <span data-ttu-id="3d963-116">列出该协议的唯一标识。</span><span class="sxs-lookup"><span data-stu-id="3d963-116">Lists unique identification for the agreement.</span></span> <span data-ttu-id="3d963-117">此文本框不可编辑，并在单击后将显示协议 ID**应用**接受的第一个的时间和设置。</span><span class="sxs-lookup"><span data-stu-id="3d963-117">This text box is not editable and will display the agreement ID after you click **Apply** for the first time and settings are accepted.</span></span>               |
      |  <span data-ttu-id="3d963-118">**“状态”**</span><span class="sxs-lookup"><span data-stu-id="3d963-118">**Status**</span></span>  | <span data-ttu-id="3d963-119">指定协议的状态。</span><span class="sxs-lookup"><span data-stu-id="3d963-119">Specifies the status of the agreement.</span></span> <span data-ttu-id="3d963-120">默认情况下，在创建协议**Active**状态。</span><span class="sxs-lookup"><span data-stu-id="3d963-120">By default, an agreement is created in an **Active** state.</span></span> <span data-ttu-id="3d963-121">如果希望协议时首先创建，选择要禁用**禁用**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="3d963-121">If you want the agreement to be disabled when it is first created, select **Disabled** from the drop-down list.</span></span> |
      | <span data-ttu-id="3d963-122">**协议**</span><span class="sxs-lookup"><span data-stu-id="3d963-122">**Protocol**</span></span> |                                                  <span data-ttu-id="3d963-123">指定该协议的协议。</span><span class="sxs-lookup"><span data-stu-id="3d963-123">Specifies the protocol for the agreement.</span></span> <span data-ttu-id="3d963-124">对于 AS2 传输协议，选择**AS2**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="3d963-124">For an AS2 transport protocol, select **AS2** from the drop-down list.</span></span>                                                  |


   2. <span data-ttu-id="3d963-125">在中**第一个合作伙伴**部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3d963-125">In the **First Partner** section, do the following:</span></span>  


      |     <span data-ttu-id="3d963-126">使用此选项</span><span class="sxs-lookup"><span data-stu-id="3d963-126">Use this</span></span>     |                                                                                                      <span data-ttu-id="3d963-127">执行的操作</span><span class="sxs-lookup"><span data-stu-id="3d963-127">To do this</span></span>                                                                                                       |
      |------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
      |     <span data-ttu-id="3d963-128">**名称**</span><span class="sxs-lookup"><span data-stu-id="3d963-128">**Name**</span></span>     |                                           <span data-ttu-id="3d963-129">显示具有要为其创建协议的业务配置文件的合作伙伴名称。</span><span class="sxs-lookup"><span data-stu-id="3d963-129">Displays the partner name that has the business profile for which you are creating the agreement.</span></span> <span data-ttu-id="3d963-130">此文本框不可编辑。</span><span class="sxs-lookup"><span data-stu-id="3d963-130">This text box is not editable.</span></span>                                            |
      |   <span data-ttu-id="3d963-131">**配置文件**</span><span class="sxs-lookup"><span data-stu-id="3d963-131">**Profile**</span></span>    |                                                       <span data-ttu-id="3d963-132">显示要为其创建协议的配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="3d963-132">Displays the name of the profile for which you are creating the agreement.</span></span> <span data-ttu-id="3d963-133">此文本框不可编辑。</span><span class="sxs-lookup"><span data-stu-id="3d963-133">This text box is not editable.</span></span>                                                       |
      | <span data-ttu-id="3d963-134">**协议集**</span><span class="sxs-lookup"><span data-stu-id="3d963-134">**Protocol Set**</span></span> | <span data-ttu-id="3d963-135">如果您创建了一个 AS2 协议集作为业务配置文件的一部分，则可从下拉列表中选择该协议集。</span><span class="sxs-lookup"><span data-stu-id="3d963-135">If you created an AS2 protocol set as part of the business profile, you can select that from the drop-down list.</span></span> <span data-ttu-id="3d963-136">如果未创建 AS2 协议集作为业务配置文件的一部分，则可保留为空白。</span><span class="sxs-lookup"><span data-stu-id="3d963-136">If you did not create an AS2 protocol set as part of the business profile, you can leave this empty.</span></span> |


   3. <span data-ttu-id="3d963-137">在中**第二个合作伙伴**部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3d963-137">In the **Second Partner** section, do the following:</span></span>  

      |<span data-ttu-id="3d963-138">使用此选项</span><span class="sxs-lookup"><span data-stu-id="3d963-138">Use this</span></span>|<span data-ttu-id="3d963-139">执行的操作</span><span class="sxs-lookup"><span data-stu-id="3d963-139">To do this</span></span>|  
      |--------------|----------------|  
      |<span data-ttu-id="3d963-140">**名称**</span><span class="sxs-lookup"><span data-stu-id="3d963-140">**Name**</span></span>|<span data-ttu-id="3d963-141">从下拉列表中选择具有您希望用其创建协议的业务配置文件的参与方。</span><span class="sxs-lookup"><span data-stu-id="3d963-141">From the drop-down select a party that has the business profile with which you want to create an agreement.</span></span>|  
      |<span data-ttu-id="3d963-142">**配置文件**</span><span class="sxs-lookup"><span data-stu-id="3d963-142">**Profile**</span></span>|<span data-ttu-id="3d963-143">从下拉列表中选择您要通过其创建协议的简介。</span><span class="sxs-lookup"><span data-stu-id="3d963-143">From the drop-down select a profile with which you want to create an agreement.</span></span>|  
      |<span data-ttu-id="3d963-144">**协议集**</span><span class="sxs-lookup"><span data-stu-id="3d963-144">**Protocol Set**</span></span>|<span data-ttu-id="3d963-145">如果您创建了一个 AS2 协议集作为业务配置文件的一部分，则可从下拉列表中选择该协议集。</span><span class="sxs-lookup"><span data-stu-id="3d963-145">If you created an AS2 protocol set as part of the business profile, you can select that from the drop-down list.</span></span> <span data-ttu-id="3d963-146">如果未创建 AS2 协议集作为业务配置文件的一部分，则可保留为空白。</span><span class="sxs-lookup"><span data-stu-id="3d963-146">If you did not create an AS2 protocol set as part of the business profile, you can leave this empty.</span></span>|  

      > [!TIP]
      >  <span data-ttu-id="3d963-147">按`CTRL`，选择的业务配置文件，将为协议的一部分，右键单击业务配置文件，指向**新建**，然后单击**协议**。</span><span class="sxs-lookup"><span data-stu-id="3d963-147">Press `CTRL`, select the business profiles that will be part of the agreement, right-click either business profile, point to **New**, and then click **Agreement**.</span></span> <span data-ttu-id="3d963-148">值的合作伙伴名称，适用于这两个合作伙伴的业务配置文件将在自动填充**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="3d963-148">The values for partner name and business profiles for both the partners will be automatically populated in the **Agreement Properties** dialog box.</span></span>  

      > [!NOTE]
      >  <span data-ttu-id="3d963-149">一旦您选择其他配置文件，旁边添加两个选项卡**常规**选项卡。每个选项卡都代表参与双方之间的一个单向 AS2 协议。</span><span class="sxs-lookup"><span data-stu-id="3d963-149">As soon as you select the other profile, two tabs are added next to the **General** tab. Each tab represents a one-way AS2 agreement between the two parties.</span></span> <span data-ttu-id="3d963-150">您可以使用这些选项卡来指定选项卡中的与交换和事务集相关的设置。</span><span class="sxs-lookup"><span data-stu-id="3d963-150">You use the tabs to specify interchange and transaction set related settings in the tabs.</span></span>  

   4. <span data-ttu-id="3d963-151">选择**启用协议**复选框可启用该协议并执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3d963-151">Select the **Enable Agreement** check box to enable the agreement and do the following:</span></span>  


      |    <span data-ttu-id="3d963-152">使用此选项</span><span class="sxs-lookup"><span data-stu-id="3d963-152">Use this</span></span>     |                                        <span data-ttu-id="3d963-153">执行的操作</span><span class="sxs-lookup"><span data-stu-id="3d963-153">To do this</span></span>                                         |
      |-----------------|-------------------------------------------------------------------------------------------|
      |    <span data-ttu-id="3d963-154">**From**</span><span class="sxs-lookup"><span data-stu-id="3d963-154">**From**</span></span>     |             <span data-ttu-id="3d963-155">选址协议的有效期起始日期和时间。</span><span class="sxs-lookup"><span data-stu-id="3d963-155">Select the date and time from which the agreement will be valid.</span></span>              |
      | <span data-ttu-id="3d963-156">**无结束日期**</span><span class="sxs-lookup"><span data-stu-id="3d963-156">**No End Date**</span></span> | <span data-ttu-id="3d963-157">如果您不希望设置禁用协议的结束日期，则选择该选项。</span><span class="sxs-lookup"><span data-stu-id="3d963-157">Select this option if you do not want to set an end date when the agreement is disabled.</span></span>  |
      |   <span data-ttu-id="3d963-158">**结束的步骤**</span><span class="sxs-lookup"><span data-stu-id="3d963-158">**End By**</span></span>    | <span data-ttu-id="3d963-159">选择该选项并指定协议有效的结束日期和时间。</span><span class="sxs-lookup"><span data-stu-id="3d963-159">Select this option and specify the date and time until which the agreement will be valid.</span></span> |


   5. <span data-ttu-id="3d963-160">在中**公用主机设置**部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3d963-160">In the **Common Host Settings** section, do the following:</span></span>  


      |       <span data-ttu-id="3d963-161">使用此选项</span><span class="sxs-lookup"><span data-stu-id="3d963-161">Use this</span></span>        |                                                                                                                                                          <span data-ttu-id="3d963-162">执行的操作</span><span class="sxs-lookup"><span data-stu-id="3d963-162">To do this</span></span>                                                                                                                                                          |
      |-----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
      | <span data-ttu-id="3d963-163">**打开报告**</span><span class="sxs-lookup"><span data-stu-id="3d963-163">**Turn ON reporting**</span></span> | <span data-ttu-id="3d963-164">若要显示中的所有 AS2 消息 （传入和传出） 的状态条目**AS2 消息和相关 MDN 状态**选项卡**组概述**窗格中的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="3d963-164">to display status entries for all AS2 messages (incoming and outgoing) in the **AS2 Message and Correlated MDN Status** tab of the **Group Overview** pane in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="3d963-165">如果清除此项，则不会显示任何状态项</span><span class="sxs-lookup"><span data-stu-id="3d963-165">If cleared, no status entries will be displayed</span></span> |


3. <span data-ttu-id="3d963-166">在中**常规**选项卡中，**联系人信息**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3d963-166">In the **General** tab, on the **Contact Information** page, do the following:</span></span>  

   1.  <span data-ttu-id="3d963-167">在中**联系人 1**选项卡上，输入用于创建协议的参与方的配置文件的联系信息。</span><span class="sxs-lookup"><span data-stu-id="3d963-167">In the **Contact1** tab, enter the contact information for the party’s profile with which you are creating an agreement.</span></span> <span data-ttu-id="3d963-168">此数据仅供参考；BizTalk 运行时不会使用此数据。</span><span class="sxs-lookup"><span data-stu-id="3d963-168">This data is for information purposes only; it will not be used by the BizTalk Runtime.</span></span>  

   2.  <span data-ttu-id="3d963-169">若要添加的联系人的另一个选项卡，单击**新建联系人**选项卡。</span><span class="sxs-lookup"><span data-stu-id="3d963-169">To add another tab for contact, click the **New Contact** tab.</span></span>  

   3.  <span data-ttu-id="3d963-170">若要删除联系人选项卡上，单击**删除**从选项卡页的右上角。</span><span class="sxs-lookup"><span data-stu-id="3d963-170">To delete a contact tab, click **Delete** from the top right corner of the tab page.</span></span>  

       > [!NOTE]
       >  <span data-ttu-id="3d963-171">不能删除**联系人 1**选项卡。只能删除您添加的新选项卡。</span><span class="sxs-lookup"><span data-stu-id="3d963-171">You cannot delete the **Contact1** tab. You can only delete the new tabs that you add.</span></span>  

4. <span data-ttu-id="3d963-172">在中**常规**选项卡中，**其他属性**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3d963-172">In the **General** tab, on the **Additional Properties** page, do the following:</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="3d963-173">BizTalk Server 未使用此页上指定的信息进行任何处理；此数据仅供参考。</span><span class="sxs-lookup"><span data-stu-id="3d963-173">The information you specify on this page is not used by the BizTalk Server for any processing; this data is for information purposes only.</span></span>  

   1.  <span data-ttu-id="3d963-174">在中**附加属性**网格中，输入你想要添加的任何信息相关的参与方或协议的名称 / 值对。</span><span class="sxs-lookup"><span data-stu-id="3d963-174">In the **Additional Properties** grid, enter name-value pairs for any information that you want to add related to the party or agreement.</span></span>  <span data-ttu-id="3d963-175">输入一个名称/值对以存储有关参与方的任何信息。</span><span class="sxs-lookup"><span data-stu-id="3d963-175">Enter a name-value pair to store any information about the party.</span></span> <span data-ttu-id="3d963-176">可以根据需要添加任意数量的名称/值对。</span><span class="sxs-lookup"><span data-stu-id="3d963-176">You can add as many name-value pairs as you want.</span></span>  

        <span data-ttu-id="3d963-177">若要删除的名称-值对，选择的行，然后单击**删除**从右上角。</span><span class="sxs-lookup"><span data-stu-id="3d963-177">To delete a name-value pair, select the row and click **Delete** from the top-right corner.</span></span>  

   2.  <span data-ttu-id="3d963-178">在中**文本 1**，**文本 2**，并**协议**文本框中，输入有关与参与方协议的信息。</span><span class="sxs-lookup"><span data-stu-id="3d963-178">In the **Text 1**, **Text 2**, and **Agreement** text boxes, enter information about the agreement with a party.</span></span>  

       > [!IMPORTANT]
       >  <span data-ttu-id="3d963-179">如果单击**确定**或**应用**此页中提供的所有值列出后，将收到错误。</span><span class="sxs-lookup"><span data-stu-id="3d963-179">If you click **OK** or **Apply** after providing all the values listed in this page, you will get an error.</span></span> <span data-ttu-id="3d963-180">这是因为还未提供创建协议的必需值。</span><span class="sxs-lookup"><span data-stu-id="3d963-180">That is because the mandatory values to create an agreement are not yet provided.</span></span> <span data-ttu-id="3d963-181">这些是 AS2-从到 AS2-上的值**标识符**的每个单向协议选项卡页。</span><span class="sxs-lookup"><span data-stu-id="3d963-181">These are AS2-From to AS2-To values on the **Identifiers** page of each one-way agreement tab.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="3d963-182">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3d963-182">Next Steps</span></span>  
 <span data-ttu-id="3d963-183">现在您必须为协议配置标识符设置。</span><span class="sxs-lookup"><span data-stu-id="3d963-183">You must now configure the identifier settings for the agreement.</span></span> <span data-ttu-id="3d963-184">有关说明，请参阅[配置标识符 (AS2)](../core/configuring-identifiers-as2.md)。</span><span class="sxs-lookup"><span data-stu-id="3d963-184">For instructions see [Configuring Identifiers (AS2)](../core/configuring-identifiers-as2.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="3d963-185">请参阅</span><span class="sxs-lookup"><span data-stu-id="3d963-185">See Also</span></span>  
 [<span data-ttu-id="3d963-186">配置 AS2 协议属性</span><span class="sxs-lookup"><span data-stu-id="3d963-186">Configuring AS2 Agreement Properties</span></span>](../core/configuring-as2-agreement-properties.md)