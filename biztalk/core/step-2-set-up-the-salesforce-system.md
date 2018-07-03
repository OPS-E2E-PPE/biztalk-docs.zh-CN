---
title: 步骤 2： 设置 Salesforce 系统 |Microsoft Docs
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
ms.openlocfilehash: 772c18f87351d17b726ad498122715659dca79bc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986526"
---
# <a name="step-2-set-up-the-salesforce-system"></a><span data-ttu-id="8e652-102">步骤 2： 设置 Salesforce 系统</span><span class="sxs-lookup"><span data-stu-id="8e652-102">Step 2: Set up the Salesforce System</span></span>
<span data-ttu-id="8e652-103">在此步骤中，你要将 Salesforce 配置为在机会成功关闭时发送通知。</span><span class="sxs-lookup"><span data-stu-id="8e652-103">In this step, you configure Salesforce to send notifications when an opportunity is successfully closed.</span></span> <span data-ttu-id="8e652-104">你需要先执行以下步骤，然后才能发送通知：</span><span class="sxs-lookup"><span data-stu-id="8e652-104">Before you can send notifications, you need to perform the following steps:</span></span>  
  
-   <span data-ttu-id="8e652-105">在 Salesforce 中创建帐户。</span><span class="sxs-lookup"><span data-stu-id="8e652-105">Create an account in Salesforce.</span></span> <span data-ttu-id="8e652-106">帐户代表 Northwind 的客户。</span><span class="sxs-lookup"><span data-stu-id="8e652-106">An account represents a customer for Northwind.</span></span>  
  
-   <span data-ttu-id="8e652-107">为帐户创建机会。</span><span class="sxs-lookup"><span data-stu-id="8e652-107">Create an opportunity for the account.</span></span> <span data-ttu-id="8e652-108">机会代表客户所带来的潜在销售机会。</span><span class="sxs-lookup"><span data-stu-id="8e652-108">An opportunity represents a prospective sales opportunity with the customer.</span></span> <span data-ttu-id="8e652-109">在机会中，你还可以添加客户感兴趣的产品详细信息。</span><span class="sxs-lookup"><span data-stu-id="8e652-109">As part of the opportunity, you also add the product details that the customer is interested in.</span></span>  
  
-   <span data-ttu-id="8e652-110">在 Salesforce 中创建工作流。</span><span class="sxs-lookup"><span data-stu-id="8e652-110">Create a workflow in Salesforce.</span></span>  
  
-   <span data-ttu-id="8e652-111">创建与 Salesforce 连接的应用程序定义。</span><span class="sxs-lookup"><span data-stu-id="8e652-111">Create a Salesforce connected application definition.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8e652-112">本主题中的步骤假定你已拥有 Salesforce 开发人员帐户。</span><span class="sxs-lookup"><span data-stu-id="8e652-112">The steps in this topic assume that you already have a Salesforce developer account.</span></span> <span data-ttu-id="8e652-113">若要在 Salesforce 中创建新的开发人员帐户，请转到[ http://go.microsoft.com/fwlink/?LinkId=296424 ](http://go.microsoft.com/fwlink/?LinkId=296424)。</span><span class="sxs-lookup"><span data-stu-id="8e652-113">To create a new developer account in Salesforce, go to [http://go.microsoft.com/fwlink/?LinkId=296424](http://go.microsoft.com/fwlink/?LinkId=296424).</span></span>  
  
### <a name="to-create-an-account-in-salesforce"></a><span data-ttu-id="8e652-114">在 Salesforce 中创建帐户</span><span class="sxs-lookup"><span data-stu-id="8e652-114">To create an Account in Salesforce</span></span>  
  
1.  <span data-ttu-id="8e652-115">使用你的开发人员凭据登录到 Salesforce.com 门户。</span><span class="sxs-lookup"><span data-stu-id="8e652-115">Log on to the Salesforce.com portal using your developer credentials.</span></span>  
  
2.  <span data-ttu-id="8e652-116">在门户中，单击**帐户**选项卡，然后依次**新建**。</span><span class="sxs-lookup"><span data-stu-id="8e652-116">On the portal, click the **Accounts** tab, and then click **New**.</span></span>  
  
3.  <span data-ttu-id="8e652-117">上**新的帐户**页上，为各字段提供值。</span><span class="sxs-lookup"><span data-stu-id="8e652-117">On the **New Account** page, provide values for the various fields.</span></span> <span data-ttu-id="8e652-118">为指定值**帐户名**是必需的。</span><span class="sxs-lookup"><span data-stu-id="8e652-118">Specifying a value for **Account Name** is mandatory.</span></span> <span data-ttu-id="8e652-119">对于本教程中，帐户名称指定为`Customer1`。</span><span class="sxs-lookup"><span data-stu-id="8e652-119">For this tutorial, specify the account name as `Customer1`.</span></span>  
  
4.  <span data-ttu-id="8e652-120">单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="8e652-120">Click **Save**.</span></span>  
  
### <a name="to-create-an-opportunity-for-the-customer"></a><span data-ttu-id="8e652-121">为客户创建机会</span><span class="sxs-lookup"><span data-stu-id="8e652-121">To create an Opportunity for the customer</span></span>  
  
1. <span data-ttu-id="8e652-122">在 Salesforce.com 门户中，单击**机会**选项卡。</span><span class="sxs-lookup"><span data-stu-id="8e652-122">On the Salesforce.com portal, click the **Opportunities** tab.</span></span>  
  
2. <span data-ttu-id="8e652-123">在中**最近的机会**部分中，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="8e652-123">In the **Recent Opportunities** section, click **New**.</span></span>  
  
3. <span data-ttu-id="8e652-124">在“新建机会”页中，指定以下值：</span><span class="sxs-lookup"><span data-stu-id="8e652-124">In the New Opportunity page, specify the following values:</span></span>  
  
   1. <span data-ttu-id="8e652-125">指定**机会名称**，例如， `Opportunity with Customer 1`。</span><span class="sxs-lookup"><span data-stu-id="8e652-125">Specify an **Opportunity Name**, for example, `Opportunity with Customer 1`.</span></span>  
  
   2. <span data-ttu-id="8e652-126">指定**帐户名**。</span><span class="sxs-lookup"><span data-stu-id="8e652-126">Specify the **Account Name**.</span></span> <span data-ttu-id="8e652-127">此项表示与该机会关联的帐户。</span><span class="sxs-lookup"><span data-stu-id="8e652-127">This represents the account with which this opportunity is associated.</span></span> <span data-ttu-id="8e652-128">对于本教程中，设置该帐户为`Customer1`。</span><span class="sxs-lookup"><span data-stu-id="8e652-128">For this tutorial, set the Account to `Customer1`.</span></span> <span data-ttu-id="8e652-129">你已在上一步中创建了此帐户。</span><span class="sxs-lookup"><span data-stu-id="8e652-129">You created this account in the previous procedure.</span></span>  
  
   3. <span data-ttu-id="8e652-130">指定**关闭日期**。</span><span class="sxs-lookup"><span data-stu-id="8e652-130">Specify a **Close Date**.</span></span> <span data-ttu-id="8e652-131">此项表示机会应截止的日期。</span><span class="sxs-lookup"><span data-stu-id="8e652-131">This represents the date by which the opportunity should be closed.</span></span>  
  
   4. <span data-ttu-id="8e652-132">指定**阶段**。</span><span class="sxs-lookup"><span data-stu-id="8e652-132">Specify a **Stage**.</span></span> <span data-ttu-id="8e652-133">此项表示机会的当前阶段。</span><span class="sxs-lookup"><span data-stu-id="8e652-133">This denotes the current stage for the opportunity.</span></span> <span data-ttu-id="8e652-134">开始时，您可以将机会设置为任何内容，例如，**需要分析**。</span><span class="sxs-lookup"><span data-stu-id="8e652-134">To start with, you can set the opportunity to anything, for example, **Needs Analysis**.</span></span>  
  
       <span data-ttu-id="8e652-135">![在 Salesforce 中创建机会](../core/media/bts-sf-create-opp.jpg "BTS_SF_Create_Opp")</span><span class="sxs-lookup"><span data-stu-id="8e652-135">![Create an opportunity in Salesforce](../core/media/bts-sf-create-opp.jpg "BTS_SF_Create_Opp")</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="8e652-136">请确保未将阶段设置为**已结束-赢得**开始。</span><span class="sxs-lookup"><span data-stu-id="8e652-136">Make sure you do not set the stage to **Closed Won** to start with.</span></span> <span data-ttu-id="8e652-137">本教程中，每次将阶段设置中的方案**已结束-赢得**上将通知发送到中继终结点[!INCLUDE[winazure](../includes/winazure-md.md)] [!INCLUDE[sb](../includes/sb-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8e652-137">For the scenario in this tutorial, every time the stage is set to **Closed Won** a notification is sent to a relay endpoint on [!INCLUDE[winazure](../includes/winazure-md.md)][!INCLUDE[sb](../includes/sb-md.md)].</span></span> <span data-ttu-id="8e652-138">我们尚未设置解决方案的该部分，因此不应将阶段设置为**已结束-赢得**。</span><span class="sxs-lookup"><span data-stu-id="8e652-138">We haven’t set up that part of the solution yet, so you should not set the stage to **Closed Won**.</span></span>  
  
   5. <span data-ttu-id="8e652-139">指定的其他可选字段的值，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="8e652-139">Specify values for other optional fields and then click **Save**.</span></span>  
  
   6. <span data-ttu-id="8e652-140">在有机会页上为 Customer1 下,**产品**部分中，单击**添加产品**。</span><span class="sxs-lookup"><span data-stu-id="8e652-140">On the Opportunity page for Customer1, under the **Products** section, click **Add Product**.</span></span>  
  
   7. <span data-ttu-id="8e652-141">从产品的列表中，选择客户感兴趣的产品，然后单击**选择**。</span><span class="sxs-lookup"><span data-stu-id="8e652-141">From the list of products, select the products that the customer is interested in, and then click **Select**.</span></span>  
  
   8. <span data-ttu-id="8e652-142">对于每个所选的产品，指定以客户所需的数量，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="8e652-142">For each selected product, specify a quantity that the customer wants, and then click **Save**.</span></span>  
  
       <span data-ttu-id="8e652-143">![向机会添加产品](../core/media/bts-sf-add-product.gif "BTS_SF_Add_Product")</span><span class="sxs-lookup"><span data-stu-id="8e652-143">![Add products to an opportunity](../core/media/bts-sf-add-product.gif "BTS_SF_Add_Product")</span></span>  
  
## <a name="create-a-salesforce-workflow"></a><span data-ttu-id="8e652-144">创建 Salesforce 工作流</span><span class="sxs-lookup"><span data-stu-id="8e652-144">Create a Salesforce Workflow</span></span>  
 <span data-ttu-id="8e652-145">在此步骤中，我们将创建一个工作流，用于在每次机会成功关闭时发送通知。</span><span class="sxs-lookup"><span data-stu-id="8e652-145">In this step we create a workflow to send out a notification every time an opportunity is closed successfully.</span></span> <span data-ttu-id="8e652-146">通知采用 SOAP 消息的形式并发送到中继终结点上托管[!INCLUDE[winazure](../includes/winazure-md.md)] [!INCLUDE[sb](../includes/sb-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8e652-146">The notification is in the form of a SOAP message and is sent to a relay endpoint hosted on [!INCLUDE[winazure](../includes/winazure-md.md)][!INCLUDE[sb](../includes/sb-md.md)].</span></span>  
  
#### <a name="to-create-a-workflow-for-opportunities"></a><span data-ttu-id="8e652-147">为机会创建工作流</span><span class="sxs-lookup"><span data-stu-id="8e652-147">To create a workflow for opportunities</span></span>  
  
1. <span data-ttu-id="8e652-148">在 Salesforce 门户中，单击位于页面右上角的登录名，然后单击**安装程序**。</span><span class="sxs-lookup"><span data-stu-id="8e652-148">On the Salesforce portal, click your login name at the top right corner of the page, and then click **Setup**.</span></span>  
  
2. <span data-ttu-id="8e652-149">在左窗格中下,**应用安装程序**，展开**创建**，展开**工作流和审批**，然后单击**工作流规则**。</span><span class="sxs-lookup"><span data-stu-id="8e652-149">In the left pane, under **App Setup**, expand **Create**, expand **Workflow & Approvals**, and then click **Workflow Rules**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="8e652-150">如果你是首次打开“工作流规则”页，则系统会向你显示一些信息，让你了解工作流在 Salesforce 中是如何工作的。</span><span class="sxs-lookup"><span data-stu-id="8e652-150">If you are opening the Workflow Rules page for the first time, you will be presented with some information to understand how workflows work in Salesforce.</span></span> <span data-ttu-id="8e652-151">阅读的信息，然后单击**继续**。</span><span class="sxs-lookup"><span data-stu-id="8e652-151">Read through the information and then click **Continue**.</span></span>  
  
3. <span data-ttu-id="8e652-152">上**所有工作流规则**页上，单击**新规则**。</span><span class="sxs-lookup"><span data-stu-id="8e652-152">On the **All Workflow Rules** page, click **New Rule**.</span></span>  
  
4. <span data-ttu-id="8e652-153">从**选择对象**列表中，单击**机会**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="8e652-153">From the **Select Object** list, click **Opportunity**, and then click **Next**.</span></span>  
  
5. <span data-ttu-id="8e652-154">在下一页中，指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="8e652-154">In the next page, specify the following:</span></span>  
  
   1.  <span data-ttu-id="8e652-155">设置**规则名称**作为`Closed Opportunity`。</span><span class="sxs-lookup"><span data-stu-id="8e652-155">Set the **Rule Name** as `Closed Opportunity`.</span></span>  
  
   2.  <span data-ttu-id="8e652-156">设置**评估条件**作为**创建，并随时对其进行编辑以以后满足条件**。</span><span class="sxs-lookup"><span data-stu-id="8e652-156">Set the **Evaluation Criteria** as **created, and any time it’s edited to subsequently meet criteria**.</span></span>  
  
   3.  <span data-ttu-id="8e652-157">有关**规则条件**，设置为运行规则时**满足条件**。</span><span class="sxs-lookup"><span data-stu-id="8e652-157">For the **Rule Criteria**, set to run the rule when the **criteria are met**.</span></span>  
  
   4.  <span data-ttu-id="8e652-158">设置**字段**到**机会： 阶段**，**运算符**到**等于**，并**值**到`Closed Won`.</span><span class="sxs-lookup"><span data-stu-id="8e652-158">Set **Field** to **Opportunity: Stage**, **Operator** to **equals**, and **Value** to `Closed Won`.</span></span>  
  
        <span data-ttu-id="8e652-159">![创建 Salesforce 工作流](../core/media/bts-sf-create-workflow.jpg "BTS_SF_Create_Workflow")</span><span class="sxs-lookup"><span data-stu-id="8e652-159">![Create a Salesforce workflow](../core/media/bts-sf-create-workflow.jpg "BTS_SF_Create_Workflow")</span></span>  
  
   5.  <span data-ttu-id="8e652-160">单击**保存并下一步**。</span><span class="sxs-lookup"><span data-stu-id="8e652-160">Click **Save & Next**.</span></span>  
  
6. <span data-ttu-id="8e652-161">为新规则定义工作流操作：</span><span class="sxs-lookup"><span data-stu-id="8e652-161">Define the workflow action for the new rule:</span></span>  
  
   1. <span data-ttu-id="8e652-162">上**指定工作流操作**页上，单击**添加工作流操作**按钮，然后单击**新建出站消息**。</span><span class="sxs-lookup"><span data-stu-id="8e652-162">On the **Specify Workflow Actions** page, click **Add Workflow Action** button and then click **New Outbound Message**.</span></span>  
  
   2. <span data-ttu-id="8e652-163">设置**名称**并**唯一的名称**字段设置为`NewOp1`。</span><span class="sxs-lookup"><span data-stu-id="8e652-163">Set the **Name** and **Unique Name** fields to `NewOp1`.</span></span>  
  
   3. <span data-ttu-id="8e652-164">指定描述，例如， `Message sent when an opportunity is successfully closed`。</span><span class="sxs-lookup"><span data-stu-id="8e652-164">Specify a description, such as, the `Message sent when an opportunity is successfully closed`.</span></span>  
  
   4. <span data-ttu-id="8e652-165">指定**终结点 URL**作为`https://btssalesforce.servicebus.windows.net/notifications/opportunity`。</span><span class="sxs-lookup"><span data-stu-id="8e652-165">Specify the **Endpoint URL** as `https://btssalesforce.servicebus.windows.net/notifications/opportunity`.</span></span>  
  
       <span data-ttu-id="8e652-166">在这里， **btssalesforce**是你[!INCLUDE[sb](../includes/sb-md.md)]之前的步骤中创建的命名空间。</span><span class="sxs-lookup"><span data-stu-id="8e652-166">Here, **btssalesforce** is your [!INCLUDE[sb](../includes/sb-md.md)] namespace that you created in earlier steps.</span></span> <span data-ttu-id="8e652-167">**/notifications/opportunity/** 表示我们将在本教程的后续步骤中创建的中继。</span><span class="sxs-lookup"><span data-stu-id="8e652-167">**/notifications/opportunity/** represents the relay that we will create in later steps of this tutorial.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="8e652-168">你必须指定你在前面创建的 [!INCLUDE[sb](../includes/sb-md.md)] 命名空间。</span><span class="sxs-lookup"><span data-stu-id="8e652-168">You must specify the [!INCLUDE[sb](../includes/sb-md.md)] namespace that you created earlier.</span></span>  
  
   5. <span data-ttu-id="8e652-169">请确保**受保护的组件**复选框已清除并**发送会话 ID**选中复选框。</span><span class="sxs-lookup"><span data-stu-id="8e652-169">Make sure the **Protected Component** check box is clear and the **Send Session ID** check box is checked.</span></span>  
  
   6. <span data-ttu-id="8e652-170">有关**机会字段发送**中选择相关字段从**可用字段**列表，然后单击**添加**按钮。</span><span class="sxs-lookup"><span data-stu-id="8e652-170">For **Opportunity fields to send** select the relevant fields from the **Available Fields** list and then click the **Add** button.</span></span>  
  
   7. <span data-ttu-id="8e652-171">单击**保存**，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="8e652-171">Click **Save** and then click **Done**.</span></span>  
  
   8. <span data-ttu-id="8e652-172">在左窗格中下,**应用安装程序**，展开**创建**，展开**工作流和审批**，然后单击**工作流规则**。</span><span class="sxs-lookup"><span data-stu-id="8e652-172">In the left pane, under **App Setup**, expand **Create**, expand **Workflow & Approvals**, and then click **Workflow Rules**.</span></span> <span data-ttu-id="8e652-173">确认**关闭机会**列出规则。</span><span class="sxs-lookup"><span data-stu-id="8e652-173">Verify that the **Closed Opportunity** rule is listed there.</span></span> <span data-ttu-id="8e652-174">下**操作**的列**关闭机会**规则中，单击**激活**以启用该规则。</span><span class="sxs-lookup"><span data-stu-id="8e652-174">Under the **Action** column for the **Closed Opportunity** rule, click **Activate** to activate the rule.</span></span>  
  
## <a name="create-a-salesforce-connected-application"></a><span data-ttu-id="8e652-175">创建与 Salesforce 连接的应用程序</span><span class="sxs-lookup"><span data-stu-id="8e652-175">Create a Salesforce Connected Application</span></span>  
 <span data-ttu-id="8e652-176">创建连接的应用程序定义时，将生成一组请求用于访问并连接到 Salesforce 的 OAuth 令牌所需的密钥。</span><span class="sxs-lookup"><span data-stu-id="8e652-176">Creating a connected application definition generates a set of keys required to request OAuth tokens to access to connect to Salesforce.</span></span> <span data-ttu-id="8e652-177">在本教程中的后面阶段，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将成为使用连接的应用程序定义查询 Salesforce 的连接应用程序。</span><span class="sxs-lookup"><span data-stu-id="8e652-177">In the later stages of this tutorial, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will be the connected application that queries Salesforce using the connected application definition.</span></span>  
  
#### <a name="to-create-a-connected-application-for-salesforce"></a><span data-ttu-id="8e652-178">为 Salesforce 创建连接应用程序定义</span><span class="sxs-lookup"><span data-stu-id="8e652-178">To create a connected application for Salesforce</span></span>  
  
1. <span data-ttu-id="8e652-179">在 Salesforce 门户中，单击位于页面右上角的登录名，然后单击**安装程序**。</span><span class="sxs-lookup"><span data-stu-id="8e652-179">On the Salesforce portal, click your login name at the top right corner of the page, and then click **Setup**.</span></span>  
  
2. <span data-ttu-id="8e652-180">在左窗格中下,**应用安装程序**，展开**创建**，然后展开**应用**。</span><span class="sxs-lookup"><span data-stu-id="8e652-180">In the left pane, under **App Setup**, expand **Create**, and then expand **Apps**.</span></span> <span data-ttu-id="8e652-181">上**应用程序**页面上，在**连接的应用**部分中，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="8e652-181">On the **Apps** page, under the **Connected Apps** section, click **New**.</span></span>  
  
3. <span data-ttu-id="8e652-182">在中**新的连接应用**页上，指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="8e652-182">In the **New Connection App** page, specify the following:</span></span>  
  
   1. <span data-ttu-id="8e652-183">有关**连接应用名称**，指定`BizTalk_Salesforce`。</span><span class="sxs-lookup"><span data-stu-id="8e652-183">For **Connected App Name**, specify `BizTalk_Salesforce`.</span></span>  
  
   2. <span data-ttu-id="8e652-184">有关**开发人员姓名**，指定你的登录名。</span><span class="sxs-lookup"><span data-stu-id="8e652-184">For **Developer Name**, specify your log on name.</span></span>  
  
   3. <span data-ttu-id="8e652-185">有关**Contact Email**，指定你的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="8e652-185">For **Contact Email**, specify your e-mail.</span></span>  
  
   4. <span data-ttu-id="8e652-186">有关**回叫 URL**，指定有效的 URL。</span><span class="sxs-lookup"><span data-stu-id="8e652-186">For **Callback URL**, specify a valid URL.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="8e652-187">鉴于在此方案中我们向 Salesforce 进行身份验证的方式，不使用你在此处指定的值。</span><span class="sxs-lookup"><span data-stu-id="8e652-187">Because of the way we authenticate with Salesforce in this scenario, the value you specify here is not used.</span></span>  
  
   5. <span data-ttu-id="8e652-188">下**可用 OAuth 作用域**，选择**的完全访问权限**，**随时代表你执行请求**，和**访问和管理你的数据**，然后单击**添加**按钮以将其移入**所选 OAuth 作用域**。</span><span class="sxs-lookup"><span data-stu-id="8e652-188">Under **Available OAuth Scopes**, select **Full access**, **Perform requests on your behalf at any time**, and **Access and manage your data** and then click the **Add** button to move them into the **Selected OAuth Scopes**.</span></span>  
  
   6. <span data-ttu-id="8e652-189">单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="8e652-189">Click **Save**.</span></span> <span data-ttu-id="8e652-190">显示的页包含有关的信息**使用者密钥**并**使用者机密**。</span><span class="sxs-lookup"><span data-stu-id="8e652-190">The page that appears contains information about the **Consumer Key** and **Consumer Secret**.</span></span> <span data-ttu-id="8e652-191">你必须记下这些值。</span><span class="sxs-lookup"><span data-stu-id="8e652-191">You must make a note of these values.</span></span> <span data-ttu-id="8e652-192">从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 连接到 Salesforce 时，将需要这些值。</span><span class="sxs-lookup"><span data-stu-id="8e652-192">You will need these values while connecting to Salesforce from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
       <span data-ttu-id="8e652-193">![为 Salesforce 的访问密钥](../core/media/bts-sf-consumer-keys.jpg "BTS_SF_Consumer_Keys")</span><span class="sxs-lookup"><span data-stu-id="8e652-193">![Keys for Salesforce access](../core/media/bts-sf-consumer-keys.jpg "BTS_SF_Consumer_Keys")</span></span>  
  
4. <span data-ttu-id="8e652-194">最后，生成从未知的网络位置连接到 Salesforce 时所需的安全令牌。</span><span class="sxs-lookup"><span data-stu-id="8e652-194">Finally, generate a security token required for connecting to Salesforce from unknown network locations.</span></span>  
  
   1.  <span data-ttu-id="8e652-195">在 Salesforce 门户的左窗格下**个人的安装程序**，展开**个人信息**，然后单击**重置我的安全令牌**。</span><span class="sxs-lookup"><span data-stu-id="8e652-195">On the left pane of the Salesforce portal, under **Personal Setup**, expand **Personal Information**, and then click **Reset My Security Token**.</span></span>  
  
   2.  <span data-ttu-id="8e652-196">阅读该警告，然后单击**重置安全令牌**。</span><span class="sxs-lookup"><span data-stu-id="8e652-196">Read the warning and then click **Reset Security Token**.</span></span>  
  
   3.  <span data-ttu-id="8e652-197">你应该使用在创建你的 Salesforce 帐户时指定的电子邮件地址来接收安全令牌。</span><span class="sxs-lookup"><span data-stu-id="8e652-197">You should receive the security token at the e-mail address you specified while creating your Salesforce account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e652-198">请参阅</span><span class="sxs-lookup"><span data-stu-id="8e652-198">See Also</span></span>  
 [<span data-ttu-id="8e652-199">教程 6： 将 BizTalk Server 2013 与 Salesforce 集成</span><span class="sxs-lookup"><span data-stu-id="8e652-199">Tutorial 6: Integrating BizTalk Server 2013 with Salesforce</span></span>](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)