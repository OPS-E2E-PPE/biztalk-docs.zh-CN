---
title: "如何： 拆分将交换，并将生成的消息路由到多个文件位置，使用不同的路线 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ccd46bee-e4a1-4846-8bde-b0460bda1e72
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c752c4b98f6a68e0a86ba4a418eab0705a7c513
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-split-an-interchange-and-route-the-resulting-messages-to-multiple-file-locations-using-distinct-itineraries"></a><span data-ttu-id="3bf09-102">如何： 拆分将交换，并将生成的消息路由到多个使用不同路线的文件位置</span><span class="sxs-lookup"><span data-stu-id="3bf09-102">How to: Split an Interchange and Route the Resulting Messages to Multiple File Locations Using Distinct Itineraries</span></span>
## <a name="goal"></a><span data-ttu-id="3bf09-103">目的</span><span class="sxs-lookup"><span data-stu-id="3bf09-103">Goal</span></span>  
 <span data-ttu-id="3bf09-104">本部分演示如何创建 ESB 入口使用**ItinerarySelectReceiveXml**管道以及如何配置在管道的组件，拆分的入站的交换，并选择适当的路由选择滑动的每个生成的消息，根据消息上下文。</span><span class="sxs-lookup"><span data-stu-id="3bf09-104">This section demonstrates how to create an ESB on-ramp that uses the **ItinerarySelectReceiveXml** pipeline and how to configure the pipeline's components to split an inbound interchange and select the appropriate routing slip for each resulting message, based on message context.</span></span> <span data-ttu-id="3bf09-105">会使用业务规则策略，解析路线的选择，并将以不同的方式根据客户所在的地区路由消息。</span><span class="sxs-lookup"><span data-stu-id="3bf09-105">Itinerary selection will be resolved using a business rules policy, and messages will be routed differently based on the region in which the customer resides.</span></span>  
  
 <span data-ttu-id="3bf09-106">在本操作方法主题中，你将完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="3bf09-106">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="3bf09-107">创建 ESB 入口将拆分 XML 交换。</span><span class="sxs-lookup"><span data-stu-id="3bf09-107">Create an ESB on-ramp that splits an XML interchange.</span></span>  
  
-   <span data-ttu-id="3bf09-108">配置要使用业务规则策略来选择适当的路线的路线选择器管道组件。</span><span class="sxs-lookup"><span data-stu-id="3bf09-108">Configure the Itinerary Selector pipeline component to use a business rules policy to select the appropriate itinerary.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3bf09-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="3bf09-109">Prerequisites</span></span>  
 <span data-ttu-id="3bf09-110">此操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="3bf09-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="3bf09-111">开始之前</span><span class="sxs-lookup"><span data-stu-id="3bf09-111">Before You Begin</span></span>  
 <span data-ttu-id="3bf09-112">本操作方法主题中的更高版本执行的步骤之前，请完成以下任务：</span><span class="sxs-lookup"><span data-stu-id="3bf09-112">Complete the following tasks before you perform the steps later in this How-to topic:</span></span>  
  
-   <span data-ttu-id="3bf09-113">创建所需的项目。</span><span class="sxs-lookup"><span data-stu-id="3bf09-113">Create the required artifacts.</span></span>  
  
-   <span data-ttu-id="3bf09-114">向模式解决方案中添加架构项目。</span><span class="sxs-lookup"><span data-stu-id="3bf09-114">Add a schemas project to the Patterns solution.</span></span>  
  
-   <span data-ttu-id="3bf09-115">将项目添加到架构项目。</span><span class="sxs-lookup"><span data-stu-id="3bf09-115">Add the artifacts to the Schemas project.</span></span>  
  
-   <span data-ttu-id="3bf09-116">创建 BRE 策略来选择使用自定义消息属性路线。</span><span class="sxs-lookup"><span data-stu-id="3bf09-116">Create a BRE policy to select an itinerary using custom message properties.</span></span>  
  
-   <span data-ttu-id="3bf09-117">添加客户 GlobalBank 西部选择规则。</span><span class="sxs-lookup"><span data-stu-id="3bf09-117">Add a selection rule for customer GlobalBank West.</span></span>  
  
-   <span data-ttu-id="3bf09-118">添加客户 GlobalBank 东部选择规则。</span><span class="sxs-lookup"><span data-stu-id="3bf09-118">Add a selection rule for customer GlobalBank East.</span></span>  
  
-   <span data-ttu-id="3bf09-119">发布和部署策略。</span><span class="sxs-lookup"><span data-stu-id="3bf09-119">Publish and deploy the policy.</span></span>  
  
-   <span data-ttu-id="3bf09-120">创建 GlobalBank 西部消息 ESB 路线域特定语言 (DSL) 模型。</span><span class="sxs-lookup"><span data-stu-id="3bf09-120">Create an ESB itinerary domain-specific language (DSL) model for GlobalBank West messages.</span></span>  
  
-   <span data-ttu-id="3bf09-121">配置 GlobalBank 西部路线的属性。</span><span class="sxs-lookup"><span data-stu-id="3bf09-121">Configure the properties of the GlobalBank West itinerary.</span></span>  
  
-   <span data-ttu-id="3bf09-122">定义 GlobalBank 西部路线的结构。</span><span class="sxs-lookup"><span data-stu-id="3bf09-122">Define the structure of the GlobalBank West itinerary.</span></span>  
  
-   <span data-ttu-id="3bf09-123">将 GlobalBank 西部模型导出到路线的数据库。</span><span class="sxs-lookup"><span data-stu-id="3bf09-123">Export the GlobalBank West model to the itinerary database.</span></span>  
  
-   <span data-ttu-id="3bf09-124">创建 GlobalBank 东部消息 ESB 路线 DSL 模型。</span><span class="sxs-lookup"><span data-stu-id="3bf09-124">Create an ESB itinerary DSL model for GlobalBank East messages.</span></span>  
  
-   <span data-ttu-id="3bf09-125">配置 GlobalBank 东部路线的属性。</span><span class="sxs-lookup"><span data-stu-id="3bf09-125">Configure the properties of the GlobalBank East itinerary.</span></span>  
  
-   <span data-ttu-id="3bf09-126">定义 GlobalBank 东部路线的结构。</span><span class="sxs-lookup"><span data-stu-id="3bf09-126">Define the structure of the GlobalBank East itinerary.</span></span>  
  
-   <span data-ttu-id="3bf09-127">将 GlobalBank 东部模型导出到路线的数据库。</span><span class="sxs-lookup"><span data-stu-id="3bf09-127">Export the GlobalBank East model to the itinerary database.</span></span>  
  
     <span data-ttu-id="3bf09-128">下面的过程介绍如何执行其中每个操作。</span><span class="sxs-lookup"><span data-stu-id="3bf09-128">The following procedures describe how to do each of these.</span></span>  
  
#### <a name="to-create-the-required-artifacts"></a><span data-ttu-id="3bf09-129">若要创建所需的项目</span><span class="sxs-lookup"><span data-stu-id="3bf09-129">To create the required artifacts</span></span>  
  
1.  <span data-ttu-id="3bf09-130">在 Windows 资源管理器，浏览到 C:\HowTos。</span><span class="sxs-lookup"><span data-stu-id="3bf09-130">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="3bf09-131">创建名为 OrderDocEnvelope.xsd 的新文本文档。</span><span class="sxs-lookup"><span data-stu-id="3bf09-131">Create a new text document named OrderDocEnvelope.xsd.</span></span>  
  
3.  <span data-ttu-id="3bf09-132">在记事本中打开 OrderDocEnvelope.xsd 架构。</span><span class="sxs-lookup"><span data-stu-id="3bf09-132">Open the OrderDocEnvelope.xsd schema in Notepad.</span></span>  
  
4.  <span data-ttu-id="3bf09-133">编辑使用下面的代码的文档。</span><span class="sxs-lookup"><span data-stu-id="3bf09-133">Edit the document using the following code.</span></span>  
  
    ```  
    <?xml version="1.0" ?>  
    <xs:schema xmlns:ns0="http://globalbank.esb.dynamicresolution.com/northamericanservices/" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" xmlns="http://ESB.BizUnit.Map.Test" targetNamespace="http://ESB.BizUnit.Map.Test" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  
      <xs:import schemaLocation="GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc" namespace="http://globalbank.esb.dynamicresolution.com/northamericanservices/" />  
      <xs:annotation>  
        <xs:appinfo>  
          <b:schemaInfo is_envelope="yes" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" />  
          <b:references>  
            <b:reference targetNamespace="http://globalbank.esb.dynamicresolution.com/northamericanservices/" />  
          </b:references>  
        </xs:appinfo>  
      </xs:annotation>  
      <xs:element name="OrderEnvelope">  
        <xs:annotation>  
          <xs:appinfo>  
            <b:recordInfo body_xpath="/*[local-name()='OrderEnvelope' and namespace-uri()='http://ESB.BizUnit.Map.Test']" />  
          </xs:appinfo>  
        </xs:annotation>  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element ref="ns0:OrderDoc" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:schema>  
    ```  
  
5.  <span data-ttu-id="3bf09-134">将 OrderDocEnvelope.xsd 另存为 utf-8，，然后关闭记事本。</span><span class="sxs-lookup"><span data-stu-id="3bf09-134">Save OrderDocEnvelope.xsd as UTF-8, and then close Notepad.</span></span>  
  
6.  <span data-ttu-id="3bf09-135">在 C:\HowTos 文件夹中，创建名为 Batch.xml 的新文本文档。</span><span class="sxs-lookup"><span data-stu-id="3bf09-135">In the C:\HowTos folder, create a new text document named Batch.xml.</span></span>  
  
7.  <span data-ttu-id="3bf09-136">在记事本中，打开 Batch.xml。</span><span class="sxs-lookup"><span data-stu-id="3bf09-136">In Notepad, open Batch.xml.</span></span>  
  
8.  <span data-ttu-id="3bf09-137">编辑使用下面的代码的文档。</span><span class="sxs-lookup"><span data-stu-id="3bf09-137">Edit the document using the following code.</span></span>  
  
    ```  
    <?xml version="1.0" ?>  
    <ns0:OrderEnvelope xmlns:ns0="http://ESB.BizUnit.Map.Test">  
      <ns0:OrderDoc xmlns:ns0="http://globalbank.esb.dynamicresolution.com/northamericanservices/">  
        <ns0:customerName>GlobalBankWest</ns0:customerName>  
        <ns0:ID>ns0:ID_0</ns0:ID>  
        <ns0:requestType>10</ns0:requestType>  
      </ns0:OrderDoc>  
      <ns0:OrderDoc xmlns:ns0="http://globalbank.esb.dynamicresolution.com/northamericanservices/">  
        <ns0:customerName>GlobalBankEast</ns0:customerName>  
        <ns0:ID>ns0:ID_0</ns0:ID>  
        <ns0:requestType>11</ns0:requestType>  
      </ns0:OrderDoc>  
      <ns0:OrderDoc xmlns:ns0="http://globalbank.esb.dynamicresolution.com/northamericanservices/">  
        <ns0:customerName>GlobalBankEast</ns0:customerName>  
        <ns0:ID>ns0:ID_0</ns0:ID>  
        <ns0:requestType>12</ns0:requestType>  
      </ns0:OrderDoc>  
    </ns0:OrderEnvelope>  
    ```  
  
9. <span data-ttu-id="3bf09-138">保存并关闭 Batch.xml。</span><span class="sxs-lookup"><span data-stu-id="3bf09-138">Save and close Batch.xml.</span></span>  
  
#### <a name="to-add-a-schemas-project-to-the-patterns-solution"></a><span data-ttu-id="3bf09-139">若要将架构项目添加到模式解决方案</span><span class="sxs-lookup"><span data-stu-id="3bf09-139">To add a schemas project to the Patterns solution</span></span>  
  
1.  <span data-ttu-id="3bf09-140">在[!INCLUDE[vs2010](../includes/vs2010-md.md)]，打开 C:\HowTos\Patterns\Patterns.sln。</span><span class="sxs-lookup"><span data-stu-id="3bf09-140">In [!INCLUDE[vs2010](../includes/vs2010-md.md)], open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="3bf09-141">在解决方案资源管理器，右键单击**解决方案模式**，指向**添加**，然后单击**新项目**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-141">In Solution Explorer, right-click **Solution 'Patterns'**, point to **Add**, and then click **New Project**.</span></span>  
  
3.  <span data-ttu-id="3bf09-142">在**添加新项目**对话框中，在项目类型窗格中，单击**BizTalk 项目**，然后执行以下：</span><span class="sxs-lookup"><span data-stu-id="3bf09-142">In the **Add New Project** dialog box, in the Project types pane, click **BizTalk Projects**, and then do the following:</span></span>  
  
    1.  <span data-ttu-id="3bf09-143">在模板窗格中，单击**空 BizTalk 服务器项目**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-143">In the Templates pane, click **Empty BizTalk Server Project**.</span></span>  
  
    2.  <span data-ttu-id="3bf09-144">在**名称**框中，键入**Patterns.Schemas**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-144">In the **Name** box, type **Patterns.Schemas**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="3bf09-145">在解决方案资源管理器，右键单击**Patterns.Schemas**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-145">In Solution Explorer, right-click **Patterns.Schemas**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="3bf09-146">在属性窗口上**签名**选项卡上，选择**对程序集签名**复选框。</span><span class="sxs-lookup"><span data-stu-id="3bf09-146">In the Properties window, on the **Signing** tab, select the **Sign the assembly** check box.</span></span>  
  
6.  <span data-ttu-id="3bf09-147">在**选择强名称密钥文件**下拉列表中，单击**\<新建 … >**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-147">In the **Choose a strong name key file** drop-down list, click **\<New...>**.</span></span>  
  
7.  <span data-ttu-id="3bf09-148">在**创建强名称密钥**对话框框中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="3bf09-148">In the **Create Strong Name Key** dialog box, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3bf09-149">在**密钥文件名称**框中，键入**拆分**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-149">In the **Key file name** box, type **Splitting**.</span></span>  
  
    2.  <span data-ttu-id="3bf09-150">清除**保护我使用密码的密钥文件**复选框，并依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-150">Clear the **Protect my key file with a password** check box, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="3bf09-151">在属性窗口上**部署**选项卡上，在**应用程序名称**框中，键入**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-151">In the Properties window, on the **Deployment** tab, in the **Application Name** box, type **Microsoft.Practices.ESB**.</span></span>  
  
9. <span data-ttu-id="3bf09-152">关闭“属性”窗口。</span><span class="sxs-lookup"><span data-stu-id="3bf09-152">Close the Properties window.</span></span>  
  
#### <a name="to-add-the-artifacts-to-the-schemas-project"></a><span data-ttu-id="3bf09-153">若要将项目添加到架构项目</span><span class="sxs-lookup"><span data-stu-id="3bf09-153">To add the artifacts to the Schemas project</span></span>  
  
1.  <span data-ttu-id="3bf09-154">在解决方案资源管理器，右键单击**Patterns.Schemas**，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-154">In Solution Explorer, right-click **Patterns.Schemas**, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="3bf09-155">上**浏览**选项卡**添加引用**对话框中，浏览到并选择 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB。DynamicResolution.Schemas\bin\Debug\GlobalBank.ESB.DynamicResolution.Schemas.dll，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-155">On the **Browse** tab of the **Add Reference** dialog box, browse to and select C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB.DynamicResolution.Schemas\bin\Debug\GlobalBank.ESB.DynamicResolution.Schemas.dll, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="3bf09-156">在解决方案资源管理器，右键单击**Patterns.Schemas**，指向**添加**，然后单击**现有项**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-156">In Solution Explorer, right-click **Patterns.Schemas**, point to **Add**, and then click **Existing Item**.</span></span>  
  
4.  <span data-ttu-id="3bf09-157">在**添加现有项**对话框中，浏览并选择 C:\HowTos\OrderDocEnvelope.xsd，，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-157">In the **Add Existing Item** dialog box, browse to and select C:\HowTos\OrderDocEnvelope.xsd, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="3bf09-158">保存所有解决方案项目。</span><span class="sxs-lookup"><span data-stu-id="3bf09-158">Save all solution artifacts.</span></span>  
  
6.  <span data-ttu-id="3bf09-159">在解决方案资源管理器，右键单击**Patterns.Schemas**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-159">In Solution Explorer, right-click **Patterns.Schemas**, and then click **Deploy**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3bf09-160">本操作指南主题使用了相同的业务规则策略和路线与在中创建[如何： 选择使用业务规则策略路线](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)主题。</span><span class="sxs-lookup"><span data-stu-id="3bf09-160">This How-to topic uses the same business rules policy and itineraries as those created in the [How to: Select an Itinerary Using a Business Rules Policy](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md) topic.</span></span> <span data-ttu-id="3bf09-161">如果尚未完成该部分，请完成以下附加步骤。</span><span class="sxs-lookup"><span data-stu-id="3bf09-161">If you have not already completed that section, please complete the following additional steps.</span></span> <span data-ttu-id="3bf09-162">如果你已完成该部分，继续直接进入"步骤"部分。</span><span class="sxs-lookup"><span data-stu-id="3bf09-162">If you have completed that section, continue directly to the "Steps" section.</span></span>  
  
#### <a name="to-create-a-business-rules-engine-bre-policy-to-select-an-itinerary-using-custom-message-properties"></a><span data-ttu-id="3bf09-163">若要创建业务规则引擎 (BRE) 策略来选择使用自定义消息属性路线</span><span class="sxs-lookup"><span data-stu-id="3bf09-163">To create a Business Rules Engine (BRE) policy to select an itinerary using custom message properties</span></span>  
  
1.  <span data-ttu-id="3bf09-164">单击**启动**在任务栏中，指向**所有程序**，指向 **[!INCLUDE[prague](../includes/prague-md.md)]** ，然后单击**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-164">Click **Start** on the taskbar, point to **All Programs**, point to **[!INCLUDE[prague](../includes/prague-md.md)]**, and then click **Business Rule Composer**.</span></span>  
  
2.  <span data-ttu-id="3bf09-165">在策略资源管理器中，右键单击**策略**，然后单击**添加新策略**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-165">In Policy Explorer, right-click **Policies**, and then click **Add New Policy**.</span></span> <span data-ttu-id="3bf09-166">命名策略时**ResolveItineraryBasedOnCustomer**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-166">Name the policy **ResolveItineraryBasedOnCustomer**.</span></span>  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-west"></a><span data-ttu-id="3bf09-167">若要添加客户 GlobalBank 西部选择规则</span><span class="sxs-lookup"><span data-stu-id="3bf09-167">To add a selection rule for customer GlobalBank West</span></span>  
  
1.  <span data-ttu-id="3bf09-168">在**ResolveItineraryBasedOnCustomer**策略，右键单击**（不保存） 1.0 版**，然后单击**添加新规则**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-168">In the **ResolveItineraryBasedOnCustomer** policy, right-click **Version 1.0 (not saved)**, and then click **Add New Rule**.</span></span> <span data-ttu-id="3bf09-169">命名规则**SetGlobalBankWestItinerary**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-169">Name the rule **SetGlobalBankWestItinerary**.</span></span>  
  
2.  <span data-ttu-id="3bf09-170">在事实数据资源管理器，单击**XML 架构**选项卡上，右键单击**架构**，然后单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-170">In Facts Explorer, click the **XML Schemas** tab, right-click **Schemas**, and then click **Browse**.</span></span>  
  
3.  <span data-ttu-id="3bf09-171">在**架构文件**对话框中，浏览到 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB。DynamicResolution.Schemas，选择 NAOrderDoc.xsd，，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-171">In the **Schema Files** dialog box, browse to C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB.DynamicResolution.Schemas, select NAOrderDoc.xsd, and then click **Open**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3bf09-172">这是定义 NAOrderDoc.xml 消息，用于创建将用于测试的西部和东部消息的架构。</span><span class="sxs-lookup"><span data-stu-id="3bf09-172">This is the schema that defines the NAOrderDoc.xml message, which was used to create the West and East messages you will use for testing.</span></span>  
  
4.  <span data-ttu-id="3bf09-173">在事实数据资源管理器，单击 NAOrderDoc.xsd，单击**文档类型**属性在属性窗格中，然后键入**GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-173">In Facts Explorer, click NAOrderDoc.xsd, click the **Document Type** property in the Properties pane, and then type **GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3bf09-174">这是架构的完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="3bf09-174">This is the fully qualified name of the schema.</span></span>  
  
5.  <span data-ttu-id="3bf09-175">在事实数据资源管理器中，展开**NAOrderDoc.xsd**，然后展开**OrderDoc**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-175">In Facts Explorer, expand **NAOrderDoc.xsd**, and then expand **OrderDoc**.</span></span>  
  
6.  <span data-ttu-id="3bf09-176">在规则窗口中，右键单击**条件**，指向**谓词**，然后单击**相等**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-176">In the Rule window, right-click **Conditions**, point to **Predicates**, and then click **Equal**.</span></span>  
  
7.  <span data-ttu-id="3bf09-177">从事实数据资源管理器拖动**customerName**元素**argument1**节点下的**条件**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-177">From Facts Explorer, drag the **customerName** element to the **argument1** node under **Conditions**.</span></span>  
  
8.  <span data-ttu-id="3bf09-178">单击**argument2**节点，并键入**GlobalBankWest**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-178">Click the **argument2** node, and then type **GlobalBankWest**.</span></span>  
  
9. <span data-ttu-id="3bf09-179">在事实数据资源管理器，单击**词汇**选项卡。展开**ESB。路线**词汇，展开**版本 1.1**，然后拖动**设置路线名称**定义与**操作**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-179">In Facts Explorer, click the **Vocabularies** tab. Expand the **ESB.Itinerary** vocabulary, expand **Version 1.1**, and then drag the **Set Itinerary Name** definition to **Actions**.</span></span>  
  
10. <span data-ttu-id="3bf09-180">单击**\<空字符串 >**然后键入**GlobalBankWestItinerary**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-180">Click **\<empty string>** and then type **GlobalBankWestItinerary**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3bf09-181">更高版本在本操作方法主题中，你将创建处理这些消息的此路线，从 GlobalBank 西部。</span><span class="sxs-lookup"><span data-stu-id="3bf09-181">Later in this How-to topic, you will create this itinerary to process messages from GlobalBank West.</span></span>  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-east"></a><span data-ttu-id="3bf09-182">若要添加客户 GlobalBank 东部选择规则</span><span class="sxs-lookup"><span data-stu-id="3bf09-182">To add a selection rule for customer GlobalBank East</span></span>  
  
1.  <span data-ttu-id="3bf09-183">在策略资源管理器中，右键单击**SetGlobalBankWestItinerary**规则，并依次**复制**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-183">In Policy Explorer, right-click the **SetGlobalBankWestItinerary** rule, and then click **Copy**.</span></span>  
  
2.  <span data-ttu-id="3bf09-184">右键单击**（不保存） 1.0 版**，然后单击**粘贴**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-184">Right-click **Version 1.0 (not saved)**, and then click **Paste**.</span></span>  
  
3.  <span data-ttu-id="3bf09-185">在**新规则名称**对话框中，键入**SetGlobalBankEastItinerary**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-185">In the **New Rule Name** dialog box, type **SetGlobalBankEastItinerary**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="3bf09-186">在策略资源管理器，单击**SetGlobalBankEastItinerary**规则。</span><span class="sxs-lookup"><span data-stu-id="3bf09-186">In Policy Explorer, click the **SetGlobalBankEastItinerary** rule.</span></span>  
  
5.  <span data-ttu-id="3bf09-187">在**条件**部分中，右键单击**GlobalBankWest**，然后单击**重置参数**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-187">In the **Conditions** section, right-click **GlobalBankWest**, and then click **Reset argument**.</span></span>  
  
6.  <span data-ttu-id="3bf09-188">单击**argument2**，然后键入**GlobalBankEast**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-188">Click **argument2**, and then type **GlobalBankEast**.</span></span>  
  
7.  <span data-ttu-id="3bf09-189">在**操作**部分中，右键单击**GlobalBankWestItinerary**，然后单击**重置参数**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-189">In the **Actions** section, right-click **GlobalBankWestItinerary**, and then click **Reset argument**.</span></span>  
  
8.  <span data-ttu-id="3bf09-190">单击**\<空字符串 >**然后键入**GlobalBankEastItinerary。**</span><span class="sxs-lookup"><span data-stu-id="3bf09-190">Click **\<empty string>** and then type **GlobalBankEastItinerary.**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3bf09-191">更高版本在本操作方法主题中，你将创建处理这些消息的此路线，从 GlobalBank 东部。</span><span class="sxs-lookup"><span data-stu-id="3bf09-191">Later in this How-to topic, you will create this itinerary to process messages from GlobalBank East.</span></span>  
  
#### <a name="to-publish-and-deploy-the-policy"></a><span data-ttu-id="3bf09-192">若要发布和部署策略</span><span class="sxs-lookup"><span data-stu-id="3bf09-192">To publish and deploy the policy</span></span>  
  
1.  <span data-ttu-id="3bf09-193">在策略资源管理器下**ResolveItineraryBasedOnCustomer**策略，单击**（不保存） 1.0 版**，然后单击**发布**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-193">In Policy Explorer, under the **ResolveItineraryBasedOnCustomer** policy, click **Version 1.0 (not saved)**, and then click **Publish**.</span></span>  
  
2.  <span data-ttu-id="3bf09-194">在策略资源管理器下**ResolveItineraryBasedOnCustomer**策略，单击**版本 1.0-发布**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-194">In Policy Explorer, under the **ResolveItineraryBasedOnCustomer** policy, click **Version 1.0 - Published**, and then click **Deploy**.</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model-for-globalbank-west-messages"></a><span data-ttu-id="3bf09-195">若要创建 GlobalBank 西部消息 ESB 路线 DSL 模型</span><span class="sxs-lookup"><span data-stu-id="3bf09-195">To create an ESB itinerary DSL model for GlobalBank West messages</span></span>  
  
1.  <span data-ttu-id="3bf09-196">在 **[!INCLUDE[vs2010](../includes/vs2010-md.md)]** ，打开 C:\HowTos\Patterns\Patterns.sln。</span><span class="sxs-lookup"><span data-stu-id="3bf09-196">In **[!INCLUDE[vs2010](../includes/vs2010-md.md)]**, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="3bf09-197">在解决方案资源管理器，右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-197">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="3bf09-198">在**添加新项**对话框中，在模板窗格中，单击**ItineraryDsl**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-198">In the **Add New Item** dialog box, in the Templates pane, click **ItineraryDsl**.</span></span>  
  
4.  <span data-ttu-id="3bf09-199">在**名称**框中，键入**GlobalBankWestItinerary**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-199">In the **Name** box, type **GlobalBankWestItinerary**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-globalbank-west-itinerary"></a><span data-ttu-id="3bf09-200">若要配置 GlobalBank 西部路线的属性</span><span class="sxs-lookup"><span data-stu-id="3bf09-200">To configure the properties of the GlobalBank West itinerary</span></span>  
  
1.  <span data-ttu-id="3bf09-201">在 Visual Studio 中，单击的设计图面**GlobalBankWestItinerary.itinerary**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-201">In Visual Studio, click the design surface of **GlobalBankWestItinerary.itinerary**.</span></span> <span data-ttu-id="3bf09-202">在**GlobalBankWestItinerary**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="3bf09-202">In the **GlobalBankWestItinerary** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3bf09-203">在**模型导出程序**下拉列表中，单击**数据库路线导出程序**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-203">In the **Model Exporter** drop-down list, click **Database Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="3bf09-204">单击旁边的省略号按钮 （...）**路线数据库**属性。</span><span class="sxs-lookup"><span data-stu-id="3bf09-204">Click the ellipsis button (...) next to the **Itinerary Database** property.</span></span>  
  
    3.  <span data-ttu-id="3bf09-205">在**连接属性**对话框中，选择承载路线存储库数据库中，SQL Server，然后指定数据库的名称 (默认名称是**EsbItineraryDb**)。</span><span class="sxs-lookup"><span data-stu-id="3bf09-205">In the **Connection Properties** dialog box, choose the SQL Server that hosts the itinerary repository database, and then specify the name of the database (the default name is **EsbItineraryDb**).</span></span>  
  
2.  <span data-ttu-id="3bf09-206">在**路线状态**下拉列表中，单击**已部署**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-206">In the **Itinerary Status** drop-down list, click **Deployed**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3bf09-207">此步骤允许您将导出到一个中心存储库; 路线可以选择路线，并将其从此存储库中接收消息时附加。</span><span class="sxs-lookup"><span data-stu-id="3bf09-207">This step enables you to export the itinerary to a central repository; itineraries can be selected and attached from this repository when messages are received.</span></span> <span data-ttu-id="3bf09-208">更高版本，你将配置路线选择器管道组件配置为使用 BRI 解析程序要评估的入站的消息和从此存储库中选择相应的路线。</span><span class="sxs-lookup"><span data-stu-id="3bf09-208">You will later configure the Itinerary Selector pipeline component to use the BRI resolver to evaluate inbound messages and select the appropriate itinerary from this repository.</span></span>  
  
#### <a name="to-define-the-structure-of-the-globalbank-west-itinerary"></a><span data-ttu-id="3bf09-209">若要定义 GlobalBank 西部路线的结构</span><span class="sxs-lookup"><span data-stu-id="3bf09-209">To define the structure of the GlobalBank West itinerary</span></span>  
  
1.  <span data-ttu-id="3bf09-210">从工具箱中，拖动**上负载增加**到设计图面上的模型元素。</span><span class="sxs-lookup"><span data-stu-id="3bf09-210">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="3bf09-211">在**OnRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="3bf09-211">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3bf09-212">单击**名称**属性，再然后键入**ReceiveNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-212">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="3bf09-213">在**扩展程序**下拉列表中，单击**上负载增加 ESB 服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-213">In the **Extender** drop-down list, click **On-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="3bf09-214">在**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-214">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="3bf09-215">在**接收端口**下拉列表中，单击**OnRamp.Itinerary**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-215">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="3bf09-216">从工具箱中，拖动**关闭负载增加**模型元素到设计图面，然后将其放到右侧**ReceiveNAOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="3bf09-216">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **ReceiveNAOrder** model element.</span></span> <span data-ttu-id="3bf09-217">在**OffRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="3bf09-217">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3bf09-218">单击**名称**属性，再然后键入**SendNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-218">Click the **Name** property, and then type **SendNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="3bf09-219">在**扩展程序**下拉列表中，单击**关闭负载增加 ESB 服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-219">In the **Extender** drop-down list, click **Off-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="3bf09-220">在**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-220">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="3bf09-221">在**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-221">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
3.  <span data-ttu-id="3bf09-222">从工具箱中，拖动**路线服务**模型元素到设计图面，然后将它之间**ReceiveNAOrder**模型元素和**SendNAOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="3bf09-222">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **ReceiveNAOrder** model element and the **SendNAOrder** model element.</span></span> <span data-ttu-id="3bf09-223">在**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="3bf09-223">In the **ItineraryService1** properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3bf09-224">单击**名称**属性，再然后键入**RouteMessage**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-224">Click the **Name** property, and then type **RouteMessage**.</span></span>  
  
    2.  <span data-ttu-id="3bf09-225">在**路线服务扩展程序**下拉列表中，单击**关闭负载增加路线服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-225">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Itinerary Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="3bf09-226">在**关闭负载增加**下拉列表中，展开**SendNAOrder**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-226">In the **Off-Ramp** drop-down list, expand **SendNAOrder**, and then click **Send Handlers**.</span></span>  
  
4.  <span data-ttu-id="3bf09-227">右键单击**冲突解决程序**集合**RouteMessage**模型元素，并依次**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-227">Right-click the **Resolver** collection of the **RouteMessage** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="3bf09-228">在**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="3bf09-228">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3bf09-229">单击**名称**属性，再然后键入**StaticResolver**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-229">Click the **Name** property, and then type **StaticResolver**.</span></span>  
  
    2.  <span data-ttu-id="3bf09-230">在**解析程序实现**下拉列表中，单击**静态冲突解决程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-230">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="3bf09-231">在**传输名称**下拉列表中，单击**文件**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-231">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="3bf09-232">单击**传输位置**属性，再然后键入**C:\HowTos\Out\West%MessageID%.xml**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-232">Click the **Transport Location** property, and then type **C:\HowTos\Out\West%MessageID%.xml**.</span></span>  
  
5.  <span data-ttu-id="3bf09-233">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-233">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="3bf09-234">将从连接**ReceiveNAOrder**到模型元素**RouteMessage**模型元素。</span><span class="sxs-lookup"><span data-stu-id="3bf09-234">Drag a connection from the **ReceiveNAOrder** model element to the  **RouteMessage** model element.</span></span>  
  
6.  <span data-ttu-id="3bf09-235">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-235">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="3bf09-236">将从连接**RouteMessage**到模型元素**SendNAOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="3bf09-236">Drag a connection from the **RouteMessage** model element to the **SendNAOrder** model element.</span></span>  
  
#### <a name="to-export-the-globalbank-west-model-to-the-itinerary-database"></a><span data-ttu-id="3bf09-237">将导出到路线的数据库的 GlobalBank 西部模型</span><span class="sxs-lookup"><span data-stu-id="3bf09-237">To export the GlobalBank West model to the itinerary database</span></span>  
  
1.  <span data-ttu-id="3bf09-238">在 Visual Studio 中，右键单击的设计图面**GlobalBankWestItinerary**路线，，然后单击**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-238">In Visual Studio, right-click the design surface of the **GlobalBankWestItinerary** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3bf09-239">路线已导出到路线的数据库，现在可以使用由路线选择器组件。</span><span class="sxs-lookup"><span data-stu-id="3bf09-239">The itinerary has been exported to the itinerary database and can now be used by the Itinerary Selector component.</span></span>  
  
2.  <span data-ttu-id="3bf09-240">保存所有项目。</span><span class="sxs-lookup"><span data-stu-id="3bf09-240">Save all project artifacts.</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model-for-globalbank-east-message"></a><span data-ttu-id="3bf09-241">若要创建 GlobalBank 东部消息 ESB 路线 DSL 模型</span><span class="sxs-lookup"><span data-stu-id="3bf09-241">To create an ESB itinerary DSL model for GlobalBank East message</span></span>  
  
1.  <span data-ttu-id="3bf09-242">在 **[!INCLUDE[vs2010](../includes/vs2010-md.md)]** ，打开 C:\HowTos\Patterns.sln。</span><span class="sxs-lookup"><span data-stu-id="3bf09-242">In **[!INCLUDE[vs2010](../includes/vs2010-md.md)]**, open C:\HowTos\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="3bf09-243">在解决方案资源管理器，右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-243">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="3bf09-244">在**添加新项**对话框中，在模板窗格中，单击**ItineraryDsl**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-244">In the **Add New Item** dialog box, in the Templates pane, click **ItineraryDsl**.</span></span>  
  
4.  <span data-ttu-id="3bf09-245">在**名称**框中，键入**GlobalBankEastItinerary**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-245">In the **Name** box, type **GlobalBankEastItinerary**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-globalbank-east-itinerary"></a><span data-ttu-id="3bf09-246">若要配置 GlobalBank 东部路线的属性</span><span class="sxs-lookup"><span data-stu-id="3bf09-246">To configure the properties of the GlobalBank East itinerary</span></span>  
  
1.  <span data-ttu-id="3bf09-247">在 Visual Studio 中，单击的设计图面**GlobalBankEastItinerary.itinerary**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-247">In Visual Studio, click the design surface of **GlobalBankEastItinerary.itinerary**.</span></span> <span data-ttu-id="3bf09-248">在**GlobalBankEastItinerary**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="3bf09-248">In the **GlobalBankEastItinerary** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3bf09-249">在**模型导出程序**下拉列表中，单击**数据库路线导出程序**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-249">In the **Model Exporter** drop-down list, click **Database Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="3bf09-250">单击旁边的省略号按钮 （...）**路线数据库**属性。</span><span class="sxs-lookup"><span data-stu-id="3bf09-250">Click the ellipsis button (...) next to the **Itinerary Database** property.</span></span>  
  
    3.  <span data-ttu-id="3bf09-251">在**连接属性**对话框中，选择承载路线存储库数据库中，SQL Server，然后指定数据库的名称 (默认名称是**EsbItineraryDb**)。</span><span class="sxs-lookup"><span data-stu-id="3bf09-251">In the **Connection Properties** dialog box, choose the SQL Server that hosts the itinerary repository database, and then specify the name of the database (the default name is **EsbItineraryDb**).</span></span>  
  
2.  <span data-ttu-id="3bf09-252">在**路线状态**下拉列表中，单击**已部署**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-252">In the **Itinerary Status** drop-down list, click **Deployed**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3bf09-253">此步骤允许您将导出到一个中心存储库; 路线可以选择路线，并将其从此存储库中接收消息时附加。</span><span class="sxs-lookup"><span data-stu-id="3bf09-253">This step enables you to export the itinerary to a central repository; itineraries can be selected and attached from this repository when messages are received.</span></span> <span data-ttu-id="3bf09-254">更高版本，你将配置路线选择器管道组件配置为使用 BRI 解析程序要评估的入站的消息和从此存储库中选择相应的路线。</span><span class="sxs-lookup"><span data-stu-id="3bf09-254">You will later configure the Itinerary Selector pipeline component to use the BRI resolver to evaluate inbound messages and select the appropriate itinerary from this repository.</span></span>  
  
#### <a name="to-define-the-structure-of-the-globalbank-east-itinerary"></a><span data-ttu-id="3bf09-255">若要定义 GlobalBank 东部路线的结构</span><span class="sxs-lookup"><span data-stu-id="3bf09-255">To define the structure of the GlobalBank East itinerary</span></span>  
  
1.  <span data-ttu-id="3bf09-256">从工具箱中，拖动**上负载增加**到设计图面上的模型元素。</span><span class="sxs-lookup"><span data-stu-id="3bf09-256">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="3bf09-257">在**OnRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="3bf09-257">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3bf09-258">单击**名称**属性，再然后键入**ReceiveNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-258">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="3bf09-259">在**扩展程序**下拉列表中，单击**上负载增加 ESB 服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-259">In the **Extender** drop-down list, click **On-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="3bf09-260">在**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-260">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="3bf09-261">在**接收端口**下拉列表中，单击**OnRamp.Itinerary**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-261">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="3bf09-262">从工具箱中，拖动**关闭负载增加**模型元素到设计图面，然后将其放到右侧**ReceiveNAOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="3bf09-262">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **ReceiveNAOrder** model element.</span></span> <span data-ttu-id="3bf09-263">在**OffRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="3bf09-263">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3bf09-264">单击**名称**属性，再然后键入**SendNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-264">Click the **Name** property, and then type **SendNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="3bf09-265">在**扩展程序**下拉列表中，单击**关闭负载增加 ESB 服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-265">In the **Extender** drop-down list, click **Off-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="3bf09-266">在**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-266">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="3bf09-267">在**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-267">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
3.  <span data-ttu-id="3bf09-268">从工具箱中，拖动**路线服务**模型元素到设计图面，然后将它之间**ReceiveNAOrder**模型元素和**SendNAOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="3bf09-268">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **ReceiveNAOrder** model element and the **SendNAOrder** model element.</span></span> <span data-ttu-id="3bf09-269">在**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="3bf09-269">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3bf09-270">单击**名称**属性，再然后键入**RouteMessage**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-270">Click the **Name** property, and then type **RouteMessage**.</span></span>  
  
    2.  <span data-ttu-id="3bf09-271">在**路线服务扩展程序**下拉列表中，单击**关闭负载增加路线服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-271">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Itinerary Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="3bf09-272">在**关闭负载增加**下拉列表中，展开**SendNAOrder**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-272">In the **Off-Ramp** drop-down list, expand **SendNAOrder**, and then click **Send Handlers**.</span></span>  
  
4.  <span data-ttu-id="3bf09-273">右键单击**冲突解决程序**集合**RouteMessage**模型元素，并依次**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-273">Right-click the **Resolver** collection of the **RouteMessage** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="3bf09-274">在**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="3bf09-274">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3bf09-275">单击**名称**属性，再然后键入**StaticResolver**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-275">Click the **Name** property, and then type **StaticResolver**.</span></span>  
  
    2.  <span data-ttu-id="3bf09-276">在**解析程序实现**下拉列表中，单击**静态冲突解决程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-276">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="3bf09-277">在**传输名称**下拉列表中，单击**文件**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-277">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="3bf09-278">单击**传输位置**属性，再然后键入**C:\HowTos\Out\East%MessageID%.xml**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-278">Click the **Transport Location** property, and then type **C:\HowTos\Out\East%MessageID%.xml**.</span></span>  
  
5.  <span data-ttu-id="3bf09-279">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-279">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="3bf09-280">将从连接**ReceiveNAOrder**到模型元素**RouteMessage**模型元素。</span><span class="sxs-lookup"><span data-stu-id="3bf09-280">Drag a connection from the **ReceiveNAOrder** model element to the **RouteMessage** model element.</span></span>  
  
6.  <span data-ttu-id="3bf09-281">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-281">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="3bf09-282">将从连接**RouteMessage**到模型元素**SendNAOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="3bf09-282">Drag a connection from the **RouteMessage** model element to the **SendNAOrder** model element.</span></span>  
  
#### <a name="to-export-the-globalbank-east-model-to-the-itinerary-database"></a><span data-ttu-id="3bf09-283">将导出到路线的数据库的 GlobalBank 东部模型</span><span class="sxs-lookup"><span data-stu-id="3bf09-283">To export the GlobalBank East model to the itinerary database</span></span>  
  
1.  <span data-ttu-id="3bf09-284">在 Visual Studio 中，右键单击的设计图面**GlobalBankEastItinerary**路线，，然后单击**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-284">In Visual Studio, right-click the design surface of the **GlobalBankEastItinerary** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3bf09-285">路线已导出到路线的数据库，现在可以使用由路线选择器组件。</span><span class="sxs-lookup"><span data-stu-id="3bf09-285">The itinerary has been exported to the itinerary database and can now be used by the Itinerary Selector component.</span></span>  
  
2.  <span data-ttu-id="3bf09-286">保存所有项目。</span><span class="sxs-lookup"><span data-stu-id="3bf09-286">Save all project artifacts.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="3bf09-287">步骤</span><span class="sxs-lookup"><span data-stu-id="3bf09-287">Steps</span></span>  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a><span data-ttu-id="3bf09-288">若要创建和配置 ESB 入口</span><span class="sxs-lookup"><span data-stu-id="3bf09-288">To create and configure an ESB on-ramp</span></span>  
  
1.  <span data-ttu-id="3bf09-289">单击**启动**在任务栏中，指向**所有程序**，指向 **[!INCLUDE[prague](../includes/prague-md.md)]** ，然后单击**BizTalk Server 管理**.</span><span class="sxs-lookup"><span data-stu-id="3bf09-289">Click **Start** on the taskbar, point to **All Programs**, point to **[!INCLUDE[prague](../includes/prague-md.md)]**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="3bf09-290">在[!INCLUDE[prague](../includes/prague-md.md)]管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后展开**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-290">In the [!INCLUDE[prague](../includes/prague-md.md)] Administration Console, expand **BizTalk Group**, expand **Applications**, and then expand **Microsoft.Practices.ESB**.</span></span>  
  
3.  <span data-ttu-id="3bf09-291">右键单击**接收位置**，指向**新建**，然后单击**单向接收位置**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-291">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
4.  <span data-ttu-id="3bf09-292">在**选择接收端口**对话框中，单击**OnRamp.Itinerary**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-292">In the **Select a Receive Port** dialog box, click **OnRamp.Itinerary**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="3bf09-293">在**接收位置属性**对话框中，在**名称**框中，键入**OnRamp.Itinerary.HowTo**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-293">In the **Receive Location Properties** dialog box, in the **Name** box, type **OnRamp.Itinerary.HowTo**.</span></span>  
  
6.  <span data-ttu-id="3bf09-294">在**类型**下拉列表中，单击**文件，** ，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-294">In the **Type** drop-down list, click **FILE,** and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="3bf09-295">在**文件传输属性**对话框中，在**接收文件夹**框中，键入**C:\HowTos\DropFolder**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-295">In the **FILE Transport Properties** dialog box, in the **Receive folder** box, type **C:\HowTos\DropFolder**, and then click **OK**.</span></span>  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a><span data-ttu-id="3bf09-296">若要配置路线选择器管道组件</span><span class="sxs-lookup"><span data-stu-id="3bf09-296">To configure the Itinerary Selector pipeline component</span></span>  
  
1.  <span data-ttu-id="3bf09-297">在**接收位置属性**对话框中，单击**ItinerarySelectReceiveXml**中**接收管道**下拉列表，，然后单击省略号按钮 （…）。</span><span class="sxs-lookup"><span data-stu-id="3bf09-297">In the **Receive Location Properties** dialog box, click **ItinerarySelectReceiveXml** in the **Receive pipeline** drop-down list, and then click the ellipsis button (...).</span></span>  
  
2.  <span data-ttu-id="3bf09-298">使用**配置管道**对话框中，配置以下各项**路线选择器**组件属性：</span><span class="sxs-lookup"><span data-stu-id="3bf09-298">Use the **Configure Pipeline** dialog box to configure the following **Itinerary Selector** component properties:</span></span>  
  
    1.  <span data-ttu-id="3bf09-299">单击**ItineraryFactKey**属性，再然后键入**Resolver.Itinerary**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-299">Click the **ItineraryFactKey** property, and then type **Resolver.Itinerary**.</span></span>  
  
    2.  <span data-ttu-id="3bf09-300">单击**ResolverConnectionString**属性，再然后键入**BRI:\\\policy=ResolveItineraryBasedOnCustomer;useMsg=true;recognizeMessageFormat=true;**</span><span class="sxs-lookup"><span data-stu-id="3bf09-300">Click the **ResolverConnectionString** property, and then type **BRI:\\\policy=ResolveItineraryBasedOnCustomer;useMsg=true;recognizeMessageFormat=true;**</span></span>  
  
    3.  <span data-ttu-id="3bf09-301">单击**确定**关闭**配置管道**对话框。</span><span class="sxs-lookup"><span data-stu-id="3bf09-301">Click **OK** to close the **Configure Pipeline** dialog box.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="3bf09-302">由于此接收位置反汇编 XML 交换，不不需要任何 XML 反汇编程序组件配置。</span><span class="sxs-lookup"><span data-stu-id="3bf09-302">Because this receive location is disassembling an XML interchange, no XML Disassembler component configuration is required.</span></span>  
  
3.  <span data-ttu-id="3bf09-303">单击**确定**关闭**接收位置属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="3bf09-303">Click **OK** to close the **Receive Location Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="3bf09-304">在[!INCLUDE[prague](../includes/prague-md.md)]管理控制台中，右键单击**OnRamp.Itinerary.HowTo**接收位置，并依次**启用**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-304">In the [!INCLUDE[prague](../includes/prague-md.md)] Administration Console, right-click the **OnRamp.Itinerary.HowTo** receive location, and then click **Enable**.</span></span>  
  
#### <a name="to-test-the-itinerary-selector-and-business-rules"></a><span data-ttu-id="3bf09-305">若要测试的路线选择器和业务规则</span><span class="sxs-lookup"><span data-stu-id="3bf09-305">To test the Itinerary Selector and business rules</span></span>  
  
1.  <span data-ttu-id="3bf09-306">在 Windows 资源管理器，浏览到 C:\HowTos。</span><span class="sxs-lookup"><span data-stu-id="3bf09-306">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="3bf09-307">复制 （不移动） 到 DropFolder 文件夹 Batch.xml。</span><span class="sxs-lookup"><span data-stu-id="3bf09-307">Copy (do not move) Batch.xml to the DropFolder folder.</span></span>  
  
3.  <span data-ttu-id="3bf09-308">浏览到 C:\HowTos\Out。验证一个 West%MessageID%.xml 消息和两个 East%MessageID%.xml 消息已写入到的目录。</span><span class="sxs-lookup"><span data-stu-id="3bf09-308">Browse to C:\HowTos\Out. Verify that one West%MessageID%.xml message and two East%MessageID%.xml messages have been written to the directory.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3bf09-309">虽然消息除外客户元素的值相同，但在处理使用不同路线，根据路线选择器管道组件的分辨率。</span><span class="sxs-lookup"><span data-stu-id="3bf09-309">Although the messages are identical except for the value of the customer element, they were processed using different itineraries, based on the resolution of the Itinerary Selector pipeline component.</span></span>  
  
4.  <span data-ttu-id="3bf09-310">在[!INCLUDE[prague](../includes/prague-md.md)]管理控制台中，右键单击 OnRamp.Itinerary.HowTo 接收位置，然后单击禁用。</span><span class="sxs-lookup"><span data-stu-id="3bf09-310">In the [!INCLUDE[prague](../includes/prague-md.md)] Administration Console, right-click the OnRamp.Itinerary.HowTo receive location, and then click Disable.</span></span>  
  
5.  <span data-ttu-id="3bf09-311">后**OnRamp.Itinerary.HowTo**接收位置处于禁用状态，右键单击它，，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-311">After the **OnRamp.Itinerary.HowTo** receive location is disabled, right-click it, and then click **Delete**.</span></span> <span data-ttu-id="3bf09-312">在**确认删除接收位置**对话框中，单击**是**。</span><span class="sxs-lookup"><span data-stu-id="3bf09-312">In the **Confirm delete receive location** dialog box, click **Yes**.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="3bf09-313">其他资源</span><span class="sxs-lookup"><span data-stu-id="3bf09-313">Additional Resources</span></span>  
 <span data-ttu-id="3bf09-314">有关详细信息，请参阅下列相关主题：</span><span class="sxs-lookup"><span data-stu-id="3bf09-314">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="3bf09-315">如何： 选择使用业务规则策略路线</span><span class="sxs-lookup"><span data-stu-id="3bf09-315">How to: Select an Itinerary Using a Business Rules Policy</span></span>](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [<span data-ttu-id="3bf09-316">开发活动</span><span class="sxs-lookup"><span data-stu-id="3bf09-316">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="3bf09-317">安装和运行动态解析示例</span><span class="sxs-lookup"><span data-stu-id="3bf09-317">Installing and Running the Dynamic Resolution Sample</span></span>](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)  
  
-   [<span data-ttu-id="3bf09-318">使用动态解析和路由</span><span class="sxs-lookup"><span data-stu-id="3bf09-318">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)  
  
-   [<span data-ttu-id="3bf09-319">消息路由模式</span><span class="sxs-lookup"><span data-stu-id="3bf09-319">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)