---
title: 如何：将文本文档转换为 XML 并使用路线传送名单的文件位置的路由 |Microsoft Docs
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
ms.openlocfilehash: 9258493ebd15e12bcb10d4a4dba51a14fdb51c0c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302056"
---
# <a name="how-to-convert-a-text-document-to-xml-and-route-to-a-file-location-using-an-itinerary-routing-slip"></a><span data-ttu-id="d3dae-102">如何：将文本文档转换为 XML 并路由到使用路线传送名单的文件位置</span><span class="sxs-lookup"><span data-stu-id="d3dae-102">How to: Convert a Text Document to XML and Route to a File Location Using an Itinerary Routing Slip</span></span>
## <a name="goal"></a><span data-ttu-id="d3dae-103">目的</span><span class="sxs-lookup"><span data-stu-id="d3dae-103">Goal</span></span>  
 <span data-ttu-id="d3dae-104">部分演示如何创建一个管道，用于将转换为 XML 文本文档然后选择相应的路线并将消息路由到某个文件位置。</span><span class="sxs-lookup"><span data-stu-id="d3dae-104">The section demonstrates how to create a pipeline that will convert a text document to XML and then select the appropriate itinerary and route the message to a FILE location.</span></span>  
  
 <span data-ttu-id="d3dae-105">在本操作指南主题中，您将完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="d3dae-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="d3dae-106">使用管道以接收平面文件文档并将其转换为 XML。</span><span class="sxs-lookup"><span data-stu-id="d3dae-106">Use a pipeline to receive a flat file document and convert it to XML.</span></span>  
  
-   <span data-ttu-id="d3dae-107">配置路线选择器管道组件以解析相应的传送名单。</span><span class="sxs-lookup"><span data-stu-id="d3dae-107">Configure the Itinerary Selector pipeline component to resolve the appropriate routing slip.</span></span>  
  
-   <span data-ttu-id="d3dae-108">创建入口使用自定义管道。</span><span class="sxs-lookup"><span data-stu-id="d3dae-108">Create an on-ramp that uses the custom pipeline.</span></span>  
  
-   <span data-ttu-id="d3dae-109">测试基于路线的路由的平面文件消息。</span><span class="sxs-lookup"><span data-stu-id="d3dae-109">Test itinerary-based routing of a flat file message.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d3dae-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="d3dae-110">Prerequisites</span></span>  
 <span data-ttu-id="d3dae-111">本操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="d3dae-111">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="d3dae-112">开始之前</span><span class="sxs-lookup"><span data-stu-id="d3dae-112">Before You Begin</span></span>  
 <span data-ttu-id="d3dae-113">在本操作指南主题的后面部分执行的步骤之前，请完成以下任务：</span><span class="sxs-lookup"><span data-stu-id="d3dae-113">Complete the following tasks before you perform the steps later in this How-to topic:</span></span>  
  
- <span data-ttu-id="d3dae-114">部署**DataFormatTransformation**路线。</span><span class="sxs-lookup"><span data-stu-id="d3dae-114">Deploy the **DataFormatTransformation** itinerary.</span></span>  
  
- <span data-ttu-id="d3dae-115">创建测试消息。</span><span class="sxs-lookup"><span data-stu-id="d3dae-115">Create the test message.</span></span>  
  
  <span data-ttu-id="d3dae-116">以下过程介绍如何执行其中每项功能。</span><span class="sxs-lookup"><span data-stu-id="d3dae-116">The following procedures describe how to do each of these.</span></span>  
  
#### <a name="to-deploy-the-dataformattransformation-itinerary"></a><span data-ttu-id="d3dae-117">若要部署 DataFormatTransformation 路线</span><span class="sxs-lookup"><span data-stu-id="d3dae-117">To deploy the DataFormatTransformation itinerary</span></span>  
  
1.  <span data-ttu-id="d3dae-118">In Visual Studio, open C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation\DataFormatTransformation.sln.</span><span class="sxs-lookup"><span data-stu-id="d3dae-118">In Visual Studio, open C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation\DataFormatTransformation.sln.</span></span>  
  
2.  <span data-ttu-id="d3dae-119">在解决方案资源管理器中**Itinerary.Library**项目中，双击**DataFormatTransformation.itinerary**在路线设计器中打开它。</span><span class="sxs-lookup"><span data-stu-id="d3dae-119">In Solution Explorer, in the **Itinerary.Library** project, double-click **DataFormatTransformation.itinerary** to open it in the Itinerary Designer.</span></span>  
  
3.  <span data-ttu-id="d3dae-120">在 Visual Studio 中，单击的设计图面**DataFormatTransformation.itinerary**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-120">In Visual Studio, click the design surface of **DataFormatTransformation.itinerary**.</span></span> <span data-ttu-id="d3dae-121">在中**DataFormatTransformation.itinerary**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="d3dae-121">In the **DataFormatTransformation.itinerary** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="d3dae-122">在中**路线状态**下拉列表中，单击**已部署**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-122">In the **Itinerary Status** drop-down list, click **Deployed**.</span></span>  
  
    2.  <span data-ttu-id="d3dae-123">在中**模型导出程序**下拉列表中，单击**数据库路线导出程序**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-123">In the **Model Exporter** drop-down list, click **Database Itinerary Exporter**.</span></span>  
  
    3.  <span data-ttu-id="d3dae-124">单击省略号按钮 （...） 下一步**行程数据库**属性。</span><span class="sxs-lookup"><span data-stu-id="d3dae-124">Click the ellipsis button (...) next to the **Itinerary Database** property.</span></span>  
  
    4.  <span data-ttu-id="d3dae-125">在中**连接属性**对话框中，选择承载路线的存储库数据库的 SQL 服务器，然后指定数据库的名称 (默认名称是**EsbItineraryDb**)。</span><span class="sxs-lookup"><span data-stu-id="d3dae-125">In the **Connection Properties** dialog box, choose the SQL Server that hosts the itinerary repository database, and then specify the name of the database (the default name is **EsbItineraryDb**).</span></span>  
  
4.  <span data-ttu-id="d3dae-126">保存项目的所有项目。</span><span class="sxs-lookup"><span data-stu-id="d3dae-126">Save all project artifacts.</span></span>  
  
5.  <span data-ttu-id="d3dae-127">在 Visual Studio 中，右键单击设计图面的**DataModelTransformation**路线，并单击**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-127">In Visual Studio, right-click the design surface of the **DataModelTransformation** itinerary, and then click **Export Model**.</span></span>  
  
#### <a name="to-create-the-receive-pipeline"></a><span data-ttu-id="d3dae-128">若要创建的接收管道</span><span class="sxs-lookup"><span data-stu-id="d3dae-128">To create the receive pipeline</span></span>  
  
1.  <span data-ttu-id="d3dae-129">在 Visual Studio 中，右键单击**DataFormatTransformation.Schemas**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-129">In Visual Studio, right-click **DataFormatTransformation.Schemas**, and then click **Properties**.</span></span> <span data-ttu-id="d3dae-130">单击**应用程序**，然后键入**GlobalBank.ESB.DataFormatTransformation.Schemas**中**程序集名称**框。</span><span class="sxs-lookup"><span data-stu-id="d3dae-130">Click **Application**, and then type **GlobalBank.ESB.DataFormatTransformation.Schemas** in the **Assembly name** box.</span></span>  
  
2.  <span data-ttu-id="d3dae-131">右键单击**DataFormatTransformation.Schemas**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-131">Right-click **DataFormatTransformation.Schemas**, and then click **Properties**.</span></span> <span data-ttu-id="d3dae-132">单击**签名**，然后确认**程序集签名**复选框处于选中状态和程序集位置指向 **。\\...\\..\\..\\..\\..\keys\Microsoft.Practices.ESB.snk**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-132">Click **Signing**, and then verify that the **Sign the assembly** check box is selected and that the assembly location points to **.\\..\\..\\..\\..\\..\keys\Microsoft.Practices.ESB.snk**.</span></span>  
  
3.  <span data-ttu-id="d3dae-133">右键单击**DataFormatTransformation.Pipelines**，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-133">Right-click **DataFormatTransformation.Pipelines**, and then click **Remove**.</span></span>  
  
4.  <span data-ttu-id="d3dae-134">右键单击**DataFormatTransformation**，依次指向**添加**，然后单击**新项目**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-134">Right-click **DataFormatTransformation**, point to **Add**, and then click **New Project**.</span></span> <span data-ttu-id="d3dae-135">单击**Biztalk 项目**，然后单击**空的 Biztalk Server 项目**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-135">Click **Biztalk Projects**, and then click **Empty Biztalk Server Project**.</span></span> <span data-ttu-id="d3dae-136">在中**名称**框中，键入**DataFormatTransformationReceive.Pipeline**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-136">In the **Name** box, type **DataFormatTransformationReceive.Pipeline**.</span></span>  
  
5.  <span data-ttu-id="d3dae-137">右键单击**DataFormatTransformationReceive.Pipeline**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-137">Right-click **DataFormatTransformationReceive.Pipeline**, and then click **Properties**.</span></span> <span data-ttu-id="d3dae-138">单击**签名**，然后确认**程序集签名**复选框处于选中状态和程序集位置指向**C:\projects\Microsoft.Practices.ESB\keys\Microsoft.Practices.ESB.snk**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-138">Click **Signing**, and then verify that the **Sign the assembly** check box is selected and that the assembly location points to **C:\projects\Microsoft.Practices.ESB\keys\Microsoft.Practices.ESB.snk**.</span></span>  
  
6.  <span data-ttu-id="d3dae-139">右键单击**DataFormatTransformationReceive.Pipeline**，依次指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-139">Right-click **DataFormatTransformationReceive.Pipeline**, point to **Add**, and then click **New Item**.</span></span>  
  
7.  <span data-ttu-id="d3dae-140">在中**添加新项**对话框中，单击**接收管道**模板窗格中。</span><span class="sxs-lookup"><span data-stu-id="d3dae-140">In the **Add New Item** dialog box, click **Receive Pipeline** in the Templates pane.</span></span> <span data-ttu-id="d3dae-141">在中**名称**框中，键入**ItinerarySelectReceiveFF**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-141">In the **Name** box, type **ItinerarySelectReceiveFF**, and then click **Add**.</span></span>  
  
8.  <span data-ttu-id="d3dae-142">右键单击**引用**DataFormatTransformationReceive.Pipeline 项目，并单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-142">Right-click **References** for the DataFormatTransformationReceive.Pipeline project, and then click **Add Reference**.</span></span> <span data-ttu-id="d3dae-143">单击**项目**选项卡，然后依次**DataFormatTransformation.Schemas**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-143">Click the **Projects** tab, and then click **DataFormatTransformation.Schemas**.</span></span> <span data-ttu-id="d3dae-144">单击**确定**将引用添加。</span><span class="sxs-lookup"><span data-stu-id="d3dae-144">Click **OK** to add the reference.</span></span>  
  
9. <span data-ttu-id="d3dae-145">从工具箱拖动**平面文件拆装器**管道组件**拆装**管道阶段。</span><span class="sxs-lookup"><span data-stu-id="d3dae-145">From the Toolbox, drag a **Flat file disassembler** pipeline component to the **Disassemble** stage of the pipeline.</span></span>  
  
10. <span data-ttu-id="d3dae-146">在属性窗口中的平面文件反汇编，请单击**DataModelTransformation.Schemas.NAOrderDocFF**中**文档架构**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="d3dae-146">In the Properties window for the flat file disassemble, click **DataModelTransformation.Schemas.NAOrderDocFF** in the **Document schema** drop-down list.</span></span>  
  
11. <span data-ttu-id="d3dae-147">从工具箱拖动**ESB 路线选择器**管道组件**解析参与方**管道阶段。</span><span class="sxs-lookup"><span data-stu-id="d3dae-147">From the Toolbox, drag an **ESB Itinerary Selector** pipeline component to the **Resolve Party** stage of the pipeline.</span></span>  
  
12. <span data-ttu-id="d3dae-148">从工具箱拖动**ESB 调度程序**管道组件**解析参与方**阶段的管道，然后将它下放**ESB 路线选择器**管道组件。</span><span class="sxs-lookup"><span data-stu-id="d3dae-148">From the Toolbox, drag an **ESB Dispatcher** pipeline component to the **Resolve Party** stage of the pipeline, and then place it under the **ESB Itinerary Selector** pipeline component.</span></span>  
  
13. <span data-ttu-id="d3dae-149">保存项目的所有项目。</span><span class="sxs-lookup"><span data-stu-id="d3dae-149">Save all project artifacts.</span></span>  
  
## <a name="to-create-the-test-message"></a><span data-ttu-id="d3dae-150">若要创建测试消息</span><span class="sxs-lookup"><span data-stu-id="d3dae-150">To create the test message</span></span>  
  
1.  <span data-ttu-id="d3dae-151">DataFormatTransformation.Schemas 项目在 NAOrderDocFF.xsd 架构文件中单击一次。</span><span class="sxs-lookup"><span data-stu-id="d3dae-151">Click once in the NAOrderDocFF.xsd schema file of the DataFormatTransformation.Schemas project.</span></span> <span data-ttu-id="d3dae-152">在 Visual Studio 属性窗格中，更改以下两个属性：</span><span class="sxs-lookup"><span data-stu-id="d3dae-152">In the Properties pane of Visual Studio, change the following two properties:</span></span>  
  
    -   <span data-ttu-id="d3dae-153">**生成实例输出类型**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-153">**Generate Instance Output Type**.</span></span> <span data-ttu-id="d3dae-154">单击以将其更改为此属性的下拉列表**本机**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-154">Click the drop-down list for this property to change it to **Native**.</span></span>  
  
    -   <span data-ttu-id="d3dae-155">**输出实例文件名**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-155">**Output Instance Filename**.</span></span> <span data-ttu-id="d3dae-156">单击此属性的省略号按钮 （...） 并接受 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation 的默认路径。</span><span class="sxs-lookup"><span data-stu-id="d3dae-156">Click the ellipsis button (…) for this property and accept the default path of C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation.</span></span> <span data-ttu-id="d3dae-157">在中**文件名**框中，键入**NAOrderDocFF**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-157">In the **File name** box, type **NAOrderDocFF**, and then click **Save**.</span></span>  
  
2.  <span data-ttu-id="d3dae-158">右键单击**NAOrderDocFF.xsd**下**DataFormatTransformation.Schemas**，然后单击**生成实例**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-158">Right-click **NAOrderDocFF.xsd** under **DataFormatTransformation.Schemas**, and then click **Generate Instance**.</span></span> <span data-ttu-id="d3dae-159">此时，应具有 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation 目录中生成一个新文件。</span><span class="sxs-lookup"><span data-stu-id="d3dae-159">At this point, you should have a new file generated in the C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation directory.</span></span>  
  
3.  <span data-ttu-id="d3dae-160">复制 （不移动） 到 C:\HowTos NAOrderDocFF.txt C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation 从该文件。</span><span class="sxs-lookup"><span data-stu-id="d3dae-160">Copy (do not move) the file NAOrderDocFF.txt from C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation to C:\HowTos.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d3dae-161">这是将接收并将转换为 XML 的消息。</span><span class="sxs-lookup"><span data-stu-id="d3dae-161">This is the message you will receive and convert to XML.</span></span> <span data-ttu-id="d3dae-162">本文档表示 North American 订单文档的平面文件版本。</span><span class="sxs-lookup"><span data-stu-id="d3dae-162">This document represents a flat file version of North American Order document.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="d3dae-163">步骤</span><span class="sxs-lookup"><span data-stu-id="d3dae-163">Steps</span></span>  
  
#### <a name="to-deploy-the-receive-pipeline-and-the-schema"></a><span data-ttu-id="d3dae-164">若要部署接收管道和架构</span><span class="sxs-lookup"><span data-stu-id="d3dae-164">To deploy the receive pipeline and the schema</span></span>  
  
1.  <span data-ttu-id="d3dae-165">右键单击**DataFormatTransformationReceive.Pipeline**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-165">Right-click **DataFormatTransformationReceive.Pipeline**, and then click **Properties**.</span></span> <span data-ttu-id="d3dae-166">单击**部署**，然后键入**Microsoft.Practices.ESB**中**应用程序名称**框。</span><span class="sxs-lookup"><span data-stu-id="d3dae-166">Click **Deployment**, and then type **Microsoft.Practices.ESB** in the **Application Name** box.</span></span>  
  
2.  <span data-ttu-id="d3dae-167">右键单击**DataFormatTransformation.Schemas**项目，并单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-167">Right-click the **DataFormatTransformation.Schemas** project, and then click **Properties**.</span></span> <span data-ttu-id="d3dae-168">单击**部署**，然后键入**Microsoft.Practices.ESB**中**应用程序名称**框。</span><span class="sxs-lookup"><span data-stu-id="d3dae-168">Click **Deployment**, and then type **Microsoft.Practices.ESB** in the **Application Name** box.</span></span>  
  
3.  <span data-ttu-id="d3dae-169">同时关闭属性窗格**DataFormatTransformationReceive.Pipeline**并**DataFormatTransformation.Schemas**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-169">Close the Properties panes for both **DataFormatTransformationReceive.Pipeline** and **DataFormatTransformation.Schemas**.</span></span>  
  
4.  <span data-ttu-id="d3dae-170">在解决方案资源管理器中右键单击**DataFormatTransformation**项目，并单击**部署解决方案**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-170">In Solution Explorer, right-click the **DataFormatTransformation** project, and then click **Deploy Solution**.</span></span>  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a><span data-ttu-id="d3dae-171">若要创建和配置 ESB 接入点</span><span class="sxs-lookup"><span data-stu-id="d3dae-171">To create and configure an ESB on-ramp</span></span>  
  
1.  <span data-ttu-id="d3dae-172">单击**启动**在任务栏上，依次指向**所有程序**，指向**BizTalk Server**，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-172">Click **Start** on the taskbar, point to **All Programs**, point to **BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="d3dae-173">在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后单击**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-173">In the BizTalk Server Administration Console, expand **BizTalk Group**, expand **Applications**, and then click **Microsoft.Practices.ESB**.</span></span>  
  
3.  <span data-ttu-id="d3dae-174">右键单击**接收位置**，依次指向**新建**，然后单击**单向接收位置**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-174">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
4.  <span data-ttu-id="d3dae-175">在中**选择接收端口**对话框中，单击**OnRamp.Itinerary**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-175">In the **Select a Receive Port** dialog box, click **OnRamp.Itinerary**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="d3dae-176">在中**接收位置属性**对话框中**名称**框中，键入**OnRamp.Itinerary.FlatFile.FILE**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-176">In the **Receive Location Properties** dialog box, in the **Name** box, type **OnRamp.Itinerary.FlatFile.FILE**.</span></span>  
  
6.  <span data-ttu-id="d3dae-177">在中**类型**下拉列表中，单击**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-177">In the **Type** drop-down list, click **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="d3dae-178">在中**FILE 传输属性**对话框中**接收文件夹**框中，键入**C:\HowTos\DropFolder**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-178">In the **FILE Transport Properties** dialog box, in the **Receive Folder** box, type **C:\HowTos\DropFolder**.</span></span>  
  
8.  <span data-ttu-id="d3dae-179">在中**FILE 传输属性**对话框中**文件掩码**框中，键入 **\*.txt**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-179">In the **FILE Transport Properties** dialog box, in the **File mask** box, type **\*.txt**, and then click **OK**.</span></span>  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a><span data-ttu-id="d3dae-180">若要配置路线选择器管道组件</span><span class="sxs-lookup"><span data-stu-id="d3dae-180">To configure the Itinerary Selector pipeline component</span></span>  
  
1.  <span data-ttu-id="d3dae-181">在中**接收位置属性**对话框中，单击**ItinerarySelectReceiveFF**中**接收管道**下拉列表中，然后单击省略号按钮 （...）。</span><span class="sxs-lookup"><span data-stu-id="d3dae-181">In the **Receive Location Properties** dialog box, click **ItinerarySelectReceiveFF** in the **Receive pipeline** drop down list, and then click the ellipsis button (...).</span></span>  
  
2.  <span data-ttu-id="d3dae-182">使用**配置管道**对话框可以配置以下**路线选择器**组件属性：</span><span class="sxs-lookup"><span data-stu-id="d3dae-182">Use the **Configure Pipeline** dialog box to configure the following **Itinerary Selector** component properties:</span></span>  
  
    1.  <span data-ttu-id="d3dae-183">单击**ItineraryFactKey**属性，并键入**Resolver.Itinerary**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-183">Click the **ItineraryFactKey** property, and then type **Resolver.Itinerary**.</span></span>  
  
    2.  <span data-ttu-id="d3dae-184">单击**ResolverConnectionString**属性中，键入**路线：\\\name=DataFormatTransformation;** ，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-184">Click the **ResolverConnectionString** property, type **ITINERARY:\\\name=DataFormatTransformation;** and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="d3dae-185">单击**确定**以关闭**接收位置属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="d3dae-185">Click **OK** to close the **Receive Location Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="d3dae-186">在 BizTalk Server 管理控制台中，右键单击**OnRamp.Itinerary.FlatFile.FILE**接收位置，然后依次**启用**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-186">In the BizTalk Server Administration Console, right-click the **OnRamp.Itinerary.FlatFile.FILE** receive location, and then click **Enable**.</span></span>  
  
#### <a name="to-test-itinerary-based-routing-of-a-flat-file-message"></a><span data-ttu-id="d3dae-187">若要测试基于路线的路由的平面文件消息</span><span class="sxs-lookup"><span data-stu-id="d3dae-187">To test itinerary-based routing of a flat file message</span></span>  
  
1.  <span data-ttu-id="d3dae-188">在 Windows 资源管理器，浏览到 C:\HowTos。</span><span class="sxs-lookup"><span data-stu-id="d3dae-188">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="d3dae-189">复制 （不移动） 到 C:\HowTos\DropFolder NAOrderDocFF.txt。</span><span class="sxs-lookup"><span data-stu-id="d3dae-189">Copy (do not move) NAOrderDocFF.txt to C:\HowTos\DropFolder.</span></span>  
  
3.  <span data-ttu-id="d3dae-190">浏览到 C:\HowTos\Out。验证 DFT%MessageID%.xml 消息已写入到目录。</span><span class="sxs-lookup"><span data-stu-id="d3dae-190">Browse to C:\HowTos\Out. Verify that the DFT%MessageID%.xml message has been written to the directory.</span></span>  
  
4.  <span data-ttu-id="d3dae-191">在 BizTalk Server 管理控制台中，右键单击**OnRamp.Itinerary.FlatFile.FILE**接收位置，然后依次**禁用**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-191">In the BizTalk Server Administration Console, right-click the **OnRamp.Itinerary.FlatFile.FILE** receive location, and then click **Disable**.</span></span>  
  
5.  <span data-ttu-id="d3dae-192">之后**OnRamp.Itinerary.FlatFile.FILE**接收位置被禁用，右键单击它，并单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-192">After the **OnRamp.Itinerary.FlatFile.FILE** receive location is disabled, right-click it, and then click **Delete**.</span></span> <span data-ttu-id="d3dae-193">在中**确认删除接收位置**对话框中，单击**是**。</span><span class="sxs-lookup"><span data-stu-id="d3dae-193">In the **Confirm delete receive location** dialog box, click **Yes**.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="d3dae-194">其他资源</span><span class="sxs-lookup"><span data-stu-id="d3dae-194">Additional Resources</span></span>  
 <span data-ttu-id="d3dae-195">有关详细信息，请参阅下列相关主题：</span><span class="sxs-lookup"><span data-stu-id="d3dae-195">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="d3dae-196">如何：转换消息并将生成的消息路由到使用路线传送名单的文件位置</span><span class="sxs-lookup"><span data-stu-id="d3dae-196">How to: Transform a Message and Route the Resulting Message to a File Location Using an Itinerary Routing Slip</span></span>](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
-   [<span data-ttu-id="d3dae-197">如何：将一条消息路由到多个收件人使用路线传送名单</span><span class="sxs-lookup"><span data-stu-id="d3dae-197">How to: Route a Single Message to Multiple Recipients Using an Itinerary Routing Slip</span></span>](../esb-toolkit/route-a-single-message-to-multiple-recipients-using-an-itinerary-routing-slip.md)  
  
-   [<span data-ttu-id="d3dae-198">开发活动</span><span class="sxs-lookup"><span data-stu-id="d3dae-198">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="d3dae-199">消息转换模式</span><span class="sxs-lookup"><span data-stu-id="d3dae-199">Message Transformation Patterns</span></span>](../esb-toolkit/message-transformation-patterns.md)