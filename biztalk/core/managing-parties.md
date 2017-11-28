---
title: "管理方 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.admin.resultsobject.party
helpviewer_keywords:
- Administration Console [BizTalk Server], parties
- managing [parties]
- managing [parties], about managing parties
- parties, managing
ms.assetid: 96d2bcb3-1e38-4dad-a0d6-e5913ba531e7
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06f0c552b84fd8c4f56e2a88c59e8557585c947e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="managing-parties"></a><span data-ttu-id="41300-102">管理方</span><span class="sxs-lookup"><span data-stu-id="41300-102">Managing Parties</span></span>
<span data-ttu-id="41300-103">使用**方**节点，你可以设置业务合作伙伴 （参与方） 或内部的部门 （业务配置文件） 与其[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案进行交互。</span><span class="sxs-lookup"><span data-stu-id="41300-103">Using the **Parties** node, you can set up business partners (parties) or internal departments (business profiles) with which [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solutions interact.</span></span> <span data-ttu-id="41300-104">有关详细信息，请参阅[贸易合作伙伴](../core/trading-partners-and-business-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="41300-104">For more information, see [Trading Partners](../core/trading-partners-and-business-profiles.md).</span></span>  

<span data-ttu-id="41300-105">您可以使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台创建和配置参与方。</span><span class="sxs-lookup"><span data-stu-id="41300-105">You can create and configure a party using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="41300-106">在 BizTalk Server 中创建参与方后，您可能希望使用业务流程与参与方进行交互。</span><span class="sxs-lookup"><span data-stu-id="41300-106">After you create a party in BizTalk Server, it is likely that you want to interact with that party using an orchestration.</span></span> <span data-ttu-id="41300-107">参与方通过角色与业务流程进行交互。</span><span class="sxs-lookup"><span data-stu-id="41300-107">Parties interact with orchestrations through roles.</span></span> <span data-ttu-id="41300-108">例如，业务流程中可能具有发运方角色。</span><span class="sxs-lookup"><span data-stu-id="41300-108">For example, you might have a shipping role in your orchestration.</span></span> <span data-ttu-id="41300-109">发运方具有一个或多个关联的参与方。</span><span class="sxs-lookup"><span data-stu-id="41300-109">The shipper would have one or more parties associated with it.</span></span> <span data-ttu-id="41300-110">当业务流程需要确定要使用费用最低的送货公司来发运货物时，则可比较发运方角色中各个参与方的价格。</span><span class="sxs-lookup"><span data-stu-id="41300-110">When the orchestration needs to decide the least expensive shipping company to use to ship an item, it can compare the prices of the parties in the shipper role.</span></span>  
  
 <span data-ttu-id="41300-111">必须登记参与方以将其与特定角色相关联。</span><span class="sxs-lookup"><span data-stu-id="41300-111">You must enlist a party to tie it to a specific role.</span></span> <span data-ttu-id="41300-112">通过登记参与方，业务流程可以与该参与方进行交互。</span><span class="sxs-lookup"><span data-stu-id="41300-112">Enlisting a party enables an orchestration to interact with the party.</span></span> <span data-ttu-id="41300-113">请参阅[如何登记或取消登记角色方](../core/how-to-enlist-or-unenlist-a-party-for-a-role.md)。</span><span class="sxs-lookup"><span data-stu-id="41300-113">See [How to Enlist or Unenlist a Party for a Role](../core/how-to-enlist-or-unenlist-a-party-for-a-role.md).</span></span>
 
## <a name="prerequisites"></a><span data-ttu-id="41300-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="41300-114">Prerequisites</span></span>  
 <span data-ttu-id="41300-115">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="41300-115">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
## <a name="create-or-edit-a-party"></a><span data-ttu-id="41300-116">创建或编辑参与方</span><span class="sxs-lookup"><span data-stu-id="41300-116">Create or edit a party</span></span>
  
1.  <span data-ttu-id="41300-117">打开 **“BizTalk Server 管理”**。</span><span class="sxs-lookup"><span data-stu-id="41300-117">Open **BizTalk Server Administration**.</span></span>  <span data-ttu-id="41300-118">展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，右键单击**方**，选择**新建**，然后选择**方**。</span><span class="sxs-lookup"><span data-stu-id="41300-118">Expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, right-click **Parties**, select **New**, and then select **Party**.</span></span>  
  
2.  <span data-ttu-id="41300-119">上**常规**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="41300-119">On the **General** page, do the following:</span></span>  
  
    |<span data-ttu-id="41300-120">使用此选项</span><span class="sxs-lookup"><span data-stu-id="41300-120">Use this</span></span>|<span data-ttu-id="41300-121">执行的操作</span><span class="sxs-lookup"><span data-stu-id="41300-121">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="41300-122">**名称**</span><span class="sxs-lookup"><span data-stu-id="41300-122">**Name**</span></span>|<span data-ttu-id="41300-123">输入参与方名称。</span><span class="sxs-lookup"><span data-stu-id="41300-123">Enter a party name.</span></span>|  
    |<span data-ttu-id="41300-124">**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**</span><span class="sxs-lookup"><span data-stu-id="41300-124">**Local BizTalk processes messages received by the party or supports sending messages from this party**</span></span>|<span data-ttu-id="41300-125">选中此复选框以指定该参与方代表托管 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的同一个贸易合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="41300-125">Select this checkbox to specify that the party represents the same trading partner that also hosts [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="41300-126">**重要说明：**两方 Tpm 使用全新的管道的解决方案附带[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，你必须选择至少一个方此复选框。</span><span class="sxs-lookup"><span data-stu-id="41300-126">**Important:**  For a two-party TPM solution that uses out-of-the-box pipelines shipped with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you must select this check box for at least one party.</span></span> <span data-ttu-id="41300-127">**注意：**如果清除此复选框，将创建此参与方的协议时禁用某些属性。</span><span class="sxs-lookup"><span data-stu-id="41300-127">**Note:**  If you clear this check box, some properties will be disabled while creating the agreements for this party.</span></span>|  
    |<span data-ttu-id="41300-128">**其他属性 – 名称/值**</span><span class="sxs-lookup"><span data-stu-id="41300-128">**Additional Properties – Name / Value**</span></span>|<span data-ttu-id="41300-129">输入一个名称/值对以存储有关参与方的任何信息。</span><span class="sxs-lookup"><span data-stu-id="41300-129">Enter a name-value pair to store any information about the party.</span></span> <span data-ttu-id="41300-130">可以根据需要添加任意数量的名称/值对。</span><span class="sxs-lookup"><span data-stu-id="41300-130">You can add as many name-value pairs as you want.</span></span> <span data-ttu-id="41300-131">**请注意**： 名称-值对不用于 BizTalk server 任何处理; 此数据是仅供信息。</span><span class="sxs-lookup"><span data-stu-id="41300-131">**Note**:  The name-value pairs are not used by the BizTalk Server for any processing; this data is for information purposes only.</span></span>|  
    |<span data-ttu-id="41300-132">**删除**</span><span class="sxs-lookup"><span data-stu-id="41300-132">**Delete**</span></span>|<span data-ttu-id="41300-133">选择要删除所选的名称-值对。</span><span class="sxs-lookup"><span data-stu-id="41300-133">Select to delete the selected name-value pair.</span></span>|  
  
3.  <span data-ttu-id="41300-134">上**发送端口**页上，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="41300-134">On the **Send Ports** page, do the following.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="41300-135">在 [!INCLUDE[prague](../includes/prague-md.md)] 中，发送端口关联在协议级别执行。</span><span class="sxs-lookup"><span data-stu-id="41300-135">In [!INCLUDE[prague](../includes/prague-md.md)], the send port association is done at the agreement level.</span></span> <span data-ttu-id="41300-136">**发送端口**作为一部分的参与方属性是只是为了向后兼容，会出现页面。</span><span class="sxs-lookup"><span data-stu-id="41300-136">The **Send Ports** page available as part of the party properties is purely for backward compatibility.</span></span> <span data-ttu-id="41300-137">每当您将发送端口与协议相关联时，发送端口设置也会传播到参与方设置，您同时会在此页面上看到发送端口关联。</span><span class="sxs-lookup"><span data-stu-id="41300-137">Whenever you associate a send port with an agreement, the send port setting is also propagated to the party setting and you can see the send port association in this page as well.</span></span> <span data-ttu-id="41300-138">但是，反之则不然。</span><span class="sxs-lookup"><span data-stu-id="41300-138">However, the reverse is not true.</span></span> <span data-ttu-id="41300-139">不能将发送端口与参与方关联，然后使该发送端口自动作为协议设置的一部分使用。</span><span class="sxs-lookup"><span data-stu-id="41300-139">You cannot associate a send port with a party and then have that send port be automatically available as part of the agreement settings.</span></span>  
  
    |<span data-ttu-id="41300-140">使用此选项</span><span class="sxs-lookup"><span data-stu-id="41300-140">Use this</span></span>|<span data-ttu-id="41300-141">执行的操作</span><span class="sxs-lookup"><span data-stu-id="41300-141">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="41300-142">**发送端口的名称**</span><span class="sxs-lookup"><span data-stu-id="41300-142">**Send ports - Name**</span></span>|<span data-ttu-id="41300-143">从下拉列表中选择要绑定到此参与方的发送端口。</span><span class="sxs-lookup"><span data-stu-id="41300-143">From the drop-down list, select a send port to bind to this party.</span></span>|  
    |<span data-ttu-id="41300-144">**发送端口的 URI**</span><span class="sxs-lookup"><span data-stu-id="41300-144">**Send ports - URI**</span></span>|<span data-ttu-id="41300-145">显示发送端口地址。</span><span class="sxs-lookup"><span data-stu-id="41300-145">Displays the send port address.</span></span>|  
    |<span data-ttu-id="41300-146">**删除**</span><span class="sxs-lookup"><span data-stu-id="41300-146">**Remove**</span></span>|<span data-ttu-id="41300-147">选择此选项可删除所选端口从发送方。</span><span class="sxs-lookup"><span data-stu-id="41300-147">Select to remove the selected send port from the party.</span></span>|  
    |<span data-ttu-id="41300-148">**属性**</span><span class="sxs-lookup"><span data-stu-id="41300-148">**Properties**</span></span>|<span data-ttu-id="41300-149">选择此项可显示**发送端口属性**所选的发送端口的对话框。</span><span class="sxs-lookup"><span data-stu-id="41300-149">Select to display the **Send Port Properties** dialog box for the selected send port.</span></span>|  
  
4.  <span data-ttu-id="41300-150">上**证书**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="41300-150">On the **Certificate** page, do the following:</span></span>  
  
    |<span data-ttu-id="41300-151">使用此选项</span><span class="sxs-lookup"><span data-stu-id="41300-151">Use this</span></span>|<span data-ttu-id="41300-152">执行的操作</span><span class="sxs-lookup"><span data-stu-id="41300-152">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="41300-153">**浏览**</span><span class="sxs-lookup"><span data-stu-id="41300-153">**Browse**</span></span>|<span data-ttu-id="41300-154">选择要显示**选择证书**对话框中，其中从本地计算机或其他人证书存储，将应用到消息传输到方选择签名证书。</span><span class="sxs-lookup"><span data-stu-id="41300-154">Select to display the **Select Certificate** dialog box, where you select the signature certificate from the Local Machine or Other People certificate store to apply to messages transmitted to the party.</span></span>|  
    |<span data-ttu-id="41300-155">**公用名**</span><span class="sxs-lookup"><span data-stu-id="41300-155">**Common Name**</span></span>|<span data-ttu-id="41300-156">显示所选证书的说明。</span><span class="sxs-lookup"><span data-stu-id="41300-156">Displays a description of the selected certificate.</span></span>|  
    |<span data-ttu-id="41300-157">**指纹**</span><span class="sxs-lookup"><span data-stu-id="41300-157">**Thumbprint**</span></span>|<span data-ttu-id="41300-158">显示用于参与方解析和签名验证的私钥证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="41300-158">Displays the thumbprint of the private key certificate that is used for party resolution and signature verification.</span></span> <span data-ttu-id="41300-159">证书指纹的格式 HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH，其中 H 是十六进制数字 （介于 0 到 9） 或从 A 到 F 字母。</span><span class="sxs-lookup"><span data-stu-id="41300-159">The certificate thumbprint has the format HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, where H is a hexadecimal digit (a number from 0 through 9 or a letter from A through F).</span></span>|  
    |<span data-ttu-id="41300-160">**删除证书**</span><span class="sxs-lookup"><span data-stu-id="41300-160">**Remove certificate**</span></span>|<span data-ttu-id="41300-161">选择要删除显示的证书。</span><span class="sxs-lookup"><span data-stu-id="41300-161">Select to remove the displayed certificate.</span></span>|  
  
5.  <span data-ttu-id="41300-162">选择**应用**接受属性，或选择**确定**完成的配置设置。</span><span class="sxs-lookup"><span data-stu-id="41300-162">Select **Apply** to accept the properties, or select **OK** to complete the configuration setting.</span></span> <span data-ttu-id="41300-163">以上任一操作均会验证设置</span><span class="sxs-lookup"><span data-stu-id="41300-163">Either action will validate the settings</span></span>  

### <a name="update-an-existing-party"></a><span data-ttu-id="41300-164">更新现有方</span><span class="sxs-lookup"><span data-stu-id="41300-164">Update an existing party</span></span>
<span data-ttu-id="41300-165">当事方登记到角色和端口绑定后，你可以：</span><span class="sxs-lookup"><span data-stu-id="41300-165">After a party is enlisted to a role and the ports are bound, you can:</span></span>  
  
-   <span data-ttu-id="41300-166">编辑方的名称和描述</span><span class="sxs-lookup"><span data-stu-id="41300-166">Edit the party's name and description</span></span>  
-   <span data-ttu-id="41300-167">编辑方的证书</span><span class="sxs-lookup"><span data-stu-id="41300-167">Edit the party's certificate</span></span>  
-   <span data-ttu-id="41300-168">指定当事方是用于组织托管[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41300-168">Specify whether the party is for the organization hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>

1. <span data-ttu-id="41300-169">在**BizTalk Server 管理**，然后选择**方**。</span><span class="sxs-lookup"><span data-stu-id="41300-169">In **BizTalk Server Administration**, and select **Parties**.</span></span>

2. <span data-ttu-id="41300-170">在**方和业务配置文件**窗格中右键单击你想要查看或编辑，当事方，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="41300-170">In the **Parties and Business Profiles** pane, right-click the party you want to view or edit, and then select **Properties**.</span></span>  

3. <span data-ttu-id="41300-171">查看或编辑的属性。</span><span class="sxs-lookup"><span data-stu-id="41300-171">View or edit the properties.</span></span> 

4. <span data-ttu-id="41300-172">选择**应用**接受属性，或选择**确定**完成的配置设置。</span><span class="sxs-lookup"><span data-stu-id="41300-172">Select **Apply** to accept the properties, or select **OK** to complete the configuration setting.</span></span> <span data-ttu-id="41300-173">以上任一操作验证设置。</span><span class="sxs-lookup"><span data-stu-id="41300-173">Either action validate the settings.</span></span>  

## <a name="delete-a-party"></a><span data-ttu-id="41300-174">删除参与方</span><span class="sxs-lookup"><span data-stu-id="41300-174">Delete a party</span></span>
<span data-ttu-id="41300-175">删除使用方[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="41300-175">Delete the party using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="41300-176">您只能删除未在角色中登记的参与方。</span><span class="sxs-lookup"><span data-stu-id="41300-176">You can only delete a party that is not enlisted in a role.</span></span> <span data-ttu-id="41300-177">在删除参与方之前，必须首先从该参与方所登记的任何角色中取消登记。</span><span class="sxs-lookup"><span data-stu-id="41300-177">Before you can delete a party, you must first un-enlist it from any of the roles where it is enlisted.</span></span> <span data-ttu-id="41300-178">请参阅[如何登记或取消登记角色方](../core/how-to-enlist-or-unenlist-a-party-for-a-role.md)。</span><span class="sxs-lookup"><span data-stu-id="41300-178">See [How to Enlist or Unenlist a Party for a Role](../core/how-to-enlist-or-unenlist-a-party-for-a-role.md).</span></span> 

1. <span data-ttu-id="41300-179">在**BizTalk Server 管理**，选择**方**，右键单击你想要删除，然后选择的方**删除**。</span><span class="sxs-lookup"><span data-stu-id="41300-179">In **BizTalk Server Administration**, select **Parties**, right-click the party you want to delete, and then select **Delete**.</span></span>  
  
2.  <span data-ttu-id="41300-180">在**确认删除方**对话框中，选择**是**删除当事方。</span><span class="sxs-lookup"><span data-stu-id="41300-180">In the **Confirm delete party** dialog box, select **Yes** to delete the party.</span></span>  

## <a name="search-for-a-party"></a><span data-ttu-id="41300-181">搜索方</span><span class="sxs-lookup"><span data-stu-id="41300-181">Search for a party</span></span>
<span data-ttu-id="41300-182">如果你有大量的参与方创建，则可以使用**搜索**选项以显示你想要查看的方。</span><span class="sxs-lookup"><span data-stu-id="41300-182">If you have a large number of parties created, you can use the **Search** option to  display the parties that you want to see.</span></span>  

1. <span data-ttu-id="41300-183">在**BizTalk Server 管理**，选择**方**。</span><span class="sxs-lookup"><span data-stu-id="41300-183">In **BizTalk Server Administration**, select **Parties**.</span></span>

3.  <span data-ttu-id="41300-184">在**方和业务配置文件**窗格中，向右上角，输入中的搜索字符串**搜索方**文本框中，然后选择搜索图标。</span><span class="sxs-lookup"><span data-stu-id="41300-184">In the **Parties and Business Profiles** pane, towards the top right corner, enter a search string in the **Search Party** text box, and select the search icon.</span></span> <span data-ttu-id="41300-185">你还可按 Enter 键开始搜索。</span><span class="sxs-lookup"><span data-stu-id="41300-185">You can also press ENTER to start the search.</span></span>  
  
     <span data-ttu-id="41300-186">使用搜索选项时，你必须注意以下几点：</span><span class="sxs-lookup"><span data-stu-id="41300-186">You must consider the following points while using search:</span></span>  
  
    -   <span data-ttu-id="41300-187">搜索字符串不区分大小写</span><span class="sxs-lookup"><span data-stu-id="41300-187">The search string is not case-sensitive</span></span>
  
    -   <span data-ttu-id="41300-188">你可以在中搜索文本名称 （子字符串搜索）。</span><span class="sxs-lookup"><span data-stu-id="41300-188">You can search for text within the name (sub-string search).</span></span> <span data-ttu-id="41300-189">例如，如果搜索“ar”，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台将显示以该搜索字符串开头的参与方（如 Artist）或名称中包含该搜索字符串的参与方（如 Party1）。</span><span class="sxs-lookup"><span data-stu-id="41300-189">For example, if you search for ‘ar’, the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console displays the parties that either start with the search string (e.g. Artist) or the parties that have the search string in their name (e.g. Party1).</span></span>  
  
    -   <span data-ttu-id="41300-190">搜索操作仅限于方名称。</span><span class="sxs-lookup"><span data-stu-id="41300-190">The search operation is limited to party names.</span></span>  
  
4.  <span data-ttu-id="41300-191">若要清除搜索结果，请选择搜索文本框旁边的红色 x。</span><span class="sxs-lookup"><span data-stu-id="41300-191">To clear the search results, select the red 'x' next to the search text box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41300-192">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41300-192">See Also</span></span>  
 <span data-ttu-id="41300-193">[管理角色链接](../core/managing-role-links.md) </span><span class="sxs-lookup"><span data-stu-id="41300-193">[Managing Role Links](../core/managing-role-links.md) </span></span>  
 [<span data-ttu-id="41300-194">如何配置参与方解析管道组件</span><span class="sxs-lookup"><span data-stu-id="41300-194">How to Configure the Party Resolution Pipeline Component</span></span>](../core/how-to-configure-the-party-resolution-pipeline-component.md)  
 [<span data-ttu-id="41300-195">管理 EDI 和 AS2 解决方案</span><span class="sxs-lookup"><span data-stu-id="41300-195">Managing EDI and AS2 Solutions</span></span>](../core/managing-edi-and-as2-solutions.md)