---
title: 步骤 2： 设置 Salesforce 系统 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0a4b09fb-70a7-4eec-b1e3-f05de0e84df1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d65a1c741103b9c8f1e9493b7bd2aa56eef8cf18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279925"
---
# <a name="step-2-set-up-the-salesforce-system"></a><span data-ttu-id="9c72e-102">步骤 2： 设置 Salesforce 系统</span><span class="sxs-lookup"><span data-stu-id="9c72e-102">Step 2: Set up the Salesforce System</span></span>
<span data-ttu-id="9c72e-103">在此步骤中，你要将 Salesforce 配置为在机会成功关闭时发送通知。</span><span class="sxs-lookup"><span data-stu-id="9c72e-103">In this step, you configure Salesforce to send notifications when an opportunity is successfully closed.</span></span> <span data-ttu-id="9c72e-104">你需要先执行以下步骤，然后才能发送通知：</span><span class="sxs-lookup"><span data-stu-id="9c72e-104">Before you can send notifications, you need to perform the following steps:</span></span>  
  
-   <span data-ttu-id="9c72e-105">在 Salesforce 中创建帐户。</span><span class="sxs-lookup"><span data-stu-id="9c72e-105">Create an account in Salesforce.</span></span> <span data-ttu-id="9c72e-106">帐户代表 Northwind 的客户。</span><span class="sxs-lookup"><span data-stu-id="9c72e-106">An account represents a customer for Northwind.</span></span>  
  
-   <span data-ttu-id="9c72e-107">为帐户创建机会。</span><span class="sxs-lookup"><span data-stu-id="9c72e-107">Create an opportunity for the account.</span></span> <span data-ttu-id="9c72e-108">机会代表客户所带来的潜在销售机会。</span><span class="sxs-lookup"><span data-stu-id="9c72e-108">An opportunity represents a prospective sales opportunity with the customer.</span></span> <span data-ttu-id="9c72e-109">在机会中，你还可以添加客户感兴趣的产品详细信息。</span><span class="sxs-lookup"><span data-stu-id="9c72e-109">As part of the opportunity, you also add the product details that the customer is interested in.</span></span>  
  
-   <span data-ttu-id="9c72e-110">在 Salesforce 中创建工作流。</span><span class="sxs-lookup"><span data-stu-id="9c72e-110">Create a workflow in Salesforce.</span></span>  
  
-   <span data-ttu-id="9c72e-111">创建与 Salesforce 连接的应用程序定义。</span><span class="sxs-lookup"><span data-stu-id="9c72e-111">Create a Salesforce connected application definition.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9c72e-112">本主题中的步骤假定你已拥有 Salesforce 开发人员帐户。</span><span class="sxs-lookup"><span data-stu-id="9c72e-112">The steps in this topic assume that you already have a Salesforce developer account.</span></span> <span data-ttu-id="9c72e-113">若要在 Salesforce 中创建新的开发人员帐户，请转到[http://go.microsoft.com/fwlink/?LinkId=296424](http://go.microsoft.com/fwlink/?LinkId=296424)。</span><span class="sxs-lookup"><span data-stu-id="9c72e-113">To create a new developer account in Salesforce, go to [http://go.microsoft.com/fwlink/?LinkId=296424](http://go.microsoft.com/fwlink/?LinkId=296424).</span></span>  
  
### <a name="to-create-an-account-in-salesforce"></a><span data-ttu-id="9c72e-114">在 Salesforce 中创建帐户</span><span class="sxs-lookup"><span data-stu-id="9c72e-114">To create an Account in Salesforce</span></span>  
  
1.  <span data-ttu-id="9c72e-115">使用你的开发人员凭据登录到 Salesforce.com 门户。</span><span class="sxs-lookup"><span data-stu-id="9c72e-115">Log on to the Salesforce.com portal using your developer credentials.</span></span>  
  
2.  <span data-ttu-id="9c72e-116">在门户中，单击**帐户**选项卡上，并依次**新建**。</span><span class="sxs-lookup"><span data-stu-id="9c72e-116">On the portal, click the **Accounts** tab, and then click **New**.</span></span>  
  
3.  <span data-ttu-id="9c72e-117">上**新帐户**页上，为各个字段提供值。</span><span class="sxs-lookup"><span data-stu-id="9c72e-117">On the **New Account** page, provide values for the various fields.</span></span> <span data-ttu-id="9c72e-118">指定的值**帐户名称**是必需的。</span><span class="sxs-lookup"><span data-stu-id="9c72e-118">Specifying a value for **Account Name** is mandatory.</span></span> <span data-ttu-id="9c72e-119">对于本教程中，指定为帐户名`Customer1`。</span><span class="sxs-lookup"><span data-stu-id="9c72e-119">For this tutorial, specify the account name as `Customer1`.</span></span>  
  
4.  <span data-ttu-id="9c72e-120">单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="9c72e-120">Click **Save**.</span></span>  
  
### <a name="to-create-an-opportunity-for-the-customer"></a><span data-ttu-id="9c72e-121">为客户创建机会</span><span class="sxs-lookup"><span data-stu-id="9c72e-121">To create an Opportunity for the customer</span></span>  
  
1.  <span data-ttu-id="9c72e-122">在 Salesforce.com 门户中，单击**机会**选项卡。</span><span class="sxs-lookup"><span data-stu-id="9c72e-122">On the Salesforce.com portal, click the **Opportunities** tab.</span></span>  
  
2.  <span data-ttu-id="9c72e-123">在**最近的商机**部分中，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="9c72e-123">In the **Recent Opportunities** section, click **New**.</span></span>  
  
3.  <span data-ttu-id="9c72e-124">在“新建机会”页中，指定以下值：</span><span class="sxs-lookup"><span data-stu-id="9c72e-124">In the New Opportunity page, specify the following values:</span></span>  
  
    1.  <span data-ttu-id="9c72e-125">指定**机会名称**，例如， `Opportunity with Customer 1`。</span><span class="sxs-lookup"><span data-stu-id="9c72e-125">Specify an **Opportunity Name**, for example, `Opportunity with Customer 1`.</span></span>  
  
    2.  <span data-ttu-id="9c72e-126">指定**帐户名称**。</span><span class="sxs-lookup"><span data-stu-id="9c72e-126">Specify the **Account Name**.</span></span> <span data-ttu-id="9c72e-127">此项表示与该机会关联的帐户。</span><span class="sxs-lookup"><span data-stu-id="9c72e-127">This represents the account with which this opportunity is associated.</span></span> <span data-ttu-id="9c72e-128">对于本教程中，将帐户设置为`Customer1`。</span><span class="sxs-lookup"><span data-stu-id="9c72e-128">For this tutorial, set the Account to `Customer1`.</span></span> <span data-ttu-id="9c72e-129">你已在上一步中创建了此帐户。</span><span class="sxs-lookup"><span data-stu-id="9c72e-129">You created this account in the previous procedure.</span></span>  
  
    3.  <span data-ttu-id="9c72e-130">指定**关闭日期**。</span><span class="sxs-lookup"><span data-stu-id="9c72e-130">Specify a **Close Date**.</span></span> <span data-ttu-id="9c72e-131">此项表示机会应截止的日期。</span><span class="sxs-lookup"><span data-stu-id="9c72e-131">This represents the date by which the opportunity should be closed.</span></span>  
  
    4.  <span data-ttu-id="9c72e-132">指定**阶段**。</span><span class="sxs-lookup"><span data-stu-id="9c72e-132">Specify a **Stage**.</span></span> <span data-ttu-id="9c72e-133">此项表示机会的当前阶段。</span><span class="sxs-lookup"><span data-stu-id="9c72e-133">This denotes the current stage for the opportunity.</span></span> <span data-ttu-id="9c72e-134">开始时，你可以将设置可以为任何内容，例如，**需要分析**。</span><span class="sxs-lookup"><span data-stu-id="9c72e-134">To start with, you can set the opportunity to anything, for example, **Needs Analysis**.</span></span>  
  
         <span data-ttu-id="9c72e-135">![在 Salesforce 中创建的商机](../core/media/bts-sf-create-opp.jpg "BTS_SF_Create_Opp")</span><span class="sxs-lookup"><span data-stu-id="9c72e-135">![Create an opportunity in Salesforce](../core/media/bts-sf-create-opp.jpg "BTS_SF_Create_Opp")</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="9c72e-136">请确保你未设置为阶段**关闭获胜**开始。</span><span class="sxs-lookup"><span data-stu-id="9c72e-136">Make sure you do not set the stage to **Closed Won** to start with.</span></span> <span data-ttu-id="9c72e-137">对于本教程中，每次阶段设置为中的方案**关闭获胜**将通知发送到中继终结点[!INCLUDE[winazure](../includes/winazure-md.md)] [!INCLUDE[sb](../includes/sb-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9c72e-137">For the scenario in this tutorial, every time the stage is set to **Closed Won** a notification is sent to a relay endpoint on [!INCLUDE[winazure](../includes/winazure-md.md)][!INCLUDE[sb](../includes/sb-md.md)].</span></span> <span data-ttu-id="9c72e-138">我们尚未将设置为解决方案的该部分，不应设置阶段，为**关闭获胜**。</span><span class="sxs-lookup"><span data-stu-id="9c72e-138">We haven’t set up that part of the solution yet, so you should not set the stage to **Closed Won**.</span></span>  
  
    5.  <span data-ttu-id="9c72e-139">指定为其他可选字段的值，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="9c72e-139">Specify values for other optional fields and then click **Save**.</span></span>  
  
    6.  <span data-ttu-id="9c72e-140">在有机会页上，为 Customer1 下,**产品**部分中，单击**添加产品**。</span><span class="sxs-lookup"><span data-stu-id="9c72e-140">On the Opportunity page for Customer1, under the **Products** section, click **Add Product**.</span></span>  
  
    7.  <span data-ttu-id="9c72e-141">从产品的列表中，选择客户有兴趣的产品，然后单击**选择**。</span><span class="sxs-lookup"><span data-stu-id="9c72e-141">From the list of products, select the products that the customer is interested in, and then click **Select**.</span></span>  
  
    8.  <span data-ttu-id="9c72e-142">对于每个所选的产品，指定客户想要数量，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="9c72e-142">For each selected product, specify a quantity that the customer wants, and then click **Save**.</span></span>  
  
         <span data-ttu-id="9c72e-143">![将产品添加到有机会](../core/media/bts-sf-add-product.gif "BTS_SF_Add_Product")</span><span class="sxs-lookup"><span data-stu-id="9c72e-143">![Add products to an opportunity](../core/media/bts-sf-add-product.gif "BTS_SF_Add_Product")</span></span>  
  
## <a name="create-a-salesforce-workflow"></a><span data-ttu-id="9c72e-144">创建 Salesforce 工作流</span><span class="sxs-lookup"><span data-stu-id="9c72e-144">Create a Salesforce Workflow</span></span>  
 <span data-ttu-id="9c72e-145">在此步骤中，我们将创建一个工作流，用于在每次机会成功关闭时发送通知。</span><span class="sxs-lookup"><span data-stu-id="9c72e-145">In this step we create a workflow to send out a notification every time an opportunity is closed successfully.</span></span> <span data-ttu-id="9c72e-146">通知的 SOAP 消息的格式并发送到中继终结点上承载[!INCLUDE[winazure](../includes/winazure-md.md)] [!INCLUDE[sb](../includes/sb-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9c72e-146">The notification is in the form of a SOAP message and is sent to a relay endpoint hosted on [!INCLUDE[winazure](../includes/winazure-md.md)][!INCLUDE[sb](../includes/sb-md.md)].</span></span>  
  
#### <a name="to-create-a-workflow-for-opportunities"></a><span data-ttu-id="9c72e-147">为机会创建工作流</span><span class="sxs-lookup"><span data-stu-id="9c72e-147">To create a workflow for opportunities</span></span>  
  
1.  <span data-ttu-id="9c72e-148">在 Salesforce 门户中，单击您在页上，右上角的登录名，然后单击**安装**。</span><span class="sxs-lookup"><span data-stu-id="9c72e-148">On the Salesforce portal, click your login name at the top right corner of the page, and then click **Setup**.</span></span>  
  
2.  <span data-ttu-id="9c72e-149">在左窗格中，在**应用安装程序**，展开**创建**，展开**工作流和审批**，然后单击**工作流规则**。</span><span class="sxs-lookup"><span data-stu-id="9c72e-149">In the left pane, under **App Setup**, expand **Create**, expand **Workflow & Approvals**, and then click **Workflow Rules**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c72e-150">如果你是首次打开“工作流规则”页，则系统会向你显示一些信息，让你了解工作流在 Salesforce 中是如何工作的。</span><span class="sxs-lookup"><span data-stu-id="9c72e-150">If you are opening the Workflow Rules page for the first time, you will be presented with some information to understand how workflows work in Salesforce.</span></span> <span data-ttu-id="9c72e-151">阅读通过信息，然后单击**继续**。</span><span class="sxs-lookup"><span data-stu-id="9c72e-151">Read through the information and then click **Continue**.</span></span>  
  
3.  <span data-ttu-id="9c72e-152">上**所有工作流规则**页上，单击**新规则**。</span><span class="sxs-lookup"><span data-stu-id="9c72e-152">On the **All Workflow Rules** page, click **New Rule**.</span></span>  
  
4.  <span data-ttu-id="9c72e-153">从**选择对象**列表中，单击**机会**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9c72e-153">From the **Select Object** list, click **Opportunity**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="9c72e-154">在下一页中，指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="9c72e-154">In the next page, specify the following:</span></span>  
  
    1.  <span data-ttu-id="9c72e-155">设置**规则名称**作为`Closed Opportunity`。</span><span class="sxs-lookup"><span data-stu-id="9c72e-155">Set the **Rule Name** as `Closed Opportunity`.</span></span>  
  
    2.  <span data-ttu-id="9c72e-156">设置**评估条件**作为**创建，和其进行编辑以随后满足条件的任何时间**。</span><span class="sxs-lookup"><span data-stu-id="9c72e-156">Set the **Evaluation Criteria** as **created, and any time it’s edited to subsequently meet criteria**.</span></span>  
  
    3.  <span data-ttu-id="9c72e-157">有关**规则条件**，设置以运行规则时**满足条件**。</span><span class="sxs-lookup"><span data-stu-id="9c72e-157">For the **Rule Criteria**, set to run the rule when the **criteria are met**.</span></span>  
  
    4.  <span data-ttu-id="9c72e-158">设置**字段**到**机会： 阶段**，**运算符**到**等于**，和**值**到`Closed Won`.</span><span class="sxs-lookup"><span data-stu-id="9c72e-158">Set **Field** to **Opportunity: Stage**, **Operator** to **equals**, and **Value** to `Closed Won`.</span></span>  
  
         <span data-ttu-id="9c72e-159">![创建工作流，Salesforce](../core/media/bts-sf-create-workflow.jpg "BTS_SF_Create_Workflow")</span><span class="sxs-lookup"><span data-stu-id="9c72e-159">![Create a Salesforce workflow](../core/media/bts-sf-create-workflow.jpg "BTS_SF_Create_Workflow")</span></span>  
  
    5.  <span data-ttu-id="9c72e-160">单击**保存和下一步**。</span><span class="sxs-lookup"><span data-stu-id="9c72e-160">Click **Save & Next**.</span></span>  
  
6.  <span data-ttu-id="9c72e-161">为新规则定义工作流操作：</span><span class="sxs-lookup"><span data-stu-id="9c72e-161">Define the workflow action for the new rule:</span></span>  
  
    1.  <span data-ttu-id="9c72e-162">上**指定工作流操作**页上，单击**添加工作流操作**按钮，然后单击**新的出站消息**。</span><span class="sxs-lookup"><span data-stu-id="9c72e-162">On the **Specify Workflow Actions** page, click **Add Workflow Action** button and then click **New Outbound Message**.</span></span>  
  
    2.  <span data-ttu-id="9c72e-163">设置**名称**和**唯一名称**字段设置为`NewOp1`。</span><span class="sxs-lookup"><span data-stu-id="9c72e-163">Set the **Name** and **Unique Name** fields to `NewOp1`.</span></span>  
  
    3.  <span data-ttu-id="9c72e-164">例如，指定的描述， `Message sent when an opportunity is successfully closed`。</span><span class="sxs-lookup"><span data-stu-id="9c72e-164">Specify a description, such as, the `Message sent when an opportunity is successfully closed`.</span></span>  
  
    4.  <span data-ttu-id="9c72e-165">指定**终结点 URL**作为`https://btssalesforce.servicebus.windows.net/notifications/opportunity`。</span><span class="sxs-lookup"><span data-stu-id="9c72e-165">Specify the **Endpoint URL** as `https://btssalesforce.servicebus.windows.net/notifications/opportunity`.</span></span>  
  
         <span data-ttu-id="9c72e-166">在这里， **btssalesforce**是你[!INCLUDE[sb](../includes/sb-md.md)]在之前的步骤中创建的命名空间。</span><span class="sxs-lookup"><span data-stu-id="9c72e-166">Here, **btssalesforce** is your [!INCLUDE[sb](../includes/sb-md.md)] namespace that you created in earlier steps.</span></span> <span data-ttu-id="9c72e-167">**/notifications/机会/** 表示我们将在本教程的后续步骤中创建的中继。</span><span class="sxs-lookup"><span data-stu-id="9c72e-167">**/notifications/opportunity/** represents the relay that we will create in later steps of this tutorial.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="9c72e-168">你必须指定你在前面创建的 [!INCLUDE[sb](../includes/sb-md.md)] 命名空间。</span><span class="sxs-lookup"><span data-stu-id="9c72e-168">You must specify the [!INCLUDE[sb](../includes/sb-md.md)] namespace that you created earlier.</span></span>  
  
    5.  <span data-ttu-id="9c72e-169">请确保**保护组件**复选框已清除与**发送会话 ID**选中复选框。</span><span class="sxs-lookup"><span data-stu-id="9c72e-169">Make sure the **Protected Component** check box is clear and the **Send Session ID** check box is checked.</span></span>  
  
    6.  <span data-ttu-id="9c72e-170">有关**机会字段发送**选择从的相关字段**可用字段**列表，然后单击**添加**按钮。</span><span class="sxs-lookup"><span data-stu-id="9c72e-170">For **Opportunity fields to send** select the relevant fields from the **Available Fields** list and then click the **Add** button.</span></span>  
  
    7.  <span data-ttu-id="9c72e-171">单击**保存**，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="9c72e-171">Click **Save** and then click **Done**.</span></span>  
  
    8.  <span data-ttu-id="9c72e-172">在左窗格中，在**应用安装程序**，展开**创建**，展开**工作流和审批**，然后单击**工作流规则**。</span><span class="sxs-lookup"><span data-stu-id="9c72e-172">In the left pane, under **App Setup**, expand **Create**, expand **Workflow & Approvals**, and then click **Workflow Rules**.</span></span> <span data-ttu-id="9c72e-173">验证**关闭机会**存在列出规则。</span><span class="sxs-lookup"><span data-stu-id="9c72e-173">Verify that the **Closed Opportunity** rule is listed there.</span></span> <span data-ttu-id="9c72e-174">下**操作**列**关闭机会**规则，请单击**激活**以启用该规则。</span><span class="sxs-lookup"><span data-stu-id="9c72e-174">Under the **Action** column for the **Closed Opportunity** rule, click **Activate** to activate the rule.</span></span>  
  
## <a name="create-a-salesforce-connected-application"></a><span data-ttu-id="9c72e-175">创建与 Salesforce 连接的应用程序</span><span class="sxs-lookup"><span data-stu-id="9c72e-175">Create a Salesforce Connected Application</span></span>  
 <span data-ttu-id="9c72e-176">创建连接的应用程序定义时，将生成一组请求用于访问并连接到 Salesforce 的 OAuth 令牌所需的密钥。</span><span class="sxs-lookup"><span data-stu-id="9c72e-176">Creating a connected application definition generates a set of keys required to request OAuth tokens to access to connect to Salesforce.</span></span> <span data-ttu-id="9c72e-177">在本教程中的后面阶段，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将成为使用连接的应用程序定义查询 Salesforce 的连接应用程序。</span><span class="sxs-lookup"><span data-stu-id="9c72e-177">In the later stages of this tutorial, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will be the connected application that queries Salesforce using the connected application definition.</span></span>  
  
#### <a name="to-create-a-connected-application-for-salesforce"></a><span data-ttu-id="9c72e-178">为 Salesforce 创建连接应用程序定义</span><span class="sxs-lookup"><span data-stu-id="9c72e-178">To create a connected application for Salesforce</span></span>  
  
1.  <span data-ttu-id="9c72e-179">在 Salesforce 门户中，单击您在页上，右上角的登录名，然后单击**安装**。</span><span class="sxs-lookup"><span data-stu-id="9c72e-179">On the Salesforce portal, click your login name at the top right corner of the page, and then click **Setup**.</span></span>  
  
2.  <span data-ttu-id="9c72e-180">在左窗格中，在**应用安装程序**，展开**创建**，然后展开**应用**。</span><span class="sxs-lookup"><span data-stu-id="9c72e-180">In the left pane, under **App Setup**, expand **Create**, and then expand **Apps**.</span></span> <span data-ttu-id="9c72e-181">上**应用**页上，在**连接应用**部分中，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="9c72e-181">On the **Apps** page, under the **Connected Apps** section, click **New**.</span></span>  
  
3.  <span data-ttu-id="9c72e-182">在**新连接应用程序**页上，指定下列各项：</span><span class="sxs-lookup"><span data-stu-id="9c72e-182">In the **New Connection App** page, specify the following:</span></span>  
  
    1.  <span data-ttu-id="9c72e-183">有关**连接应用程序名称**，指定`BizTalk_Salesforce`。</span><span class="sxs-lookup"><span data-stu-id="9c72e-183">For **Connected App Name**, specify `BizTalk_Salesforce`.</span></span>  
  
    2.  <span data-ttu-id="9c72e-184">有关**开发人员姓名**，指定你的日志名称。</span><span class="sxs-lookup"><span data-stu-id="9c72e-184">For **Developer Name**, specify your log on name.</span></span>  
  
    3.  <span data-ttu-id="9c72e-185">有关**联系人电子邮件**，指定你的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9c72e-185">For **Contact Email**, specify your e-mail.</span></span>  
  
    4.  <span data-ttu-id="9c72e-186">有关**回调 URL**，指定有效的 URL。</span><span class="sxs-lookup"><span data-stu-id="9c72e-186">For **Callback URL**, specify a valid URL.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="9c72e-187">鉴于在此方案中我们向 Salesforce 进行身份验证的方式，不使用你在此处指定的值。</span><span class="sxs-lookup"><span data-stu-id="9c72e-187">Because of the way we authenticate with Salesforce in this scenario, the value you specify here is not used.</span></span>  
  
    5.  <span data-ttu-id="9c72e-188">下**可用的 OAuth 作用域**，选择**完全访问**，**随时替你执行请求**，和**访问和管理数据**，然后单击**添加**按钮以将它们移到**选择 OAuth 作用域**。</span><span class="sxs-lookup"><span data-stu-id="9c72e-188">Under **Available OAuth Scopes**, select **Full access**, **Perform requests on your behalf at any time**, and **Access and manage your data** and then click the **Add** button to move them into the **Selected OAuth Scopes**.</span></span>  
  
    6.  <span data-ttu-id="9c72e-189">单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="9c72e-189">Click **Save**.</span></span> <span data-ttu-id="9c72e-190">显示的页，包含有关的信息**使用者密钥**和**使用者机密**。</span><span class="sxs-lookup"><span data-stu-id="9c72e-190">The page that appears contains information about the **Consumer Key** and **Consumer Secret**.</span></span> <span data-ttu-id="9c72e-191">你必须记下这些值。</span><span class="sxs-lookup"><span data-stu-id="9c72e-191">You must make a note of these values.</span></span> <span data-ttu-id="9c72e-192">从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 连接到 Salesforce 时，将需要这些值。</span><span class="sxs-lookup"><span data-stu-id="9c72e-192">You will need these values while connecting to Salesforce from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
         <span data-ttu-id="9c72e-193">![为 Salesforce 访问密钥](../core/media/bts-sf-consumer-keys.jpg "BTS_SF_Consumer_Keys")</span><span class="sxs-lookup"><span data-stu-id="9c72e-193">![Keys for Salesforce access](../core/media/bts-sf-consumer-keys.jpg "BTS_SF_Consumer_Keys")</span></span>  
  
4.  <span data-ttu-id="9c72e-194">最后，生成从未知的网络位置连接到 Salesforce 时所需的安全令牌。</span><span class="sxs-lookup"><span data-stu-id="9c72e-194">Finally, generate a security token required for connecting to Salesforce from unknown network locations.</span></span>  
  
    1.  <span data-ttu-id="9c72e-195">在 Salesforce 门户的左窗格下**个人设置**，展开**个人信息**，然后单击**重置我的安全令牌**。</span><span class="sxs-lookup"><span data-stu-id="9c72e-195">On the left pane of the Salesforce portal, under **Personal Setup**, expand **Personal Information**, and then click **Reset My Security Token**.</span></span>  
  
    2.  <span data-ttu-id="9c72e-196">阅读警告，然后单击**重置安全令牌**。</span><span class="sxs-lookup"><span data-stu-id="9c72e-196">Read the warning and then click **Reset Security Token**.</span></span>  
  
    3.  <span data-ttu-id="9c72e-197">你应该使用在创建你的 Salesforce 帐户时指定的电子邮件地址来接收安全令牌。</span><span class="sxs-lookup"><span data-stu-id="9c72e-197">You should receive the security token at the e-mail address you specified while creating your Salesforce account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c72e-198">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9c72e-198">See Also</span></span>  
 [<span data-ttu-id="9c72e-199">教程 6： 将与 Salesforce 集成 BizTalk Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c72e-199">Tutorial 6: Integrating BizTalk Server 2013 with Salesforce</span></span>](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)