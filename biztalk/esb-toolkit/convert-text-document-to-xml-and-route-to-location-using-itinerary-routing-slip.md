---
title: 如何： 将文本文档转换为 XML 和路由到文件位置使用路线的路由滑动 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01597a5f-5ca3-440e-ad97-70332233f319
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8284c1623329133533fe03aab567b1281f07c1a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010190"
---
# <a name="how-to-convert-a-text-document-to-xml-and-route-to-a-file-location-using-an-itinerary-routing-slip"></a><span data-ttu-id="ab9df-102">如何： 将文本文档转换为 XML 和路由到使用路线的路由滑动的文件位置</span><span class="sxs-lookup"><span data-stu-id="ab9df-102">How to: Convert a Text Document to XML and Route to a File Location Using an Itinerary Routing Slip</span></span>
## <a name="goal"></a><span data-ttu-id="ab9df-103">目的</span><span class="sxs-lookup"><span data-stu-id="ab9df-103">Goal</span></span>  
 <span data-ttu-id="ab9df-104">部分演示如何创建将将文本文档转换为 XML，选择适当的路线，然后将消息路由到某个文件位置的管道。</span><span class="sxs-lookup"><span data-stu-id="ab9df-104">The section demonstrates how to create a pipeline that will convert a text document to XML and then select the appropriate itinerary and route the message to a FILE location.</span></span>  
  
 <span data-ttu-id="ab9df-105">在本操作方法主题中，你将完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="ab9df-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="ab9df-106">使用管道接收平面文件文档并将其转换为 XML。</span><span class="sxs-lookup"><span data-stu-id="ab9df-106">Use a pipeline to receive a flat file document and convert it to XML.</span></span>  
  
-   <span data-ttu-id="ab9df-107">配置要解决适当的路由滑动的路线选择器管道组件。</span><span class="sxs-lookup"><span data-stu-id="ab9df-107">Configure the Itinerary Selector pipeline component to resolve the appropriate routing slip.</span></span>  
  
-   <span data-ttu-id="ab9df-108">创建入口使用自定义的管道。</span><span class="sxs-lookup"><span data-stu-id="ab9df-108">Create an on-ramp that uses the custom pipeline.</span></span>  
  
-   <span data-ttu-id="ab9df-109">测试路线基于路由的平面文件消息。</span><span class="sxs-lookup"><span data-stu-id="ab9df-109">Test itinerary-based routing of a flat file message.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ab9df-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="ab9df-110">Prerequisites</span></span>  
 <span data-ttu-id="ab9df-111">此操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="ab9df-111">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="ab9df-112">开始之前</span><span class="sxs-lookup"><span data-stu-id="ab9df-112">Before You Begin</span></span>  
 <span data-ttu-id="ab9df-113">本操作方法主题中的更高版本执行的步骤之前，请完成以下任务：</span><span class="sxs-lookup"><span data-stu-id="ab9df-113">Complete the following tasks before you perform the steps later in this How-to topic:</span></span>  
  
-   <span data-ttu-id="ab9df-114">部署**DataFormatTransformation**路线。</span><span class="sxs-lookup"><span data-stu-id="ab9df-114">Deploy the **DataFormatTransformation** itinerary.</span></span>  
  
-   <span data-ttu-id="ab9df-115">创建测试消息。</span><span class="sxs-lookup"><span data-stu-id="ab9df-115">Create the test message.</span></span>  
  
 <span data-ttu-id="ab9df-116">下面的过程介绍如何执行其中每个操作。</span><span class="sxs-lookup"><span data-stu-id="ab9df-116">The following procedures describe how to do each of these.</span></span>  
  
#### <a name="to-deploy-the-dataformattransformation-itinerary"></a><span data-ttu-id="ab9df-117">若要部署 DataFormatTransformation 路线</span><span class="sxs-lookup"><span data-stu-id="ab9df-117">To deploy the DataFormatTransformation itinerary</span></span>  
  
1.  <span data-ttu-id="ab9df-118">在 Visual Studio 中，打开 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation\DataFormatTransformation.sln。</span><span class="sxs-lookup"><span data-stu-id="ab9df-118">In Visual Studio, open C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation\DataFormatTransformation.sln.</span></span>  
  
2.  <span data-ttu-id="ab9df-119">在解决方案资源管理器，在**Itinerary.Library**项目中，双击**DataFormatTransformation.itinerary**在路线设计器中打开它。</span><span class="sxs-lookup"><span data-stu-id="ab9df-119">In Solution Explorer, in the **Itinerary.Library** project, double-click **DataFormatTransformation.itinerary** to open it in the Itinerary Designer.</span></span>  
  
3.  <span data-ttu-id="ab9df-120">在 Visual Studio 中，单击的设计图面**DataFormatTransformation.itinerary**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-120">In Visual Studio, click the design surface of **DataFormatTransformation.itinerary**.</span></span> <span data-ttu-id="ab9df-121">在**DataFormatTransformation.itinerary**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="ab9df-121">In the **DataFormatTransformation.itinerary** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="ab9df-122">在**路线状态**下拉列表中，单击**已部署**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-122">In the **Itinerary Status** drop-down list, click **Deployed**.</span></span>  
  
    2.  <span data-ttu-id="ab9df-123">在**模型导出程序**下拉列表中，单击**数据库路线导出程序**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-123">In the **Model Exporter** drop-down list, click **Database Itinerary Exporter**.</span></span>  
  
    3.  <span data-ttu-id="ab9df-124">单击旁边的省略号按钮 （...）**路线数据库**属性。</span><span class="sxs-lookup"><span data-stu-id="ab9df-124">Click the ellipsis button (...) next to the **Itinerary Database** property.</span></span>  
  
    4.  <span data-ttu-id="ab9df-125">在**连接属性**对话框中，选择承载路线存储库数据库中，SQL Server，然后指定数据库的名称 (默认名称是**EsbItineraryDb**)。</span><span class="sxs-lookup"><span data-stu-id="ab9df-125">In the **Connection Properties** dialog box, choose the SQL Server that hosts the itinerary repository database, and then specify the name of the database (the default name is **EsbItineraryDb**).</span></span>  
  
4.  <span data-ttu-id="ab9df-126">保存所有项目。</span><span class="sxs-lookup"><span data-stu-id="ab9df-126">Save all project artifacts.</span></span>  
  
5.  <span data-ttu-id="ab9df-127">在 Visual Studio 中，右键单击的设计图面**DataModelTransformation**路线，，然后单击**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-127">In Visual Studio, right-click the design surface of the **DataModelTransformation** itinerary, and then click **Export Model**.</span></span>  
  
#### <a name="to-create-the-receive-pipeline"></a><span data-ttu-id="ab9df-128">若要创建接收管道</span><span class="sxs-lookup"><span data-stu-id="ab9df-128">To create the receive pipeline</span></span>  
  
1.  <span data-ttu-id="ab9df-129">在 Visual Studio 中，右键单击**DataFormatTransformation.Schemas**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-129">In Visual Studio, right-click **DataFormatTransformation.Schemas**, and then click **Properties**.</span></span> <span data-ttu-id="ab9df-130">单击**应用程序**，然后键入**GlobalBank.ESB.DataFormatTransformation.Schemas**中**程序集名称**框。</span><span class="sxs-lookup"><span data-stu-id="ab9df-130">Click **Application**, and then type **GlobalBank.ESB.DataFormatTransformation.Schemas** in the **Assembly name** box.</span></span>  
  
2.  <span data-ttu-id="ab9df-131">右键单击**DataFormatTransformation.Schemas**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-131">Right-click **DataFormatTransformation.Schemas**, and then click **Properties**.</span></span> <span data-ttu-id="ab9df-132">单击**签名**，然后确认**对程序集签名**复选框处于选中状态，该程序集位置指向 **。\\...\\..\\..\\..\\..\keys\Microsoft.Practices.ESB.snk**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-132">Click **Signing**, and then verify that the **Sign the assembly** check box is selected and that the assembly location points to **.\\..\\..\\..\\..\\..\keys\Microsoft.Practices.ESB.snk**.</span></span>  
  
3.  <span data-ttu-id="ab9df-133">右键单击**DataFormatTransformation.Pipelines**，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-133">Right-click **DataFormatTransformation.Pipelines**, and then click **Remove**.</span></span>  
  
4.  <span data-ttu-id="ab9df-134">右键单击**DataFormatTransformation**，指向**添加**，然后单击**新项目**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-134">Right-click **DataFormatTransformation**, point to **Add**, and then click **New Project**.</span></span> <span data-ttu-id="ab9df-135">单击**Biztalk 项目**，然后单击**空 Biztalk 服务器项目**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-135">Click **Biztalk Projects**, and then click **Empty Biztalk Server Project**.</span></span> <span data-ttu-id="ab9df-136">在**名称**框中，键入**DataFormatTransformationReceive.Pipeline**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-136">In the **Name** box, type **DataFormatTransformationReceive.Pipeline**.</span></span>  
  
5.  <span data-ttu-id="ab9df-137">右键单击**DataFormatTransformationReceive.Pipeline**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-137">Right-click **DataFormatTransformationReceive.Pipeline**, and then click **Properties**.</span></span> <span data-ttu-id="ab9df-138">单击**签名**，然后确认**对程序集签名**复选框处于选中状态，该程序集位置指向**C:\projects\Microsoft.Practices.ESB\keys\Microsoft.Practices.ESB.snk**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-138">Click **Signing**, and then verify that the **Sign the assembly** check box is selected and that the assembly location points to **C:\projects\Microsoft.Practices.ESB\keys\Microsoft.Practices.ESB.snk**.</span></span>  
  
6.  <span data-ttu-id="ab9df-139">右键单击**DataFormatTransformationReceive.Pipeline**，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-139">Right-click **DataFormatTransformationReceive.Pipeline**, point to **Add**, and then click **New Item**.</span></span>  
  
7.  <span data-ttu-id="ab9df-140">在**添加新项**对话框中，单击**接收管道**在模板窗格中。</span><span class="sxs-lookup"><span data-stu-id="ab9df-140">In the **Add New Item** dialog box, click **Receive Pipeline** in the Templates pane.</span></span> <span data-ttu-id="ab9df-141">在**名称**框中，键入**ItinerarySelectReceiveFF**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-141">In the **Name** box, type **ItinerarySelectReceiveFF**, and then click **Add**.</span></span>  
  
8.  <span data-ttu-id="ab9df-142">右键单击**引用**作为 DataFormatTransformationReceive.Pipeline 项目，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-142">Right-click **References** for the DataFormatTransformationReceive.Pipeline project, and then click **Add Reference**.</span></span> <span data-ttu-id="ab9df-143">单击**项目**选项卡上，并依次**DataFormatTransformation.Schemas**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-143">Click the **Projects** tab, and then click **DataFormatTransformation.Schemas**.</span></span> <span data-ttu-id="ab9df-144">单击**确定**添加引用。</span><span class="sxs-lookup"><span data-stu-id="ab9df-144">Click **OK** to add the reference.</span></span>  
  
9. <span data-ttu-id="ab9df-145">从工具箱中，拖动**平面文件反汇编程序**到管道组件**拆卸**管道的阶段。</span><span class="sxs-lookup"><span data-stu-id="ab9df-145">From the Toolbox, drag a **Flat file disassembler** pipeline component to the **Disassemble** stage of the pipeline.</span></span>  
  
10. <span data-ttu-id="ab9df-146">在平面文件的属性窗口中反汇编，请单击**DataModelTransformation.Schemas.NAOrderDocFF**中**文档架构**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="ab9df-146">In the Properties window for the flat file disassemble, click **DataModelTransformation.Schemas.NAOrderDocFF** in the **Document schema** drop-down list.</span></span>  
  
11. <span data-ttu-id="ab9df-147">从工具箱中，拖动**ESB 路线选择器**到管道组件**解决方**管道的阶段。</span><span class="sxs-lookup"><span data-stu-id="ab9df-147">From the Toolbox, drag an **ESB Itinerary Selector** pipeline component to the **Resolve Party** stage of the pipeline.</span></span>  
  
12. <span data-ttu-id="ab9df-148">从工具箱中，拖动**ESB 调度程序**到管道组件**解决方**阶段的管道，然后将其在放**ESB 路线选择器**管道组件。</span><span class="sxs-lookup"><span data-stu-id="ab9df-148">From the Toolbox, drag an **ESB Dispatcher** pipeline component to the **Resolve Party** stage of the pipeline, and then place it under the **ESB Itinerary Selector** pipeline component.</span></span>  
  
13. <span data-ttu-id="ab9df-149">保存所有项目。</span><span class="sxs-lookup"><span data-stu-id="ab9df-149">Save all project artifacts.</span></span>  
  
## <a name="to-create-the-test-message"></a><span data-ttu-id="ab9df-150">若要创建测试消息</span><span class="sxs-lookup"><span data-stu-id="ab9df-150">To create the test message</span></span>  
  
1.  <span data-ttu-id="ab9df-151">单击 DataFormatTransformation.Schemas 项目 NAOrderDocFF.xsd 架构文件中的一次。</span><span class="sxs-lookup"><span data-stu-id="ab9df-151">Click once in the NAOrderDocFF.xsd schema file of the DataFormatTransformation.Schemas project.</span></span> <span data-ttu-id="ab9df-152">在 Visual Studio 的属性窗格中，将更改以下两个属性：</span><span class="sxs-lookup"><span data-stu-id="ab9df-152">In the Properties pane of Visual Studio, change the following two properties:</span></span>  
  
    -   <span data-ttu-id="ab9df-153">**生成实例输出类型**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-153">**Generate Instance Output Type**.</span></span> <span data-ttu-id="ab9df-154">单击以将其更改为此属性的下拉列表**本机**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-154">Click the drop-down list for this property to change it to **Native**.</span></span>  
  
    -   <span data-ttu-id="ab9df-155">**输出实例文件名**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-155">**Output Instance Filename**.</span></span> <span data-ttu-id="ab9df-156">单击此属性的省略号按钮 （…） 并接受 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation 的默认路径。</span><span class="sxs-lookup"><span data-stu-id="ab9df-156">Click the ellipsis button (…) for this property and accept the default path of C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation.</span></span> <span data-ttu-id="ab9df-157">在**文件名**框中，键入**NAOrderDocFF**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-157">In the **File name** box, type **NAOrderDocFF**, and then click **Save**.</span></span>  
  
2.  <span data-ttu-id="ab9df-158">右键单击**NAOrderDocFF.xsd**下**DataFormatTransformation.Schemas**，然后单击**生成实例**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-158">Right-click **NAOrderDocFF.xsd** under **DataFormatTransformation.Schemas**, and then click **Generate Instance**.</span></span> <span data-ttu-id="ab9df-159">此时，你应具有 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation 目录中生成一个新文件。</span><span class="sxs-lookup"><span data-stu-id="ab9df-159">At this point, you should have a new file generated in the C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation directory.</span></span>  
  
3.  <span data-ttu-id="ab9df-160">复制 （不移动） 到 C:\HowTos 从 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation NAOrderDocFF.txt 的文件。</span><span class="sxs-lookup"><span data-stu-id="ab9df-160">Copy (do not move) the file NAOrderDocFF.txt from C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation to C:\HowTos.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ab9df-161">这是你将收到并将转换为 XML 的消息。</span><span class="sxs-lookup"><span data-stu-id="ab9df-161">This is the message you will receive and convert to XML.</span></span> <span data-ttu-id="ab9df-162">本文档表示北美顺序文档的平面文件版本。</span><span class="sxs-lookup"><span data-stu-id="ab9df-162">This document represents a flat file version of North American Order document.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="ab9df-163">步骤</span><span class="sxs-lookup"><span data-stu-id="ab9df-163">Steps</span></span>  
  
#### <a name="to-deploy-the-receive-pipeline-and-the-schema"></a><span data-ttu-id="ab9df-164">若要部署接收管道和架构</span><span class="sxs-lookup"><span data-stu-id="ab9df-164">To deploy the receive pipeline and the schema</span></span>  
  
1.  <span data-ttu-id="ab9df-165">右键单击**DataFormatTransformationReceive.Pipeline**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-165">Right-click **DataFormatTransformationReceive.Pipeline**, and then click **Properties**.</span></span> <span data-ttu-id="ab9df-166">单击**部署**，然后键入**Microsoft.Practices.ESB**中**应用程序名称**框。</span><span class="sxs-lookup"><span data-stu-id="ab9df-166">Click **Deployment**, and then type **Microsoft.Practices.ESB** in the **Application Name** box.</span></span>  
  
2.  <span data-ttu-id="ab9df-167">右键单击**DataFormatTransformation.Schemas**项目，，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-167">Right-click the **DataFormatTransformation.Schemas** project, and then click **Properties**.</span></span> <span data-ttu-id="ab9df-168">单击**部署**，然后键入**Microsoft.Practices.ESB**中**应用程序名称**框。</span><span class="sxs-lookup"><span data-stu-id="ab9df-168">Click **Deployment**, and then type **Microsoft.Practices.ESB** in the **Application Name** box.</span></span>  
  
3.  <span data-ttu-id="ab9df-169">关闭两个属性窗格**DataFormatTransformationReceive.Pipeline**和**DataFormatTransformation.Schemas**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-169">Close the Properties panes for both **DataFormatTransformationReceive.Pipeline** and **DataFormatTransformation.Schemas**.</span></span>  
  
4.  <span data-ttu-id="ab9df-170">在解决方案资源管理器，右键单击**DataFormatTransformation**项目，，然后单击**部署解决方案**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-170">In Solution Explorer, right-click the **DataFormatTransformation** project, and then click **Deploy Solution**.</span></span>  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a><span data-ttu-id="ab9df-171">若要创建和配置 ESB 入口</span><span class="sxs-lookup"><span data-stu-id="ab9df-171">To create and configure an ESB on-ramp</span></span>  
  
1.  <span data-ttu-id="ab9df-172">单击**启动**在任务栏中，指向**所有程序**，指向**BizTalk Server**，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-172">Click **Start** on the taskbar, point to **All Programs**, point to **BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="ab9df-173">在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后单击**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-173">In the BizTalk Server Administration Console, expand **BizTalk Group**, expand **Applications**, and then click **Microsoft.Practices.ESB**.</span></span>  
  
3.  <span data-ttu-id="ab9df-174">右键单击**接收位置**，指向**新建**，然后单击**单向接收位置**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-174">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
4.  <span data-ttu-id="ab9df-175">在**选择接收端口**对话框中，单击**OnRamp.Itinerary**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-175">In the **Select a Receive Port** dialog box, click **OnRamp.Itinerary**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="ab9df-176">在**接收位置属性**对话框中，在**名称**框中，键入**OnRamp.Itinerary.FlatFile.FILE**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-176">In the **Receive Location Properties** dialog box, in the **Name** box, type **OnRamp.Itinerary.FlatFile.FILE**.</span></span>  
  
6.  <span data-ttu-id="ab9df-177">在**类型**下拉列表中，单击**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-177">In the **Type** drop-down list, click **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="ab9df-178">在**文件传输属性**对话框中，在**接收文件夹**框中，键入**C:\HowTos\DropFolder**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-178">In the **FILE Transport Properties** dialog box, in the **Receive Folder** box, type **C:\HowTos\DropFolder**.</span></span>  
  
8.  <span data-ttu-id="ab9df-179">在**文件传输属性**对话框中，在**文件掩码**框中，键入 **\*.txt**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-179">In the **FILE Transport Properties** dialog box, in the **File mask** box, type **\*.txt**, and then click **OK**.</span></span>  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a><span data-ttu-id="ab9df-180">若要配置路线选择器管道组件</span><span class="sxs-lookup"><span data-stu-id="ab9df-180">To configure the Itinerary Selector pipeline component</span></span>  
  
1.  <span data-ttu-id="ab9df-181">在**接收位置属性**对话框中，单击**ItinerarySelectReceiveFF**中**接收管道**下拉列表中，然后单击省略号按钮 （…）。</span><span class="sxs-lookup"><span data-stu-id="ab9df-181">In the **Receive Location Properties** dialog box, click **ItinerarySelectReceiveFF** in the **Receive pipeline** drop down list, and then click the ellipsis button (...).</span></span>  
  
2.  <span data-ttu-id="ab9df-182">使用**配置管道**对话框中，配置以下各项**路线选择器**组件属性：</span><span class="sxs-lookup"><span data-stu-id="ab9df-182">Use the **Configure Pipeline** dialog box to configure the following **Itinerary Selector** component properties:</span></span>  
  
    1.  <span data-ttu-id="ab9df-183">单击**ItineraryFactKey**属性，再然后键入**Resolver.Itinerary**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-183">Click the **ItineraryFactKey** property, and then type **Resolver.Itinerary**.</span></span>  
  
    2.  <span data-ttu-id="ab9df-184">单击**ResolverConnectionString**属性中，键入**路线：\\\name=DataFormatTransformation;** ，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-184">Click the **ResolverConnectionString** property, type **ITINERARY:\\\name=DataFormatTransformation;** and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="ab9df-185">单击**确定**关闭**接收位置属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="ab9df-185">Click **OK** to close the **Receive Location Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="ab9df-186">在 BizTalk Server 管理控制台中，右键单击**OnRamp.Itinerary.FlatFile.FILE**接收位置，并依次**启用**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-186">In the BizTalk Server Administration Console, right-click the **OnRamp.Itinerary.FlatFile.FILE** receive location, and then click **Enable**.</span></span>  
  
#### <a name="to-test-itinerary-based-routing-of-a-flat-file-message"></a><span data-ttu-id="ab9df-187">若要测试基于路线的平面文件消息的路由</span><span class="sxs-lookup"><span data-stu-id="ab9df-187">To test itinerary-based routing of a flat file message</span></span>  
  
1.  <span data-ttu-id="ab9df-188">在 Windows 资源管理器，浏览到 C:\HowTos。</span><span class="sxs-lookup"><span data-stu-id="ab9df-188">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="ab9df-189">复制 （不移动） 到 C:\HowTos\DropFolder NAOrderDocFF.txt。</span><span class="sxs-lookup"><span data-stu-id="ab9df-189">Copy (do not move) NAOrderDocFF.txt to C:\HowTos\DropFolder.</span></span>  
  
3.  <span data-ttu-id="ab9df-190">浏览到 C:\HowTos\Out。验证 DFT%MessageID%.xml 消息已写入到目录。</span><span class="sxs-lookup"><span data-stu-id="ab9df-190">Browse to C:\HowTos\Out. Verify that the DFT%MessageID%.xml message has been written to the directory.</span></span>  
  
4.  <span data-ttu-id="ab9df-191">在 BizTalk Server 管理控制台中，右键单击**OnRamp.Itinerary.FlatFile.FILE**接收位置，并依次**禁用**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-191">In the BizTalk Server Administration Console, right-click the **OnRamp.Itinerary.FlatFile.FILE** receive location, and then click **Disable**.</span></span>  
  
5.  <span data-ttu-id="ab9df-192">后**OnRamp.Itinerary.FlatFile.FILE**接收位置处于禁用状态，右键单击它，，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-192">After the **OnRamp.Itinerary.FlatFile.FILE** receive location is disabled, right-click it, and then click **Delete**.</span></span> <span data-ttu-id="ab9df-193">在**确认删除接收位置**对话框中，单击**是**。</span><span class="sxs-lookup"><span data-stu-id="ab9df-193">In the **Confirm delete receive location** dialog box, click **Yes**.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="ab9df-194">其他资源</span><span class="sxs-lookup"><span data-stu-id="ab9df-194">Additional Resources</span></span>  
 <span data-ttu-id="ab9df-195">有关详细信息，请参阅下列相关主题：</span><span class="sxs-lookup"><span data-stu-id="ab9df-195">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="ab9df-196">如何：转换消息并使用路线传送名单将生成的消息路由至文件位置</span><span class="sxs-lookup"><span data-stu-id="ab9df-196">How to: Transform a Message and Route the Resulting Message to a File Location Using an Itinerary Routing Slip</span></span>](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
-   [<span data-ttu-id="ab9df-197">如何：使用路线传送名单将单条消息路由至多个收件人</span><span class="sxs-lookup"><span data-stu-id="ab9df-197">How to: Route a Single Message to Multiple Recipients Using an Itinerary Routing Slip</span></span>](../esb-toolkit/route-a-single-message-to-multiple-recipients-using-an-itinerary-routing-slip.md)  
  
-   [<span data-ttu-id="ab9df-198">开发活动</span><span class="sxs-lookup"><span data-stu-id="ab9df-198">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="ab9df-199">消息转换模式</span><span class="sxs-lookup"><span data-stu-id="ab9df-199">Message Transformation Patterns</span></span>](../esb-toolkit/message-transformation-patterns.md)