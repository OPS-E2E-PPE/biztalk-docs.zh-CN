---
title: 演练： 模块 2-集成 Office 与 Windows SharePoint Services 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services adapters, InfoPath forms
- InfoPath forms, creating
- InfoPath forms, Windows SharePoint Services adapters
- tutorials, Windows SharePoint Services adapters
- Windows SharePoint Services adapter tutorials, integrating Microsoft Office
- Windows SharePoint Services, document libraries
ms.assetid: 2f81a712-bb20-4c32-bbac-fb438deded38
caps.latest.revision: 48
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64e23cef8b362accba726c60945548a3345c9c45
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22291453"
---
# <a name="walkthrough-module-2---integrating-office-with-the-windows-sharepoint-services-adapter"></a><span data-ttu-id="404ca-102">演练： 模块 2-与 Windows SharePoint Services Adapter 集成 Office</span><span class="sxs-lookup"><span data-stu-id="404ca-102">Walkthrough: Module 2 - Integrating Office with the Windows SharePoint Services Adapter</span></span>
<span data-ttu-id="404ca-103">本演练是的延续[演练： 模块 1-发送和接收消息与 Windows SharePoint Services Adapter](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md)并演示如何集成与 Microsoft Office[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]基于内容的创建路由 (CBR) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="404ca-103">This walkthrough is a continuation of [Walkthrough: Module 1 - Sending and Receiving Messages with the Windows SharePoint Services Adapter](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md) and shows you how to integrate Microsoft Office with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] content-based routing (CBR) application you created.</span></span> <span data-ttu-id="404ca-104">有关 Windows SharePoint Services 适配器的简介，请参阅[什么是 Windows SharePoint Services Adapter？](../core/what-is-the-windows-sharepoint-services-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="404ca-104">For an introduction to the Windows SharePoint Services adapter see [What Is the Windows SharePoint Services Adapter?](../core/what-is-the-windows-sharepoint-services-adapter.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="404ca-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="404ca-105">Prerequisites</span></span>  
 <span data-ttu-id="404ca-106">以下为执行本主题中步骤的前提条件：</span><span class="sxs-lookup"><span data-stu-id="404ca-106">The following are prerequisites for performing the procedures in this topic:</span></span>  
  
-   <span data-ttu-id="404ca-107">必须具有包含 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 完整安装的单服务器部署。</span><span class="sxs-lookup"><span data-stu-id="404ca-107">You must have a single-server deployment with a complete installation of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="404ca-108">你必须完成以下演练：[演练： 模块 1-发送和接收消息与 Windows SharePoint Services Adapter](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md)</span><span class="sxs-lookup"><span data-stu-id="404ca-108">You must complete the following walkthrough: [Walkthrough: Module 1 - Sending and Receiving Messages with the Windows SharePoint Services Adapter](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md)</span></span>  
  
 <span data-ttu-id="404ca-109">有关使用 Windows SharePoint Services Adapter 多服务器部署中的信息，请参阅[设置和部署 Windows SharePoint Services Adapter](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="404ca-109">For information about using the Windows SharePoint Services Adapter in a multiserver deployment, see [Setting Up and Deploying the Windows SharePoint Services Adapter](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md).</span></span>  
  
## <a name="create-a-biztalk-project"></a><span data-ttu-id="404ca-110">创建 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="404ca-110">Create a BizTalk project</span></span>  
 <span data-ttu-id="404ca-111">在此过程中，使用 BizTalk 编辑器来创建空的 BizTalk 项目和架构。</span><span class="sxs-lookup"><span data-stu-id="404ca-111">In this procedure you create an empty BizTalk project and a schema using the BizTalk Editor.</span></span> <span data-ttu-id="404ca-112">此过程对于为随后将用到的 InfoPath 表单创建架构是必需的。</span><span class="sxs-lookup"><span data-stu-id="404ca-112">This procedure is required to create the schema for the InfoPath form that is used later.</span></span>  
  
#### <a name="create-a-strong-name-key-file"></a><span data-ttu-id="404ca-113">创建强名称密钥文件</span><span class="sxs-lookup"><span data-stu-id="404ca-113">Create a strong name key file</span></span>  
  
1.  <span data-ttu-id="404ca-114">启动**Visual Studio 命令提示**。</span><span class="sxs-lookup"><span data-stu-id="404ca-114">Start **Visual Studio Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="404ca-115">类型`sn -k C:\WSSAdapterWalkthrough\OrderProcess.snk`，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="404ca-115">Type `sn -k C:\WSSAdapterWalkthrough\OrderProcess.snk`, and then press **Enter**.</span></span> <span data-ttu-id="404ca-116">将写入密钥对。</span><span class="sxs-lookup"><span data-stu-id="404ca-116">The key pair will be written.</span></span>  
  
3.  <span data-ttu-id="404ca-117">关闭命令提示符。</span><span class="sxs-lookup"><span data-stu-id="404ca-117">Close the command prompt.</span></span>  
  
#### <a name="create-an-empty-biztalk-project"></a><span data-ttu-id="404ca-118">创建空的 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="404ca-118">Create an empty BizTalk project</span></span>  
  
1.  <span data-ttu-id="404ca-119">启动**Microsoft Visual Studio**。</span><span class="sxs-lookup"><span data-stu-id="404ca-119">Start **Microsoft Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="404ca-120">单击**文件**，**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="404ca-120">Click **File**, **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="404ca-121">下**项目类型**，选择**BizTalk 项目**。</span><span class="sxs-lookup"><span data-stu-id="404ca-121">Under **Project types**, select **BizTalk Projects**.</span></span>  
  
4.  <span data-ttu-id="404ca-122">下**模板**，选择**空 BizTalk 服务器项目**。</span><span class="sxs-lookup"><span data-stu-id="404ca-122">Under **Templates**, select **Empty BizTalk Server Project**.</span></span>  
  
5.  <span data-ttu-id="404ca-123">类型`OrderProcess`中**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="404ca-123">Type `OrderProcess` in the **Name** field.</span></span>  
  
6.  <span data-ttu-id="404ca-124">键入你的工作目录中的文件路径**位置**字段。</span><span class="sxs-lookup"><span data-stu-id="404ca-124">Type the file path to your working directory in the **Location** field.</span></span> <span data-ttu-id="404ca-125">例如， `C:\WSSAdapterWalkthrough\`。</span><span class="sxs-lookup"><span data-stu-id="404ca-125">For example, `C:\WSSAdapterWalkthrough\`.</span></span>  
  
7.  <span data-ttu-id="404ca-126">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="404ca-126">Click **OK**.</span></span>  
  
#### <a name="associate-the-key-file-with-the-assembly"></a><span data-ttu-id="404ca-127">将密钥文件与程序集相关联</span><span class="sxs-lookup"><span data-stu-id="404ca-127">Associate the key file with the assembly</span></span>  
  
1.  <span data-ttu-id="404ca-128">在解决方案资源管理器，右键单击`OrderProcess`项目，，然后单击**属性**以启动项目设计器。</span><span class="sxs-lookup"><span data-stu-id="404ca-128">In Solution Explorer, right-click the `OrderProcess` project, and then click **Properties** to launch the Project Designer.</span></span>  
  
2.  <span data-ttu-id="404ca-129">单击“签名”  选项卡。</span><span class="sxs-lookup"><span data-stu-id="404ca-129">Click the **Signing** tab.</span></span>  
  
3.  <span data-ttu-id="404ca-130">选择“为程序集签名”  选项，单击下拉列表中的“选择强名称密钥文件”  选项，然后单击“浏览” 。</span><span class="sxs-lookup"><span data-stu-id="404ca-130">Select **Sign the assembly** option, click drop-down list for the **Choose a strong name key file** option, and then click **Browse**.</span></span>  
  
4.  <span data-ttu-id="404ca-131">键入 `C:\WSSAdapterWalkthrough\OrderProcess.snk`。</span><span class="sxs-lookup"><span data-stu-id="404ca-131">Type `C:\WSSAdapterWalkthrough\OrderProcess.snk`.</span></span>  
  
5.  <span data-ttu-id="404ca-132">单击 **“打开”**。</span><span class="sxs-lookup"><span data-stu-id="404ca-132">Click **Open**.</span></span>  
  
#### <a name="create-an-xsd-schema-by-using-the-biztalk-editor"></a><span data-ttu-id="404ca-133">使用 BizTalk 编辑器创建 XSD 架构</span><span class="sxs-lookup"><span data-stu-id="404ca-133">Create an XSD schema by using the BizTalk Editor</span></span>  
  
1.  <span data-ttu-id="404ca-134">在解决方案资源管理器，右键单击`OrderProcess`项目中，单击**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="404ca-134">In Solution Explorer, right-click the `OrderProcess` project, click **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="404ca-135">下**类别**，单击**架构文件**。</span><span class="sxs-lookup"><span data-stu-id="404ca-135">Under **Categories**, click **Schema Files**.</span></span>  
  
3.  <span data-ttu-id="404ca-136">下**模板**，单击**架构**。</span><span class="sxs-lookup"><span data-stu-id="404ca-136">Under **Templates**, click **Schema**.</span></span>  
  
4.  <span data-ttu-id="404ca-137">类型`OrderProcessSchema`中**名称**字段，然后再单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="404ca-137">Type `OrderProcessSchema` in the **Name** field, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="404ca-138">中的属性窗口`OrderProcessSchema`，选择`Qualified`为**元素 FormDefault**属性。</span><span class="sxs-lookup"><span data-stu-id="404ca-138">In the Properties Window for `OrderProcessSchema`, select `Qualified` for the **Element FormDefault** property.</span></span>  
  
6.  <span data-ttu-id="404ca-139">中的属性窗口`OrderProcessSchema`，类型`http://OrderProcess.PurchaseOrder`中**目标 Namespace**字段。</span><span class="sxs-lookup"><span data-stu-id="404ca-139">In the Properties Window for `OrderProcessSchema`, type `http://OrderProcess.PurchaseOrder` in the **Target Namespace** field.</span></span>  
  
7.  <span data-ttu-id="404ca-140">在**BizTalk 编辑器**，右键单击`Root`，单击**重命名**，然后键入`PurchaseOrder`。</span><span class="sxs-lookup"><span data-stu-id="404ca-140">In the **BizTalk Editor**, right-click `Root`, click **Rename**, and then type `PurchaseOrder`.</span></span>  
  
8.  <span data-ttu-id="404ca-141">右键单击**PurchaseOrder**节点，单击**插入架构节点**，然后单击**子字段元素**。</span><span class="sxs-lookup"><span data-stu-id="404ca-141">Right-click the **PurchaseOrder** node, click **Insert Schema Node**, then click **Child Field Element**.</span></span>  
  
9. <span data-ttu-id="404ca-142">将其命名为 `PurchaseOrderID`。</span><span class="sxs-lookup"><span data-stu-id="404ca-142">Name it `PurchaseOrderID`.</span></span>  
  
10. <span data-ttu-id="404ca-143">创建另一个子字段元素并将其命名为 `BillTo`。</span><span class="sxs-lookup"><span data-stu-id="404ca-143">Create another child field element and name it `BillTo`.</span></span>  
  
11. <span data-ttu-id="404ca-144">创建另一个子字段元素并将其命名为 `Amount`。</span><span class="sxs-lookup"><span data-stu-id="404ca-144">Create another child field element and name it `Amount`.</span></span>  
  
12. <span data-ttu-id="404ca-145">在属性窗口中，设置**数据类型**属性`Amount`到 xs:unsignedInt。</span><span class="sxs-lookup"><span data-stu-id="404ca-145">In the Properties Window, set the **Data Type** property for `Amount` to xs:unsignedInt.</span></span>  
  
13. <span data-ttu-id="404ca-146">创建另一个子字段元素并将其命名为 `PurchaseOrderDate`。</span><span class="sxs-lookup"><span data-stu-id="404ca-146">Create another child field element and name it `PurchaseOrderDate`.</span></span>  
  
14. <span data-ttu-id="404ca-147">在属性窗口中，设置**数据类型**属性`PurchaseOrderDate`到 xs: datetime。</span><span class="sxs-lookup"><span data-stu-id="404ca-147">In the Properties Window, set the **Data Type** property for `PurchaseOrderDate` to xs:dateTime.</span></span>  
  
15. <span data-ttu-id="404ca-148">单击**文件**，然后单击**保存所有**。</span><span class="sxs-lookup"><span data-stu-id="404ca-148">Click **File**, and then click **Save All**.</span></span>  
  
16. <span data-ttu-id="404ca-149">关闭 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="404ca-149">Close [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
## <a name="create-an-infopath-form"></a><span data-ttu-id="404ca-150">创建 InfoPath 表单</span><span class="sxs-lookup"><span data-stu-id="404ca-150">Create an InfoPath form</span></span>  
 <span data-ttu-id="404ca-151">在此过程中，基于在上一步骤中创建的架构来创建另一个文档库和 InfoPath 表单。</span><span class="sxs-lookup"><span data-stu-id="404ca-151">In this procedure you create another document library and an InfoPath form based on the schema you created in the last procedure.</span></span> <span data-ttu-id="404ca-152">此 InfoPath 表单将用于向 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提交文档。</span><span class="sxs-lookup"><span data-stu-id="404ca-152">This InfoPath form will be used to submit a document to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="404ca-153">本演练需要 Microsoft Office InfoPath 2007</span><span class="sxs-lookup"><span data-stu-id="404ca-153">This walkthrough requires Microsoft Office InfoPath 2007</span></span>  
  
#### <a name="create-a-new-document-library"></a><span data-ttu-id="404ca-154">创建新文档库</span><span class="sxs-lookup"><span data-stu-id="404ca-154">Create a new document library</span></span>  
  
1.  <span data-ttu-id="404ca-155">打开 Web 浏览器并导航到所创建站点的 URL。</span><span class="sxs-lookup"><span data-stu-id="404ca-155">Open a Web browser and navigate to the URL of the site you created.</span></span> <span data-ttu-id="404ca-156">例如， `http://<server_name>/sites/WSSAdapterWalkthrough`。</span><span class="sxs-lookup"><span data-stu-id="404ca-156">For example, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span></span>  
  
2.  <span data-ttu-id="404ca-157">在顶部导航栏上，单击**创建**。</span><span class="sxs-lookup"><span data-stu-id="404ca-157">On the top navigation bar, click **Create**.</span></span>  
  
3.  <span data-ttu-id="404ca-158">下**文档库**，单击**文档库**。</span><span class="sxs-lookup"><span data-stu-id="404ca-158">Under **Document Libraries**, click **Document Library**.</span></span>  
  
4.  <span data-ttu-id="404ca-159">在**名称和描述**部分中，键入`InfoPathSolutions`中**名称字段**。</span><span class="sxs-lookup"><span data-stu-id="404ca-159">In the **Name and Description** section, type `InfoPathSolutions` in the **Name field**.</span></span>  
  
5.  <span data-ttu-id="404ca-160">在**导航**部分中，选择**是**在快速启动栏上显示此窗体库。</span><span class="sxs-lookup"><span data-stu-id="404ca-160">In the **Navigation** section, select **Yes** to display this form library on the Quick Launch bar.</span></span>  
  
6.  <span data-ttu-id="404ca-161">在**文档模板**部分中，选择`None`为**文档模板**。</span><span class="sxs-lookup"><span data-stu-id="404ca-161">In the **Document Template** section, select `None` for the **Document Template**.</span></span>  
  
7.  <span data-ttu-id="404ca-162">单击 **“创建”**。</span><span class="sxs-lookup"><span data-stu-id="404ca-162">Click **Create**.</span></span> <span data-ttu-id="404ca-163">将重定向到刚创建的空库。</span><span class="sxs-lookup"><span data-stu-id="404ca-163">You will be redirected to the empty library you just created.</span></span>  
  
8.  <span data-ttu-id="404ca-164">在左侧，单击**修改设置和列**。</span><span class="sxs-lookup"><span data-stu-id="404ca-164">On the left side, click **Modify Settings and Columns**.</span></span>  
  
9. <span data-ttu-id="404ca-165">下**列**，单击**添加一个新列**。</span><span class="sxs-lookup"><span data-stu-id="404ca-165">Under **Columns**, click **Add a New Column**.</span></span>  
  
10. <span data-ttu-id="404ca-166">下**名称和类型**，类型`Namespace`中**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="404ca-166">Under **Name and Type**, type `Namespace` in the **Name** field.</span></span>  
  
11. <span data-ttu-id="404ca-167">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="404ca-167">Click **OK**.</span></span>  
  
12. <span data-ttu-id="404ca-168">关闭 `WSSAdapterWalkthrough` 网站。</span><span class="sxs-lookup"><span data-stu-id="404ca-168">Close the `WSSAdapterWalkthrough` Web site.</span></span>  
  
#### <a name="create-an-infopath-form-based-on-the-orderprocessschema-schema-file"></a><span data-ttu-id="404ca-169">基于 OrderProcessSchema 架构文件创建 InfoPath 表单</span><span class="sxs-lookup"><span data-stu-id="404ca-169">Create an InfoPath form based on the OrderProcessSchema schema file</span></span>  
  
1.  <span data-ttu-id="404ca-170">单击**启动**，指向**所有程序**，指向**Microsoft Office**，然后单击**Microsoft Office InfoPath 2007**。</span><span class="sxs-lookup"><span data-stu-id="404ca-170">Click **Start**, point to **All Programs**, point to **Microsoft Office**, and then click **Microsoft Office InfoPath 2007**.</span></span>  
  
2.  <span data-ttu-id="404ca-171">在**填写表单**对话框中，选择**设计窗体。**</span><span class="sxs-lookup"><span data-stu-id="404ca-171">In the **Fill Out a Form** dialog box, select **Design a Form.**</span></span>  
  
3.  <span data-ttu-id="404ca-172">在**设计窗体**任务窗格中，选择**从 XML 文档或架构新建**。</span><span class="sxs-lookup"><span data-stu-id="404ca-172">In the **Design a Form** task pane, select **New from XML Document or Schema**.</span></span>  
  
4.  <span data-ttu-id="404ca-173">在**数据源向导**，单击**浏览**并选择你在上一个过程中创建的架构文件。</span><span class="sxs-lookup"><span data-stu-id="404ca-173">In the **Data Source Wizard**, click **Browse** and select the schema file you created in the last procedure.</span></span> <span data-ttu-id="404ca-174">例如， `C:\WSSAdapterWalkthrough\OrderProcess\OrderProcess\OrderProcessSchema.xsd`。</span><span class="sxs-lookup"><span data-stu-id="404ca-174">For example, `C:\WSSAdapterWalkthrough\OrderProcess\OrderProcess\OrderProcessSchema.xsd`.</span></span>  
  
5.  <span data-ttu-id="404ca-175">单击“下一步” ，然后单击“完成” 。</span><span class="sxs-lookup"><span data-stu-id="404ca-175">Click **Next**, and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="404ca-176">在**数据源**任务窗格中，右键单击**PurchaseOrder**节点，，然后单击**带有控件的节**。</span><span class="sxs-lookup"><span data-stu-id="404ca-176">In the **Data Source** task pane, right-click the **PurchaseOrder** node, and then click **Section with Controls**.</span></span> <span data-ttu-id="404ca-177">这将在模板上创建表单。</span><span class="sxs-lookup"><span data-stu-id="404ca-177">This will create the form on the template.</span></span>  
  
7.  <span data-ttu-id="404ca-178">单击**文件**，单击**保存**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="404ca-178">Click **File**, click **Save**, and then click **Save**.</span></span>  
  
8.  <span data-ttu-id="404ca-179">在**另存为**对话框中，键入`PurchaseOrder.xsn`中**文件名**字段，然后再单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="404ca-179">In the **Save As** dialog box, type `PurchaseOrder.xsn` in the **File name** field, and then click **Save**.</span></span>  
  
9. <span data-ttu-id="404ca-180">单击**文件**，然后单击**发布**。</span><span class="sxs-lookup"><span data-stu-id="404ca-180">Click **File**, and then click **Publish**.</span></span>  
  
10. <span data-ttu-id="404ca-181">在**发布向导**，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="404ca-181">In the **Publishing Wizard**, click **Next**.</span></span>  
  
11. <span data-ttu-id="404ca-182">选择**到 Web 服务器**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="404ca-182">Select **To a Web Server**, and then click **Next**.</span></span>  
  
12. <span data-ttu-id="404ca-183">键入的路径和文件名你`InfoPathSolutions`文档库，并依次**下一步**。</span><span class="sxs-lookup"><span data-stu-id="404ca-183">Type the path and filename to your `InfoPathSolutions` document library, and then click **Next**.</span></span> <span data-ttu-id="404ca-184">例如， `http://<server_name>/sites/WSSAdapterWalkthrough/InfoPathSolutions/PurchaseOrder.xsn`。</span><span class="sxs-lookup"><span data-stu-id="404ca-184">For example, `http://<server_name>/sites/WSSAdapterWalkthrough/InfoPathSolutions/PurchaseOrder.xsn`.</span></span>  
  
13. <span data-ttu-id="404ca-185">单击**完成**，然后单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="404ca-185">Click **Finish**, and then click **Close**.</span></span>  
  
14. <span data-ttu-id="404ca-186">关闭 Microsoft InfoPath。</span><span class="sxs-lookup"><span data-stu-id="404ca-186">Close Microsoft InfoPath.</span></span>  
  
## <a name="modify-the-sharepoint-document-libraries"></a><span data-ttu-id="404ca-187">修改 SharePoint 文档库</span><span class="sxs-lookup"><span data-stu-id="404ca-187">Modify the SharePoint document libraries</span></span>  
 <span data-ttu-id="404ca-188">在此过程中，将更新 PurchaseOrder.xsn 文件的命名空间属性，并修改目标文档库。</span><span class="sxs-lookup"><span data-stu-id="404ca-188">In this procedure you will update the namespace property for the PurchaseOrder.xsn file and modify the Destination Document Library.</span></span> <span data-ttu-id="404ca-189">为基于内容的路由方案确定已发布文档的订户时，此命名空间用作变量。</span><span class="sxs-lookup"><span data-stu-id="404ca-189">This namespace is used as a variable when determining subscribers of published documents for content based routing scenarios.</span></span>  
  
#### <a name="update-the-namespace-for-purchaseorderxsn"></a><span data-ttu-id="404ca-190">更新 PurchaseOrder.xsn 的命名空间</span><span class="sxs-lookup"><span data-stu-id="404ca-190">Update the namespace for PurchaseOrder.xsn</span></span>  
  
1.  <span data-ttu-id="404ca-191">打开 Web 浏览器并导航到所创建站点的 URL。</span><span class="sxs-lookup"><span data-stu-id="404ca-191">Open a Web browser and navigate to the URL of the site you created.</span></span> <span data-ttu-id="404ca-192">例如， `http://<server_name>/sites/WSSAdapterWalkthrough`。</span><span class="sxs-lookup"><span data-stu-id="404ca-192">For example, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span></span>  
  
2.  <span data-ttu-id="404ca-193">在左侧下,**文档**，单击`InfoPathSolutions`。</span><span class="sxs-lookup"><span data-stu-id="404ca-193">On the left side, under **Documents**, click `InfoPathSolutions`.</span></span>  
  
3.  <span data-ttu-id="404ca-194">将指针移`PurchaseOrder.xsn`，右键单击它，，然后单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="404ca-194">Move the pointer over `PurchaseOrder.xsn`, right-click it, and then click **Edit Properties**.</span></span>  
  
4.  <span data-ttu-id="404ca-195">类型`http://OrderProcess.PurchaseOrder`中**Namespace**字段，然后再单击**保存并关闭**。</span><span class="sxs-lookup"><span data-stu-id="404ca-195">Type `http://OrderProcess.PurchaseOrder` in the **Namespace** field, and then click **Save and Close**.</span></span>  
  
#### <a name="modify-the-destination-document-library"></a><span data-ttu-id="404ca-196">修改目标文档库</span><span class="sxs-lookup"><span data-stu-id="404ca-196">Modify the Destination document library</span></span>  
  
1.  <span data-ttu-id="404ca-197">在顶部导航栏上，单击**文档和列表**。</span><span class="sxs-lookup"><span data-stu-id="404ca-197">On the top navigation bar, click **Documents and Lists**.</span></span>  
  
2.  <span data-ttu-id="404ca-198">下**文档库**，单击**目标**。</span><span class="sxs-lookup"><span data-stu-id="404ca-198">Under **Document Libraries**, click **Destination**.</span></span>  
  
3.  <span data-ttu-id="404ca-199">在左侧，单击**修改设置和列**。</span><span class="sxs-lookup"><span data-stu-id="404ca-199">On the left side, click **Modify Settings and Columns**.</span></span>  
  
4.  <span data-ttu-id="404ca-200">下**列**，单击**添加新列**。</span><span class="sxs-lookup"><span data-stu-id="404ca-200">Under **Columns**, click **Add New Column**.</span></span>  
  
5.  <span data-ttu-id="404ca-201">下**名称和类型**，类型`Partner Name`中**列名**字段。</span><span class="sxs-lookup"><span data-stu-id="404ca-201">Under **Name and Type**, type `Partner Name` in the **Column name** field.</span></span>  
  
6.  <span data-ttu-id="404ca-202">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="404ca-202">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="404ca-203">关闭 `WSSAdapterWalkthrough` 网站。</span><span class="sxs-lookup"><span data-stu-id="404ca-203">Close the `WSSAdapterWalkthrough` Web site.</span></span>  
  
## <a name="modify-the-send-port-from-walkthrough-1"></a><span data-ttu-id="404ca-204">修改演练 1 中的发送端口</span><span class="sxs-lookup"><span data-stu-id="404ca-204">Modify the send port from walkthrough 1</span></span>  
 <span data-ttu-id="404ca-205">在此过程中，您将修改演练 1 中的发送端口。</span><span class="sxs-lookup"><span data-stu-id="404ca-205">In this procedure you modify the send port from walkthrough 1.</span></span> <span data-ttu-id="404ca-206">只有执行此过程，才能确保将此演练中处理的文档正确路由到该发送端口。</span><span class="sxs-lookup"><span data-stu-id="404ca-206">This procedure is required to ensure that the document processed in this walkthrough is correctly routed to the send port.</span></span>  
  
#### <a name="modify-the-send-port"></a><span data-ttu-id="404ca-207">修改发送端口</span><span class="sxs-lookup"><span data-stu-id="404ca-207">Modify the send port</span></span>  
  
1.  <span data-ttu-id="404ca-208">打开**BizTalk Server 管理。**</span><span class="sxs-lookup"><span data-stu-id="404ca-208">Open **BizTalk Server Administration.**</span></span>  
  
2.  <span data-ttu-id="404ca-209">展开**Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**发送端口**节点。</span><span class="sxs-lookup"><span data-stu-id="404ca-209">Expand **Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and then click the **Send Ports** node.</span></span>  
  
3.  <span data-ttu-id="404ca-210">右键单击`SendToDestination`，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="404ca-210">Right-click `SendToDestination`, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="404ca-211">下**传输**，单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="404ca-211">Under **Transport**, click **Configure**.</span></span>  
  
5.  <span data-ttu-id="404ca-212">在**Filename**字段中，键入`PurchaseOrder2-%XPATH=//pons:PurchaseOrder/pons:PurchaseOrderID%.xml`。</span><span class="sxs-lookup"><span data-stu-id="404ca-212">In the **Filename** field, type `PurchaseOrder2-%XPATH=//pons:PurchaseOrder/pons:PurchaseOrderID%.xml`.</span></span>  
  
6.  <span data-ttu-id="404ca-213">在**Namespace 别名**字段中，键入`pons="http://OrderProcess.PurchaseOrder"`。</span><span class="sxs-lookup"><span data-stu-id="404ca-213">In the **Namespace Aliases** field, type `pons="http://OrderProcess.PurchaseOrder"`.</span></span>  
  
7.  <span data-ttu-id="404ca-214">在**模板文档库**，类型`InfoPathSolutions`。</span><span class="sxs-lookup"><span data-stu-id="404ca-214">In the **Templates Document Library**, type `InfoPathSolutions`.</span></span>  
  
8.  <span data-ttu-id="404ca-215">在**模板 Namespace 列**，类型`Namespace`。</span><span class="sxs-lookup"><span data-stu-id="404ca-215">In the **Templates Namespace Column**, type `Namespace`.</span></span>  
  
9. <span data-ttu-id="404ca-216">选择`Yes`为**Microsoft Office 集成**属性。</span><span class="sxs-lookup"><span data-stu-id="404ca-216">Select `Yes` for the **Microsoft Office Integration** property.</span></span>  
  
10. <span data-ttu-id="404ca-217">下**Windows SharePoint Services 集成**，类型`Partner Name`中**列 01**字段。</span><span class="sxs-lookup"><span data-stu-id="404ca-217">Under **Windows SharePoint Services Integration**, type `Partner Name` in the **Column 01** field.</span></span>  
  
11. <span data-ttu-id="404ca-218">类型`%XPATH=//pons:PurchaseOrder/pons:BillTo%`中**01 列值**字段中，单击**确定**，然后单击**确定**再次以退出**发送端口属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="404ca-218">Type `%XPATH=//pons:PurchaseOrder/pons:BillTo%` in the **Column 01 Value** field, click **OK**, and then click **OK** again to exit the **Send Port Properties** dialog box.</span></span>  
  
#### <a name="restart-the-send-port"></a><span data-ttu-id="404ca-219">重新启动发送端口</span><span class="sxs-lookup"><span data-stu-id="404ca-219">Restart the send port</span></span>  
  
1.  <span data-ttu-id="404ca-220">在**BizTalk 管理控制台**，单击**发送端口**节点。</span><span class="sxs-lookup"><span data-stu-id="404ca-220">In the **BizTalk Administration Console**, click the **Send Ports** node.</span></span>  
  
2.  <span data-ttu-id="404ca-221">右键单击`SendToDestination`，然后单击**Unenlist**。</span><span class="sxs-lookup"><span data-stu-id="404ca-221">Right-click `SendToDestination`, and then click **Unenlist**.</span></span>  
  
3.  <span data-ttu-id="404ca-222">右键单击`SendToDestination`，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="404ca-222">Right-click `SendToDestination`, and then click **Start**.</span></span>  
  
4.  <span data-ttu-id="404ca-223">关闭**BizTalk 管理控制台**。</span><span class="sxs-lookup"><span data-stu-id="404ca-223">Close the **BizTalk Administration Console**.</span></span>  
  
## <a name="send-a-message-through-the-system"></a><span data-ttu-id="404ca-224">通过系统发送消息</span><span class="sxs-lookup"><span data-stu-id="404ca-224">Send a message through the system</span></span>  
 <span data-ttu-id="404ca-225">在此过程中，将创建 InfoPath 表单并将其上载到 Windows SharePoint Services 网站。</span><span class="sxs-lookup"><span data-stu-id="404ca-225">In this procedure you create an InfoPath form and upload it to the Windows SharePoint Services Web site.</span></span> <span data-ttu-id="404ca-226">Windows SharePoint Services 适配器将接受该消息并将其存档在存档文档库中，然后将其发送到目标文档库。</span><span class="sxs-lookup"><span data-stu-id="404ca-226">The Windows SharePoint Services adapter will take that message, archive it in the Archive document library, and then send it to the Destination document library.</span></span> <span data-ttu-id="404ca-227">此过程说明文档是如何通过 Windows Sharepoint Services 适配器，从 Sharepoint 网站流出，通过 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，到达 Sharepoint Services 网站的。</span><span class="sxs-lookup"><span data-stu-id="404ca-227">This procedure demonstrates how a document flows from a Sharepoint web site, through [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and to a Sharepoint Services Web site using the Windows Sharepoint Services adapter.</span></span>  
  
#### <a name="create-an-infopath-form-to-send-through-the-system"></a><span data-ttu-id="404ca-228">创建要通过系统发送的 InfoPath 表单</span><span class="sxs-lookup"><span data-stu-id="404ca-228">Create an InfoPath form to send through the system</span></span>  
  
1.  <span data-ttu-id="404ca-229">打开 Web 浏览器并导航到所创建站点的 URL。</span><span class="sxs-lookup"><span data-stu-id="404ca-229">Open a Web browser and navigate to the URL of the site you created.</span></span> <span data-ttu-id="404ca-230">例如， `http://<server_name>/sites/WSSAdapterWalkthrough`。</span><span class="sxs-lookup"><span data-stu-id="404ca-230">For example, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span></span>  
  
2.  <span data-ttu-id="404ca-231">在左侧下,**文档**，单击`InfoPathSolutions`。</span><span class="sxs-lookup"><span data-stu-id="404ca-231">On the left side, under **Documents**, click `InfoPathSolutions`.</span></span>  
  
3.  <span data-ttu-id="404ca-232">单击`PurchaseOrder`文件以显示**文件下载**对话框中，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="404ca-232">Click the `PurchaseOrder` file to display the **File Download** dialog box, and then click **Open**.</span></span> <span data-ttu-id="404ca-233">InfoPath 将加载该表单。</span><span class="sxs-lookup"><span data-stu-id="404ca-233">InfoPath will load the form.</span></span>  
  
4.  <span data-ttu-id="404ca-234">在**采购订单 ID**字段中，键入`1002`。</span><span class="sxs-lookup"><span data-stu-id="404ca-234">In the **Purchase Order ID** field, type `1002`.</span></span>  
  
5.  <span data-ttu-id="404ca-235">在**帐单到**字段中，键入`John Doe`。</span><span class="sxs-lookup"><span data-stu-id="404ca-235">In the **Bill To** field, type `John Doe`.</span></span>  
  
6.  <span data-ttu-id="404ca-236">在**量**字段中，键入`750`。</span><span class="sxs-lookup"><span data-stu-id="404ca-236">In the **Amount** field, type `750`.</span></span>  
  
7.  <span data-ttu-id="404ca-237">在**采购订单日期**字段中，键入`1/2/2005`。</span><span class="sxs-lookup"><span data-stu-id="404ca-237">In the **Purchase Order Date** field, type `1/2/2005`.</span></span>  
  
8.  <span data-ttu-id="404ca-238">单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="404ca-238">Click **Save**.</span></span>  
  
9. <span data-ttu-id="404ca-239">在**另存为**对话框中，键入`http://<server_name>/sites/WSSAdapterWalkthrough/Source`中**文件名**字段，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="404ca-239">In the **Save As** dialog box, type `http://<server_name>/sites/WSSAdapterWalkthrough/Source`in the **file name** field, and then hit Enter.</span></span>  
  
10. <span data-ttu-id="404ca-240">类型`PurchaseOrder2.xml`中**文件名**字段，然后再单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="404ca-240">Type `PurchaseOrder2.xml` in the **file name** field, and then click **Save**.</span></span>  
  
11. <span data-ttu-id="404ca-241">关闭 Microsoft Office InfoPath。</span><span class="sxs-lookup"><span data-stu-id="404ca-241">Close Microsoft Office InfoPath.</span></span>  
  
12. <span data-ttu-id="404ca-242">在 Web 浏览器中，在顶部导航栏上，单击**文档和列表**。</span><span class="sxs-lookup"><span data-stu-id="404ca-242">In the Web browser, on the top navigation bar, click **Documents and Lists**.</span></span>  
  
13. <span data-ttu-id="404ca-243">下**文档库**，单击**目标**。</span><span class="sxs-lookup"><span data-stu-id="404ca-243">Under **Document Libraries**, click **Destination**.</span></span>  
  
14. <span data-ttu-id="404ca-244">在目标文档库中，现在你将看到你的消息已列出。</span><span class="sxs-lookup"><span data-stu-id="404ca-244">In the Destination document library, you will now see your message listed.</span></span> <span data-ttu-id="404ca-245">你还将在存档文档库中找到存档副本。</span><span class="sxs-lookup"><span data-stu-id="404ca-245">You will also find a copy archived in the Archive document library.</span></span>  
  
15. <span data-ttu-id="404ca-246">在目标文档库中，单击 `PurchaseOrder1.xml`。</span><span class="sxs-lookup"><span data-stu-id="404ca-246">In the Destination document library, click `PurchaseOrder1.xml`.</span></span> <span data-ttu-id="404ca-247">请注意，此 XML 文件通过 Microsoft Internet Explorer 打开。</span><span class="sxs-lookup"><span data-stu-id="404ca-247">Note that this XML file is opened in Microsoft Internet Explorer.</span></span>  
  
16. <span data-ttu-id="404ca-248">在目标文档库中，单击 `PurchaseOrder2.xml`。</span><span class="sxs-lookup"><span data-stu-id="404ca-248">In the Destination document library, click `PurchaseOrder2.xml`.</span></span> <span data-ttu-id="404ca-249">请注意，此 XML 文件通过 Microsoft Office InfoPath 打开。</span><span class="sxs-lookup"><span data-stu-id="404ca-249">Note that this XML file is opened in Microsoft Office InfoPath.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="404ca-250">在目标文档库中，“文件名”列应该包含“PurchaseOrderID”字段的值，“合作伙伴名称”列应该包含“BillTo”字段的值。</span><span class="sxs-lookup"><span data-stu-id="404ca-250">In the Destination document library, the file name column should contain the value of the PurchaseOrderID field and the Partner Name column should contain the value of the BillTo field.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="404ca-251">摘要</span><span class="sxs-lookup"><span data-stu-id="404ca-251">Summary</span></span>  
 <span data-ttu-id="404ca-252">在本演练中，你学习了如何使用 Windows SharePoint Services 适配器和基于内容的路由 (CBR) 来添加与 Microsoft InfoPath 更紧密的集成。</span><span class="sxs-lookup"><span data-stu-id="404ca-252">In this walkthrough you have seen how to add tighter integration with Microsoft InfoPath using the Windows SharePoint Services Adapter and content-based routing (CBR).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="404ca-253">后续步骤</span><span class="sxs-lookup"><span data-stu-id="404ca-253">Next Steps</span></span>  
 <span data-ttu-id="404ca-254">现在，你已完成本演练中，执行[演练： 模块 3-从业务流程访问 SharePoint 属性](../core/walkthrough-module-3-accessing-sharepoint-properties-from-an-orchestration.md)演练用于对你已完成本演练中，扩展集成业务流程到项目，并演示如何访问 SharePoint 中的属性。</span><span class="sxs-lookup"><span data-stu-id="404ca-254">Now that you have completed this walkthrough, perform the [Walkthrough: Module 3 - Accessing SharePoint Properties from an Orchestration](../core/walkthrough-module-3-accessing-sharepoint-properties-from-an-orchestration.md) walkthrough which expands on the work you have done with this walkthrough, integrates an orchestration into the project, and shows you how to access SharePoint properties from within it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="404ca-255">另请参阅</span><span class="sxs-lookup"><span data-stu-id="404ca-255">See Also</span></span>  
 <span data-ttu-id="404ca-256">[什么是 Windows SharePoint Services Adapter？](../core/what-is-the-windows-sharepoint-services-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="404ca-256">[What Is the Windows SharePoint Services Adapter?](../core/what-is-the-windows-sharepoint-services-adapter.md) </span></span>  
 [<span data-ttu-id="404ca-257">Windows SharePoint Services 适配器演练</span><span class="sxs-lookup"><span data-stu-id="404ca-257">Windows SharePoint Services Adapter Walkthroughs</span></span>](../core/windows-sharepoint-services-adapter-walkthroughs.md)