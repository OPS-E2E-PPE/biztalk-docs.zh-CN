---
title: "如何： 验证使用 ESB 入口的消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 43dfc791-7cb6-45a4-898f-f53def199c08
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63a6a79a12949148f77363d7e4cffd2b2c321d00
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-validate-a-message-using-an-esb-on-ramp"></a><span data-ttu-id="492cf-102">如何： 验证使用 ESB 入口的消息</span><span class="sxs-lookup"><span data-stu-id="492cf-102">How to: Validate a Message Using an ESB On-Ramp</span></span>
## <a name="goal"></a><span data-ttu-id="492cf-103">目的</span><span class="sxs-lookup"><span data-stu-id="492cf-103">Goal</span></span>  
 <span data-ttu-id="492cf-104">本部分演示如何配置 ESB 调度程序反汇编管道组件来执行消息验证的 XML 消息提交到 ESB 入口。</span><span class="sxs-lookup"><span data-stu-id="492cf-104">This section demonstrates how to configure the ESB Dispatcher Disassemble pipeline component to perform message validation for XML messages submitted to an ESB on-ramp.</span></span>  
  
 <span data-ttu-id="492cf-105">在本操作方法主题中，你将完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="492cf-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="492cf-106">创建 ESB 入口使用**ItinerarySelectReceiveXml**管道。</span><span class="sxs-lookup"><span data-stu-id="492cf-106">Create an ESB on-ramp that uses the **ItinerarySelectReceiveXml** pipeline.</span></span>  
  
-   <span data-ttu-id="492cf-107">配置 ESB 调度程序反汇编管道组件，以验证消息的内容。</span><span class="sxs-lookup"><span data-stu-id="492cf-107">Configure the ESB Dispatcher Disassemble pipeline component to validate message content.</span></span>  
  
-   <span data-ttu-id="492cf-108">配置路线选择器管道组件，若要解决适当的路线。</span><span class="sxs-lookup"><span data-stu-id="492cf-108">Configure the Itinerary Selector pipeline component to resolve the appropriate itinerary.</span></span>  
  
-   <span data-ttu-id="492cf-109">测试使用有效的消息和一个无效的消息的消息验证。</span><span class="sxs-lookup"><span data-stu-id="492cf-109">Test message validation using a valid message and an invalid message.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="492cf-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="492cf-110">Prerequisites</span></span>  
 <span data-ttu-id="492cf-111">此操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="492cf-111">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="492cf-112">开始之前</span><span class="sxs-lookup"><span data-stu-id="492cf-112">Before You Begin</span></span>  
 <span data-ttu-id="492cf-113">本操作方法主题中的更高版本执行的步骤之前，请完成以下任务：</span><span class="sxs-lookup"><span data-stu-id="492cf-113">Complete the following tasks before you perform the steps later in this How-to topic:</span></span>  
  
-   <span data-ttu-id="492cf-114">创建一个无效的测试消息。</span><span class="sxs-lookup"><span data-stu-id="492cf-114">Create an invalid test message.</span></span>  
  
-   <span data-ttu-id="492cf-115">创建一个 ESB 路线域特定语言 (DSL) 模型。</span><span class="sxs-lookup"><span data-stu-id="492cf-115">Create an ESB itinerary domain-specific language (DSL) model.</span></span>  
  
-   <span data-ttu-id="492cf-116">配置路线的属性。</span><span class="sxs-lookup"><span data-stu-id="492cf-116">Configure the properties of the itinerary.</span></span>  
  
-   <span data-ttu-id="492cf-117">定义路线的结构。</span><span class="sxs-lookup"><span data-stu-id="492cf-117">Define the structure of the itinerary.</span></span>  
  
-   <span data-ttu-id="492cf-118">导出到路线数据库模型。</span><span class="sxs-lookup"><span data-stu-id="492cf-118">Export the model to the Itinerary database.</span></span>  
  
 <span data-ttu-id="492cf-119">下面的过程介绍如何执行其中每个操作。</span><span class="sxs-lookup"><span data-stu-id="492cf-119">The following procedures describe how to do each of these.</span></span>  
  
#### <a name="to-create-an-invalid-test-message"></a><span data-ttu-id="492cf-120">若要创建一个无效的测试消息</span><span class="sxs-lookup"><span data-stu-id="492cf-120">To create an invalid test message</span></span>  
  
1.  <span data-ttu-id="492cf-121">在 Windows 资源管理器，浏览到 C:\HowTos。</span><span class="sxs-lookup"><span data-stu-id="492cf-121">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="492cf-122">创建一份 NAOrderDoc.xml，，然后重命名副本 Invalid.xml。</span><span class="sxs-lookup"><span data-stu-id="492cf-122">Create a copy of NAOrderDoc.xml, and then rename the copy Invalid.xml.</span></span>  
  
3.  <span data-ttu-id="492cf-123">在记事本中，打开 Invalid.xml。</span><span class="sxs-lookup"><span data-stu-id="492cf-123">In Notepad, open Invalid.xml.</span></span>  
  
4.  <span data-ttu-id="492cf-124">更改 **\<ns0:requestType > 10\</ns0:requestType > 到\<ns0:requestType > 10 个\</ns0:requestType >**。</span><span class="sxs-lookup"><span data-stu-id="492cf-124">Change **\<ns0:requestType>10\</ns0:requestType> to \<ns0:requestType>TEN\</ns0:requestType>**.</span></span>  
  
5.  <span data-ttu-id="492cf-125">将 Invalid.xml 另存为 utf-8，，然后关闭记事本。</span><span class="sxs-lookup"><span data-stu-id="492cf-125">Save Invalid.xml as UTF-8, and then close Notepad.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="492cf-126">通过将此元素的数字值更改为文本，消息不再将根据架构有效。</span><span class="sxs-lookup"><span data-stu-id="492cf-126">By changing the numerical value of this element to text, the message will no longer be valid according to the schema.</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="492cf-127">若要创建 ESB 路线 DSL 模型</span><span class="sxs-lookup"><span data-stu-id="492cf-127">To create an ESB itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="492cf-128">在[!INCLUDE[vs2010](../includes/vs2010-md.md)]，打开 C:\HowTos\Patterns\Patterns.sln。</span><span class="sxs-lookup"><span data-stu-id="492cf-128">In [!INCLUDE[vs2010](../includes/vs2010-md.md)], open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="492cf-129">在解决方案资源管理器，右键单击**ItineraryLibrary**，指向**添加**，然后单击**新路线**。</span><span class="sxs-lookup"><span data-stu-id="492cf-129">In Solution Explorer, right-click **ItineraryLibrary**, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="492cf-130">在**添加新项**对话框中，键入**验证**中**名称**框中，并依次**添加**。</span><span class="sxs-lookup"><span data-stu-id="492cf-130">In the **Add New Item** dialog box, type **Validation** in the **Name** box, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="492cf-131">若要配置路线的属性</span><span class="sxs-lookup"><span data-stu-id="492cf-131">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="492cf-132">在 Visual Studio 中，单击的设计图面**Validation.itinerary**。</span><span class="sxs-lookup"><span data-stu-id="492cf-132">In Visual Studio, click the design surface of **Validation.itinerary**.</span></span> <span data-ttu-id="492cf-133">在**验证**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="492cf-133">In the **Validation** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="492cf-134">在**模型导出程序**下拉列表中，单击**数据库路线导出程序**。</span><span class="sxs-lookup"><span data-stu-id="492cf-134">In the **Model Exporter** drop-down list, click **Database Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="492cf-135">单击旁边的省略号按钮 （...）**路线数据库**属性。</span><span class="sxs-lookup"><span data-stu-id="492cf-135">Click the ellipsis button (...) next to the **Itinerary Database** property.</span></span>  
  
    3.  <span data-ttu-id="492cf-136">在**连接属性**对话框中，选择承载路线存储库数据库中，SQL Server，然后指定数据库的名称 (默认名称是**EsbItineraryDb**)。</span><span class="sxs-lookup"><span data-stu-id="492cf-136">In the **Connection Properties** dialog box, choose the SQL Server that hosts the itinerary repository database, and then specify the name of the database (the default name is **EsbItineraryDb**).</span></span>  
  
2.  <span data-ttu-id="492cf-137">在**路线状态**下拉列表中，单击**已部署**。</span><span class="sxs-lookup"><span data-stu-id="492cf-137">In the **Itinerary Status** drop-down list, click **Deployed**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="492cf-138">此步骤允许您将导出到一个中心存储库; 路线可以选择并收到消息时，从该存储库附加路线。</span><span class="sxs-lookup"><span data-stu-id="492cf-138">This step enables you to export the itinerary to a central repository; itineraries can be selected and attached from this repository when the message is received.</span></span> <span data-ttu-id="492cf-139">更高版本，你将配置路线选择器管道组件配置为使用静态冲突解决程序从此存储库中选择相应的路线。</span><span class="sxs-lookup"><span data-stu-id="492cf-139">You will later configure the Itinerary Selector pipeline component to use a static resolver to select the appropriate itinerary from this repository.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="492cf-140">若要定义路线的结构</span><span class="sxs-lookup"><span data-stu-id="492cf-140">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="492cf-141">从工具箱中，拖动**上负载增加**到设计图面上的模型元素。</span><span class="sxs-lookup"><span data-stu-id="492cf-141">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="492cf-142">在**OnRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="492cf-142">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="492cf-143">单击**名称**属性，再然后键入**ReceiveNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="492cf-143">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="492cf-144">在**扩展程序**下拉列表中，单击**上负载增加 ESB 扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="492cf-144">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="492cf-145">在**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="492cf-145">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="492cf-146">在**接收端口**下拉列表中，单击**OnRamp.Itinerary**。</span><span class="sxs-lookup"><span data-stu-id="492cf-146">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="492cf-147">从工具箱中，拖动**关闭负载增加**模型元素到设计图面，然后将其放到现有的模型元素的右侧。</span><span class="sxs-lookup"><span data-stu-id="492cf-147">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the existing model element.</span></span> <span data-ttu-id="492cf-148">在**OffRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="492cf-148">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="492cf-149">单击**名称**属性，再然后键入**SendNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="492cf-149">Click the **Name** property, and then type **SendNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="492cf-150">在**扩展程序**下拉列表中，单击**关闭负载增加 ESB 扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="492cf-150">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="492cf-151">在**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。</span><span class="sxs-lookup"><span data-stu-id="492cf-151">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="492cf-152">在**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。</span><span class="sxs-lookup"><span data-stu-id="492cf-152">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
3.  <span data-ttu-id="492cf-153">从工具箱中，拖动**路线服务**模型元素到设计图面，然后将它之间**ReceiveNAOrder**模型元素和**SendNAOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="492cf-153">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **ReceiveNAOrder** model element and the **SendNAOrder** model element.</span></span> <span data-ttu-id="492cf-154">在**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="492cf-154">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="492cf-155">单击**名称**属性，再然后键入**SendPortFilter**。</span><span class="sxs-lookup"><span data-stu-id="492cf-155">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="492cf-156">在**路线服务扩展程序**下拉列表中，单击**关闭负载增加扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="492cf-156">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="492cf-157">在**关闭负载增加**下拉列表中，展开**SendNAOrder**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="492cf-157">In the **Off-Ramp** drop-down list, expand **SendNAOrder**, and then click **Send Handlers**.</span></span>  
  
4.  <span data-ttu-id="492cf-158">右键单击**冲突解决程序**集合**SendPortFilter**元素，，然后单击**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="492cf-158">Right-click the **Resolver** collection of the **SendPortFilter** element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="492cf-159">在**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="492cf-159">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="492cf-160">单击**名称**属性，再然后键入**ConfigureOffRamp**。</span><span class="sxs-lookup"><span data-stu-id="492cf-160">Click the **Name** property, and then type **ConfigureOffRamp**.</span></span>  
  
    2.  <span data-ttu-id="492cf-161">在**解析程序实现**下拉列表中，单击**静态冲突解决程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="492cf-161">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="492cf-162">在**传输名称**下拉列表中，单击**文件**。</span><span class="sxs-lookup"><span data-stu-id="492cf-162">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="492cf-163">单击**传输位置**属性，再然后键入**C:\HowTos\Out\Validated%MessageID%.xml**。</span><span class="sxs-lookup"><span data-stu-id="492cf-163">Click the **Transport Location** property, and then type **C:\HowTos\Out\Validated%MessageID%.xml**.</span></span>  
  
5.  <span data-ttu-id="492cf-164">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="492cf-164">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="492cf-165">将从连接**ReceiveNAOrder**到模型元素**SendPortFilter**模型元素。</span><span class="sxs-lookup"><span data-stu-id="492cf-165">Drag a connection from the **ReceiveNAOrder** model element to the **SendPortFilter** model element.</span></span>  
  
6.  <span data-ttu-id="492cf-166">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="492cf-166">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="492cf-167">将从连接**SendPortFilter**到模型元素**SendNAOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="492cf-167">Drag a connection from the **SendPortFilter** model element to the **SendNAOrder** model element.</span></span>  
  
#### <a name="to-export-the-model-to-the-itinerary-database"></a><span data-ttu-id="492cf-168">将导出到路线的数据库的模型</span><span class="sxs-lookup"><span data-stu-id="492cf-168">To export the model to the itinerary database</span></span>  
  
1.  <span data-ttu-id="492cf-169">在 Visual Studio 中，右键单击的设计图面**验证**路线，，然后单击**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="492cf-169">In Visual Studio, right-click the design surface of the **Validation** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="492cf-170">路线已导出到路线的数据库，现在可以使用通过路线选择器管道组件。</span><span class="sxs-lookup"><span data-stu-id="492cf-170">The itinerary has been exported to the itinerary database and can now be used by the Itinerary Selector pipeline component.</span></span>  
  
2.  <span data-ttu-id="492cf-171">保存所有项目。</span><span class="sxs-lookup"><span data-stu-id="492cf-171">Save all project artifacts.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="492cf-172">步骤</span><span class="sxs-lookup"><span data-stu-id="492cf-172">Steps</span></span>  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a><span data-ttu-id="492cf-173">若要创建和配置 ESB 入口</span><span class="sxs-lookup"><span data-stu-id="492cf-173">To create and configure an ESB on-ramp</span></span>  
  
1.  <span data-ttu-id="492cf-174">单击**启动**在任务栏中，指向**所有程序**，指向 **[!INCLUDE[prague](../includes/prague-md.md)]** ，然后单击**BizTalk Server 管理**.</span><span class="sxs-lookup"><span data-stu-id="492cf-174">Click **Start** on the taskbar, point to **All Programs**, point to **[!INCLUDE[prague](../includes/prague-md.md)]**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="492cf-175">在[!INCLUDE[prague](../includes/prague-md.md)]管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后展开**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="492cf-175">In the [!INCLUDE[prague](../includes/prague-md.md)] Administration Console, expand **BizTalk Group**, expand **Applications**, and then expand **Microsoft.Practices.ESB**.</span></span>  
  
3.  <span data-ttu-id="492cf-176">右键单击**接收位置**，指向**新建**，然后单击**单向接收位置**。</span><span class="sxs-lookup"><span data-stu-id="492cf-176">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
4.  <span data-ttu-id="492cf-177">在**选择接收端口**对话框中，单击**OnRamp.Itinerary**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="492cf-177">In the **Select a Receive Port** dialog box, click **OnRamp.Itinerary**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="492cf-178">在**接收位置属性**对话框中，键入**OnRamp.Itinerary.HowTo**中**名称**框。</span><span class="sxs-lookup"><span data-stu-id="492cf-178">In the **Receive Location Properties** dialog box, type **OnRamp.Itinerary.HowTo** in the **Name** box.</span></span>  
  
6.  <span data-ttu-id="492cf-179">在**类型**下拉列表中，单击**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="492cf-179">In the **Type** drop-down list, click **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="492cf-180">在**文件传输属性**对话框中，键入**C:\HowTos\DropFolder**中**接收文件夹**框中，并依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="492cf-180">In the **FILE Transport Properties** dialog box, type **C:\HowTos\DropFolder** in the **Receive folder** box, and then click **OK**.</span></span>  
  
#### <a name="to-configure-the-on-ramp-to-perform-message-validation"></a><span data-ttu-id="492cf-181">若要配置上的负载增加执行消息验证</span><span class="sxs-lookup"><span data-stu-id="492cf-181">To configure the on-ramp to perform message validation</span></span>  
  
1.  <span data-ttu-id="492cf-182">在**接收位置属性**对话框中，在**接收管道**下拉列表中，单击**ItinerarySelectReceiveXml**，然后单击省略号按钮 （...).</span><span class="sxs-lookup"><span data-stu-id="492cf-182">In the **Receive Location Properties** dialog box, in the **Receive pipeline** drop-down list, click **ItinerarySelectReceiveXml**, and then click the ellipsis button (...).</span></span>  
  
2.  <span data-ttu-id="492cf-183">使用**配置管道**对话框中，配置以下各项**XML 反汇编程序**组件属性：</span><span class="sxs-lookup"><span data-stu-id="492cf-183">Use the **Configure Pipeline** dialog box to configure the following **XML disassembler** component properties:</span></span>  
  
    1.  <span data-ttu-id="492cf-184">展开 GlobalBank.Esb 应用程序，，然后单击**架构**。</span><span class="sxs-lookup"><span data-stu-id="492cf-184">Expand the GlobalBank.Esb application, and then click **Schemas**.</span></span> <span data-ttu-id="492cf-185">右键单击**GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="492cf-185">Right-click **GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**, and then click **Properties**.</span></span> <span data-ttu-id="492cf-186">复制**名称**和**程序集**属性并将其粘贴到文本文件。</span><span class="sxs-lookup"><span data-stu-id="492cf-186">Copy the **Name** and **Assembly** properties and paste them into a text file.</span></span>  
  
    2.  <span data-ttu-id="492cf-187">在**拆卸**组件，请单击**True**中**ValidateDocument**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="492cf-187">In the **Disassemble** component, click **True** in the **ValidateDocument** drop-down list.</span></span>  
  
    3.  <span data-ttu-id="492cf-188">单击**DocumentSpecNames**属性，再然后键入完全限定名称的架构。</span><span class="sxs-lookup"><span data-stu-id="492cf-188">Click the **DocumentSpecNames** property, and then type the fully qualified name of the schema.</span></span> <span data-ttu-id="492cf-189">完全限定的名名称开头后, 跟一个逗号和在步骤中提取的程序集信息。</span><span class="sxs-lookup"><span data-stu-id="492cf-189">The fully qualified name starts with the name and is followed by a comma and the assembly information extracted in step a.</span></span> <span data-ttu-id="492cf-190">以下是一个示例：</span><span class="sxs-lookup"><span data-stu-id="492cf-190">The following is an example:</span></span>  
  
         <span data-ttu-id="492cf-191">GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc，GlobalBank.ESB.DynamicResolution.Schemas，版本 = 2.0.0.0，区域性 = neutral，PublicKeyToken = c2c8b2b87f54180a</span><span class="sxs-lookup"><span data-stu-id="492cf-191">GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc, GlobalBank.ESB.DynamicResolution.Schemas, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c2c8b2b87f54180a</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="492cf-192">这是架构的要进行验证，则的完全限定的名称它包含的架构名称和四个程序集属性： 程序集名称、 版本、 区域性和公钥标记。</span><span class="sxs-lookup"><span data-stu-id="492cf-192">This is the fully qualified name of the schema to be validated; it is comprised of the schema name and four assembly properties: assembly name, version, culture, and public key token.</span></span> <span data-ttu-id="492cf-193">允许多个值;用管道 (&#124;) 分隔多个架构符号。</span><span class="sxs-lookup"><span data-stu-id="492cf-193">Multiple values are allowed; separate multiple schemas with a pipe (&#124;) symbol.</span></span>  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a><span data-ttu-id="492cf-194">若要配置路线选择器管道组件</span><span class="sxs-lookup"><span data-stu-id="492cf-194">To configure the Itinerary Selector Pipeline component</span></span>  
  
1.  <span data-ttu-id="492cf-195">在**配置管道**对话框框中，配置以下各项**路线选择器**组件属性：</span><span class="sxs-lookup"><span data-stu-id="492cf-195">In the **Configure Pipeline** dialog box, configure the following **Itinerary Selector** component properties:</span></span>  
  
    1.  <span data-ttu-id="492cf-196">单击**ItineraryFactKey**属性，再然后键入**Resolver.Itinerary**。</span><span class="sxs-lookup"><span data-stu-id="492cf-196">Click the **ItineraryFactKey** property, and then type **Resolver.Itinerary**.</span></span>  
  
    2.  <span data-ttu-id="492cf-197">单击**ResolverConnectionString**属性，再然后键入**路线：\\\name=Validation;**。</span><span class="sxs-lookup"><span data-stu-id="492cf-197">Click the **ResolverConnectionString** property, and then type **ITINERARY:\\\name=Validation;**.</span></span>  
  
    3.  <span data-ttu-id="492cf-198">单击**确定**关闭**配置管道**对话框。</span><span class="sxs-lookup"><span data-stu-id="492cf-198">Click **OK** to close the **Configure Pipeline** dialog box.</span></span>  
  
2.  <span data-ttu-id="492cf-199">单击**确定**关闭**接收位置属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="492cf-199">Click **OK** to close the **Receive Location Properties** dialog box.</span></span>  
  
3.  <span data-ttu-id="492cf-200">在[!INCLUDE[prague](../includes/prague-md.md)]管理控制台中，右键单击**OnRamp.Itinerary.HowTo**接收位置，并依次**启用**。</span><span class="sxs-lookup"><span data-stu-id="492cf-200">In the [!INCLUDE[prague](../includes/prague-md.md)] Administration Console, right-click the **OnRamp.Itinerary.HowTo** receive location, and then click **Enable**.</span></span>  
  
#### <a name="to-test-the-message-validation-and-itinerary-selection"></a><span data-ttu-id="492cf-201">若要测试的消息验证和路线选择</span><span class="sxs-lookup"><span data-stu-id="492cf-201">To test the message validation and itinerary selection</span></span>  
  
1.  <span data-ttu-id="492cf-202">在 Windows 资源管理器，浏览到 C:\HowTos。</span><span class="sxs-lookup"><span data-stu-id="492cf-202">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="492cf-203">复制 （不移动） 到 DropFolder 文件夹 NAOrderDoc.xml。</span><span class="sxs-lookup"><span data-stu-id="492cf-203">Copy (do not move) NAOrderDoc.xml to the DropFolder folder.</span></span>  
  
3.  <span data-ttu-id="492cf-204">浏览到 C:\HowTos\Out。验证 Validated%MessageID%.xml 已写入到目录。</span><span class="sxs-lookup"><span data-stu-id="492cf-204">Browse to C:\HowTos\Out. Verify that Validated%MessageID%.xml has been written to the directory.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="492cf-205">有效的消息完成其路线基于的路由，按预期方式。</span><span class="sxs-lookup"><span data-stu-id="492cf-205">The valid message completed its itinerary-based routing, as expected.</span></span>  
  
4.  <span data-ttu-id="492cf-206">删除扩展文件夹 Validated%MessageID%.xml。</span><span class="sxs-lookup"><span data-stu-id="492cf-206">Delete Validated%MessageID%.xml from the Out folder.</span></span>  
  
5.  <span data-ttu-id="492cf-207">在 Windows 资源管理器，浏览到 C:\HowTos。</span><span class="sxs-lookup"><span data-stu-id="492cf-207">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
6.  <span data-ttu-id="492cf-208">复制 （不移动） 到 DropFolder 文件夹 Invalid.xml。</span><span class="sxs-lookup"><span data-stu-id="492cf-208">Copy (do not move) Invalid.xml to the DropFolder folder.</span></span>  
  
7.  <span data-ttu-id="492cf-209">浏览到 C:\HowTos\Out。验证已传递任何新的消息。</span><span class="sxs-lookup"><span data-stu-id="492cf-209">Browse to C:\HowTos\Out. Verify that no new message has been delivered.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="492cf-210">无法验证消息;因此，基于路线的路由无法完成。</span><span class="sxs-lookup"><span data-stu-id="492cf-210">The message could not be validated; therefore, itinerary-based routing could not be completed.</span></span>  
  
8.  <span data-ttu-id="492cf-211">单击**启动**在任务栏中，指向**管理工具**，然后单击**事件查看器**。</span><span class="sxs-lookup"><span data-stu-id="492cf-211">Click **Start** on the taskbar, point to **Administrative Tools**, and then click **Event Viewer**.</span></span>  
  
9. <span data-ttu-id="492cf-212">在事件查看器中，展开**Windows 日志**，然后单击**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="492cf-212">In Event Viewer, expand **Windows Logs**, and then click **Application**.</span></span>  
  
10. <span data-ttu-id="492cf-213">找到的最新事件其中**源**是 **[!INCLUDE[prague](../includes/prague-md.md)]** ，和**事件 ID**是**5719**。</span><span class="sxs-lookup"><span data-stu-id="492cf-213">Locate a recent event where the **Source** is **[!INCLUDE[prague](../includes/prague-md.md)]**, and the **Event ID** is **5719**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="492cf-214">提交和失败的无效消息应用程序事件日志导致的异常条目。</span><span class="sxs-lookup"><span data-stu-id="492cf-214">The submission and failure of the invalid message resulted in an exception entry to the application event log.</span></span>  
  
11. <span data-ttu-id="492cf-215">在[!INCLUDE[prague](../includes/prague-md.md)]管理控制台中，右键单击**OnRamp.Itinerary.HowTo**接收位置，并依次**禁用**。</span><span class="sxs-lookup"><span data-stu-id="492cf-215">In the [!INCLUDE[prague](../includes/prague-md.md)] Administration Console, right-click the **OnRamp.Itinerary.HowTo** receive location, and then click **Disable**.</span></span>  
  
12. <span data-ttu-id="492cf-216">后**OnRamp.Itinerary.HowTo**接收位置处于禁用状态，右键单击它，，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="492cf-216">After the **OnRamp.Itinerary.HowTo** receive location is disabled, right-click it, and then click **Delete**.</span></span> <span data-ttu-id="492cf-217">在**确认删除接收位置**对话框中，单击**是**。</span><span class="sxs-lookup"><span data-stu-id="492cf-217">In the **Confirm delete receive location** dialog box, click **Yes**.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="492cf-218">其他资源</span><span class="sxs-lookup"><span data-stu-id="492cf-218">Additional Resources</span></span>  
 <span data-ttu-id="492cf-219">有关详细信息，请参阅下列相关主题：</span><span class="sxs-lookup"><span data-stu-id="492cf-219">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="492cf-220">如何： 选择使用业务规则策略路线</span><span class="sxs-lookup"><span data-stu-id="492cf-220">How to: Select an Itinerary Using a Business Rules Policy</span></span>](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [<span data-ttu-id="492cf-221">开发活动</span><span class="sxs-lookup"><span data-stu-id="492cf-221">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="492cf-222">安装和运行动态解析示例</span><span class="sxs-lookup"><span data-stu-id="492cf-222">Installing and Running the Dynamic Resolution Sample</span></span>](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)