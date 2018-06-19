---
title: 如何： 实现基于内容的路由使用业务规则的一个已知的消息类型的策略 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 44451c85-929a-4d13-b0dd-53ea600d0859
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 878a6e180aaf7e5f37c5cf98ca0a67790917859a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010038"
---
# <a name="how-to-implement-content-based-routing-using-a-business-rules-policy-for-a-known-message-type"></a><span data-ttu-id="32da6-102">如何： 实现基于内容的路由使用业务规则的一个已知的消息类型的策略</span><span class="sxs-lookup"><span data-stu-id="32da6-102">How to: Implement Content-Based Routing Using a Business Rules Policy for a Known Message Type</span></span>
## <a name="goal"></a><span data-ttu-id="32da6-103">目的</span><span class="sxs-lookup"><span data-stu-id="32da6-103">Goal</span></span>  
 <span data-ttu-id="32da6-104">本部分演示如何创建动态路由消息，基于路线上一个已知的消息类型 （部署到 Microsoft BizTalk Server 配置数据库的架构） 的内容，使用业务规则策略。</span><span class="sxs-lookup"><span data-stu-id="32da6-104">This section demonstrates how to create an itinerary that dynamically routes a message, based on the content of a known message type (schema deployed to the Microsoft BizTalk Server Configuration database), using a business rules policy.</span></span>  
  
 <span data-ttu-id="32da6-105">在本操作方法主题中，你将完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="32da6-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="32da6-106">创建业务规则策略将使用基于内容将消息路由。</span><span class="sxs-lookup"><span data-stu-id="32da6-106">Create a business rules policy that will be used to route a message based on content.</span></span>  
  
-   <span data-ttu-id="32da6-107">使用 BRE 解析程序将消息路由动态创建路线的路由滑动。</span><span class="sxs-lookup"><span data-stu-id="32da6-107">Create an itinerary routing slip with a BRE resolver to dynamically route a message.</span></span>  
  
-   <span data-ttu-id="32da6-108">测试路线使用路线测试客户端示例应用程序。</span><span class="sxs-lookup"><span data-stu-id="32da6-108">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="32da6-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="32da6-109">Prerequisites</span></span>  
 <span data-ttu-id="32da6-110">此操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="32da6-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="32da6-111">开始之前</span><span class="sxs-lookup"><span data-stu-id="32da6-111">Before You Begin</span></span>  
 <span data-ttu-id="32da6-112">本操作方法主题中的更高版本执行的步骤之前，请完成以下任务：</span><span class="sxs-lookup"><span data-stu-id="32da6-112">Complete the following tasks before you perform the steps later in this How-to topic:</span></span>  
  
-   <span data-ttu-id="32da6-113">创建 GlobalBank 西部测试消息。</span><span class="sxs-lookup"><span data-stu-id="32da6-113">Create the GlobalBank West test message.</span></span>  
  
-   <span data-ttu-id="32da6-114">创建 GlobalBank 东部测试消息。</span><span class="sxs-lookup"><span data-stu-id="32da6-114">Create the GlobalBank East test message.</span></span>  
  
 <span data-ttu-id="32da6-115">下面的过程介绍如何执行其中每个操作。</span><span class="sxs-lookup"><span data-stu-id="32da6-115">The following procedures describe how to do each of these.</span></span>  
  
#### <a name="to-create-the-globalbank-west-test-message"></a><span data-ttu-id="32da6-116">若要创建 GlobalBank 西部测试消息</span><span class="sxs-lookup"><span data-stu-id="32da6-116">To create the GlobalBank West test message</span></span>  
  
1.  <span data-ttu-id="32da6-117">在 Windows 资源管理器，浏览到 C:\HowTos。</span><span class="sxs-lookup"><span data-stu-id="32da6-117">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="32da6-118">创建一份 NAOrderDoc.xml，并将其命名为复制 West.xml。</span><span class="sxs-lookup"><span data-stu-id="32da6-118">Create a copy of NAOrderDoc.xml, and then name the copy West.xml.</span></span>  
  
3.  <span data-ttu-id="32da6-119">在记事本中，打开 West.xml，并将的值**customerName**元素**GlobalBankWest**。</span><span class="sxs-lookup"><span data-stu-id="32da6-119">In Notepad, open West.xml, and then change the value of the **customerName** element to **GlobalBankWest**.</span></span>  
  
4.  <span data-ttu-id="32da6-120">将 West.xml 另存为 utf-8，，然后关闭记事本。</span><span class="sxs-lookup"><span data-stu-id="32da6-120">Save West.xml as UTF-8, and then close Notepad.</span></span>  
  
#### <a name="to-create-the-globalbank-east-test-message"></a><span data-ttu-id="32da6-121">若要创建 GlobalBank 东部测试消息</span><span class="sxs-lookup"><span data-stu-id="32da6-121">To create the GlobalBank East test message</span></span>  
  
1.  <span data-ttu-id="32da6-122">在 Windows 资源管理器，浏览到 C:\HowTos。</span><span class="sxs-lookup"><span data-stu-id="32da6-122">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="32da6-123">创建一份 NAOrderDoc.xml，并将其命名为复制 East.xml。</span><span class="sxs-lookup"><span data-stu-id="32da6-123">Create a copy of NAOrderDoc.xml, and then name the copy East.xml.</span></span>  
  
3.  <span data-ttu-id="32da6-124">在记事本中，打开 East.xml，并将的值**customerName**元素**GlobalBankEast**。</span><span class="sxs-lookup"><span data-stu-id="32da6-124">In Notepad, open East.xml, and then change the value of the **customerName** element to **GlobalBankEast**.</span></span>  
  
4.  <span data-ttu-id="32da6-125">将 East.xml 另存为 utf-8，，然后关闭记事本。</span><span class="sxs-lookup"><span data-stu-id="32da6-125">Save East.xml as UTF-8, and then close Notepad.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="32da6-126">步骤</span><span class="sxs-lookup"><span data-stu-id="32da6-126">Steps</span></span>  
  
#### <a name="to-create-a-bre-policy-to-route-using-custom-message-properties"></a><span data-ttu-id="32da6-127">若要创建 BRE 策略来路由使用自定义消息属性</span><span class="sxs-lookup"><span data-stu-id="32da6-127">To create a BRE policy to route using custom message properties</span></span>  
 <span data-ttu-id="32da6-128">此规则将使用客户的动态设置用于将消息路由到的终结点。</span><span class="sxs-lookup"><span data-stu-id="32da6-128">This rule will use the customer's name to dynamically set the endpoint used to route the message.</span></span>  
  
1.  <span data-ttu-id="32da6-129">单击**启动**在任务栏中，指向**所有程序**，指向**BizTalk Server**，然后单击**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="32da6-129">Click **Start** on the taskbar, point to **All Programs**, point to **BizTalk Server**, and then click **Business Rule Composer**.</span></span>  
  
2.  <span data-ttu-id="32da6-130">在策略资源管理器中，右键单击**策略**，然后单击**添加新策略**。</span><span class="sxs-lookup"><span data-stu-id="32da6-130">In Policy Explorer, right-click **Policies**, and then click **Add New Policy**.</span></span> <span data-ttu-id="32da6-131">命名策略时**RouteBasedOnCustomerKnownType**。</span><span class="sxs-lookup"><span data-stu-id="32da6-131">Name the policy **RouteBasedOnCustomerKnownType**.</span></span>  
  
#### <a name="to-add-a-routing-rule-for-customer-globalbank-west"></a><span data-ttu-id="32da6-132">若要添加客户 GlobalBank 西部的路由规则</span><span class="sxs-lookup"><span data-stu-id="32da6-132">To add a routing rule for customer GlobalBank West</span></span>  
  
1.  <span data-ttu-id="32da6-133">在**RouteBasedOnCustomerKnownType**策略，右键单击 **（不保存） 1.0 版**，然后单击**添加新规则**。</span><span class="sxs-lookup"><span data-stu-id="32da6-133">In the **RouteBasedOnCustomerKnownType** policy, right-click **Version 1.0 (not saved)**, and then click **Add New Rule**.</span></span> <span data-ttu-id="32da6-134">命名规则**SetWestEndpoint**。</span><span class="sxs-lookup"><span data-stu-id="32da6-134">Name the rule **SetWestEndpoint**.</span></span>  
  
2.  <span data-ttu-id="32da6-135">在事实数据资源管理器，单击**XML 架构**选项卡上，右键单击**架构**，然后单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="32da6-135">In Facts Explorer, click the **XML Schemas** tab, right-click **Schemas**, and then click **Browse**.</span></span>  
  
3.  <span data-ttu-id="32da6-136">在**架构文件**对话框中，浏览到 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB。DynamicResolution.Schemas，选择**NAOrderDoc.xsd**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="32da6-136">In the **Schema Files** dialog box, browse to C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB.DynamicResolution.Schemas, select **NAOrderDoc.xsd**, and then click **Open**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="32da6-137">这是定义 NAOrderDoc.xml 消息，用于创建将用于测试的西部和东部消息的架构。</span><span class="sxs-lookup"><span data-stu-id="32da6-137">This is the schema that defines the NAOrderDoc.xml message, which was used to create the West and East messages you will use for testing.</span></span>  
  
4.  <span data-ttu-id="32da6-138">在事实数据资源管理器，单击**NAOrderDoc.xsd**，然后在属性窗格中，单击**文档类型**属性，再然后键入**GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.</span><span class="sxs-lookup"><span data-stu-id="32da6-138">In Facts Explorer, click **NAOrderDoc.xsd**, and then in the Properties pane, click the **Document Type** property, and then type **GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="32da6-139">这是架构的完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="32da6-139">This is the fully qualified name of the schema.</span></span>  
  
5.  <span data-ttu-id="32da6-140">在事实数据资源管理器中，展开**NAOrderDoc.xsd**，然后展开**OrderDoc**。</span><span class="sxs-lookup"><span data-stu-id="32da6-140">In Facts Explorer, expand **NAOrderDoc.xsd**, and then expand **OrderDoc**.</span></span>  
  
6.  <span data-ttu-id="32da6-141">在规则窗口中，右键单击**条件**，指向**谓词**，然后单击**相等**。</span><span class="sxs-lookup"><span data-stu-id="32da6-141">In the Rule window, right-click **Conditions**, point to **Predicates**, and then click **Equal**.</span></span>  
  
7.  <span data-ttu-id="32da6-142">从事实数据资源管理器拖动**customerName**元素**argument1**节点下的**条件**。</span><span class="sxs-lookup"><span data-stu-id="32da6-142">From Facts Explorer, drag the **customerName** element to the **argument1** node under **Conditions**.</span></span>  
  
8.  <span data-ttu-id="32da6-143">单击**argument2**节点，并键入**GlobalBankWest**。</span><span class="sxs-lookup"><span data-stu-id="32da6-143">Click the **argument2** node, and then type **GlobalBankWest**.</span></span>  
  
9. <span data-ttu-id="32da6-144">在事实数据资源管理器，单击**词汇**选项卡上，展开**ESB。EndPointInfo**，然后展开**版本 1.0**。</span><span class="sxs-lookup"><span data-stu-id="32da6-144">In Facts Explorer, click the **Vocabularies** tab, expand **ESB.EndPointInfo**, and then expand **Version 1.0**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="32da6-145">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括可以用于在 ESB 中创建使用规则的多个词汇。</span><span class="sxs-lookup"><span data-stu-id="32da6-145">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes several vocabularies that can be used for creating rules for use in the ESB.</span></span> <span data-ttu-id="32da6-146">其中一些应替换或扩充自己词汇。</span><span class="sxs-lookup"><span data-stu-id="32da6-146">Some of these should be replaced or augmented with your own vocabularies.</span></span> <span data-ttu-id="32da6-147">例如， **DynamicRunTimeMaptypes**拥有中提供的映射用于定义**GlobalBank**示例。</span><span class="sxs-lookup"><span data-stu-id="32da6-147">For example, the **DynamicRunTimeMaptypes** has definitions for the maps provided in the **GlobalBank** samples.</span></span>  
  
10. <span data-ttu-id="32da6-148">从事实数据资源管理器拖动**设置终结点出站传输位置**定义与**操作**。</span><span class="sxs-lookup"><span data-stu-id="32da6-148">From Facts Explorer, drag the **Set End Point Outbound Transport Location** definition to **Actions**.</span></span>  
  
11. <span data-ttu-id="32da6-149">单击**\<空字符串\>** 然后键入**C:\HowTos\Out\West%MessageID%.xml**。</span><span class="sxs-lookup"><span data-stu-id="32da6-149">Click **\<empty string\>** and then type **C:\HowTos\Out\West%MessageID%.xml**.</span></span>  
  
12. <span data-ttu-id="32da6-150">从事实数据资源管理器拖动**设置终结点出站传输类型**定义与**操作**。</span><span class="sxs-lookup"><span data-stu-id="32da6-150">From Facts Explorer, drag the **Set End Point Outbound Transport Type** definition to **Actions**.</span></span>  
  
13. <span data-ttu-id="32da6-151">在事实数据资源管理器中，展开**ESB。TransportTypes**，展开**版本 1.0**，然后拖动**适配器提供程序**定义与**\<空字符串\>**.</span><span class="sxs-lookup"><span data-stu-id="32da6-151">In Facts Explorer, expand **ESB.TransportTypes**, expand **Version 1.0**, and then drag the **Adaptor Providers** definition to **\<empty string\>**.</span></span>  
  
14. <span data-ttu-id="32da6-152">在**操作**窗格中，展开**适配器提供程序**下拉列表，然后单击**文件**。</span><span class="sxs-lookup"><span data-stu-id="32da6-152">In the **Actions** pane, expand the **Adaptor Providers** drop-down list, and then click **FILE**.</span></span>  
  
#### <a name="to-add-a-routing-rule-for-customer-globalbank-east"></a><span data-ttu-id="32da6-153">若要添加客户 GlobalBank 东部的路由规则</span><span class="sxs-lookup"><span data-stu-id="32da6-153">To add a routing rule for customer GlobalBank East</span></span>  
  
1.  <span data-ttu-id="32da6-154">在策略资源管理器中，右键单击**SetWestEndpoint**规则，并依次**复制**。</span><span class="sxs-lookup"><span data-stu-id="32da6-154">In Policy Explorer, right-click the **SetWestEndpoint** rule, and then click **Copy**.</span></span>  
  
2.  <span data-ttu-id="32da6-155">右键单击 **（不保存） 1.0 版**，然后单击**粘贴**。</span><span class="sxs-lookup"><span data-stu-id="32da6-155">Right-click **Version 1.0 (not saved)**, and then click **Paste**.</span></span>  
  
3.  <span data-ttu-id="32da6-156">在**新规则名称**对话框中，键入**SetEastEndpoint**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="32da6-156">In the **New Rule Name** dialog box, type **SetEastEndpoint**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="32da6-157">在策略资源管理器，单击**SetEastEndpoint**规则。</span><span class="sxs-lookup"><span data-stu-id="32da6-157">In Policy Explorer, click the **SetEastEndpoint** rule.</span></span>  
  
5.  <span data-ttu-id="32da6-158">在**条件**部分中，右键单击**GlobalBankWest**，然后单击**重置参数**。</span><span class="sxs-lookup"><span data-stu-id="32da6-158">In the **Conditions** section, right-click **GlobalBankWest**, and then click **Reset argument**.</span></span>  
  
6.  <span data-ttu-id="32da6-159">单击**argument2**，然后键入**GlobalBankEast**。</span><span class="sxs-lookup"><span data-stu-id="32da6-159">Click **argument2**, and then type **GlobalBankEast**.</span></span>  
  
7.  <span data-ttu-id="32da6-160">在**操作**部分中，右键单击**C:\HowTos\Out\West%MessageID%.xml**，然后单击**重置参数**。</span><span class="sxs-lookup"><span data-stu-id="32da6-160">In the **Actions** section, right-click **C:\HowTos\Out\West%MessageID%.xml**, and then click **Reset argument**.</span></span>  
  
8.  <span data-ttu-id="32da6-161">单击**\<空字符串\>**，然后键入**C:\HowTos\Out\East%MessageID%.xml**。</span><span class="sxs-lookup"><span data-stu-id="32da6-161">Click **\<empty string\>**, and then type **C:\HowTos\Out\East%MessageID%.xml**.</span></span>  
  
#### <a name="to-add-a-routing-rule-for-unknown-customers"></a><span data-ttu-id="32da6-162">若要为未知客户添加一个路由规则</span><span class="sxs-lookup"><span data-stu-id="32da6-162">To add a routing rule for unknown customers</span></span>  
  
1.  <span data-ttu-id="32da6-163">在 RouteBasedOnCustomerKnownType 策略中，右键单击 （不保存），版本 1.0，然后单击添加新规则。</span><span class="sxs-lookup"><span data-stu-id="32da6-163">In the RouteBasedOnCustomerKnownType policy, right-click Version 1.0 (not saved), and then click Add New Rule.</span></span> <span data-ttu-id="32da6-164">命名规则 SetUnknownCustomerEndpoint。</span><span class="sxs-lookup"><span data-stu-id="32da6-164">Name the rule SetUnknownCustomerEndpoint.</span></span>  
  
2.  <span data-ttu-id="32da6-165">在规则窗口中，右键单击条件，，然后单击添加逻辑 and。</span><span class="sxs-lookup"><span data-stu-id="32da6-165">In the Rule window, right-click Conditions, and then click Add logical AND.</span></span>  
  
3.  <span data-ttu-id="32da6-166">在规则窗口中，右键单击，指向谓词，，然后单击 NotEqual。</span><span class="sxs-lookup"><span data-stu-id="32da6-166">In the Rule window, right-click AND, point to Predicates, and then click NotEqual.</span></span>  
  
4.  <span data-ttu-id="32da6-167">在事实数据资源管理器中，单击 XML 架构选项卡，展开 NAOrderDoc.xsd，，然后展开 OrderDoc。</span><span class="sxs-lookup"><span data-stu-id="32da6-167">In Facts Explorer, click the XML Schemas tab, expand NAOrderDoc.xsd, and then expand OrderDoc.</span></span>  
  
5.  <span data-ttu-id="32da6-168">从事实数据资源管理器中，将 customerName 元素拖到条件下的 argument1 节点。</span><span class="sxs-lookup"><span data-stu-id="32da6-168">From Facts Explorer, drag the customerName element to the argument1 node under Conditions.</span></span>  
  
6.  <span data-ttu-id="32da6-169">单击 argument2 节点，然后键入 GlobalBankWest。</span><span class="sxs-lookup"><span data-stu-id="32da6-169">Click the argument2 node, and then type GlobalBankWest.</span></span>  
  
7.  <span data-ttu-id="32da6-170">在规则窗口中，右键单击，指向谓词，，然后单击 NotEqual。</span><span class="sxs-lookup"><span data-stu-id="32da6-170">In the Rule window, right-click AND, point to Predicates, and then click NotEqual.</span></span>  
  
8.  <span data-ttu-id="32da6-171">从事实数据资源管理器中，将 customerName 元素拖到条件下的 argument1 节点。</span><span class="sxs-lookup"><span data-stu-id="32da6-171">From Facts Explorer, drag the customerName element to the argument1 node under Conditions.</span></span>  
  
9. <span data-ttu-id="32da6-172">单击 argument2 节点，然后键入 GlobalBankEast。</span><span class="sxs-lookup"><span data-stu-id="32da6-172">Click the argument2 node, and then type GlobalBankEast.</span></span>  
  
10. <span data-ttu-id="32da6-173">在事实数据资源管理器，单击词汇选项卡中，展开 ESB。EndPointInfo，然后展开版本 1.0。</span><span class="sxs-lookup"><span data-stu-id="32da6-173">In Facts Explorer, click the Vocabularies tab, expand ESB.EndPointInfo, and then expand Version 1.0.</span></span>  
  
11. <span data-ttu-id="32da6-174">从事实数据资源管理器中，将设置终结点出站传输位置定义拖动到操作。</span><span class="sxs-lookup"><span data-stu-id="32da6-174">From Facts Explorer, drag the Set End Point Outbound Transport Location definition to Actions.</span></span>  
  
12. <span data-ttu-id="32da6-175">单击\<空字符串\>，然后键入 C:\HowTos\Out\CustomerUnknown%MessageID%.xml。</span><span class="sxs-lookup"><span data-stu-id="32da6-175">Click \<empty string\>, and then type C:\HowTos\Out\CustomerUnknown%MessageID%.xml.</span></span>  
  
13. <span data-ttu-id="32da6-176">从事实数据资源管理器中，将设置终结点出站传输类型定义拖动到操作。</span><span class="sxs-lookup"><span data-stu-id="32da6-176">From Facts Explorer, drag the Set End Point Outbound Transport Type definition to Actions.</span></span>  
  
14. <span data-ttu-id="32da6-177">在事实数据资源管理器中，展开 ESB。TransportTypes，展开版本 1.0，然后拖动到的适配器提供程序定义\<空字符串\>。</span><span class="sxs-lookup"><span data-stu-id="32da6-177">In Facts Explorer, expand ESB.TransportTypes, expand Version 1.0, and then drag the Adaptor Providers definition to \<empty string\>.</span></span>  
  
15. <span data-ttu-id="32da6-178">在操作窗格中，展开适配器提供程序下拉列表中，，然后单击文件。</span><span class="sxs-lookup"><span data-stu-id="32da6-178">In the Actions pane, expand the Adaptor Providers drop-down list, and then click FILE.</span></span>  
  
#### <a name="to-publish-and-deploy-the-policy"></a><span data-ttu-id="32da6-179">若要发布和部署策略</span><span class="sxs-lookup"><span data-stu-id="32da6-179">To publish and deploy the policy</span></span>  
  
1.  <span data-ttu-id="32da6-180">在策略资源管理器下**RouteBasedOnCustomerKnownType**策略中，右击 **（不保存） 1.0 版**，然后单击**发布**。</span><span class="sxs-lookup"><span data-stu-id="32da6-180">In Policy Explorer, under the **RouteBasedOnCustomerKnownType** policy, right click **Version 1.0 (not saved)**, and then click **Publish**.</span></span>  
  
2.  <span data-ttu-id="32da6-181">在策略资源管理器下**RouteBasedOnCustomerKnownType**策略中，右击**版本 1.0-发布**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="32da6-181">In Policy Explorer, under the **RouteBasedOnCustomerKnownType** policy, right click **Version 1.0 - Published**, and then click **Deploy**.</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="32da6-182">若要创建 ESB 路线 DSL 模型</span><span class="sxs-lookup"><span data-stu-id="32da6-182">To create an ESB itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="32da6-183">在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。</span><span class="sxs-lookup"><span data-stu-id="32da6-183">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="32da6-184">在解决方案资源管理器，右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。</span><span class="sxs-lookup"><span data-stu-id="32da6-184">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="32da6-185">在**添加新项**对话框中，在**名称**框中，键入**CbrKnownType**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="32da6-185">In the **Add New Item** dialog box, in the **Name** box, type **CbrKnownType**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="32da6-186">若要配置路线的属性</span><span class="sxs-lookup"><span data-stu-id="32da6-186">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="32da6-187">在 Visual Studio 中，单击的设计图面**CbrKnownType.itinerary**。</span><span class="sxs-lookup"><span data-stu-id="32da6-187">In Visual Studio, click the design surface of **CbrKnownType.itinerary**.</span></span> <span data-ttu-id="32da6-188">在**CbrKnownType**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="32da6-188">In the **CbrKnownType** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="32da6-189">在**模型导出程序**下拉列表中，单击**XML 路线导出程序**。</span><span class="sxs-lookup"><span data-stu-id="32da6-189">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="32da6-190">在**扩展程序设置**部分，旁边**路线 XML 文件**属性，单击省略号按钮 （…）。</span><span class="sxs-lookup"><span data-stu-id="32da6-190">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="32da6-191">在**选择 XML 文件**对话框中，键入**C:\HowTos\Itineraries\CbrKnownType**中**文件名**框中，并依次**保存**。</span><span class="sxs-lookup"><span data-stu-id="32da6-191">In the **Select XML File** dialog box, type **C:\HowTos\Itineraries\CbrKnownType** in the **File name** box, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="32da6-192">此步骤允许您路线作为 XML 导出到本地文件位置。</span><span class="sxs-lookup"><span data-stu-id="32da6-192">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="32da6-193">通过到路线的数据库，而不导出到本地文件的位置，一条路线使测试路线使用 ESB 测试客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="32da6-193">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="32da6-194">你将完成本操作方法主题中后面此过程。</span><span class="sxs-lookup"><span data-stu-id="32da6-194">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="32da6-195">若要定义路线的结构</span><span class="sxs-lookup"><span data-stu-id="32da6-195">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="32da6-196">从工具箱中，拖动**上负载增加**到设计图面上的模型元素。</span><span class="sxs-lookup"><span data-stu-id="32da6-196">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="32da6-197">在**OnRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="32da6-197">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="32da6-198">单击**名称**属性，再然后键入**ReceiveNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="32da6-198">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="32da6-199">在**扩展程序**下拉列表中，单击**上负载增加 ESB 扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="32da6-199">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="32da6-200">在**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="32da6-200">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="32da6-201">在**接收端口**下拉列表中，单击**OnRamp.Itinerary**。</span><span class="sxs-lookup"><span data-stu-id="32da6-201">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="32da6-202">从工具箱中，拖动**关闭负载增加**模型元素到设计图面，然后将其放到右侧**ReceiveNAOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="32da6-202">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **ReceiveNAOrder** model element.</span></span> <span data-ttu-id="32da6-203">在**OffRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="32da6-203">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="32da6-204">单击**名称**属性，再然后键入**SendRegionalOrders**。</span><span class="sxs-lookup"><span data-stu-id="32da6-204">Click the **Name** property, and then type **SendRegionalOrders**.</span></span>  
  
    2.  <span data-ttu-id="32da6-205">在**扩展程序**下拉列表中，单击**关闭负载增加 ESB 扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="32da6-205">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="32da6-206">在**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。</span><span class="sxs-lookup"><span data-stu-id="32da6-206">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="32da6-207">在**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。</span><span class="sxs-lookup"><span data-stu-id="32da6-207">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
3.  <span data-ttu-id="32da6-208">从工具箱中，拖动**路线服务**模型元素到设计图面，然后将它之间**ReceiveNAOrder**模型元素和**SendRegionalOrders**模型元素。</span><span class="sxs-lookup"><span data-stu-id="32da6-208">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **ReceiveNAOrder** model element and the **SendRegionalOrders** model element.</span></span> <span data-ttu-id="32da6-209">在**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="32da6-209">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="32da6-210">单击**名称**属性，再然后键入**SendPortFilter**。</span><span class="sxs-lookup"><span data-stu-id="32da6-210">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="32da6-211">在**路线服务扩展程序**下拉列表中，单击**关闭负载增加扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="32da6-211">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="32da6-212">在**关闭负载增加**下拉列表中，展开**SendRegionalOrders**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="32da6-212">In the **Off-Ramp** drop-down list, expand **SendRegionalOrders**, and then click **Send Handlers**.</span></span>  
  
4.  <span data-ttu-id="32da6-213">右键单击**冲突解决程序**集合**SendPortFilter**模型元素，并依次**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="32da6-213">Right-click the **Resolver** collection of the **SendPortFilter** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="32da6-214">在**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="32da6-214">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="32da6-215">单击**名称**属性，再然后键入**RouteRegionalOrders**。</span><span class="sxs-lookup"><span data-stu-id="32da6-215">Click the **Name** property, and then type **RouteRegionalOrders**.</span></span>  
  
    2.  <span data-ttu-id="32da6-216">在**传输名称**下拉列表中，单击**BRE**。</span><span class="sxs-lookup"><span data-stu-id="32da6-216">In the **Transport Name** drop-down list, click **BRE**.</span></span>  
  
    3.  <span data-ttu-id="32da6-217">在**解析程序实现**下拉列表中，单击**Bre 冲突解决程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="32da6-217">In the **Resolver Implementation** drop-down list, click **Bre Resolver Extension**.</span></span>  
  
    4.  <span data-ttu-id="32da6-218">在**策略**下拉列表中，单击**RouteBasedOnCustomerKnownType**。</span><span class="sxs-lookup"><span data-stu-id="32da6-218">In the **Policy** drop-down list, click **RouteBasedOnCustomerKnownType**.</span></span>  
  
    5.  <span data-ttu-id="32da6-219">在**识别消息格式**下拉列表中，单击**True**。</span><span class="sxs-lookup"><span data-stu-id="32da6-219">In the **Recognize Message Format** drop-down list click **True**.</span></span>  
  
    6.  <span data-ttu-id="32da6-220">在**UseMsg**下拉列表中，单击**True**。</span><span class="sxs-lookup"><span data-stu-id="32da6-220">In the **UseMsg** drop-down list, click **True**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="32da6-221">如果你使用从业务流程，BRE 冲突解决程序扩展**recognizeMessageFormat**属性必须设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="32da6-221">If you use the BRE Resolver Extension from orchestration, the **recognizeMessageFormat** property must be set to **False**.</span></span>  
  
5.  <span data-ttu-id="32da6-222">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="32da6-222">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="32da6-223">将从连接**ReceiveNAOrder**到模型元素**SendPortFilter**模型元素。</span><span class="sxs-lookup"><span data-stu-id="32da6-223">Drag a connection from the **ReceiveNAOrder** model element to the **SendPortFilter** model element.</span></span>  
  
6.  <span data-ttu-id="32da6-224">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="32da6-224">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="32da6-225">将从连接**SendPortFilter**到模型元素**SendRegionalOrders**模型元素。</span><span class="sxs-lookup"><span data-stu-id="32da6-225">Drag a connection from the **SendPortFilter** model element to the **SendRegionalOrders** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="32da6-226">若要导出与路线测试客户端一起使用的模型</span><span class="sxs-lookup"><span data-stu-id="32da6-226">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="32da6-227">在 Visual Studio 中，右键单击的设计图面**CbrKnownType**路线，，然后单击**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="32da6-227">In Visual Studio, right-click the design surface of the **CbrKnownType** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="32da6-228">在 Visual Studio 中打开的 XML 版本的路线。</span><span class="sxs-lookup"><span data-stu-id="32da6-228">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="32da6-229">保存所有项目。</span><span class="sxs-lookup"><span data-stu-id="32da6-229">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="32da6-230">在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries，并注意你路线 XML (CbrKnownType.xml) 创建。</span><span class="sxs-lookup"><span data-stu-id="32da6-230">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (CbrKnownType.xml).</span></span>  
  
#### <a name="to-test-the-itinerary-and-business-rules"></a><span data-ttu-id="32da6-231">若要测试的路线和业务规则</span><span class="sxs-lookup"><span data-stu-id="32da6-231">To test the itinerary and business rules</span></span>  
  
1.  <span data-ttu-id="32da6-232">打开路线测试客户端示例应用程序使用期间创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。</span><span class="sxs-lookup"><span data-stu-id="32da6-232">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="32da6-233">在路线测试客户端中，清除**使用 WCF 服务**复选框，并依次**负载路线**。</span><span class="sxs-lookup"><span data-stu-id="32da6-233">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="32da6-234">在**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。</span><span class="sxs-lookup"><span data-stu-id="32da6-234">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="32da6-235">选择**CbrKnownType.xml**，然后单击**打开**加载路线。</span><span class="sxs-lookup"><span data-stu-id="32da6-235">Select **CbrKnownType.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="32da6-236">单击**确定**清除**成功加载路线**消息。</span><span class="sxs-lookup"><span data-stu-id="32da6-236">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
5.  <span data-ttu-id="32da6-237">在路线测试客户端上，单击旁边的省略号按钮 （...）**负载消息**框。</span><span class="sxs-lookup"><span data-stu-id="32da6-237">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="32da6-238">在**选择要加载 XML 文档**对话框中，浏览到 C:\HowTos。</span><span class="sxs-lookup"><span data-stu-id="32da6-238">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="32da6-239">选择**West.xml**，然后单击**打开**加载测试消息。</span><span class="sxs-lookup"><span data-stu-id="32da6-239">Select **West.xml**, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="32da6-240">单击**提交请求**按钮。</span><span class="sxs-lookup"><span data-stu-id="32da6-240">Click the **Submit Request** button.</span></span> <span data-ttu-id="32da6-241">在测试完成后，单击**确定**关闭出现的确认。</span><span class="sxs-lookup"><span data-stu-id="32da6-241">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="32da6-242">在 Windows 资源管理器，浏览到 C:\HowTos\Out。验证 West%MessageID%.xml 消息已写入到目录。</span><span class="sxs-lookup"><span data-stu-id="32da6-242">In Windows Explorer, browse to C:\HowTos\Out. Verify that the West%MessageID%.xml message has been written to the directory.</span></span>  
  
9. <span data-ttu-id="32da6-243">重复使用 East.xml 消息在测试过程。</span><span class="sxs-lookup"><span data-stu-id="32da6-243">Repeat the test process using the East.xml message.</span></span>  
  
10. <span data-ttu-id="32da6-244">在 Windows 资源管理器，浏览到 C:\HowTos\Out。验证 East%MessageID%.xml 消息已写入到目录。</span><span class="sxs-lookup"><span data-stu-id="32da6-244">In Windows Explorer, browse to C:\HowTos\Out. Verify that the East%MessageID%.xml message has been written to the directory.</span></span>  
  
11. <span data-ttu-id="32da6-245">重复使用 NAOrderDoc.xml 消息在测试过程。</span><span class="sxs-lookup"><span data-stu-id="32da6-245">Repeat the test process using the NAOrderDoc.xml message.</span></span>  
  
12. <span data-ttu-id="32da6-246">在 Windows 资源管理器，浏览到 C:\HowTos\Out。验证 CustomerUnknown%MessageID%.xml 消息已写入到目录。</span><span class="sxs-lookup"><span data-stu-id="32da6-246">In Windows Explorer, browse to C:\HowTos\Out. Verify that the CustomerUnknown%MessageID%.xml message has been written to the directory.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="32da6-247">其他资源</span><span class="sxs-lookup"><span data-stu-id="32da6-247">Additional Resources</span></span>  
 <span data-ttu-id="32da6-248">有关详细信息，请参阅下列相关主题：</span><span class="sxs-lookup"><span data-stu-id="32da6-248">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="32da6-249">如何：使用业务规则策略选择路线</span><span class="sxs-lookup"><span data-stu-id="32da6-249">How to: Select an Itinerary Using a Business Rules Policy</span></span>](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [<span data-ttu-id="32da6-250">如何：使用业务规则策略动态路由基于消息上下文的消息</span><span class="sxs-lookup"><span data-stu-id="32da6-250">How to: Dynamically Route a Message Based on Message Context Using a Business Rules Policy</span></span>](../esb-toolkit/dynamically-route-messages-based-on-message-context-using-business-rules-policy.md)  
  
-   [<span data-ttu-id="32da6-251">开发活动</span><span class="sxs-lookup"><span data-stu-id="32da6-251">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="32da6-252">消息路由模式</span><span class="sxs-lookup"><span data-stu-id="32da6-252">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)