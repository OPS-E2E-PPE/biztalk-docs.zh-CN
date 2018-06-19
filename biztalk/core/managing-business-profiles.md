---
title: 管理业务配置文件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.resultsobject.businessprofile
ms.assetid: cf98c5a4-71bb-440b-8172-717ed0eb8373
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 434979376e679f1098557dc5b55f50e599ed21cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263517"
---
# <a name="managing-business-profiles"></a><span data-ttu-id="95f02-102">管理业务配置文件</span><span class="sxs-lookup"><span data-stu-id="95f02-102">Managing Business Profiles</span></span>
<span data-ttu-id="95f02-103">业务配置文件代表组织的业务部门。</span><span class="sxs-lookup"><span data-stu-id="95f02-103">A business profile represents the business divisions within of an organization.</span></span> <span data-ttu-id="95f02-104">就像一个组织可以拥有各种部门，方可以具有各种[业务配置文件](http://msdn.microsoft.com/library/f8286130-57fe-40ed-9fd8-81da2c8baaaf)。</span><span class="sxs-lookup"><span data-stu-id="95f02-104">Just like an organization can have various divisions, a party can have various [business profiles](http://msdn.microsoft.com/library/f8286130-57fe-40ed-9fd8-81da2c8baaaf).</span></span> 
  
<span data-ttu-id="95f02-105">一个业务配置文件代表组织中的一个业务部门。</span><span class="sxs-lookup"><span data-stu-id="95f02-105">A business profile represents a business division in an organization.</span></span> <span data-ttu-id="95f02-106">就像一个组织可以有多个部门（会计、采购、发货等等）一样，一个参与方也可有许多业务配置文件，每个业务配置文件代表组织中一个业务部门。</span><span class="sxs-lookup"><span data-stu-id="95f02-106">Just like an organization can have many divisions (accounting, purchase, shipping, etc.), a party can have many business profiles, each representing a business division in an organization.</span></span> <span data-ttu-id="95f02-107">业务配置文件属性包含下列信息：</span><span class="sxs-lookup"><span data-stu-id="95f02-107">Business profile properties contain the following information:</span></span>  
  
-   <span data-ttu-id="95f02-108">常规信息，例如业务配置文件名称</span><span class="sxs-lookup"><span data-stu-id="95f02-108">General information such as business profile name</span></span>  
  
-   <span data-ttu-id="95f02-109">可以与业务配置文件相关联的唯一标识</span><span class="sxs-lookup"><span data-stu-id="95f02-109">Unique identities that can be associated with a business profile</span></span>  
  
-   <span data-ttu-id="95f02-110">编码设置 （对于 X12 和 EDIFACT 消息） 和[协议设置](../core/protocol-settings.md)(AS2)，它定义如何发送或接收来自另一方的消息的业务配置文件。</span><span class="sxs-lookup"><span data-stu-id="95f02-110">Encoding settings (for X12 and EDIFACT messages) and [protocol settings](../core/protocol-settings.md) (AS2) that defines how the business profile can send or receive messages from another party.</span></span>  
  
<span data-ttu-id="95f02-111">本主题演示如何创建、 查看、 编辑或删除业务配置文件。</span><span class="sxs-lookup"><span data-stu-id="95f02-111">This topic shows you how to create, view, edit, or delete a business profile.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="95f02-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="95f02-112">Prerequisites</span></span>  
 <span data-ttu-id="95f02-113">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="95f02-113">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
## <a name="create-a-business-profile"></a><span data-ttu-id="95f02-114">创建业务配置文件</span><span class="sxs-lookup"><span data-stu-id="95f02-114">Create a business profile</span></span>  
  
1.  <span data-ttu-id="95f02-115">在**BizTalk Server 管理**，展开 BizTalk 组中，然后选择**方**。</span><span class="sxs-lookup"><span data-stu-id="95f02-115">In **BizTalk Server Administration**, expand the BizTalk group, and select **Parties**.</span></span> 
2. <span data-ttu-id="95f02-116">在**方和业务配置文件**窗格中，右击的当事方，选择**新建**，然后选择**业务配置文件**。</span><span class="sxs-lookup"><span data-stu-id="95f02-116">In the **Parties and Business Profiles** pane, right-click a party, select **New**, and then select **Business Profile**.</span></span>  
  
3.  <span data-ttu-id="95f02-117">在**常规**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="95f02-117">In the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="95f02-118">使用此选项</span><span class="sxs-lookup"><span data-stu-id="95f02-118">Use this</span></span>|<span data-ttu-id="95f02-119">执行的操作</span><span class="sxs-lookup"><span data-stu-id="95f02-119">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="95f02-120">**名称**</span><span class="sxs-lookup"><span data-stu-id="95f02-120">**Name**</span></span>|<span data-ttu-id="95f02-121">输入业务配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="95f02-121">Enter a business profile name.</span></span>|  
    |<span data-ttu-id="95f02-122">**Description**</span><span class="sxs-lookup"><span data-stu-id="95f02-122">**Description**</span></span>|<span data-ttu-id="95f02-123">为该业务配置文件输入说明。</span><span class="sxs-lookup"><span data-stu-id="95f02-123">Enter a description for the business profile.</span></span>|  
    |<span data-ttu-id="95f02-124">**其他属性 – 名称/值**</span><span class="sxs-lookup"><span data-stu-id="95f02-124">**Additional Properties – Name / Value**</span></span>|<span data-ttu-id="95f02-125">输入一个名称/值对以存储有关参与方的任何信息。</span><span class="sxs-lookup"><span data-stu-id="95f02-125">Enter a name-value pair to store any information about the party.</span></span> <span data-ttu-id="95f02-126">可以根据需要添加任意数量的名称/值对。</span><span class="sxs-lookup"><span data-stu-id="95f02-126">You can add as many name-value pairs as you want.</span></span> <span data-ttu-id="95f02-127">**注意：** 名称-值对不用于 BizTalk server 任何处理; 此数据是仅供信息。</span><span class="sxs-lookup"><span data-stu-id="95f02-127">**Note:**  The name-value pairs are not used by the BizTalk Server for any processing; this data is for information purposes only.</span></span>|  
    |<span data-ttu-id="95f02-128">**删除**</span><span class="sxs-lookup"><span data-stu-id="95f02-128">**Delete**</span></span>|<span data-ttu-id="95f02-129">选择要删除所选的名称-值对。</span><span class="sxs-lookup"><span data-stu-id="95f02-129">Select to delete the selected name-value pair.</span></span>|  
  
4.  <span data-ttu-id="95f02-130">如果需要，则为该业务配置文件添加业务标识。</span><span class="sxs-lookup"><span data-stu-id="95f02-130">If required, add business identities for the business profiles.</span></span> <span data-ttu-id="95f02-131">在**标识**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="95f02-131">In the **Identities** tab, do the following:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="95f02-132">在此阶段中添加业务标识不是强制性的。</span><span class="sxs-lookup"><span data-stu-id="95f02-132">Adding business identities at this stage is not mandatory.</span></span> <span data-ttu-id="95f02-133">你可以更高版本，添加业务标识，作为商业版配置文件的协议的一部分。</span><span class="sxs-lookup"><span data-stu-id="95f02-133">You can add the business identities later, as part of an agreement for the business profile.</span></span> <span data-ttu-id="95f02-134">如果你选择要添加业务标识现在，它们在就可创建此业务配置文件的协议。</span><span class="sxs-lookup"><span data-stu-id="95f02-134">If you chose to add the business identifies now, they are available while creating an agreement for this business profile.</span></span>  
  
    |<span data-ttu-id="95f02-135">使用此选项</span><span class="sxs-lookup"><span data-stu-id="95f02-135">Use this</span></span>|<span data-ttu-id="95f02-136">执行的操作</span><span class="sxs-lookup"><span data-stu-id="95f02-136">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="95f02-137">**名称**</span><span class="sxs-lookup"><span data-stu-id="95f02-137">**Name**</span></span>|<span data-ttu-id="95f02-138">选择空单元格，并从下拉列表网格中，选择主体提供到组织的唯一业务标识为身份验证。</span><span class="sxs-lookup"><span data-stu-id="95f02-138">Select the empty cell, and from the drop-down grid, select an authenticating body that provides unique business identities to organizations.</span></span> <span data-ttu-id="95f02-139">例如， **D-U-N-S （Bradstreet Dun)**。</span><span class="sxs-lookup"><span data-stu-id="95f02-139">For example, **D-U-N-S (Dun & Bradstreet)**.</span></span> <span data-ttu-id="95f02-140">两个业务合作伙伴可以选择一个双方商定的业务标识。</span><span class="sxs-lookup"><span data-stu-id="95f02-140">Two business partners can opt for a mutually agreed business identity.</span></span> <span data-ttu-id="95f02-141">对于这种情况下，选择**双方约定**（对于 EDIFACT) 或**双方约定 (X12)** （对于 X12)。</span><span class="sxs-lookup"><span data-stu-id="95f02-141">For such scenarios, select **Mutually Defined** (for EDIFACT) or **Mutually Defined (X12)** (for X12).</span></span>|  
    |<span data-ttu-id="95f02-142">**Qualifier**</span><span class="sxs-lookup"><span data-stu-id="95f02-142">**Qualifier**</span></span>|<span data-ttu-id="95f02-143">显示基于为选定的值的预定义的值**名称**。</span><span class="sxs-lookup"><span data-stu-id="95f02-143">Displays a predefined value based on the value you selected for **Name**.</span></span>|  
    |<span data-ttu-id="95f02-144">**值**</span><span class="sxs-lookup"><span data-stu-id="95f02-144">**Value**</span></span>|<span data-ttu-id="95f02-145">输入业务标识的值。</span><span class="sxs-lookup"><span data-stu-id="95f02-145">Enter a value for the business identity.</span></span> <span data-ttu-id="95f02-146">在提供业务标识的值时，您必须注意以下事项。</span><span class="sxs-lookup"><span data-stu-id="95f02-146">You must make the following considerations while providing a value for business identities.</span></span><br /><br /> <span data-ttu-id="95f02-147">-对于给定的当事方，你可以使用的标识名称和标识值的相同组合的多个业务配置文件。</span><span class="sxs-lookup"><span data-stu-id="95f02-147">-   For a given party, you can have more than one business profile using the same combination of identity name and identity value.</span></span> <span data-ttu-id="95f02-148">例如，对于使用方有两个业务配置文件**名称**作为**双方约定 (X12)** 和**值**作为**THEM**。</span><span class="sxs-lookup"><span data-stu-id="95f02-148">For example, you can have two business profiles for a party with **Name** as **Mutually Defined (X12)** and **Value** as **THEM**.</span></span><br /><span data-ttu-id="95f02-149">-跨方，不能有两个业务配置文件使用的标识名称和标识值的相同组合。</span><span class="sxs-lookup"><span data-stu-id="95f02-149">-   Across parties, you cannot have two business profiles using the same combination of identity name and identity value.</span></span>|  
    |<span data-ttu-id="95f02-150">**删除**</span><span class="sxs-lookup"><span data-stu-id="95f02-150">**Remove**</span></span>|<span data-ttu-id="95f02-151">选择要删除选定的标识。</span><span class="sxs-lookup"><span data-stu-id="95f02-151">Select to remove the selected identity.</span></span>|  
  
5.  <span data-ttu-id="95f02-152">如果需要，添加 X12 编码消息、 EDIFACT 编码消息或 AS2 传输的协议设置的协议设置。</span><span class="sxs-lookup"><span data-stu-id="95f02-152">If required, add the protocol settings for X12-encoded messages, EDIFACT-encoded messages, or the protocol settings for AS2 transport.</span></span> <span data-ttu-id="95f02-153">请参阅[配置业务配置文件属性](../core/configuring-business-profile-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="95f02-153">See [Configuring Business Profile Properties](../core/configuring-business-profile-properties.md).</span></span>  
  
6.  <span data-ttu-id="95f02-154">选择**应用**接受属性，或选择**确定**完成的配置设置。</span><span class="sxs-lookup"><span data-stu-id="95f02-154">Select **Apply** to accept the properties, or select **OK** to complete the configuration setting.</span></span> <span data-ttu-id="95f02-155">以上任一操作验证的设置。</span><span class="sxs-lookup"><span data-stu-id="95f02-155">Either action validates the settings.</span></span>  
  
## <a name="view-or-change-a-business-profile"></a><span data-ttu-id="95f02-156">查看或更改业务配置文件</span><span class="sxs-lookup"><span data-stu-id="95f02-156">View or change a business profile</span></span>  
  
1.  <span data-ttu-id="95f02-157">在**BizTalk Server 管理**，选择**方**。</span><span class="sxs-lookup"><span data-stu-id="95f02-157">In **BizTalk Server Administration**, select **Parties**.</span></span> 

2. <span data-ttu-id="95f02-158">在**方和业务配置文件**窗格中，展开一个方节点以查看其下的业务配置文件。</span><span class="sxs-lookup"><span data-stu-id="95f02-158">In the **Parties and Business Profiles** pane, expand a party node to see the business profiles under it.</span></span> <span data-ttu-id="95f02-159">右键单击你想要编辑，，然后选择业务配置文件**属性**。</span><span class="sxs-lookup"><span data-stu-id="95f02-159">Right-click a business profile you want to edit, and then select **Properties**.</span></span>  
  
3.  <span data-ttu-id="95f02-160">在**配置文件属性**对话框中，查看或编辑配置文件。</span><span class="sxs-lookup"><span data-stu-id="95f02-160">In the **Profile Properties** dialog box, view or edit the profile.</span></span> <span data-ttu-id="95f02-161">有关可以在不同的页指定的值的信息**配置文件属性**对话框中，请参阅[配置业务配置文件属性](../core/configuring-business-profile-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="95f02-161">For information on the values that can be specified on the different pages in the **Profile Properties** dialog box, see [Configuring Business Profile Properties](../core/configuring-business-profile-properties.md).</span></span>  
  
4.  <span data-ttu-id="95f02-162">选择**应用**接受属性，或选择**确定**完成的配置设置。</span><span class="sxs-lookup"><span data-stu-id="95f02-162">Select **Apply** to accept the properties, or select **OK** to complete the configuration setting.</span></span> <span data-ttu-id="95f02-163">以上任一操作验证的设置。</span><span class="sxs-lookup"><span data-stu-id="95f02-163">Either action validates the settings.</span></span>  

## <a name="delete-a-business-profile"></a><span data-ttu-id="95f02-164">删除业务配置文件</span><span class="sxs-lookup"><span data-stu-id="95f02-164">Delete a business profile</span></span>  
  
1.  <span data-ttu-id="95f02-165">在**BizTalk Server 管理**，选择**方**。</span><span class="sxs-lookup"><span data-stu-id="95f02-165">In **BizTalk Server Administration**, select **Parties**.</span></span>  
  
3.  <span data-ttu-id="95f02-166">在**方和业务配置文件**窗格中，展开一个方节点以查看其下的业务配置文件。</span><span class="sxs-lookup"><span data-stu-id="95f02-166">In the **Parties and Business Profiles** pane, expand a party node to see the business profiles under it.</span></span>  
  
4.  <span data-ttu-id="95f02-167">右键单击你想要删除，然后选择的业务配置文件**删除**。</span><span class="sxs-lookup"><span data-stu-id="95f02-167">Right-click the business profile you want to delete, and then select **Delete**.</span></span> 
  
5.  <span data-ttu-id="95f02-168">在**确认删除业务配置文件**对话框中，选择**是**若要删除的业务配置文件。</span><span class="sxs-lookup"><span data-stu-id="95f02-168">In the **Confirm delete business profile** dialog box, select **Yes** to delete the business profile.</span></span>  


## <a name="see-also"></a><span data-ttu-id="95f02-169">另请参阅</span><span class="sxs-lookup"><span data-stu-id="95f02-169">See Also</span></span>  
 [<span data-ttu-id="95f02-170">管理 EDI 和 AS2 解决方案</span><span class="sxs-lookup"><span data-stu-id="95f02-170">Managing EDI and AS2 Solutions</span></span>](../core/managing-edi-and-as2-solutions.md)