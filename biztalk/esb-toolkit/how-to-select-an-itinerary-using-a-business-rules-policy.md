---
title: "如何： 选择使用业务规则策略路线 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f6373a8-d9d6-46c6-95e3-f62dd33c342a
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d06bdea233c88fb740c728a414472d01a8fdc34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-select-an-itinerary-using-a-business-rules-policy"></a><span data-ttu-id="cb2ff-102">如何： 选择使用业务规则策略路线</span><span class="sxs-lookup"><span data-stu-id="cb2ff-102">How to: Select an Itinerary Using a Business Rules Policy</span></span>
## <a name="goal"></a><span data-ttu-id="cb2ff-103">目的</span><span class="sxs-lookup"><span data-stu-id="cb2ff-103">Goal</span></span>  
 <span data-ttu-id="cb2ff-104">本部分演示如何创建可用于选择一条路线基于收到的消息内容的业务规则以及如何配置路线选择器管道组件内泛型路线入口以调用这些规则。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-104">This section demonstrates how to create business rules that can be used to select an itinerary based on the content of a received message and how to configure the Itinerary Selector pipeline component within a generic itinerary on-ramp to call these rules.</span></span> <span data-ttu-id="cb2ff-105">本部分介绍在该消息将路由以不同方式，根据客户所在的地区一个业务方案。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-105">This section describes a business scenario in which messages are routed differently, based on the region in which the customer resides.</span></span>  
  
 <span data-ttu-id="cb2ff-106">在本操作方法主题中，你将完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="cb2ff-106">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="cb2ff-107">客户全局 Bank 西部和美国东部部门的的模型路线。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-107">Model itineraries for the Western and Eastern divisions of customer Global Bank.</span></span>  
  
-   <span data-ttu-id="cb2ff-108">创建将用于选择的处理请求路线的业务规则策略。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-108">Create business rules policies that will be used to select an itinerary for processing request.</span></span>  
  
-   <span data-ttu-id="cb2ff-109">配置要使用业务规则策略来选择适当的路线的路线选择器管道组件。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-109">Configure the Itinerary Selector pipeline component to use a business rules policy to select the appropriate itinerary.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cb2ff-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="cb2ff-110">Prerequisites</span></span>  
 <span data-ttu-id="cb2ff-111">此操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-111">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="cb2ff-112">开始之前</span><span class="sxs-lookup"><span data-stu-id="cb2ff-112">Before You Begin</span></span>  
 <span data-ttu-id="cb2ff-113">本操作方法主题中的更高版本执行的步骤之前，请完成以下任务：</span><span class="sxs-lookup"><span data-stu-id="cb2ff-113">Complete the following tasks before you perform the steps later in this How-to topic:</span></span>  
  
-   <span data-ttu-id="cb2ff-114">创建 GlobalBank 西部测试消息。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-114">Create the GlobalBank West test message.</span></span>  
  
-   <span data-ttu-id="cb2ff-115">创建 GlobalBank 东部测试消息。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-115">Create the GlobalBank East test message.</span></span>  
  
 <span data-ttu-id="cb2ff-116">下面的过程介绍如何执行其中每个操作。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-116">The following procedures describe how to do each of these.</span></span>  
  
#### <a name="to-create-the-globalbank-west-test-message"></a><span data-ttu-id="cb2ff-117">若要创建 GlobalBank 西部测试消息</span><span class="sxs-lookup"><span data-stu-id="cb2ff-117">To create the GlobalBank West test message</span></span>  
  
1.  <span data-ttu-id="cb2ff-118">在 Windows 资源管理器，浏览到 C:\HowTos。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-118">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="cb2ff-119">创建一份 NAOrderDoc.xml，并将其命名为复制 West.xml。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-119">Create a copy of NAOrderDoc.xml, and then name the copy West.xml.</span></span>  
  
3.  <span data-ttu-id="cb2ff-120">在记事本中，打开 West.xml，并将的值**customerName**元素**GlobalBankWest**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-120">In Notepad, open West.xml, and then change the value of the **customerName** element to **GlobalBankWest**.</span></span>  
  
4.  <span data-ttu-id="cb2ff-121">将 West.xml 另存为 utf-8，，然后关闭记事本。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-121">Save West.xml as UTF-8, and then close Notepad.</span></span>  
  
#### <a name="to-create-the-globalbank-east-test-message"></a><span data-ttu-id="cb2ff-122">若要创建 GlobalBank 东部测试消息</span><span class="sxs-lookup"><span data-stu-id="cb2ff-122">To create the GlobalBank East test message</span></span>  
  
1.  <span data-ttu-id="cb2ff-123">在 Windows 资源管理器，浏览到 C:\HowTos。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-123">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="cb2ff-124">创建一份 NAOrderDoc.xml，并将其命名为复制 East.xml。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-124">Create a copy of NAOrderDoc.xml, and then name the copy East.xml.</span></span>  
  
3.  <span data-ttu-id="cb2ff-125">在记事本中，打开 East.xml，并将的值**customerName**元素**GlobalBankEast**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-125">In Notepad, open East.xml, and then change the value of the **customerName** element to **GlobalBankEast**.</span></span>  
  
4.  <span data-ttu-id="cb2ff-126">将 East.xml 另存为 utf-8，，然后关闭记事本。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-126">Save East.xml as UTF-8, and then close Notepad.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="cb2ff-127">步骤</span><span class="sxs-lookup"><span data-stu-id="cb2ff-127">Steps</span></span>  
  
#### <a name="to-create-a-business-rules-engine-bre-policy-to-select-an-itinerary-using-custom-message-properties"></a><span data-ttu-id="cb2ff-128">若要创建业务规则引擎 (BRE) 策略来选择使用自定义消息属性路线</span><span class="sxs-lookup"><span data-stu-id="cb2ff-128">To create a Business Rules Engine (BRE) policy to select an itinerary using custom message properties</span></span>  
  
1.  <span data-ttu-id="cb2ff-129">单击**启动**在任务栏中，指向**所有程序**，指向 **[!INCLUDE[prague](../includes/prague-md.md)]** ，然后单击**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-129">Click **Start** on the taskbar, point to **All Programs**, point to **[!INCLUDE[prague](../includes/prague-md.md)]**, and then click **Business Rule Composer**.</span></span>  
  
2.  <span data-ttu-id="cb2ff-130">在策略资源管理器中，右键单击**策略**，然后单击**添加新策略**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-130">In Policy Explorer, right-click **Policies**, and then click **Add New Policy**.</span></span> <span data-ttu-id="cb2ff-131">命名策略时**ResolveItineraryBasedOnCustomer**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-131">Name the policy **ResolveItineraryBasedOnCustomer**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cb2ff-132">本操作指南主题的主题中创建使用相同的业务规则策略和路线[如何： 拆分将交换并将生成的消息路由到多个文件的位置使用不同路线](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md)。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-132">This How-to topic uses the same business rules policy and itineraries as those created in the topic [How to: Split an Interchange and Route the Resulting Messages to Multiple File Locations Using Distinct Itineraries](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md).</span></span> <span data-ttu-id="cb2ff-133">如果你已完成该部分，可以跳过本主题中后面到过程中，"以创建和配置 ESB 入口"。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-133">If you have already completed that section, you can skip to the procedure, "To create and configure an ESB on-ramp" later in this topic.</span></span>  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-west"></a><span data-ttu-id="cb2ff-134">若要添加客户 GlobalBank 西部选择规则</span><span class="sxs-lookup"><span data-stu-id="cb2ff-134">To add a selection rule for customer GlobalBank West</span></span>  
  
1.  <span data-ttu-id="cb2ff-135">在**ResolveItineraryBasedOnCustomer**策略，右键单击**（不保存） 1.0 版**，然后单击**添加新规则**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-135">In the **ResolveItineraryBasedOnCustomer** policy, right-click **Version 1.0 (not saved)**, and then click **Add New Rule**.</span></span> <span data-ttu-id="cb2ff-136">命名规则**SetGlobalBankWestItinerary**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-136">Name the rule **SetGlobalBankWestItinerary**.</span></span>  
  
2.  <span data-ttu-id="cb2ff-137">在事实数据资源管理器，单击**XML 架构**选项卡上，右键单击**架构**，然后单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-137">In Facts Explorer, click the **XML Schemas** tab, right-click **Schemas**, and then click **Browse**.</span></span>  
  
3.  <span data-ttu-id="cb2ff-138">在**架构文件**对话框中，浏览到 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB。DynamicResolution.Schemas，选择**NAOrderDoc.xsd**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-138">In the **Schema Files** dialog box, browse to C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB.DynamicResolution.Schemas, select **NAOrderDoc.xsd**, and then click **Open**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cb2ff-139">这是定义 NAOrderDoc.xml 消息，用于创建将用于测试的西部和东部消息的架构。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-139">This is the schema that defines the NAOrderDoc.xml message, which was used to create the West and East messages you will use for testing.</span></span>  
  
4.  <span data-ttu-id="cb2ff-140">在事实数据资源管理器，单击**NAOrderDoc.xsd**，单击**文档类型**属性在属性窗格中，然后键入**GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.</span><span class="sxs-lookup"><span data-stu-id="cb2ff-140">In Facts Explorer, click **NAOrderDoc.xsd**, click the **Document Type** property in the Properties pane, and then type **GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cb2ff-141">这是架构的完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-141">This is the fully qualified name of the schema.</span></span>  
  
5.  <span data-ttu-id="cb2ff-142">在事实数据资源管理器中，展开**NAOrderDoc.xsd**，然后展开**OrderDoc**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-142">In Facts Explorer, expand **NAOrderDoc.xsd**, and then expand **OrderDoc**.</span></span>  
  
6.  <span data-ttu-id="cb2ff-143">在规则窗口中，右键单击**条件**，指向**谓词**，然后单击**相等**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-143">In the Rule window, right-click **Conditions**, point to **Predicates**, and then click **Equal**.</span></span>  
  
7.  <span data-ttu-id="cb2ff-144">从事实数据资源管理器拖动**customerName**元素**argument1**节点下的**条件**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-144">From Facts Explorer, drag the **customerName** element to the **argument1** node under **Conditions**.</span></span>  
  
8.  <span data-ttu-id="cb2ff-145">单击**argument2**节点，并键入**GlobalBankWest**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-145">Click the **argument2** node, and then type **GlobalBankWest**.</span></span>  
  
9. <span data-ttu-id="cb2ff-146">在事实数据资源管理器，单击**词汇**选项卡。展开**ESB。路线**词汇，展开**版本 1.1**，然后拖动**设置路线名称**定义与**操作**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-146">In Facts Explorer, click the **Vocabularies** tab. Expand the **ESB.Itinerary** vocabulary, expand **Version 1.1**, and then drag the **Set Itinerary Name** definition to **Actions**.</span></span>  
  
10. <span data-ttu-id="cb2ff-147">单击**\<空字符串 >**，然后键入**GlobalBankWestItinerary**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-147">Click **\<empty string>**, and then type **GlobalBankWestItinerary**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cb2ff-148">更高版本在本操作方法主题中，你将创建处理这些消息的此路线，从 GlobalBank 西部。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-148">Later in this How-to topic, you will create this itinerary to process messages from GlobalBank West.</span></span>  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-east"></a><span data-ttu-id="cb2ff-149">若要为客户 GlobalBank 东部添加一个选择规则</span><span class="sxs-lookup"><span data-stu-id="cb2ff-149">To add a selection rule for Customer GlobalBank East</span></span>  
  
1.  <span data-ttu-id="cb2ff-150">在策略资源管理器中，右键单击**SetGlobalBankWestItinerary**规则，并依次**复制**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-150">In Policy Explorer, right-click the **SetGlobalBankWestItinerary** rule, and then click **Copy**.</span></span>  
  
2.  <span data-ttu-id="cb2ff-151">右键单击**（不保存） 1.0 版**，然后单击**粘贴**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-151">Right-click **Version 1.0 (not saved)**, and then click **Paste**.</span></span>  
  
3.  <span data-ttu-id="cb2ff-152">在**新规则名称**对话框中，键入**SetGlobalBankEastItinerary**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-152">In the **New Rule Name** dialog box, type **SetGlobalBankEastItinerary**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="cb2ff-153">在策略资源管理器，单击**SetGlobalBankEastItinerary**规则。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-153">In Policy Explorer, click the **SetGlobalBankEastItinerary** rule.</span></span>  
  
5.  <span data-ttu-id="cb2ff-154">在**条件**部分中，右键单击**GlobalBankWest**，然后单击**重置参数**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-154">In the **Conditions** section, right-click **GlobalBankWest**, and then click **Reset argument**.</span></span>  
  
6.  <span data-ttu-id="cb2ff-155">单击**argument2**，然后键入**GlobalBankEast**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-155">Click **argument2**, and then type **GlobalBankEast**.</span></span>  
  
7.  <span data-ttu-id="cb2ff-156">在**操作**部分中，右键单击**GlobalBankWestItinerary**，然后单击**重置参数**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-156">In the **Actions** section, right-click **GlobalBankWestItinerary**, and then click **Reset argument**.</span></span>  
  
8.  <span data-ttu-id="cb2ff-157">单击**\<空字符串 >**然后键入**GlobalBankEastItinerary**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-157">Click **\<empty string>** and then type **GlobalBankEastItinerary**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cb2ff-158">更高版本中的操作方法主题，你将从 GlobalBank 东处理这些消息创建此路线。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-158">Later in the How-to topic, you will create this itinerary to process messages from GlobalBank East.</span></span>  
  
#### <a name="to-publish-and-deploy-the-policy"></a><span data-ttu-id="cb2ff-159">若要发布和部署策略</span><span class="sxs-lookup"><span data-stu-id="cb2ff-159">To publish and deploy the policy</span></span>  
  
1.  <span data-ttu-id="cb2ff-160">在策略资源管理器下**ResolveItineraryBasedOnCustomer**策略中，右击**（不保存） 1.0 版**，然后单击**发布**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-160">In Policy Explorer, under the **ResolveItineraryBasedOnCustomer** policy, right click **Version 1.0 (not saved)**, and then click **Publish**.</span></span>  
  
2.  <span data-ttu-id="cb2ff-161">在策略资源管理器下**ResolveItineraryBasedOnCustomer**策略中，右击**版本 1.0-发布**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-161">In Policy Explorer, under the **ResolveItineraryBasedOnCustomer** policy, right click **Version 1.0 - Published**, and then click **Deploy**.</span></span>  
  
#### <a name="to-create-an-esb-itinerary-domain-specific-language-dsl-model-for-globalbank-west-messages"></a><span data-ttu-id="cb2ff-162">若要创建 GlobalBank 西部消息 ESB 路线域特定语言 (DSL) 模型</span><span class="sxs-lookup"><span data-stu-id="cb2ff-162">To create an ESB itinerary domain-specific language (DSL) model for GlobalBank West messages</span></span>  
  
1.  <span data-ttu-id="cb2ff-163">在[!INCLUDE[vs2010](../includes/vs2010-md.md)]，打开 C:\HowTos\Patterns\Patterns.sln。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-163">In [!INCLUDE[vs2010](../includes/vs2010-md.md)], open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="cb2ff-164">在解决方案资源管理器，右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-164">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="cb2ff-165">在**添加新项**对话框中，在模板窗格中，单击**ItineraryDsl**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-165">In the **Add New Item** dialog box, in the Templates pane, click **ItineraryDsl**.</span></span>  
  
4.  <span data-ttu-id="cb2ff-166">在**名称**框中，键入**GlobalBankWestItinerary**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-166">In the **Name** box, type **GlobalBankWestItinerary**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-globalbank-west-itinerary"></a><span data-ttu-id="cb2ff-167">若要配置 GlobalBank 西部路线的属性</span><span class="sxs-lookup"><span data-stu-id="cb2ff-167">To configure the properties of the GlobalBank West itinerary</span></span>  
  
1.  <span data-ttu-id="cb2ff-168">在 Visual Studio 中，单击的设计图面**GlobalBankWestItinerary.itinerary**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-168">In Visual Studio, click the design surface of **GlobalBankWestItinerary.itinerary**.</span></span> <span data-ttu-id="cb2ff-169">在**GlobalBankWestItinerary**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="cb2ff-169">In the **GlobalBankWestItinerary** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="cb2ff-170">在**模型导出程序**下拉列表中，单击**数据库路线导出程序**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-170">In the **Model Exporter** drop-down list, click **Database Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="cb2ff-171">单击旁边的省略号按钮 （...）**路线数据库**属性。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-171">Click the ellipsis button (...) next to the **Itinerary Database** property.</span></span>  
  
    3.  <span data-ttu-id="cb2ff-172">在**连接属性**对话框中，选择承载路线存储库数据库中，SQL Server，然后指定数据库的名称 (默认名称是**EsbItineraryDb**)。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-172">In the **Connection Properties** dialog box, choose the SQL Server that hosts the itinerary repository database, and then specify the name of the database (the default name is **EsbItineraryDb**).</span></span>  
  
2.  <span data-ttu-id="cb2ff-173">在**路线状态**下拉列表中，单击**已部署**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-173">In the **Itinerary Status** drop-down list, click **Deployed**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cb2ff-174">此步骤允许您将导出到一个中心存储库; 路线可以选择路线，并将其附加从在接收到消息时此存储库。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-174">This step enables you to export the itinerary to a central repository; itineraries can be selected and attached from this repository upon message reception.</span></span> <span data-ttu-id="cb2ff-175">更高版本，你将配置路线选择器管道组件配置为使用业务规则引擎冲突解决程序 (BRI) 要评估的入站的消息和从此存储库中选择相应的路线。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-175">You will later configure the Itinerary Selector pipeline component to use the Business Rules Engine resolver (BRI) to evaluate inbound messages and select the appropriate itinerary from this repository.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="cb2ff-176">若要定义路线的结构</span><span class="sxs-lookup"><span data-stu-id="cb2ff-176">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="cb2ff-177">从工具箱中，拖动**上负载增加**到设计图面上的模型元素。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-177">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="cb2ff-178">在**OnRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="cb2ff-178">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="cb2ff-179">单击**名称**属性，再然后键入**ReceiveNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-179">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="cb2ff-180">在**扩展程序**下拉列表中，单击**上负载增加 ESB 服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-180">In the **Extender** drop-down list, click **On-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="cb2ff-181">在**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-181">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="cb2ff-182">在**接收端口**下拉列表中，单击**OnRamp.Itinerary**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-182">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="cb2ff-183">从工具箱中，拖动**关闭负载增加**模型元素到设计图面，然后将其放到右侧**ReceiveNAOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-183">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **ReceiveNAOrder** model element.</span></span> <span data-ttu-id="cb2ff-184">在**OffRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="cb2ff-184">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="cb2ff-185">单击**名称**属性，再然后键入**SendNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-185">Click the **Name** property, and then type **SendNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="cb2ff-186">在**扩展程序**下拉列表中，单击**关闭负载增加 ESB 服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-186">In the **Extender** drop-down list, click **Off-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="cb2ff-187">在**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-187">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="cb2ff-188">在**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-188">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
3.  <span data-ttu-id="cb2ff-189">从工具箱中，拖动**路线服务**模型元素到设计图面，然后将它之间**ReceiveNAOrder**模型元素和**SendNAOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-189">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **ReceiveNAOrder** model element and the **SendNAOrder** model element.</span></span> <span data-ttu-id="cb2ff-190">在**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="cb2ff-190">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="cb2ff-191">单击**名称**属性，再然后键入**RouteMessage**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-191">Click the **Name** property, and then type **RouteMessage**.</span></span>  
  
    2.  <span data-ttu-id="cb2ff-192">在**路线服务扩展程序**下拉列表中，单击**关闭负载增加路线服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-192">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Itinerary Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="cb2ff-193">在**关闭负载增加**下拉列表中，展开**SendNAOrder**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-193">In the **Off-Ramp** drop-down list, expand **SendNAOrder**, and then click **Send Handlers**.</span></span>  
  
4.  <span data-ttu-id="cb2ff-194">右键单击**冲突解决程序**集合**RouteMessage**模型元素，并依次**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-194">Right-click the **Resolver** collection of the **RouteMessage** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="cb2ff-195">在**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="cb2ff-195">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="cb2ff-196">单击**名称**属性，再然后键入**StaticResolver**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-196">Click the **Name** property, and then type **StaticResolver**.</span></span>  
  
    2.  <span data-ttu-id="cb2ff-197">在**解析程序实现**下拉列表中，单击**静态冲突解决程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-197">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="cb2ff-198">在**传输名称**下拉列表中，单击**文件**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-198">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="cb2ff-199">单击**传输位置**属性，再然后键入**C:\HowTos\Out\West%MessageID%.xml**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-199">Click the **Transport Location** property, and then type **C:\HowTos\Out\West%MessageID%.xml**.</span></span>  
  
5.  <span data-ttu-id="cb2ff-200">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-200">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="cb2ff-201">将从连接**ReceiveNAOrder**到模型元素**RouteMessage**模型元素。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-201">Drag a connection from the **ReceiveNAOrder** model element to the **RouteMessage** model element.</span></span>  
  
6.  <span data-ttu-id="cb2ff-202">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-202">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="cb2ff-203">将从连接**RouteMessage**到模型元素**SendNAOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-203">Drag a connection from the **RouteMessage** model element to the **SendNAOrder** model element.</span></span>  
  
#### <a name="to-export-the-model-to-the-itinerary-database"></a><span data-ttu-id="cb2ff-204">将导出到路线的数据库的模型</span><span class="sxs-lookup"><span data-stu-id="cb2ff-204">To export the model to the itinerary database</span></span>  
  
1.  <span data-ttu-id="cb2ff-205">在 Visual Studio 中，右键单击的设计图面**GlobalBankWestItinerary**路线，，然后单击**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-205">In Visual Studio, right-click the design surface of the **GlobalBankWestItinerary** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cb2ff-206">路线已导出到路线的数据库，现在可以使用由路线选择器组件。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-206">The itinerary has been exported to the itinerary database and can now be used by the Itinerary Selector component.</span></span>  
  
2.  <span data-ttu-id="cb2ff-207">保存所有项目。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-207">Save all project artifacts.</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model-for-globalbank-east-message"></a><span data-ttu-id="cb2ff-208">若要创建 GlobalBank 东部消息 ESB 路线 DSL 模型</span><span class="sxs-lookup"><span data-stu-id="cb2ff-208">To create an ESB itinerary DSL model for GlobalBank East message</span></span>  
  
1.  <span data-ttu-id="cb2ff-209">在[!INCLUDE[vs2010](../includes/vs2010-md.md)]，打开 C:\HowTos\Patterns.sln。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-209">In [!INCLUDE[vs2010](../includes/vs2010-md.md)], open C:\HowTos\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="cb2ff-210">在解决方案资源管理器，右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-210">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="cb2ff-211">在**添加新项**对话框中，在模板窗格中，单击**ItineraryDsl**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-211">In the **Add New Item** dialog box, in the Templates pane, click **ItineraryDsl**.</span></span>  
  
4.  <span data-ttu-id="cb2ff-212">在**名称**框中，键入**GlobalBankEastItinerary**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-212">In the **Name** box, type **GlobalBankEastItinerary**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-globalbank-east-itinerary"></a><span data-ttu-id="cb2ff-213">若要配置 GlobalBank 东部路线的属性</span><span class="sxs-lookup"><span data-stu-id="cb2ff-213">To configure the properties of the GlobalBank East itinerary</span></span>  
  
1.  <span data-ttu-id="cb2ff-214">在 Visual Studio 中，单击的设计图面**GlobalBankEastItinerary.itinerary**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-214">In Visual Studio, click the design surface of **GlobalBankEastItinerary.itinerary**.</span></span> <span data-ttu-id="cb2ff-215">在**GlobalBankEastItinerary**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="cb2ff-215">In the **GlobalBankEastItinerary** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="cb2ff-216">在**模型导出程序**下拉列表中，单击**数据库路线导出程序**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-216">In the **Model Exporter** drop-down list, click **Database Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="cb2ff-217">单击旁边的省略号按钮 （...）**路线数据库**属性。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-217">Click the ellipsis button (...) next to the **Itinerary Database** property.</span></span>  
  
    3.  <span data-ttu-id="cb2ff-218">在**连接属性**对话框中，选择承载路线存储库数据库中，SQL Server，然后指定数据库的名称 (默认名称是**EsbItineraryDb**)。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-218">In the **Connection Properties** dialog box, choose the SQL Server that hosts the itinerary repository database, and then specify the name of the database (the default name is **EsbItineraryDb**).</span></span>  
  
2.  <span data-ttu-id="cb2ff-219">在**路线状态**下拉列表中，单击**已部署**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-219">In the **Itinerary Status** drop-down list, click **Deployed**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cb2ff-220">此步骤允许您将导出到一个中心存储库; 路线可以选择路线，并将其从此存储库中接收消息时附加。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-220">This step enables you to export the itinerary to a central repository; itineraries can be selected and attached from this repository when messages are received.</span></span> <span data-ttu-id="cb2ff-221">更高版本，你将配置路线选择器管道组件配置为使用 BRI 解析程序要评估的入站的消息和从此存储库中选择相应的路线。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-221">You will later configure the Itinerary Selector pipeline component to use the BRI resolver to evaluate inbound messages and select the appropriate itinerary from this repository.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="cb2ff-222">若要定义路线的结构</span><span class="sxs-lookup"><span data-stu-id="cb2ff-222">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="cb2ff-223">从工具箱中，拖动**上负载增加**到设计图面上的模型元素。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-223">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="cb2ff-224">在**OnRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="cb2ff-224">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="cb2ff-225">单击**名称**属性，再然后键入**ReceiveNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-225">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="cb2ff-226">在**扩展程序**下拉列表中，单击**上负载增加 ESB 服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-226">In the **Extender** drop-down list, click **On-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="cb2ff-227">在**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-227">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="cb2ff-228">在**接收端口**下拉列表中，单击**OnRamp.Itinerary**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-228">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="cb2ff-229">从工具箱中，拖动**关闭负载增加**模型元素到设计图面，然后将其放到右侧**ReceiveNAOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-229">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **ReceiveNAOrder** model element.</span></span> <span data-ttu-id="cb2ff-230">在**OffRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="cb2ff-230">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="cb2ff-231">单击**名称**属性，再然后键入**SendNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-231">Click the **Name** property, and then type **SendNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="cb2ff-232">在**扩展程序**下拉列表中，单击**关闭负载增加 ESB 服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-232">In the **Extender** drop-down list, click **Off-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="cb2ff-233">在**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-233">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="cb2ff-234">在**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-234">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
3.  <span data-ttu-id="cb2ff-235">从工具箱中，拖动**路线服务**模型元素到设计图面，然后将它之间**ReceiveNAOrder**模型元素和**SendNAOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-235">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **ReceiveNAOrder** model element and the **SendNAOrder** model element.</span></span> <span data-ttu-id="cb2ff-236">在**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="cb2ff-236">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="cb2ff-237">单击**名称**属性，再然后键入**RouteMessage**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-237">Click the **Name** property, and then type **RouteMessage**.</span></span>  
  
    2.  <span data-ttu-id="cb2ff-238">在**路线服务扩展程序**下拉列表中，单击**关闭负载增加路线服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-238">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Itinerary Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="cb2ff-239">在**关闭负载增加**下拉列表中，展开**SendNAOrder**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-239">In the **Off-Ramp** drop-down list, expand **SendNAOrder**, and then click **Send Handlers**.</span></span>  
  
4.  <span data-ttu-id="cb2ff-240">右键单击**冲突解决程序**集合**RouteMessage**模型元素，并依次**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-240">Right-click the **Resolver** collection of the **RouteMessage** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="cb2ff-241">在**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="cb2ff-241">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="cb2ff-242">单击**名称**属性，再然后键入**StaticResolver**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-242">Click the **Name** property, and then type **StaticResolver**.</span></span>  
  
    2.  <span data-ttu-id="cb2ff-243">在**解析程序实现**下拉列表中，单击**静态冲突解决程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-243">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="cb2ff-244">在**传输名称**下拉列表中，单击**文件**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-244">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="cb2ff-245">单击**传输位置**属性，再然后键入**C:\HowTos\Out\East%MessageID%.xml**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-245">Click the **Transport Location** property, and then type **C:\HowTos\Out\East%MessageID%.xml**.</span></span>  
  
5.  <span data-ttu-id="cb2ff-246">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-246">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="cb2ff-247">将从连接**ReceiveNAOrder**到模型元素**RouteMessage**模型元素。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-247">Drag a connection from the **ReceiveNAOrder** model element to the **RouteMessage** model element.</span></span>  
  
6.  <span data-ttu-id="cb2ff-248">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-248">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="cb2ff-249">将从连接**RouteMessage**到模型元素**SendNAOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-249">Drag a connection from the **RouteMessage** model element to the **SendNAOrder** model element.</span></span>  
  
#### <a name="to-export-the-model-to-the-itinerary-database"></a><span data-ttu-id="cb2ff-250">将导出到路线的数据库的模型</span><span class="sxs-lookup"><span data-stu-id="cb2ff-250">To export the model to the itinerary database</span></span>  
  
1.  <span data-ttu-id="cb2ff-251">在 Visual Studio 中，右键单击的设计图面**GlobalBankEastItinerary**路线，，然后单击**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-251">In Visual Studio, right-click the design surface of the **GlobalBankEastItinerary** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cb2ff-252">路线已导出到路线的数据库，现在可以使用由路线选择器组件。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-252">The itinerary has been exported to the itinerary database and can now be used by the Itinerary Selector component.</span></span>  
  
2.  <span data-ttu-id="cb2ff-253">保存所有项目。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-253">Save all project artifacts.</span></span>  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a><span data-ttu-id="cb2ff-254">若要创建和配置 ESB 入口</span><span class="sxs-lookup"><span data-stu-id="cb2ff-254">To create and configure an ESB on-ramp</span></span>  
  
1.  <span data-ttu-id="cb2ff-255">单击**启动**在任务栏中，指向**所有程序**，指向 **[!INCLUDE[prague](../includes/prague-md.md)]** ，然后单击**BizTalk Server 管理**.</span><span class="sxs-lookup"><span data-stu-id="cb2ff-255">Click **Start** on the taskbar, point to **All Programs**, point to **[!INCLUDE[prague](../includes/prague-md.md)]**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="cb2ff-256">在[!INCLUDE[prague](../includes/prague-md.md)]管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后展开**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-256">In the [!INCLUDE[prague](../includes/prague-md.md)] Administration Console, expand **BizTalk Group**, expand **Applications**, and then expand **Microsoft.Practices.ESB**.</span></span>  
  
3.  <span data-ttu-id="cb2ff-257">右键单击**接收位置**，指向**新建**，然后单击**单向接收位置**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-257">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
4.  <span data-ttu-id="cb2ff-258">在**选择接收端口**对话框中，单击**OnRamp.Itinerary**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-258">In the **Select a Receive Port** dialog box, click **OnRamp.Itinerary**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="cb2ff-259">在**接收位置属性**对话框中，在**名称**框中，键入**OnRamp.Itinerary.HowTo**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-259">In the **Receive Location Properties** dialog box, in the **Name** box, type **OnRamp.Itinerary.HowTo**.</span></span>  
  
6.  <span data-ttu-id="cb2ff-260">在**类型**下拉列表中，单击**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-260">In the **Type** drop-down list, click **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="cb2ff-261">在**文件传输属性**对话框中，在**接收文件夹**框中，键入**C:\HowTos\DropFolder**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-261">In the **FILE Transport Properties** dialog box, in the **Receive folder** box, type **C:\HowTos\DropFolder**, and then click **OK**.</span></span>  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a><span data-ttu-id="cb2ff-262">若要配置路线选择器管道组件</span><span class="sxs-lookup"><span data-stu-id="cb2ff-262">To configure the Itinerary Selector pipeline component</span></span>  
  
1.  <span data-ttu-id="cb2ff-263">在**接收位置属性**对话框中，在**接收管道**下拉列表中，单击**ItinerarySelectReceiveXml**，然后单击省略号按钮 （...).</span><span class="sxs-lookup"><span data-stu-id="cb2ff-263">In the **Receive Location Properties** dialog box, in the **Receive pipeline** drop-down list, click **ItinerarySelectReceiveXml**, and then click the ellipsis button (...).</span></span>  
  
2.  <span data-ttu-id="cb2ff-264">使用**配置管道**对话框中，配置以下各项**路线选择器**组件属性：</span><span class="sxs-lookup"><span data-stu-id="cb2ff-264">Use the **Configure Pipeline** dialog box to configure the following **Itinerary Selector** component properties:</span></span>  
  
    1.  <span data-ttu-id="cb2ff-265">单击**ItineraryFactKey**属性，再然后键入**Resolver.Itinerary**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-265">Click the **ItineraryFactKey** property, and then type **Resolver.Itinerary**.</span></span>  
  
    2.  <span data-ttu-id="cb2ff-266">单击**ResolverConnectionString**属性，再然后键入**BRI:\\\policy=ResolveItineraryBasedOnCustomer;useMsg=true;recognizeMessageFormat=true;**</span><span class="sxs-lookup"><span data-stu-id="cb2ff-266">Click the **ResolverConnectionString** property, and then type **BRI:\\\policy=ResolveItineraryBasedOnCustomer;useMsg=true;recognizeMessageFormat=true;**</span></span>  
  
    3.  <span data-ttu-id="cb2ff-267">单击**确定**关闭**配置管道**对话框。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-267">Click **OK** to close the **Configure Pipeline** dialog box.</span></span>  
  
3.  <span data-ttu-id="cb2ff-268">单击**确定**关闭**接收位置属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-268">Click **OK** to close the **Receive Location Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="cb2ff-269">在[!INCLUDE[prague](../includes/prague-md.md)]管理控制台中，右键单击**OnRamp.Itinerary.HowTo**接收位置，并依次**启用**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-269">In the [!INCLUDE[prague](../includes/prague-md.md)] Administration Console, right-click the **OnRamp.Itinerary.HowTo** receive location, and then click **Enable**.</span></span>  
  
#### <a name="to-test-the-itinerary-selector-and-business-rules"></a><span data-ttu-id="cb2ff-270">若要测试的路线的选择器和业务规则</span><span class="sxs-lookup"><span data-stu-id="cb2ff-270">To test the itinerary selector and business rules</span></span>  
  
1.  <span data-ttu-id="cb2ff-271">在 Windows 资源管理器，浏览到 C:\HowTos。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-271">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="cb2ff-272">复制 （不移动） 到 DropFolder 文件夹 East.xml 和 West.xml 的文件。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-272">Copy (do not move) the files East.xml and West.xml to the DropFolder folder.</span></span>  
  
3.  <span data-ttu-id="cb2ff-273">浏览到 C:\HowTos\Out。验证目录中已写的 East%MessageID%.xml 和 West%MessageID%.xml 消息。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-273">Browse to C:\HowTos\Out. Verify that the East%MessageID%.xml and West%MessageID%.xml messages have been written to the directory.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cb2ff-274">尽管除外客户元素的值相同，消息已处理使用不同路线，根据路线选择器管道组件的分辨率。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-274">Though identical except for the value of the customer element, the messages were processed using different itineraries, based on the resolution of the Itinerary Selector pipeline component.</span></span>  
  
4.  <span data-ttu-id="cb2ff-275">在[!INCLUDE[prague](../includes/prague-md.md)]管理控制台中，右键单击**OnRamp.Itinerary.HowTo**接收位置，并依次**禁用**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-275">In the [!INCLUDE[prague](../includes/prague-md.md)] Administration Console, right-click the **OnRamp.Itinerary.HowTo** receive location, and then click **Disable**.</span></span>  
  
5.  <span data-ttu-id="cb2ff-276">后**OnRamp.Itinerary.HowTo**接收位置处于禁用状态，右键单击它，，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-276">After the **OnRamp.Itinerary.HowTo** receive location is disabled, right-click it, and then click **Delete**.</span></span> <span data-ttu-id="cb2ff-277">在**确认删除接收位置**对话框中，单击**是**。</span><span class="sxs-lookup"><span data-stu-id="cb2ff-277">In the **Confirm delete receive location** dialog box, click **Yes**.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="cb2ff-278">其他资源</span><span class="sxs-lookup"><span data-stu-id="cb2ff-278">Additional Resources</span></span>  
 <span data-ttu-id="cb2ff-279">有关详细信息，请参阅下列相关主题：</span><span class="sxs-lookup"><span data-stu-id="cb2ff-279">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="cb2ff-280">如何： 拆分将交换，并将生成的消息路由到多个使用不同路线的文件位置</span><span class="sxs-lookup"><span data-stu-id="cb2ff-280">How to: Split an Interchange and Route the Resulting Messages to Multiple File Locations Using Distinct Itineraries</span></span>](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md)  
  
-   [<span data-ttu-id="cb2ff-281">开发活动</span><span class="sxs-lookup"><span data-stu-id="cb2ff-281">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="cb2ff-282">安装和运行动态解析示例</span><span class="sxs-lookup"><span data-stu-id="cb2ff-282">Installing and Running the Dynamic Resolution Sample</span></span>](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)  
  
-   [<span data-ttu-id="cb2ff-283">使用动态解析和路由</span><span class="sxs-lookup"><span data-stu-id="cb2ff-283">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)  
  
-   [<span data-ttu-id="cb2ff-284">消息路由模式</span><span class="sxs-lookup"><span data-stu-id="cb2ff-284">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)