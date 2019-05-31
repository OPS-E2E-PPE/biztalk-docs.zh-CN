---
title: 如何：将某个交换拆分，并将结果的消息路由到多个使用不同的路线的文件位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccd46bee-e4a1-4846-8bde-b0460bda1e72
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36287f22290f30b687e90e9a111a3ae79aa53d5e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65268903"
---
# <a name="how-to-split-an-interchange-and-route-the-resulting-messages-to-multiple-file-locations-using-distinct-itineraries"></a><span data-ttu-id="745dd-102">如何：将某个交换拆分，并将结果的消息路由到多个使用不同的路线的文件位置</span><span class="sxs-lookup"><span data-stu-id="745dd-102">How to: Split an Interchange and Route the Resulting Messages to Multiple File Locations Using Distinct Itineraries</span></span>
## <a name="goal"></a><span data-ttu-id="745dd-103">目的</span><span class="sxs-lookup"><span data-stu-id="745dd-103">Goal</span></span>  
 <span data-ttu-id="745dd-104">本部分演示如何创建 ESB 接入点使用**ItinerarySelectReceiveXml**管道以及如何配置管道组件将入站的交换拆分并选择适当的路由的滑动每个生成的消息，根据消息上下文。</span><span class="sxs-lookup"><span data-stu-id="745dd-104">This section demonstrates how to create an ESB on-ramp that uses the **ItinerarySelectReceiveXml** pipeline and how to configure the pipeline's components to split an inbound interchange and select the appropriate routing slip for each resulting message, based on message context.</span></span> <span data-ttu-id="745dd-105">将使用业务规则策略，解决路线选择，将以不同的方式根据客户所在的区域路由消息。</span><span class="sxs-lookup"><span data-stu-id="745dd-105">Itinerary selection will be resolved using a business rules policy, and messages will be routed differently based on the region in which the customer resides.</span></span>  
  
 <span data-ttu-id="745dd-106">在本操作指南主题中，您将完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="745dd-106">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="745dd-107">创建 ESB 接入点拆分为一个 XML 交换的。</span><span class="sxs-lookup"><span data-stu-id="745dd-107">Create an ESB on-ramp that splits an XML interchange.</span></span>  
  
-   <span data-ttu-id="745dd-108">配置路线选择器管道组件以使用业务规则策略选择适当的路线。</span><span class="sxs-lookup"><span data-stu-id="745dd-108">Configure the Itinerary Selector pipeline component to use a business rules policy to select the appropriate itinerary.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="745dd-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="745dd-109">Prerequisites</span></span>  
 <span data-ttu-id="745dd-110">本操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="745dd-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="745dd-111">开始之前</span><span class="sxs-lookup"><span data-stu-id="745dd-111">Before You Begin</span></span>  
 <span data-ttu-id="745dd-112">在本操作指南主题的后面部分执行的步骤之前，请完成以下任务：</span><span class="sxs-lookup"><span data-stu-id="745dd-112">Complete the following tasks before you perform the steps later in this How-to topic:</span></span>  
  
-   <span data-ttu-id="745dd-113">创建所需的项目。</span><span class="sxs-lookup"><span data-stu-id="745dd-113">Create the required artifacts.</span></span>  
  
-   <span data-ttu-id="745dd-114">将架构项目添加到模式解决方案。</span><span class="sxs-lookup"><span data-stu-id="745dd-114">Add a schemas project to the Patterns solution.</span></span>  
  
-   <span data-ttu-id="745dd-115">将项目添加到架构项目。</span><span class="sxs-lookup"><span data-stu-id="745dd-115">Add the artifacts to the Schemas project.</span></span>  
  
-   <span data-ttu-id="745dd-116">创建 BRE 策略来选择使用自定义消息属性路线。</span><span class="sxs-lookup"><span data-stu-id="745dd-116">Create a BRE policy to select an itinerary using custom message properties.</span></span>  
  
-   <span data-ttu-id="745dd-117">添加客户 GlobalBank 西部选择规则。</span><span class="sxs-lookup"><span data-stu-id="745dd-117">Add a selection rule for customer GlobalBank West.</span></span>  
  
-   <span data-ttu-id="745dd-118">添加客户 GlobalBank 东部选择规则。</span><span class="sxs-lookup"><span data-stu-id="745dd-118">Add a selection rule for customer GlobalBank East.</span></span>  
  
-   <span data-ttu-id="745dd-119">发布和部署策略。</span><span class="sxs-lookup"><span data-stu-id="745dd-119">Publish and deploy the policy.</span></span>  
  
-   <span data-ttu-id="745dd-120">创建用于 GlobalBank 西部消息的 ESB 路线域特定语言 (DSL) 模型。</span><span class="sxs-lookup"><span data-stu-id="745dd-120">Create an ESB itinerary domain-specific language (DSL) model for GlobalBank West messages.</span></span>  
  
-   <span data-ttu-id="745dd-121">配置 GlobalBank 西部路线的属性。</span><span class="sxs-lookup"><span data-stu-id="745dd-121">Configure the properties of the GlobalBank West itinerary.</span></span>  
  
-   <span data-ttu-id="745dd-122">定义 GlobalBank 西部路线的结构。</span><span class="sxs-lookup"><span data-stu-id="745dd-122">Define the structure of the GlobalBank West itinerary.</span></span>  
  
-   <span data-ttu-id="745dd-123">GlobalBank 西部模型导出到路线的数据库。</span><span class="sxs-lookup"><span data-stu-id="745dd-123">Export the GlobalBank West model to the itinerary database.</span></span>  
  
-   <span data-ttu-id="745dd-124">创建 GlobalBank 东部消息 ESB 路线 DSL 模型。</span><span class="sxs-lookup"><span data-stu-id="745dd-124">Create an ESB itinerary DSL model for GlobalBank East messages.</span></span>  
  
-   <span data-ttu-id="745dd-125">配置 GlobalBank 东部路线的属性。</span><span class="sxs-lookup"><span data-stu-id="745dd-125">Configure the properties of the GlobalBank East itinerary.</span></span>  
  
-   <span data-ttu-id="745dd-126">定义 GlobalBank 东部路线的结构。</span><span class="sxs-lookup"><span data-stu-id="745dd-126">Define the structure of the GlobalBank East itinerary.</span></span>  
  
-   <span data-ttu-id="745dd-127">GlobalBank 东部模型导出到路线的数据库。</span><span class="sxs-lookup"><span data-stu-id="745dd-127">Export the GlobalBank East model to the itinerary database.</span></span>  
  
     <span data-ttu-id="745dd-128">以下过程介绍如何执行其中每项功能。</span><span class="sxs-lookup"><span data-stu-id="745dd-128">The following procedures describe how to do each of these.</span></span>  
  
#### <a name="to-create-the-required-artifacts"></a><span data-ttu-id="745dd-129">若要创建所需的项目</span><span class="sxs-lookup"><span data-stu-id="745dd-129">To create the required artifacts</span></span>  
  
1.  <span data-ttu-id="745dd-130">在 Windows 资源管理器，浏览到 C:\HowTos。</span><span class="sxs-lookup"><span data-stu-id="745dd-130">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="745dd-131">创建名为 OrderDocEnvelope.xsd 的新文本文档。</span><span class="sxs-lookup"><span data-stu-id="745dd-131">Create a new text document named OrderDocEnvelope.xsd.</span></span>  
  
3.  <span data-ttu-id="745dd-132">在记事本中打开 OrderDocEnvelope.xsd 架构。</span><span class="sxs-lookup"><span data-stu-id="745dd-132">Open the OrderDocEnvelope.xsd schema in Notepad.</span></span>  
  
4.  <span data-ttu-id="745dd-133">编辑该文档使用以下代码。</span><span class="sxs-lookup"><span data-stu-id="745dd-133">Edit the document using the following code.</span></span>  
  
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
  
5.  <span data-ttu-id="745dd-134">将 OrderDocEnvelope.xsd 另存为 utf-8，，然后关闭记事本。</span><span class="sxs-lookup"><span data-stu-id="745dd-134">Save OrderDocEnvelope.xsd as UTF-8, and then close Notepad.</span></span>  
  
6.  <span data-ttu-id="745dd-135">在 C:\HowTos 文件夹中，创建名为 Batch.xml 的新文本文档。</span><span class="sxs-lookup"><span data-stu-id="745dd-135">In the C:\HowTos folder, create a new text document named Batch.xml.</span></span>  
  
7.  <span data-ttu-id="745dd-136">在记事本中，打开 Batch.xml。</span><span class="sxs-lookup"><span data-stu-id="745dd-136">In Notepad, open Batch.xml.</span></span>  
  
8.  <span data-ttu-id="745dd-137">编辑该文档使用以下代码。</span><span class="sxs-lookup"><span data-stu-id="745dd-137">Edit the document using the following code.</span></span>  
  
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
  
9. <span data-ttu-id="745dd-138">保存并关闭 Batch.xml。</span><span class="sxs-lookup"><span data-stu-id="745dd-138">Save and close Batch.xml.</span></span>  
  
#### <a name="to-add-a-schemas-project-to-the-patterns-solution"></a><span data-ttu-id="745dd-139">若要将架构项目添加到模式解决方案</span><span class="sxs-lookup"><span data-stu-id="745dd-139">To add a schemas project to the Patterns solution</span></span>  
  
1.  <span data-ttu-id="745dd-140">在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。</span><span class="sxs-lookup"><span data-stu-id="745dd-140">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="745dd-141">在解决方案资源管理器中右键单击**解决方案模式**，依次指向**添加**，然后单击**新项目**。</span><span class="sxs-lookup"><span data-stu-id="745dd-141">In Solution Explorer, right-click **Solution 'Patterns'**, point to **Add**, and then click **New Project**.</span></span>  
  
3.  <span data-ttu-id="745dd-142">在中**添加新项目**对话框中，在项目类型窗格中，单击**BizTalk 项目**，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="745dd-142">In the **Add New Project** dialog box, in the Project types pane, click **BizTalk Projects**, and then do the following:</span></span>  
  
    1.  <span data-ttu-id="745dd-143">在模板窗格中单击**空的 BizTalk Server 项目**。</span><span class="sxs-lookup"><span data-stu-id="745dd-143">In the Templates pane, click **Empty BizTalk Server Project**.</span></span>  
  
    2.  <span data-ttu-id="745dd-144">在中**名称**框中，键入**Patterns.Schemas**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="745dd-144">In the **Name** box, type **Patterns.Schemas**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="745dd-145">在解决方案资源管理器中右键单击**Patterns.Schemas**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="745dd-145">In Solution Explorer, right-click **Patterns.Schemas**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="745dd-146">在属性窗口上**签名**选项卡上，选择**程序集签名**复选框。</span><span class="sxs-lookup"><span data-stu-id="745dd-146">In the Properties window, on the **Signing** tab, select the **Sign the assembly** check box.</span></span>  
  
6.  <span data-ttu-id="745dd-147">在中**选择强名称密钥文件**下拉列表中，单击 **\<新建...\>** .</span><span class="sxs-lookup"><span data-stu-id="745dd-147">In the **Choose a strong name key file** drop-down list, click **\<New...\>**.</span></span>  
  
7.  <span data-ttu-id="745dd-148">在中**创建强名称密钥**对话框框中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="745dd-148">In the **Create Strong Name Key** dialog box, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="745dd-149">在中**密钥文件名称**框中，键入**拆分**。</span><span class="sxs-lookup"><span data-stu-id="745dd-149">In the **Key file name** box, type **Splitting**.</span></span>  
  
    2.  <span data-ttu-id="745dd-150">清除**保护密钥文件使用密码**复选框，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="745dd-150">Clear the **Protect my key file with a password** check box, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="745dd-151">在属性窗口上**部署**选项卡上，在**应用程序名称**框中，键入**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="745dd-151">In the Properties window, on the **Deployment** tab, in the **Application Name** box, type **Microsoft.Practices.ESB**.</span></span>  
  
9. <span data-ttu-id="745dd-152">关闭“属性”窗口。</span><span class="sxs-lookup"><span data-stu-id="745dd-152">Close the Properties window.</span></span>  
  
#### <a name="to-add-the-artifacts-to-the-schemas-project"></a><span data-ttu-id="745dd-153">若要将项目添加到架构项目</span><span class="sxs-lookup"><span data-stu-id="745dd-153">To add the artifacts to the Schemas project</span></span>  
  
1.  <span data-ttu-id="745dd-154">在解决方案资源管理器中右键单击**Patterns.Schemas**，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="745dd-154">In Solution Explorer, right-click **Patterns.Schemas**, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="745dd-155">上**浏览**选项卡**添加引用**对话框中，浏览到并选择 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB。DynamicResolution.Schemas\bin\Debug\GlobalBank.ESB.DynamicResolution.Schemas.dll，并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="745dd-155">On the **Browse** tab of the **Add Reference** dialog box, browse to and select C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB.DynamicResolution.Schemas\bin\Debug\GlobalBank.ESB.DynamicResolution.Schemas.dll, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="745dd-156">在解决方案资源管理器中右键单击**Patterns.Schemas**，依次指向**添加**，然后单击**现有项**。</span><span class="sxs-lookup"><span data-stu-id="745dd-156">In Solution Explorer, right-click **Patterns.Schemas**, point to **Add**, and then click **Existing Item**.</span></span>  
  
4.  <span data-ttu-id="745dd-157">在中**添加现有项**对话框中，浏览并选择 C:\HowTos\OrderDocEnvelope.xsd，，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="745dd-157">In the **Add Existing Item** dialog box, browse to and select C:\HowTos\OrderDocEnvelope.xsd, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="745dd-158">保存解决方案的所有项目。</span><span class="sxs-lookup"><span data-stu-id="745dd-158">Save all solution artifacts.</span></span>  
  
6.  <span data-ttu-id="745dd-159">在解决方案资源管理器中右键单击**Patterns.Schemas**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="745dd-159">In Solution Explorer, right-click **Patterns.Schemas**, and then click **Deploy**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="745dd-160">本操作指南主题中创建的那些与使用相同的业务规则策略和路线[如何：选择使用业务规则策略路线](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)主题。</span><span class="sxs-lookup"><span data-stu-id="745dd-160">This How-to topic uses the same business rules policy and itineraries as those created in the [How to: Select an Itinerary Using a Business Rules Policy](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md) topic.</span></span> <span data-ttu-id="745dd-161">如果尚未完成该部分，请完成以下附加步骤。</span><span class="sxs-lookup"><span data-stu-id="745dd-161">If you have not already completed that section, please complete the following additional steps.</span></span> <span data-ttu-id="745dd-162">如果已完成该部分，继续到"步骤"部分。</span><span class="sxs-lookup"><span data-stu-id="745dd-162">If you have completed that section, continue directly to the "Steps" section.</span></span>  
  
#### <a name="to-create-a-business-rules-engine-bre-policy-to-select-an-itinerary-using-custom-message-properties"></a><span data-ttu-id="745dd-163">若要创建业务规则引擎 (BRE) 策略来选择使用自定义消息属性路线</span><span class="sxs-lookup"><span data-stu-id="745dd-163">To create a Business Rules Engine (BRE) policy to select an itinerary using custom message properties</span></span>  
  
1.  <span data-ttu-id="745dd-164">单击**启动**在任务栏上，依次指向**所有程序**，指向**BizTalk Server**，然后单击**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="745dd-164">Click **Start** on the taskbar, point to **All Programs**, point to **BizTalk Server**, and then click **Business Rule Composer**.</span></span>  
  
2.  <span data-ttu-id="745dd-165">在策略浏览器中右键单击**策略**，然后单击**添加新策略**。</span><span class="sxs-lookup"><span data-stu-id="745dd-165">In Policy Explorer, right-click **Policies**, and then click **Add New Policy**.</span></span> <span data-ttu-id="745dd-166">将策略命名**ResolveItineraryBasedOnCustomer**。</span><span class="sxs-lookup"><span data-stu-id="745dd-166">Name the policy **ResolveItineraryBasedOnCustomer**.</span></span>  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-west"></a><span data-ttu-id="745dd-167">若要添加客户 GlobalBank 西部选择规则</span><span class="sxs-lookup"><span data-stu-id="745dd-167">To add a selection rule for customer GlobalBank West</span></span>  
  
1.  <span data-ttu-id="745dd-168">在中**ResolveItineraryBasedOnCustomer**策略中，右键单击**版本 1.0 （未保存）** ，然后单击**添加新规则**。</span><span class="sxs-lookup"><span data-stu-id="745dd-168">In the **ResolveItineraryBasedOnCustomer** policy, right-click **Version 1.0 (not saved)**, and then click **Add New Rule**.</span></span> <span data-ttu-id="745dd-169">命名规则**SetGlobalBankWestItinerary**。</span><span class="sxs-lookup"><span data-stu-id="745dd-169">Name the rule **SetGlobalBankWestItinerary**.</span></span>  
  
2.  <span data-ttu-id="745dd-170">在事实浏览器中单击**XML 架构**选项卡上，右键单击**架构**，然后单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="745dd-170">In Facts Explorer, click the **XML Schemas** tab, right-click **Schemas**, and then click **Browse**.</span></span>  
  
3.  <span data-ttu-id="745dd-171">在中**架构文件**对话框中，浏览到 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB。DynamicResolution.Schemas，选择 NAOrderDoc.xsd，，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="745dd-171">In the **Schema Files** dialog box, browse to C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB.DynamicResolution.Schemas, select NAOrderDoc.xsd, and then click **Open**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="745dd-172">这是定义 NAOrderDoc.xml 消息，用于创建将用于测试的左和右消息的架构。</span><span class="sxs-lookup"><span data-stu-id="745dd-172">This is the schema that defines the NAOrderDoc.xml message, which was used to create the West and East messages you will use for testing.</span></span>  
  
4.  <span data-ttu-id="745dd-173">在事实浏览器中单击 NAOrderDoc.xsd 中，单击**文档类型**属性中为属性窗格，然后按**GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**。</span><span class="sxs-lookup"><span data-stu-id="745dd-173">In Facts Explorer, click NAOrderDoc.xsd, click the **Document Type** property in the Properties pane, and then type **GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="745dd-174">这是架构的完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="745dd-174">This is the fully qualified name of the schema.</span></span>  
  
5.  <span data-ttu-id="745dd-175">在事实浏览器中，展开**NAOrderDoc.xsd**，然后展开**OrderDoc**。</span><span class="sxs-lookup"><span data-stu-id="745dd-175">In Facts Explorer, expand **NAOrderDoc.xsd**, and then expand **OrderDoc**.</span></span>  
  
6.  <span data-ttu-id="745dd-176">在规则窗口中，右键单击**条件**，依次指向**谓词**，然后单击**相等**。</span><span class="sxs-lookup"><span data-stu-id="745dd-176">In the Rule window, right-click **Conditions**, point to **Predicates**, and then click **Equal**.</span></span>  
  
7.  <span data-ttu-id="745dd-177">从事实浏览器中，将**customerName**元素**argument1**节点下的**条件**。</span><span class="sxs-lookup"><span data-stu-id="745dd-177">From Facts Explorer, drag the **customerName** element to the **argument1** node under **Conditions**.</span></span>  
  
8.  <span data-ttu-id="745dd-178">单击**argument2**节点，并键入**GlobalBankWest**。</span><span class="sxs-lookup"><span data-stu-id="745dd-178">Click the **argument2** node, and then type **GlobalBankWest**.</span></span>  
  
9. <span data-ttu-id="745dd-179">在事实浏览器中单击**词汇**选项卡。展开**ESB。路线**词汇，展开**版本 1.1**，然后将拖**集路线名称**定义**操作**。</span><span class="sxs-lookup"><span data-stu-id="745dd-179">In Facts Explorer, click the **Vocabularies** tab. Expand the **ESB.Itinerary** vocabulary, expand **Version 1.1**, and then drag the **Set Itinerary Name** definition to **Actions**.</span></span>  
  
10. <span data-ttu-id="745dd-180">单击 **\<空字符串\>** ，然后键入**GlobalBankWestItinerary**。</span><span class="sxs-lookup"><span data-stu-id="745dd-180">Click **\<empty string\>** and then type **GlobalBankWestItinerary**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="745dd-181">本操作指南主题中稍后将此路线创建处理消息从 GlobalBank 西部。</span><span class="sxs-lookup"><span data-stu-id="745dd-181">Later in this How-to topic, you will create this itinerary to process messages from GlobalBank West.</span></span>  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-east"></a><span data-ttu-id="745dd-182">若要添加客户 GlobalBank 东部选择规则</span><span class="sxs-lookup"><span data-stu-id="745dd-182">To add a selection rule for customer GlobalBank East</span></span>  
  
1.  <span data-ttu-id="745dd-183">在策略浏览器中右键单击**SetGlobalBankWestItinerary**规则，然后依次**副本**。</span><span class="sxs-lookup"><span data-stu-id="745dd-183">In Policy Explorer, right-click the **SetGlobalBankWestItinerary** rule, and then click **Copy**.</span></span>  
  
2.  <span data-ttu-id="745dd-184">右键单击**版本 1.0 （未保存）** ，然后单击**粘贴**。</span><span class="sxs-lookup"><span data-stu-id="745dd-184">Right-click **Version 1.0 (not saved)**, and then click **Paste**.</span></span>  
  
3.  <span data-ttu-id="745dd-185">在中**新建规则名称**对话框中，键入**SetGlobalBankEastItinerary**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="745dd-185">In the **New Rule Name** dialog box, type **SetGlobalBankEastItinerary**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="745dd-186">在策略浏览器中单击**SetGlobalBankEastItinerary**规则。</span><span class="sxs-lookup"><span data-stu-id="745dd-186">In Policy Explorer, click the **SetGlobalBankEastItinerary** rule.</span></span>  
  
5.  <span data-ttu-id="745dd-187">在中**条件**部分中，右键单击**GlobalBankWest**，然后单击**重置参数**。</span><span class="sxs-lookup"><span data-stu-id="745dd-187">In the **Conditions** section, right-click **GlobalBankWest**, and then click **Reset argument**.</span></span>  
  
6.  <span data-ttu-id="745dd-188">单击**argument2**，然后键入**GlobalBankEast**。</span><span class="sxs-lookup"><span data-stu-id="745dd-188">Click **argument2**, and then type **GlobalBankEast**.</span></span>  
  
7.  <span data-ttu-id="745dd-189">在中**操作**部分中，右键单击**GlobalBankWestItinerary**，然后单击**重置参数**。</span><span class="sxs-lookup"><span data-stu-id="745dd-189">In the **Actions** section, right-click **GlobalBankWestItinerary**, and then click **Reset argument**.</span></span>  
  
8.  <span data-ttu-id="745dd-190">单击 **\<空字符串\>** ，然后键入**GlobalBankEastItinerary。**</span><span class="sxs-lookup"><span data-stu-id="745dd-190">Click **\<empty string\>** and then type **GlobalBankEastItinerary.**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="745dd-191">本操作指南主题中稍后将此路线创建处理消息从 GlobalBank 东部。</span><span class="sxs-lookup"><span data-stu-id="745dd-191">Later in this How-to topic, you will create this itinerary to process messages from GlobalBank East.</span></span>  
  
#### <a name="to-publish-and-deploy-the-policy"></a><span data-ttu-id="745dd-192">若要发布和部署策略</span><span class="sxs-lookup"><span data-stu-id="745dd-192">To publish and deploy the policy</span></span>  
  
1.  <span data-ttu-id="745dd-193">在策略浏览器下**ResolveItineraryBasedOnCustomer**策略中，单击**版本 1.0 （未保存）** ，然后单击**发布**。</span><span class="sxs-lookup"><span data-stu-id="745dd-193">In Policy Explorer, under the **ResolveItineraryBasedOnCustomer** policy, click **Version 1.0 (not saved)**, and then click **Publish**.</span></span>  
  
2.  <span data-ttu-id="745dd-194">在策略浏览器下**ResolveItineraryBasedOnCustomer**策略中，单击**版本 1.0-已发布**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="745dd-194">In Policy Explorer, under the **ResolveItineraryBasedOnCustomer** policy, click **Version 1.0 - Published**, and then click **Deploy**.</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model-for-globalbank-west-messages"></a><span data-ttu-id="745dd-195">若要创建 GlobalBank 西部消息 ESB 路线 DSL 模型</span><span class="sxs-lookup"><span data-stu-id="745dd-195">To create an ESB itinerary DSL model for GlobalBank West messages</span></span>  
  
1.  <span data-ttu-id="745dd-196">在中**Visual Studio**，打开 C:\HowTos\Patterns\Patterns.sln。</span><span class="sxs-lookup"><span data-stu-id="745dd-196">In **Visual Studio**, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="745dd-197">在解决方案资源管理器中右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。</span><span class="sxs-lookup"><span data-stu-id="745dd-197">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="745dd-198">在中**添加新项**对话框中，在模板窗格中，单击**ItineraryDsl**。</span><span class="sxs-lookup"><span data-stu-id="745dd-198">In the **Add New Item** dialog box, in the Templates pane, click **ItineraryDsl**.</span></span>  
  
4.  <span data-ttu-id="745dd-199">在中**名称**框中，键入**GlobalBankWestItinerary**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="745dd-199">In the **Name** box, type **GlobalBankWestItinerary**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-globalbank-west-itinerary"></a><span data-ttu-id="745dd-200">若要配置 GlobalBank 西部路线的属性</span><span class="sxs-lookup"><span data-stu-id="745dd-200">To configure the properties of the GlobalBank West itinerary</span></span>  
  
1.  <span data-ttu-id="745dd-201">在 Visual Studio 中，单击的设计图面**GlobalBankWestItinerary.itinerary**。</span><span class="sxs-lookup"><span data-stu-id="745dd-201">In Visual Studio, click the design surface of **GlobalBankWestItinerary.itinerary**.</span></span> <span data-ttu-id="745dd-202">在中**GlobalBankWestItinerary**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="745dd-202">In the **GlobalBankWestItinerary** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="745dd-203">在中**模型导出程序**下拉列表中，单击**数据库路线导出程序**。</span><span class="sxs-lookup"><span data-stu-id="745dd-203">In the **Model Exporter** drop-down list, click **Database Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="745dd-204">单击省略号按钮 （...） 下一步**行程数据库**属性。</span><span class="sxs-lookup"><span data-stu-id="745dd-204">Click the ellipsis button (...) next to the **Itinerary Database** property.</span></span>  
  
    3.  <span data-ttu-id="745dd-205">在中**连接属性**对话框中，选择承载路线的存储库数据库的 SQL 服务器，然后指定数据库的名称 (默认名称是**EsbItineraryDb**)。</span><span class="sxs-lookup"><span data-stu-id="745dd-205">In the **Connection Properties** dialog box, choose the SQL Server that hosts the itinerary repository database, and then specify the name of the database (the default name is **EsbItineraryDb**).</span></span>  
  
2.  <span data-ttu-id="745dd-206">在中**路线状态**下拉列表中，单击**已部署**。</span><span class="sxs-lookup"><span data-stu-id="745dd-206">In the **Itinerary Status** drop-down list, click **Deployed**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="745dd-207">此步骤允许您将导出到一个中央存储库; 路线可以选择和接收消息时，此存储库中附加路线。</span><span class="sxs-lookup"><span data-stu-id="745dd-207">This step enables you to export the itinerary to a central repository; itineraries can be selected and attached from this repository when messages are received.</span></span> <span data-ttu-id="745dd-208">稍后将配置路线选择器管道组件以使用 BRI 冲突解决程序来评估入站的消息，并从此存储库中选择相应的路线。</span><span class="sxs-lookup"><span data-stu-id="745dd-208">You will later configure the Itinerary Selector pipeline component to use the BRI resolver to evaluate inbound messages and select the appropriate itinerary from this repository.</span></span>  
  
#### <a name="to-define-the-structure-of-the-globalbank-west-itinerary"></a><span data-ttu-id="745dd-209">若要定义 GlobalBank 西部路线的结构</span><span class="sxs-lookup"><span data-stu-id="745dd-209">To define the structure of the GlobalBank West itinerary</span></span>  
  
1.  <span data-ttu-id="745dd-210">从工具箱拖动**接入点**至设计图面上的模型元素。</span><span class="sxs-lookup"><span data-stu-id="745dd-210">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="745dd-211">在中**OnRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="745dd-211">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="745dd-212">单击**名称**属性，并键入**ReceiveNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="745dd-212">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="745dd-213">在中**Extender**下拉列表中，单击**接入点 ESB 服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="745dd-213">In the **Extender** drop-down list, click **On-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="745dd-214">在中**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="745dd-214">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="745dd-215">在中**接收端口**下拉列表中，单击**OnRamp.Itinerary**。</span><span class="sxs-lookup"><span data-stu-id="745dd-215">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="745dd-216">从工具箱拖动**关闭负载增加**模型元素到设计图面，然后将它放到右侧**ReceiveNAOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="745dd-216">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **ReceiveNAOrder** model element.</span></span> <span data-ttu-id="745dd-217">在中**OffRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="745dd-217">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="745dd-218">单击**名称**属性，并键入**SendNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="745dd-218">Click the **Name** property, and then type **SendNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="745dd-219">在中**Extender**下拉列表中，单击**关闭负载增加 ESB 服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="745dd-219">In the **Extender** drop-down list, click **Off-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="745dd-220">在中**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。</span><span class="sxs-lookup"><span data-stu-id="745dd-220">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="745dd-221">在中**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。</span><span class="sxs-lookup"><span data-stu-id="745dd-221">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
3.  <span data-ttu-id="745dd-222">从工具箱拖动**路线服务**模型元素到设计图面，然后将其之间放置**ReceiveNAOrder**模型元素和**SendNAOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="745dd-222">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **ReceiveNAOrder** model element and the **SendNAOrder** model element.</span></span> <span data-ttu-id="745dd-223">在中**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="745dd-223">In the **ItineraryService1** properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="745dd-224">单击**名称**属性，并键入**RouteMessage**。</span><span class="sxs-lookup"><span data-stu-id="745dd-224">Click the **Name** property, and then type **RouteMessage**.</span></span>  
  
    2.  <span data-ttu-id="745dd-225">在**路线服务 Extender**下拉列表中，单击**接入点关闭路线服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="745dd-225">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Itinerary Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="745dd-226">在中**关闭负载增加**下拉列表中，展开**SendNAOrder**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="745dd-226">In the **Off-Ramp** drop-down list, expand **SendNAOrder**, and then click **Send Handlers**.</span></span>  
  
4.  <span data-ttu-id="745dd-227">右键单击**冲突解决程序**系列**RouteMessage**模型元素，然后单击**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="745dd-227">Right-click the **Resolver** collection of the **RouteMessage** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="745dd-228">在中**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="745dd-228">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="745dd-229">单击**名称**属性，并键入**StaticResolver**。</span><span class="sxs-lookup"><span data-stu-id="745dd-229">Click the **Name** property, and then type **StaticResolver**.</span></span>  
  
    2.  <span data-ttu-id="745dd-230">在中**解析程序实现**下拉列表中，单击**静态解析程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="745dd-230">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="745dd-231">在中**传输名称**下拉列表中，单击**文件**。</span><span class="sxs-lookup"><span data-stu-id="745dd-231">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="745dd-232">单击**传输位置**属性，并键入**C:\HowTos\Out\West%MessageID%.xml**。</span><span class="sxs-lookup"><span data-stu-id="745dd-232">Click the **Transport Location** property, and then type **C:\HowTos\Out\West%MessageID%.xml**.</span></span>  
  
5.  <span data-ttu-id="745dd-233">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="745dd-233">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="745dd-234">将从连接**ReceiveNAOrder**到模型元素**RouteMessage**模型元素。</span><span class="sxs-lookup"><span data-stu-id="745dd-234">Drag a connection from the **ReceiveNAOrder** model element to the  **RouteMessage** model element.</span></span>  
  
6.  <span data-ttu-id="745dd-235">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="745dd-235">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="745dd-236">将从连接**RouteMessage**到模型元素**SendNAOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="745dd-236">Drag a connection from the **RouteMessage** model element to the **SendNAOrder** model element.</span></span>  
  
#### <a name="to-export-the-globalbank-west-model-to-the-itinerary-database"></a><span data-ttu-id="745dd-237">若要将 GlobalBank 西部模型导出到路线的数据库</span><span class="sxs-lookup"><span data-stu-id="745dd-237">To export the GlobalBank West model to the itinerary database</span></span>  
  
1.  <span data-ttu-id="745dd-238">在 Visual Studio 中，右键单击设计图面的**GlobalBankWestItinerary**路线，并单击**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="745dd-238">In Visual Studio, right-click the design surface of the **GlobalBankWestItinerary** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="745dd-239">路线已导出到行程数据库，并且现在可由路线选择器组件。</span><span class="sxs-lookup"><span data-stu-id="745dd-239">The itinerary has been exported to the itinerary database and can now be used by the Itinerary Selector component.</span></span>  
  
2.  <span data-ttu-id="745dd-240">保存项目的所有项目。</span><span class="sxs-lookup"><span data-stu-id="745dd-240">Save all project artifacts.</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model-for-globalbank-east-message"></a><span data-ttu-id="745dd-241">若要创建 GlobalBank 东部消息 ESB 路线 DSL 模型</span><span class="sxs-lookup"><span data-stu-id="745dd-241">To create an ESB itinerary DSL model for GlobalBank East message</span></span>  
  
1.  <span data-ttu-id="745dd-242">在中**Visual Studio**，打开 C:\HowTos\Patterns.sln。</span><span class="sxs-lookup"><span data-stu-id="745dd-242">In **Visual Studio**, open C:\HowTos\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="745dd-243">在解决方案资源管理器中右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。</span><span class="sxs-lookup"><span data-stu-id="745dd-243">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="745dd-244">在中**添加新项**对话框中，在模板窗格中，单击**ItineraryDsl**。</span><span class="sxs-lookup"><span data-stu-id="745dd-244">In the **Add New Item** dialog box, in the Templates pane, click **ItineraryDsl**.</span></span>  
  
4.  <span data-ttu-id="745dd-245">在中**名称**框中，键入**GlobalBankEastItinerary**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="745dd-245">In the **Name** box, type **GlobalBankEastItinerary**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-globalbank-east-itinerary"></a><span data-ttu-id="745dd-246">若要配置 GlobalBank 东部路线的属性</span><span class="sxs-lookup"><span data-stu-id="745dd-246">To configure the properties of the GlobalBank East itinerary</span></span>  
  
1.  <span data-ttu-id="745dd-247">在 Visual Studio 中，单击的设计图面**GlobalBankEastItinerary.itinerary**。</span><span class="sxs-lookup"><span data-stu-id="745dd-247">In Visual Studio, click the design surface of **GlobalBankEastItinerary.itinerary**.</span></span> <span data-ttu-id="745dd-248">在中**GlobalBankEastItinerary**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="745dd-248">In the **GlobalBankEastItinerary** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="745dd-249">在中**模型导出程序**下拉列表中，单击**数据库路线导出程序**。</span><span class="sxs-lookup"><span data-stu-id="745dd-249">In the **Model Exporter** drop-down list, click **Database Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="745dd-250">单击省略号按钮 （...） 下一步**行程数据库**属性。</span><span class="sxs-lookup"><span data-stu-id="745dd-250">Click the ellipsis button (...) next to the **Itinerary Database** property.</span></span>  
  
    3.  <span data-ttu-id="745dd-251">在中**连接属性**对话框中，选择承载路线的存储库数据库的 SQL 服务器，然后指定数据库的名称 (默认名称是**EsbItineraryDb**)。</span><span class="sxs-lookup"><span data-stu-id="745dd-251">In the **Connection Properties** dialog box, choose the SQL Server that hosts the itinerary repository database, and then specify the name of the database (the default name is **EsbItineraryDb**).</span></span>  
  
2.  <span data-ttu-id="745dd-252">在中**路线状态**下拉列表中，单击**已部署**。</span><span class="sxs-lookup"><span data-stu-id="745dd-252">In the **Itinerary Status** drop-down list, click **Deployed**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="745dd-253">此步骤允许您将导出到一个中央存储库; 路线可以选择和接收消息时，此存储库中附加路线。</span><span class="sxs-lookup"><span data-stu-id="745dd-253">This step enables you to export the itinerary to a central repository; itineraries can be selected and attached from this repository when messages are received.</span></span> <span data-ttu-id="745dd-254">稍后将配置路线选择器管道组件以使用 BRI 冲突解决程序来评估入站的消息，并从此存储库中选择相应的路线。</span><span class="sxs-lookup"><span data-stu-id="745dd-254">You will later configure the Itinerary Selector pipeline component to use the BRI resolver to evaluate inbound messages and select the appropriate itinerary from this repository.</span></span>  
  
#### <a name="to-define-the-structure-of-the-globalbank-east-itinerary"></a><span data-ttu-id="745dd-255">若要定义 GlobalBank 东部路线的结构</span><span class="sxs-lookup"><span data-stu-id="745dd-255">To define the structure of the GlobalBank East itinerary</span></span>  
  
1.  <span data-ttu-id="745dd-256">从工具箱拖动**接入点**至设计图面上的模型元素。</span><span class="sxs-lookup"><span data-stu-id="745dd-256">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="745dd-257">在中**OnRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="745dd-257">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="745dd-258">单击**名称**属性，并键入**ReceiveNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="745dd-258">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="745dd-259">在中**Extender**下拉列表中，单击**接入点 ESB 服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="745dd-259">In the **Extender** drop-down list, click **On-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="745dd-260">在中**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="745dd-260">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="745dd-261">在中**接收端口**下拉列表中，单击**OnRamp.Itinerary**。</span><span class="sxs-lookup"><span data-stu-id="745dd-261">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="745dd-262">从工具箱拖动**关闭负载增加**模型元素到设计图面，然后将它放到右侧**ReceiveNAOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="745dd-262">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **ReceiveNAOrder** model element.</span></span> <span data-ttu-id="745dd-263">在中**OffRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="745dd-263">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="745dd-264">单击**名称**属性，并键入**SendNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="745dd-264">Click the **Name** property, and then type **SendNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="745dd-265">在中**Extender**下拉列表中，单击**关闭负载增加 ESB 服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="745dd-265">In the **Extender** drop-down list, click **Off-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="745dd-266">在中**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。</span><span class="sxs-lookup"><span data-stu-id="745dd-266">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="745dd-267">在中**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。</span><span class="sxs-lookup"><span data-stu-id="745dd-267">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
3.  <span data-ttu-id="745dd-268">从工具箱拖动**路线服务**模型元素到设计图面，然后将其之间放置**ReceiveNAOrder**模型元素和**SendNAOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="745dd-268">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **ReceiveNAOrder** model element and the **SendNAOrder** model element.</span></span> <span data-ttu-id="745dd-269">在中**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="745dd-269">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="745dd-270">单击**名称**属性，并键入**RouteMessage**。</span><span class="sxs-lookup"><span data-stu-id="745dd-270">Click the **Name** property, and then type **RouteMessage**.</span></span>  
  
    2.  <span data-ttu-id="745dd-271">在**路线服务 Extender**下拉列表中，单击**接入点关闭路线服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="745dd-271">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Itinerary Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="745dd-272">在中**关闭负载增加**下拉列表中，展开**SendNAOrder**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="745dd-272">In the **Off-Ramp** drop-down list, expand **SendNAOrder**, and then click **Send Handlers**.</span></span>  
  
4.  <span data-ttu-id="745dd-273">右键单击**冲突解决程序**系列**RouteMessage**模型元素，然后单击**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="745dd-273">Right-click the **Resolver** collection of the **RouteMessage** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="745dd-274">在中**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="745dd-274">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="745dd-275">单击**名称**属性，并键入**StaticResolver**。</span><span class="sxs-lookup"><span data-stu-id="745dd-275">Click the **Name** property, and then type **StaticResolver**.</span></span>  
  
    2.  <span data-ttu-id="745dd-276">在中**解析程序实现**下拉列表中，单击**静态解析程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="745dd-276">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="745dd-277">在中**传输名称**下拉列表中，单击**文件**。</span><span class="sxs-lookup"><span data-stu-id="745dd-277">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="745dd-278">单击**传输位置**属性，并键入**C:\HowTos\Out\East%MessageID%.xml**。</span><span class="sxs-lookup"><span data-stu-id="745dd-278">Click the **Transport Location** property, and then type **C:\HowTos\Out\East%MessageID%.xml**.</span></span>  
  
5.  <span data-ttu-id="745dd-279">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="745dd-279">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="745dd-280">将从连接**ReceiveNAOrder**到模型元素**RouteMessage**模型元素。</span><span class="sxs-lookup"><span data-stu-id="745dd-280">Drag a connection from the **ReceiveNAOrder** model element to the **RouteMessage** model element.</span></span>  
  
6.  <span data-ttu-id="745dd-281">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="745dd-281">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="745dd-282">将从连接**RouteMessage**到模型元素**SendNAOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="745dd-282">Drag a connection from the **RouteMessage** model element to the **SendNAOrder** model element.</span></span>  
  
#### <a name="to-export-the-globalbank-east-model-to-the-itinerary-database"></a><span data-ttu-id="745dd-283">若要将 GlobalBank 东部模型导出到路线的数据库</span><span class="sxs-lookup"><span data-stu-id="745dd-283">To export the GlobalBank East model to the itinerary database</span></span>  
  
1.  <span data-ttu-id="745dd-284">在 Visual Studio 中，右键单击设计图面的**GlobalBankEastItinerary**路线，并单击**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="745dd-284">In Visual Studio, right-click the design surface of the **GlobalBankEastItinerary** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="745dd-285">路线已导出到行程数据库，并且现在可由路线选择器组件。</span><span class="sxs-lookup"><span data-stu-id="745dd-285">The itinerary has been exported to the itinerary database and can now be used by the Itinerary Selector component.</span></span>  
  
2.  <span data-ttu-id="745dd-286">保存项目的所有项目。</span><span class="sxs-lookup"><span data-stu-id="745dd-286">Save all project artifacts.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="745dd-287">步骤</span><span class="sxs-lookup"><span data-stu-id="745dd-287">Steps</span></span>  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a><span data-ttu-id="745dd-288">若要创建和配置 ESB 接入点</span><span class="sxs-lookup"><span data-stu-id="745dd-288">To create and configure an ESB on-ramp</span></span>  
  
1.  <span data-ttu-id="745dd-289">单击**启动**在任务栏上，依次指向**所有程序**，指向**BizTalk Server**，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="745dd-289">Click **Start** on the taskbar, point to **All Programs**, point to **BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="745dd-290">在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后展开**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="745dd-290">In the BizTalk Server Administration Console, expand **BizTalk Group**, expand **Applications**, and then expand **Microsoft.Practices.ESB**.</span></span>  
  
3.  <span data-ttu-id="745dd-291">右键单击**接收位置**，依次指向**新建**，然后单击**单向接收位置**。</span><span class="sxs-lookup"><span data-stu-id="745dd-291">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
4.  <span data-ttu-id="745dd-292">在中**选择接收端口**对话框中，单击**OnRamp.Itinerary**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="745dd-292">In the **Select a Receive Port** dialog box, click **OnRamp.Itinerary**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="745dd-293">在中**接收位置属性**对话框中**名称**框中，键入**OnRamp.Itinerary.HowTo**。</span><span class="sxs-lookup"><span data-stu-id="745dd-293">In the **Receive Location Properties** dialog box, in the **Name** box, type **OnRamp.Itinerary.HowTo**.</span></span>  
  
6.  <span data-ttu-id="745dd-294">在中**类型**下拉列表中，单击**文件中，** ，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="745dd-294">In the **Type** drop-down list, click **FILE,** and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="745dd-295">在中**FILE 传输属性**对话框中**接收文件夹**框中，键入**C:\HowTos\DropFolder**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="745dd-295">In the **FILE Transport Properties** dialog box, in the **Receive folder** box, type **C:\HowTos\DropFolder**, and then click **OK**.</span></span>  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a><span data-ttu-id="745dd-296">若要配置路线选择器管道组件</span><span class="sxs-lookup"><span data-stu-id="745dd-296">To configure the Itinerary Selector pipeline component</span></span>  
  
1.  <span data-ttu-id="745dd-297">在中**接收位置属性**对话框中，单击**ItinerarySelectReceiveXml**中**接收管道**下拉列表，并单击省略号按钮 （...）。</span><span class="sxs-lookup"><span data-stu-id="745dd-297">In the **Receive Location Properties** dialog box, click **ItinerarySelectReceiveXml** in the **Receive pipeline** drop-down list, and then click the ellipsis button (...).</span></span>  
  
2.  <span data-ttu-id="745dd-298">使用**配置管道**对话框可以配置以下**路线选择器**组件属性：</span><span class="sxs-lookup"><span data-stu-id="745dd-298">Use the **Configure Pipeline** dialog box to configure the following **Itinerary Selector** component properties:</span></span>  
  
    1.  <span data-ttu-id="745dd-299">单击**ItineraryFactKey**属性，并键入**Resolver.Itinerary**。</span><span class="sxs-lookup"><span data-stu-id="745dd-299">Click the **ItineraryFactKey** property, and then type **Resolver.Itinerary**.</span></span>  
  
    2.  <span data-ttu-id="745dd-300">单击**ResolverConnectionString**属性，并键入**BRI:\\\policy=ResolveItineraryBasedOnCustomer;useMsg=true;recognizeMessageFormat=true;**</span><span class="sxs-lookup"><span data-stu-id="745dd-300">Click the **ResolverConnectionString** property, and then type **BRI:\\\policy=ResolveItineraryBasedOnCustomer;useMsg=true;recognizeMessageFormat=true;**</span></span>  
  
    3.  <span data-ttu-id="745dd-301">单击**确定**以关闭**配置管道**对话框。</span><span class="sxs-lookup"><span data-stu-id="745dd-301">Click **OK** to close the **Configure Pipeline** dialog box.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="745dd-302">由于此接收位置拆装一个 XML 交换，不不需要任何 XML 拆装器组件配置。</span><span class="sxs-lookup"><span data-stu-id="745dd-302">Because this receive location is disassembling an XML interchange, no XML Disassembler component configuration is required.</span></span>  
  
3.  <span data-ttu-id="745dd-303">单击**确定**以关闭**接收位置属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="745dd-303">Click **OK** to close the **Receive Location Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="745dd-304">在 BizTalk Server 管理控制台中，右键单击**OnRamp.Itinerary.HowTo**接收位置，然后依次**启用**。</span><span class="sxs-lookup"><span data-stu-id="745dd-304">In the BizTalk Server Administration Console, right-click the **OnRamp.Itinerary.HowTo** receive location, and then click **Enable**.</span></span>  
  
#### <a name="to-test-the-itinerary-selector-and-business-rules"></a><span data-ttu-id="745dd-305">若要测试的路线选择器和业务规则</span><span class="sxs-lookup"><span data-stu-id="745dd-305">To test the Itinerary Selector and business rules</span></span>  
  
1.  <span data-ttu-id="745dd-306">在 Windows 资源管理器，浏览到 C:\HowTos。</span><span class="sxs-lookup"><span data-stu-id="745dd-306">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="745dd-307">复制 （不移动） 到 DropFolder 文件夹 Batch.xml。</span><span class="sxs-lookup"><span data-stu-id="745dd-307">Copy (do not move) Batch.xml to the DropFolder folder.</span></span>  
  
3.  <span data-ttu-id="745dd-308">浏览到 C:\HowTos\Out。验证一个 West%MessageID%.xml 消息和两个 East%MessageID%.xml 消息已写入到的目录。</span><span class="sxs-lookup"><span data-stu-id="745dd-308">Browse to C:\HowTos\Out. Verify that one West%MessageID%.xml message and two East%MessageID%.xml messages have been written to the directory.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="745dd-309">虽然消息除外客户元素的值完全相同，但在处理使用不同路线，路线选择器管道组件的分辨率。</span><span class="sxs-lookup"><span data-stu-id="745dd-309">Although the messages are identical except for the value of the customer element, they were processed using different itineraries, based on the resolution of the Itinerary Selector pipeline component.</span></span>  
  
4.  <span data-ttu-id="745dd-310">在 BizTalk Server 管理控制台中，右键单击 OnRamp.Itinerary.HowTo 的接收位置，然后单击禁用。</span><span class="sxs-lookup"><span data-stu-id="745dd-310">In the BizTalk Server Administration Console, right-click the OnRamp.Itinerary.HowTo receive location, and then click Disable.</span></span>  
  
5.  <span data-ttu-id="745dd-311">之后**OnRamp.Itinerary.HowTo**接收位置被禁用，右键单击它，并单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="745dd-311">After the **OnRamp.Itinerary.HowTo** receive location is disabled, right-click it, and then click **Delete**.</span></span> <span data-ttu-id="745dd-312">在中**确认删除接收位置**对话框中，单击**是**。</span><span class="sxs-lookup"><span data-stu-id="745dd-312">In the **Confirm delete receive location** dialog box, click **Yes**.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="745dd-313">其他资源</span><span class="sxs-lookup"><span data-stu-id="745dd-313">Additional Resources</span></span>  
 <span data-ttu-id="745dd-314">有关详细信息，请参阅下列相关主题：</span><span class="sxs-lookup"><span data-stu-id="745dd-314">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="745dd-315">如何：选择使用业务规则策略路线</span><span class="sxs-lookup"><span data-stu-id="745dd-315">How to: Select an Itinerary Using a Business Rules Policy</span></span>](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [<span data-ttu-id="745dd-316">开发活动</span><span class="sxs-lookup"><span data-stu-id="745dd-316">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="745dd-317">安装和运行动态解析示例</span><span class="sxs-lookup"><span data-stu-id="745dd-317">Installing and Running the Dynamic Resolution Sample</span></span>](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)  
  
-   [<span data-ttu-id="745dd-318">使用动态解析和路由</span><span class="sxs-lookup"><span data-stu-id="745dd-318">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)  
  
-   [<span data-ttu-id="745dd-319">消息路由模式</span><span class="sxs-lookup"><span data-stu-id="745dd-319">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)