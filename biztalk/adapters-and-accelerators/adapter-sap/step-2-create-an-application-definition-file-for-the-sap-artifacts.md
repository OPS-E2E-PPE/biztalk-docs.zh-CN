---
title: "步骤 2： 为 SAP 项目创建应用程序定义文件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application definition file, creating a
- Business Data Catalog Definition Editor
- Business Data Catalog
ms.assetid: d254b00e-dbeb-4167-ad57-6f0aa2e7a563
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d334b885b1135fb429655200090671a2a750ec0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-create-an-application-definition-file-for-the-sap-artifacts"></a><span data-ttu-id="eb922-102">步骤 2： 为 SAP 项目创建应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="eb922-102">Step 2: Create an Application Definition File for the SAP Artifacts</span></span>
<span data-ttu-id="eb922-103">![步骤 2 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span><span class="sxs-lookup"><span data-stu-id="eb922-103">![Step 2 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span></span>  
  
 <span data-ttu-id="eb922-104">**完成时间：** 15 分钟</span><span class="sxs-lookup"><span data-stu-id="eb922-104">**Time to complete:** 15 minutes</span></span>  
  
 <span data-ttu-id="eb922-105">**目标：** Microsoft SharePoint Server 中的业务数据目录功能公开，并将从-的业务线 (LOB) 应用程序的数据合并到门户。</span><span class="sxs-lookup"><span data-stu-id="eb922-105">**Objective:** The Business Data Catalog feature in Microsoft SharePoint Server exposes and incorporates data from line-of-business (LOB) applications into portals.</span></span> <span data-ttu-id="eb922-106">若要将此数据合并到您的门户网站，必须在生成应用程序定义文件，可以使用 Microsoft Office SharePoint Server。</span><span class="sxs-lookup"><span data-stu-id="eb922-106">To incorporate this data into your portal site, you must build an application definition file that Microsoft Office SharePoint Server can consume.</span></span>  
  
 <span data-ttu-id="eb922-107">业务数据目录定义编辑器工具，适用于 Microsoft Office SharePoint Server 2007 SDK，可为业务数据目录中创建应用程序定义文件。</span><span class="sxs-lookup"><span data-stu-id="eb922-107">The Business Data Catalog Definition Editor tool, available with Microsoft Office SharePoint Server 2007 SDK,enables you to create an application definition file for the Business Data Catalog.</span></span> <span data-ttu-id="eb922-108">此工具自动生成一个 XML 文件定义文件中，因此不需要手动创建该文件在 XML 编辑器。</span><span class="sxs-lookup"><span data-stu-id="eb922-108">This tool automatically generates an XML file for the definition file, so you do not need to manually create the file in an XML editor.</span></span>  
  
 <span data-ttu-id="eb922-109">要创建 Microsoft Office SharePoint Server 应用程序的目的是：</span><span class="sxs-lookup"><span data-stu-id="eb922-109">The purpose of the Microsoft Office SharePoint Server application that you are creating is to:</span></span>  
  
-   <span data-ttu-id="eb922-110">在基于客户姓名的 SAP 系统中搜索客户。</span><span class="sxs-lookup"><span data-stu-id="eb922-110">Search for a customer in the SAP system based on a customer name.</span></span>  
  
-   <span data-ttu-id="eb922-111">从提取客户的列表中选择客户和检索客户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="eb922-111">Select a customer from the list of fetched customers and retrieve the details for the customer.</span></span>  
  
-   <span data-ttu-id="eb922-112">从提取客户的列表中选择客户和检索客户的销售订单。</span><span class="sxs-lookup"><span data-stu-id="eb922-112">Select a customer from the list of fetched customers and retrieve the sales orders for the customer.</span></span>  
  
 <span data-ttu-id="eb922-113">对于每个这些要求，你必须完成一组在业务数据目录定义编辑器工具中的任务。</span><span class="sxs-lookup"><span data-stu-id="eb922-113">For each of these requirements, you must complete a set of tasks in the Business Data Catalog Definition Editor tool.</span></span> <span data-ttu-id="eb922-114">本主题提供有关如何执行这些任务的说明。</span><span class="sxs-lookup"><span data-stu-id="eb922-114">This topic provides instructions on how to perform these tasks.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="eb922-115">先决条件</span><span class="sxs-lookup"><span data-stu-id="eb922-115">Prerequisites</span></span>  
  
-   <span data-ttu-id="eb922-116">请确保已安装 Microsoft Office SharePoint Server 2007 SDK 的一部分业务数据目录定义编辑器。</span><span class="sxs-lookup"><span data-stu-id="eb922-116">Be sure that you have the Business Data Catalog Definition Editor installed as part of the Microsoft Office SharePoint Server 2007 SDK.</span></span> <span data-ttu-id="eb922-117">你可以下载 SDK 从[http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130)。</span><span class="sxs-lookup"><span data-stu-id="eb922-117">You can download the SDK from [http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130).</span></span>  
  
-   <span data-ttu-id="eb922-118">将 WCF 服务发布中所述[步骤 1： 发布 SAP 项目作为一个 WCF 服务](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md)。</span><span class="sxs-lookup"><span data-stu-id="eb922-118">Publish the WCF service as described in [Step 1: Publish the SAP Artifacts as a WCF Service](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md).</span></span>  
  
## <a name="creating-an-application-definition-file"></a><span data-ttu-id="eb922-119">创建应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="eb922-119">Creating an Application Definition File</span></span>  
 <span data-ttu-id="eb922-120">本主题提供创建应用程序定义文件的 WCF 服务的分步说明。</span><span class="sxs-lookup"><span data-stu-id="eb922-120">This topic provides step-by-step instructions to create an application definition file for the WCF service.</span></span>  
  
### <a name="connect-to-the-wcf-lob-service-and-create-entities"></a><span data-ttu-id="eb922-121">连接到 WCF LOB 服务，并创建实体</span><span class="sxs-lookup"><span data-stu-id="eb922-121">Connect to the WCF LOB Service, and Create Entities</span></span>  
 <span data-ttu-id="eb922-122">你必须连接到要提取 Web 服务描述语言 (WSDL) 服务的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="eb922-122">You must connect to the WCF service to extract the Web Services Description Language (WSDL) for the service.</span></span> <span data-ttu-id="eb922-123">从 WSDL，业务数据目录定义编辑器中提取方法。</span><span class="sxs-lookup"><span data-stu-id="eb922-123">From the WSDL, the Business Data Catalog Definition Editor extracts the methods.</span></span> <span data-ttu-id="eb922-124">这些方法可以用于创建实体。</span><span class="sxs-lookup"><span data-stu-id="eb922-124">These methods can be used to create entities.</span></span> <span data-ttu-id="eb922-125">对于此示例中，两个实体都会创建，每个用于客户和销售订单。</span><span class="sxs-lookup"><span data-stu-id="eb922-125">For this example, two entities are created, one each for the customer and sales orders.</span></span>  
  
##### <a name="to-connect-to-the-wcf-service-and-create-entities"></a><span data-ttu-id="eb922-126">若要连接到 WCF 服务并创建实体</span><span class="sxs-lookup"><span data-stu-id="eb922-126">To connect to the WCF service and create entities</span></span>  
  
1.  <span data-ttu-id="eb922-127">启动业务数据目录定义编辑器。</span><span class="sxs-lookup"><span data-stu-id="eb922-127">Start the Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="eb922-128">上**启动**菜单上，单击**Microsoft 业务数据目录定义编辑器**。</span><span class="sxs-lookup"><span data-stu-id="eb922-128">On the **Start** menu, click **Microsoft Business Data Catalog Definition Editor**.</span></span>  
  
2.  <span data-ttu-id="eb922-129">在工具栏上，单击**添加 LOB 系统**。</span><span class="sxs-lookup"><span data-stu-id="eb922-129">On the toolbar, click **Add LOB System**.</span></span>  
  
3.  <span data-ttu-id="eb922-130">在添加 LOB 系统窗口中，单击**连接到 web 服务**。</span><span class="sxs-lookup"><span data-stu-id="eb922-130">In the Add LOB System window, click **Connect to Webservice**.</span></span>  
  
4.  <span data-ttu-id="eb922-131">在**URL**框中，键入 WCF 服务的 URL。</span><span class="sxs-lookup"><span data-stu-id="eb922-131">In the **URL** box, type the URL for the WCF service.</span></span> <span data-ttu-id="eb922-132">该 URL 必须采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="eb922-132">The URL must be in the following format:</span></span>  
  
    ```  
    https://<computer_name>/Customer_Order/Rfc.svc?wsdl  
    ```  
  
     <span data-ttu-id="eb922-133">其中 Rfc.svc 是 Rfc 协定所创建的文件。</span><span class="sxs-lookup"><span data-stu-id="eb922-133">where Rfc.svc is the file created for the Rfc contract.</span></span>  
  
     <span data-ttu-id="eb922-134">当你测试是否成功，如主题所述发布 WCF 服务时，才可用 URL[步骤 1： 发布 SAP 项目作为一个 WCF 服务](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md)。</span><span class="sxs-lookup"><span data-stu-id="eb922-134">The URL is available when you test whether the WCF service is published successfully, as described in the topic [Step 1: Publish the SAP Artifacts as a WCF Service](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md).</span></span>  
  
5.  <span data-ttu-id="eb922-135">单击 **“连接”**。</span><span class="sxs-lookup"><span data-stu-id="eb922-135">Click **Connect**.</span></span>  
  
6.  <span data-ttu-id="eb922-136">若要查看在 WCF 适配器服务开发向导中选择的操作，请单击**添加 Web 方法**选项卡。你将看到以下方法：</span><span class="sxs-lookup"><span data-stu-id="eb922-136">To see the operations you selected in the WCF Adapter Service Development Wizard, click the **Add Web Method** tab. You will see the following methods:</span></span>  
  
    -   <span data-ttu-id="eb922-137">SD_RFC_CUSTOMER_GET</span><span class="sxs-lookup"><span data-stu-id="eb922-137">SD_RFC_CUSTOMER_GET</span></span>  
  
    -   <span data-ttu-id="eb922-138">BAPI_SALESORDER_GETLIST</span><span class="sxs-lookup"><span data-stu-id="eb922-138">BAPI_SALESORDER_GETLIST</span></span>  
  
         <span data-ttu-id="eb922-139">![将 web 方法添加到 BDC 应用程序](../../adapters-and-accelerators/adapter-sap/media/ea411db2-5cf4-4486-83da-57d3fc332448.gif "ea411db2-5cf4-4486-83da-57d3fc332448")</span><span class="sxs-lookup"><span data-stu-id="eb922-139">![Add web methods to the BDC application](../../adapters-and-accelerators/adapter-sap/media/ea411db2-5cf4-4486-83da-57d3fc332448.gif "ea411db2-5cf4-4486-83da-57d3fc332448")</span></span>  
  
     <span data-ttu-id="eb922-140">将方法拖到设计图面。</span><span class="sxs-lookup"><span data-stu-id="eb922-140">Drag the methods to the Design Surface.</span></span> <span data-ttu-id="eb922-141">请确保将这两种操作拖动到不同的实体。</span><span class="sxs-lookup"><span data-stu-id="eb922-141">Make sure you drag both operations to the different entities.</span></span>  
  
     <span data-ttu-id="eb922-142">![为 web 方法创建实体](../../adapters-and-accelerators/adapter-sap/media/ce4e9bc3-1eae-43ae-8375-e44cf19aaffc.gif "ce4e9bc3-1eae-43ae-8375-e44cf19aaffc")</span><span class="sxs-lookup"><span data-stu-id="eb922-142">![Create entities for the web methods](../../adapters-and-accelerators/adapter-sap/media/ce4e9bc3-1eae-43ae-8375-e44cf19aaffc.gif "ce4e9bc3-1eae-43ae-8375-e44cf19aaffc")</span></span>  
  
7.  <span data-ttu-id="eb922-143">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="eb922-143">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="eb922-144">在**输入 LOB 系统的名称**对话框中，键入一个名称中**LOB 系统名称**框。</span><span class="sxs-lookup"><span data-stu-id="eb922-144">In the **Enter the name for the LOB System** dialog box, type a name in the **LOB System Name** box.</span></span> <span data-ttu-id="eb922-145">此示例中，称之为**Customer_Order**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="eb922-145">For this example, call it **Customer_Order**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="eb922-146">在业务数据目录定义编辑器中，两个实体被列为**Entity0**和**Entity1**。</span><span class="sxs-lookup"><span data-stu-id="eb922-146">In the Business Data Catalog Definition Editor, the two entities are listed as **Entity0** and **Entity1**.</span></span> <span data-ttu-id="eb922-147">指定友好名称，这些实体。</span><span class="sxs-lookup"><span data-stu-id="eb922-147">Give these entities friendly names.</span></span> <span data-ttu-id="eb922-148">重命名为 SD_RFC_CUSTOMER_GET 到的实体**客户**，并将该实体重命名为到 BAPI_SALESORDER_GETLIST **SalesOrder**。</span><span class="sxs-lookup"><span data-stu-id="eb922-148">Rename the entity for SD_RFC_CUSTOMER_GET to **Customer**, and rename the entity for BAPI_SALESORDER_GETLIST to **SalesOrder**.</span></span> <span data-ttu-id="eb922-149">执行以下步骤以重命名实体：</span><span class="sxs-lookup"><span data-stu-id="eb922-149">Perform the following steps to rename the entities:</span></span>  
  
    1.  <span data-ttu-id="eb922-150">展开**Customer_Order**节点，然后展开**实体**节点。</span><span class="sxs-lookup"><span data-stu-id="eb922-150">Expand the **Customer_Order** node, and then expand the **Entities** node.</span></span>  
  
    2.  <span data-ttu-id="eb922-151">选择**Entity0**节点。</span><span class="sxs-lookup"><span data-stu-id="eb922-151">Select the **Entity0** node.</span></span>  
  
    3.  <span data-ttu-id="eb922-152">在属性窗格中，键入**客户**中**名称**框。</span><span class="sxs-lookup"><span data-stu-id="eb922-152">In the Properties pane, type **Customer** in the **Name** box.</span></span>  
  
         <span data-ttu-id="eb922-153">![重命名实体](../../adapters-and-accelerators/adapter-sap/media/4e83a036-3ab7-4f74-9f67-420574219d3d.gif "4e83a036-3ab7-4f74-9f67-420574219d3d")</span><span class="sxs-lookup"><span data-stu-id="eb922-153">![Rename the entity](../../adapters-and-accelerators/adapter-sap/media/4e83a036-3ab7-4f74-9f67-420574219d3d.gif "4e83a036-3ab7-4f74-9f67-420574219d3d")</span></span>  
  
    4.  <span data-ttu-id="eb922-154">选择**Entity1**节点。</span><span class="sxs-lookup"><span data-stu-id="eb922-154">Select the **Entity1** node.</span></span>  
  
    5.  <span data-ttu-id="eb922-155">在属性窗格中，键入**SalesOrder**中**名称**框。</span><span class="sxs-lookup"><span data-stu-id="eb922-155">In the Properties pane, type **SalesOrder** in the **Name** box.</span></span>  
  
### <a name="specify-user-name-and-password-headers-for-the-methods"></a><span data-ttu-id="eb922-156">为方法中指定用户名和密码标头</span><span class="sxs-lookup"><span data-stu-id="eb922-156">Specify User Name and Password Headers for the Methods</span></span>  
 <span data-ttu-id="eb922-157">时 SAP 系统中创建了所选的 Rfc WCF 服务，你将指定用户名称和密码标头，为终结点行为配置的一部分。</span><span class="sxs-lookup"><span data-stu-id="eb922-157">When creating a WCF service for the selected RFCs in the SAP system, you specified user name and password headers as part of the endpoint behavior configuration.</span></span> <span data-ttu-id="eb922-158">请参阅[步骤 1： 将 SAP 项目作为 WCF 服务发布](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md)。</span><span class="sxs-lookup"><span data-stu-id="eb922-158">See [Step 1: Publish the SAP Artifacts as a WCF Service](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md).</span></span> <span data-ttu-id="eb922-159">必须指定方法属性的相同值。</span><span class="sxs-lookup"><span data-stu-id="eb922-159">You must specify the same values for the method properties.</span></span>  
  
##### <a name="to-specify-user-name-and-password-headers"></a><span data-ttu-id="eb922-160">若要指定用户名称和密码标头</span><span class="sxs-lookup"><span data-stu-id="eb922-160">To specify user name and password headers</span></span>  
  
1.  <span data-ttu-id="eb922-161">添加 SD_RFC_CUSTOMER_GET 方法的用户名称和密码标头。</span><span class="sxs-lookup"><span data-stu-id="eb922-161">Add the user name and password headers for the SD_RFC_CUSTOMER_GET method.</span></span>  
  
    1.  <span data-ttu-id="eb922-162">在元数据对象窗格中，展开**客户**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="eb922-162">In the Metadata Objects pane, expand the **Customer** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="eb922-163">单击 SD_RFC_CUSTOMER_GET 节点中，然后在属性窗格中，单击省略号 （…） 按钮针对**属性**框。</span><span class="sxs-lookup"><span data-stu-id="eb922-163">Click the SD_RFC_CUSTOMER_GET node, and in the Properties pane click the ellipsis (…) button against the **Properties** box.</span></span>  
  
    3.  <span data-ttu-id="eb922-164">在 PropertyView 集合编辑器窗口中，单击**添加**，然后在属性窗格中，键入**HttpHeaderUserName**为**名称**框。</span><span class="sxs-lookup"><span data-stu-id="eb922-164">In the PropertyView Collection Editor window, click **Add**, and in the Property pane, type **HttpHeaderUserName** for the **Name** box.</span></span> <span data-ttu-id="eb922-165">同样，键入**MyUserHeader**为**PropertyValue**框。</span><span class="sxs-lookup"><span data-stu-id="eb922-165">Similarly, type **MyUserHeader** for the **PropertyValue** box.</span></span> <span data-ttu-id="eb922-166">选择**System.String**为**类型**框。</span><span class="sxs-lookup"><span data-stu-id="eb922-166">Select **System.String** for the **Type** box.</span></span>  
  
         <span data-ttu-id="eb922-167">![将属性添加](../../adapters-and-accelerators/adapter-sap/media/9eef32ac-8a93-45dc-8d07-12b7dbf961ba.gif "9eef32ac-8a93-45dc-8d07-12b7dbf961ba")</span><span class="sxs-lookup"><span data-stu-id="eb922-167">![Add a property](../../adapters-and-accelerators/adapter-sap/media/9eef32ac-8a93-45dc-8d07-12b7dbf961ba.gif "9eef32ac-8a93-45dc-8d07-12b7dbf961ba")</span></span>  
  
    4.  <span data-ttu-id="eb922-168">在 PropertyView 集合编辑器窗口中，单击**添加**，然后在属性窗格中，键入**HttpHeaderPassword**为**名称**框。</span><span class="sxs-lookup"><span data-stu-id="eb922-168">In the PropertyView Collection Editor window, click **Add**, and in the Property pane, type **HttpHeaderPassword** for the **Name** box.</span></span> <span data-ttu-id="eb922-169">同样，键入**MyPassHeader**为**PropertyValue**框。</span><span class="sxs-lookup"><span data-stu-id="eb922-169">Similarly, type **MyPassHeader** for the **PropertyValue** box.</span></span> <span data-ttu-id="eb922-170">选择**System.String**为**类型**框。</span><span class="sxs-lookup"><span data-stu-id="eb922-170">Select **System.String** for the **Type** box.</span></span>  
  
    5.  <span data-ttu-id="eb922-171">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="eb922-171">Click **OK**.</span></span>  
  
2.  <span data-ttu-id="eb922-172">添加 BAPI_SALESORDER_GETLIST 方法的用户名称和密码标头。</span><span class="sxs-lookup"><span data-stu-id="eb922-172">Add the user name and password headers for the BAPI_SALESORDER_GETLIST method.</span></span>  
  
    1.  <span data-ttu-id="eb922-173">在元数据对象窗格中，展开**SalesOrder**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="eb922-173">In the Metadata Objects pane, expand the **SalesOrder** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="eb922-174">单击 BAPI_SALESORDER_GETLIST 节点中，然后在属性窗格中，单击省略号 （…） 按钮针对**属性**框。</span><span class="sxs-lookup"><span data-stu-id="eb922-174">Click the BAPI_SALESORDER_GETLIST node, and in the Properties pane click the ellipsis (…) button against the **Properties** box.</span></span>  
  
    3.  <span data-ttu-id="eb922-175">在 PropertyView 集合编辑器窗口中，单击**添加**，然后在属性窗格中，键入**HttpHeaderUserName**为**名称**框。</span><span class="sxs-lookup"><span data-stu-id="eb922-175">In the PropertyView Collection Editor window, click **Add**, and in the Property pane, type **HttpHeaderUserName** for the **Name** box.</span></span> <span data-ttu-id="eb922-176">同样，键入**MyUserHeader**为**PropertyValue**框。</span><span class="sxs-lookup"><span data-stu-id="eb922-176">Similarly, type **MyUserHeader** for the **PropertyValue** box.</span></span> <span data-ttu-id="eb922-177">选择**System.String**为**类型**框。</span><span class="sxs-lookup"><span data-stu-id="eb922-177">Select **System.String** for the **Type** box.</span></span>  
  
    4.  <span data-ttu-id="eb922-178">在 PropertyView 集合编辑器窗口中，单击**添加**，然后在属性窗格中，键入**HttpHeaderPassword**为**名称**框。</span><span class="sxs-lookup"><span data-stu-id="eb922-178">In the PropertyView Collection Editor window, click **Add**, and in the Property pane, type **HttpHeaderPassword** for the **Name** box.</span></span> <span data-ttu-id="eb922-179">同样，键入**MyPassHeader**为**PropertyValue**框。</span><span class="sxs-lookup"><span data-stu-id="eb922-179">Similarly, type **MyPassHeader** for the **PropertyValue** box.</span></span> <span data-ttu-id="eb922-180">选择**System.String**为**类型**框。</span><span class="sxs-lookup"><span data-stu-id="eb922-180">Select **System.String** for the **Type** box.</span></span>  
  
    5.  <span data-ttu-id="eb922-181">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="eb922-181">Click **OK**.</span></span>  
  
### <a name="set-up-single-sign-on-for-connecting-to-the-sap-system"></a><span data-ttu-id="eb922-182">为连接到 SAP 系统上单一登录设置</span><span class="sxs-lookup"><span data-stu-id="eb922-182">Set up Single Sign-On for Connecting to the SAP System</span></span>  
 <span data-ttu-id="eb922-183">在本主题中执行的所有过程完成后，你将创建可以导入 SharePoint 应用程序的应用程序定义文件。</span><span class="sxs-lookup"><span data-stu-id="eb922-183">After you have finished performing all the procedures in this topic, you will have created an application definition file that can be imported into a SharePoint application.</span></span> <span data-ttu-id="eb922-184">从应用程序，你可以调用 SAP 方法从 SAP 系统中检索相关数据。</span><span class="sxs-lookup"><span data-stu-id="eb922-184">From the application, you invoke the SAP methods to retrieve relevant data from the SAP system.</span></span> <span data-ttu-id="eb922-185">若要启用此功能，必须在 SharePoint 应用程序中创建 SAP 系统中的用户和用户之间的映射。</span><span class="sxs-lookup"><span data-stu-id="eb922-185">To enable this, you must create a mapping between a user in the SAP system and the user in the SharePoint application.</span></span> <span data-ttu-id="eb922-186">已导入的应用程序定义文件后，可以在 SharePoint 管理中心控制台中创建此映射。</span><span class="sxs-lookup"><span data-stu-id="eb922-186">You create this mapping in SharePoint Central Administration console after you have imported the application definition file.</span></span>  
  
 <span data-ttu-id="eb922-187">但是，若要创建映射必须设置一个属性**SecondarySsoApplicationId**在业务数据目录定义编辑器中。</span><span class="sxs-lookup"><span data-stu-id="eb922-187">However, to create the mapping you must set a property **SecondarySsoApplicationId** in the Business Data Catalog Definition Editor.</span></span>  
  
##### <a name="to-set-the-secondaryssoapplicationid-property"></a><span data-ttu-id="eb922-188">若要设置 SecondarySsoApplicationId 属性</span><span class="sxs-lookup"><span data-stu-id="eb922-188">To set the SecondarySsoApplicationId property</span></span>  
  
1.  <span data-ttu-id="eb922-189">在元数据对象窗格中，展开**Customer_Order**节点，然后展开**实例**节点。</span><span class="sxs-lookup"><span data-stu-id="eb922-189">In the Metadata Objects pane, expand the **Customer_Order** node, and then expand the **Instances** node.</span></span>  
  
2.  <span data-ttu-id="eb922-190">单击**Customer_Order_Instance**，然后在属性窗格中，单击针对省略号 （...） 按钮**属性**框。</span><span class="sxs-lookup"><span data-stu-id="eb922-190">Click **Customer_Order_Instance**, and in the Properties pane, click the ellipsis (…) button against the **Properties** box.</span></span>  
  
3.  <span data-ttu-id="eb922-191">在 PropertyView 集合编辑器窗口中，单击**添加**，然后在属性窗格中，键入**SecondarySsoApplicationId**为**名称**框。</span><span class="sxs-lookup"><span data-stu-id="eb922-191">In the PropertyView Collection Editor window, click **Add**, and in the Property pane, type **SecondarySsoApplicationId** for the **Name** box.</span></span> <span data-ttu-id="eb922-192">同样，键入**SAPSSO**为**PropertyValue**框。</span><span class="sxs-lookup"><span data-stu-id="eb922-192">Similarly, type **SAPSSO** for the **PropertyValue** box.</span></span> <span data-ttu-id="eb922-193">选择**System.String**为**类型**框。</span><span class="sxs-lookup"><span data-stu-id="eb922-193">Select **System.String** for the **Type** box.</span></span>  
  
     <span data-ttu-id="eb922-194">![添加 SSO 属性](../../adapters-and-accelerators/adapter-sap/media/1eb813e4-fed2-45c2-8902-9af5dd3369bf.gif "1eb813e4-fed2-45c2-8902-9af5dd3369bf")</span><span class="sxs-lookup"><span data-stu-id="eb922-194">![Add the SSO property](../../adapters-and-accelerators/adapter-sap/media/1eb813e4-fed2-45c2-8902-9af5dd3369bf.gif "1eb813e4-fed2-45c2-8902-9af5dd3369bf")</span></span>  
  
4.  <span data-ttu-id="eb922-195">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="eb922-195">Click **OK**.</span></span>  
  
### <a name="requirement-1-search-for-customers-based-on-customer-name"></a><span data-ttu-id="eb922-196">要求 1： 基于客户姓名的客户搜索</span><span class="sxs-lookup"><span data-stu-id="eb922-196">Requirement 1: Search for Customers Based on Customer Name</span></span>  
 <span data-ttu-id="eb922-197">若要创建可以用于搜索基于客户姓名的客户的应用程序定义文件，必须执行以下一组任务。</span><span class="sxs-lookup"><span data-stu-id="eb922-197">To create an application definition file that can be used to search for customers based on customer name, you must perform the following set of tasks.</span></span>  
  
-   <span data-ttu-id="eb922-198">在 SD_RFC_CUSTOMER_GET 方法中，创建筛选器，并将其映射到存储的客户名称的参数。</span><span class="sxs-lookup"><span data-stu-id="eb922-198">In the SD_RFC_CUSTOMER_GET method, create a filter and map it to the parameter that stores the customer name.</span></span>  
  
-   <span data-ttu-id="eb922-199">创建**Finder** SD_RFC_CUSTOMER_GET 方法的方法实例。</span><span class="sxs-lookup"><span data-stu-id="eb922-199">Create a **Finder** method instance for the SD_RFC_CUSTOMER_GET method.</span></span> <span data-ttu-id="eb922-200">A **Finder**方法检索基于筛选器的记录的列表。</span><span class="sxs-lookup"><span data-stu-id="eb922-200">A **Finder** method retrieves a list of records based on a filter.</span></span>  
  
##### <a name="to-create-a-filter-and-map-it-to-the-customer-name-parameter"></a><span data-ttu-id="eb922-201">创建筛选器，并将其映射到客户名称参数</span><span class="sxs-lookup"><span data-stu-id="eb922-201">To create a filter, and map it to the customer name parameter</span></span>  
  
1.  <span data-ttu-id="eb922-202">创建筛选器。</span><span class="sxs-lookup"><span data-stu-id="eb922-202">Create a filter.</span></span>  
  
    1.  <span data-ttu-id="eb922-203">在元数据对象窗格中，展开**客户**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="eb922-203">In the Metadata Objects pane, expand the **Customer** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="eb922-204">展开 SD_RFC_CUSTOMER_GET 方法中，右键单击**筛选器**，然后单击**添加筛选器**。</span><span class="sxs-lookup"><span data-stu-id="eb922-204">Expand the SD_RFC_CUSTOMER_GET method, right-click **Filters**, and then click **Add Filter**.</span></span>  
  
         <span data-ttu-id="eb922-205">![向方法添加筛选器](../../adapters-and-accelerators/adapter-sap/media/23eaab24-66e4-486f-8f99-02a5e0fef984.gif "23eaab24-66e4-486f-8f99-02a5e0fef984")</span><span class="sxs-lookup"><span data-stu-id="eb922-205">![Add filter to a method](../../adapters-and-accelerators/adapter-sap/media/23eaab24-66e4-486f-8f99-02a5e0fef984.gif "23eaab24-66e4-486f-8f99-02a5e0fef984")</span></span>  
  
    3.  <span data-ttu-id="eb922-206">在属性窗格中，键入**CustomerName**中**名称**框。</span><span class="sxs-lookup"><span data-stu-id="eb922-206">In the Properties pane, type **CustomerName** in the **Name** box.</span></span>  
  
         <span data-ttu-id="eb922-207">![指定的筛选器名称](../../adapters-and-accelerators/adapter-sap/media/0a0d0f85-a16a-4969-a122-097355141c27.gif "0a0d0f85-a16a-4969-a122-097355141c27")</span><span class="sxs-lookup"><span data-stu-id="eb922-207">![Specify a name for the filter](../../adapters-and-accelerators/adapter-sap/media/0a0d0f85-a16a-4969-a122-097355141c27.gif "0a0d0f85-a16a-4969-a122-097355141c27")</span></span>  
  
    4.  <span data-ttu-id="eb922-208">有关**FilterType**属性中，选择**WildcardFilter**。</span><span class="sxs-lookup"><span data-stu-id="eb922-208">For the **FilterType** property, select **WildcardFilter**.</span></span>  
  
2.  <span data-ttu-id="eb922-209">映射到筛选器**NAME1** SD_RFC_CUSTOMER_GET 方法中的参数。</span><span class="sxs-lookup"><span data-stu-id="eb922-209">Map the filter to the **NAME1** parameter in the SD_RFC_CUSTOMER_GET method.</span></span>  
  
    1.  <span data-ttu-id="eb922-210">在元数据对象窗格中，展开**客户**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="eb922-210">In the Metadata Objects pane, expand the **Customer** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="eb922-211">展开 SD_RFC_CUSTOMER_GET 方法，，然后展开**参数**节点。</span><span class="sxs-lookup"><span data-stu-id="eb922-211">Expand the SD_RFC_CUSTOMER_GET method, and then expand the **Parameters** node.</span></span>  
  
    3.  <span data-ttu-id="eb922-212">展开**NAME1**节点，然后单击第二个**NAME1**节点。</span><span class="sxs-lookup"><span data-stu-id="eb922-212">Expand the **NAME1** node, and click the second **NAME1** node.</span></span> <span data-ttu-id="eb922-213">**NAME1**参数包含客户的名称。</span><span class="sxs-lookup"><span data-stu-id="eb922-213">The **NAME1** parameter contains the name of the customer.</span></span>  
  
    4.  <span data-ttu-id="eb922-214">在属性窗格中，选择**CustomerName**从**FilterDescriptor**列表。</span><span class="sxs-lookup"><span data-stu-id="eb922-214">In the Properties pane, select **CustomerName** from the **FilterDescriptor** list.</span></span>  
  
         <span data-ttu-id="eb922-215">![将筛选器映射到方法参数](../../adapters-and-accelerators/adapter-sap/media/6cc4ef85-503c-4847-95cb-633b902a715d.gif "6cc4ef85-503c-4847-95cb-633b902a715d")</span><span class="sxs-lookup"><span data-stu-id="eb922-215">![Map the filter to a method parameter](../../adapters-and-accelerators/adapter-sap/media/6cc4ef85-503c-4847-95cb-633b902a715d.gif "6cc4ef85-503c-4847-95cb-633b902a715d")</span></span>  
  
##### <a name="to-create-a-finder-method-instance-for-the-sdrfccustomerget-method"></a><span data-ttu-id="eb922-216">若要创建 SD_RFC_CUSTOMER_GET 方法的 Finder 方法实例</span><span class="sxs-lookup"><span data-stu-id="eb922-216">To create a Finder method instance for the SD_RFC_CUSTOMER_GET method</span></span>  
  
1.  <span data-ttu-id="eb922-217">在元数据对象窗格中，展开**客户**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="eb922-217">In the Metadata Objects pane, expand the **Customer** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="eb922-218">展开**SD_RFC_CUSTOMER_GET**节点，右键单击**实例**，然后单击**添加方法实例**以打开创建方法实例窗口。</span><span class="sxs-lookup"><span data-stu-id="eb922-218">Expand the **SD_RFC_CUSTOMER_GET** node, right-click **Instances**, and then click **Add Method Instance** to open the Create Method Instance window.</span></span>  
  
     <span data-ttu-id="eb922-219">![添加方法实例](../../adapters-and-accelerators/adapter-sap/media/f583f8ef-e364-4665-8514-db033219ba0b.gif "f583f8ef-e364-4665-8514-db033219ba0b")</span><span class="sxs-lookup"><span data-stu-id="eb922-219">![Add a method instance](../../adapters-and-accelerators/adapter-sap/media/f583f8ef-e364-4665-8514-db033219ba0b.gif "f583f8ef-e364-4665-8514-db033219ba0b")</span></span>  
  
3.  <span data-ttu-id="eb922-220">在创建方法实例窗口中，单击**Finder**为**方法实例类型**。</span><span class="sxs-lookup"><span data-stu-id="eb922-220">In the Create Method Instance window, click **Finder** for **Method Instance Type**.</span></span> <span data-ttu-id="eb922-221">选择**CUSTOMER_T**为**返回 TypeDescriptor**。</span><span class="sxs-lookup"><span data-stu-id="eb922-221">Select **CUSTOMER_T** for **Return TypeDescriptor**.</span></span>  
  
     <span data-ttu-id="eb922-222">![添加 Finder 方法实例](../../adapters-and-accelerators/adapter-sap/media/e9ae47f2-32f5-4586-8467-94e3713d2a06.gif "e9ae47f2-32f5-4586-8467-94e3713d2a06")</span><span class="sxs-lookup"><span data-stu-id="eb922-222">![Add a Finder method instance](../../adapters-and-accelerators/adapter-sap/media/e9ae47f2-32f5-4586-8467-94e3713d2a06.gif "e9ae47f2-32f5-4586-8467-94e3713d2a06")</span></span>  
  
4.  <span data-ttu-id="eb922-223">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="eb922-223">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="eb922-224">在属性窗格中，键入**GetCustomerByName_Instance**中**名称**框。</span><span class="sxs-lookup"><span data-stu-id="eb922-224">In the Properties pane, type **GetCustomerByName_Instance** in the **Name** box.</span></span>  
  
     <span data-ttu-id="eb922-225">![指定方法实例的名称](../../adapters-and-accelerators/adapter-sap/media/e44e02e8-b9fb-40ca-a55d-8bdc7ace02b5.gif "e44e02e8-b9fb-40ca-a55d-8bdc7ace02b5")</span><span class="sxs-lookup"><span data-stu-id="eb922-225">![Specify a name for the method instance](../../adapters-and-accelerators/adapter-sap/media/e44e02e8-b9fb-40ca-a55d-8bdc7ace02b5.gif "e44e02e8-b9fb-40ca-a55d-8bdc7ace02b5")</span></span>  
  
### <a name="requirement-2-retrieve-details-for-a-specific-customer-from-the-list-of-customers"></a><span data-ttu-id="eb922-226">要求 2： 检索客户列表从特定客户的详细信息</span><span class="sxs-lookup"><span data-stu-id="eb922-226">Requirement 2: Retrieve Details for a Specific Customer from the List of Customers</span></span>  
 <span data-ttu-id="eb922-227">若要创建可以用于搜索基于客户姓名的客户的应用程序定义文件，必须执行以下一组任务。</span><span class="sxs-lookup"><span data-stu-id="eb922-227">To create an application definition file that can be used to search for customers based on customer name, you must perform the following set of tasks.</span></span>  
  
-   <span data-ttu-id="eb922-228">在 SD_RFC_CUSTOMER_GET 方法中，创建一个标识符，并将其映射到存储的客户编号的参数。</span><span class="sxs-lookup"><span data-stu-id="eb922-228">In the SD_RFC_CUSTOMER_GET method, create an identifier, and map it to the parameter that stores the customer number.</span></span>  
  
-   <span data-ttu-id="eb922-229">创建**特定的 Finder** SD_RFC_CUSTOMER_GET 方法的方法实例。</span><span class="sxs-lookup"><span data-stu-id="eb922-229">Create a **Specific Finder** method instance for the SD_RFC_CUSTOMER_GET method.</span></span> <span data-ttu-id="eb922-230">A**特定的 Finder**方法找到了一个基于标识符的特定记录。</span><span class="sxs-lookup"><span data-stu-id="eb922-230">A **Specific Finder** method finds a specific record based on an identifier.</span></span>  
  
##### <a name="to-create-an-identifier-and-map-it-to-the-customer-number-parameter"></a><span data-ttu-id="eb922-231">创建一个标识符，并将其映射到客户数字参数</span><span class="sxs-lookup"><span data-stu-id="eb922-231">To create an identifier, and map it to the customer number parameter</span></span>  
  
1.  <span data-ttu-id="eb922-232">创建的标识符**客户**实体。</span><span class="sxs-lookup"><span data-stu-id="eb922-232">Create an identifier for the **Customer** entity.</span></span>  
  
    1.  <span data-ttu-id="eb922-233">在元数据对象窗格中，展开**客户**节点。</span><span class="sxs-lookup"><span data-stu-id="eb922-233">In the Metadata Objects pane, expand the **Customer** node.</span></span>  
  
    2.  <span data-ttu-id="eb922-234">右键单击**标识符**节点，，然后选择**添加标识符**。</span><span class="sxs-lookup"><span data-stu-id="eb922-234">Right-click the **Identifiers** node, and then select **Add Identifier**.</span></span>  
  
         <span data-ttu-id="eb922-235">![将标识符添加到方法](../../adapters-and-accelerators/adapter-sap/media/3adeeda3-426c-41fe-8d5c-5ca5863fb430.gif "3adeeda3-426c-41fe-8d5c-5ca5863fb430")</span><span class="sxs-lookup"><span data-stu-id="eb922-235">![Add an identifier to a method](../../adapters-and-accelerators/adapter-sap/media/3adeeda3-426c-41fe-8d5c-5ca5863fb430.gif "3adeeda3-426c-41fe-8d5c-5ca5863fb430")</span></span>  
  
    3.  <span data-ttu-id="eb922-236">在属性窗格中，键入**CustomerID**中**名称**框。</span><span class="sxs-lookup"><span data-stu-id="eb922-236">In the Properties pane, type **CustomerID** in the **Name** box.</span></span>  
  
    4.  <span data-ttu-id="eb922-237">选择**System.String**为**类型**框。</span><span class="sxs-lookup"><span data-stu-id="eb922-237">Select **System.String** for the **Type** box.</span></span>  
  
         <span data-ttu-id="eb922-238">![指定的标识符名称](../../adapters-and-accelerators/adapter-sap/media/a2304bca-9a54-4d2b-ba9f-461cfaafccb0.gif "a2304bca-9a54-4d2b-ba9f-461cfaafccb0")</span><span class="sxs-lookup"><span data-stu-id="eb922-238">![Specify a name for the identifier](../../adapters-and-accelerators/adapter-sap/media/a2304bca-9a54-4d2b-ba9f-461cfaafccb0.gif "a2304bca-9a54-4d2b-ba9f-461cfaafccb0")</span></span>  
  
2.  <span data-ttu-id="eb922-239">映射到 SD_RFC_CUSTOMER_GET 方法的密钥参数的标识符。</span><span class="sxs-lookup"><span data-stu-id="eb922-239">Map the identifier to the key parameter for the SD_RFC_CUSTOMER_GET method.</span></span>  
  
    1.  <span data-ttu-id="eb922-240">在元数据对象窗格中，展开**客户**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="eb922-240">In the Metadata Objects pane, expand the **Customer** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="eb922-241">展开 SD_RFC_CUSTOMER_GET 方法，，然后展开**参数**节点。</span><span class="sxs-lookup"><span data-stu-id="eb922-241">Expand the SD_RFC_CUSTOMER_GET method, and then expand the **Parameters** node.</span></span>  
  
    3.  <span data-ttu-id="eb922-242">展开**KUNNR**参数，然后单击第二个**KUNNR**节点。</span><span class="sxs-lookup"><span data-stu-id="eb922-242">Expand the **KUNNR** parameter, and then click the second **KUNNR** node.</span></span>  
  
    4.  <span data-ttu-id="eb922-243">在属性窗格中，选择**CustomerID [Customer]**从**标识符**列表。</span><span class="sxs-lookup"><span data-stu-id="eb922-243">In the Properties pane, select **CustomerID[Customer]** from the **Identifier** list.</span></span>  
  
         <span data-ttu-id="eb922-244">![标识符映射到参数](../../adapters-and-accelerators/adapter-sap/media/04ff6496-34a7-421b-ae9e-f9263895c153.gif "04ff6496-34a7-421b-ae9e-f9263895c153")</span><span class="sxs-lookup"><span data-stu-id="eb922-244">![Map the identifier to a parameter](../../adapters-and-accelerators/adapter-sap/media/04ff6496-34a7-421b-ae9e-f9263895c153.gif "04ff6496-34a7-421b-ae9e-f9263895c153")</span></span>  
  
3.  <span data-ttu-id="eb922-245">设置输入和返回参数之间的关联。</span><span class="sxs-lookup"><span data-stu-id="eb922-245">Set up an association between input and return parameters.</span></span>  
  
    1.  <span data-ttu-id="eb922-246">在元数据对象窗格中，展开**客户**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="eb922-246">In the Metadata Objects pane, expand the **Customer** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="eb922-247">展开 SD_RFC_CUSTOMER_GET 方法，，然后展开**参数**节点。</span><span class="sxs-lookup"><span data-stu-id="eb922-247">Expand the SD_RFC_CUSTOMER_GET method, and then expand the **Parameters** node.</span></span>  
  
    3.  <span data-ttu-id="eb922-248">展开**CUSTOMER_T**节点，然后第二个**CUSTOMER_T**节点，则**项**节点，，然后单击**KUNNR**节点。</span><span class="sxs-lookup"><span data-stu-id="eb922-248">Expand the **CUSTOMER_T** node, then the second **CUSTOMER_T** node, then the **Item** node, and then click the **KUNNR** node.</span></span>  
  
    4.  <span data-ttu-id="eb922-249">在属性窗格中，选择**CustomerID [Customer]**从**标识符**列表。</span><span class="sxs-lookup"><span data-stu-id="eb922-249">In the Properties pane, select **CustomerID[Customer]** from the **Identifier** list.</span></span>  
  
##### <a name="to-create-a-specific-finder-method-instance-for-the-sdrfccustomerget-method"></a><span data-ttu-id="eb922-250">若要创建特定的 Finder 方法实例 SD_RFC_CUSTOMER_GET 方法</span><span class="sxs-lookup"><span data-stu-id="eb922-250">To create a Specific Finder method instance for the SD_RFC_CUSTOMER_GET method</span></span>  
  
1.  <span data-ttu-id="eb922-251">在元数据对象窗格中，展开**客户**节点，然后**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="eb922-251">In the Metadata Objects pane, expand the **Customer** node, and then the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="eb922-252">展开**SD_RFC_CUSTOMER_GET**节点，右键单击**实例**，然后选择**添加方法实例**以打开创建方法实例窗口。</span><span class="sxs-lookup"><span data-stu-id="eb922-252">Expand the **SD_RFC_CUSTOMER_GET** node, right-click **Instances**, and then select **Add Method Instance** to open the Create Method Instance window.</span></span>  
  
     <span data-ttu-id="eb922-253">![添加方法实例](../../adapters-and-accelerators/adapter-sap/media/f583f8ef-e364-4665-8514-db033219ba0b.gif "f583f8ef-e364-4665-8514-db033219ba0b")</span><span class="sxs-lookup"><span data-stu-id="eb922-253">![Add a method instance](../../adapters-and-accelerators/adapter-sap/media/f583f8ef-e364-4665-8514-db033219ba0b.gif "f583f8ef-e364-4665-8514-db033219ba0b")</span></span>  
  
3.  <span data-ttu-id="eb922-254">在创建方法实例窗口中，选择**特定的 Finder**为**方法实例类型**。</span><span class="sxs-lookup"><span data-stu-id="eb922-254">In the Create Method Instance window, select **Specific Finder** for **Method Instance Type**.</span></span> <span data-ttu-id="eb922-255">同样，选择**CUSTOMER_T**为**返回 TypeDescriptor**。</span><span class="sxs-lookup"><span data-stu-id="eb922-255">Similarly, select **CUSTOMER_T** for **Return TypeDescriptor**.</span></span>  
  
     <span data-ttu-id="eb922-256">![添加特定的 Finder 方法实例](../../adapters-and-accelerators/adapter-sap/media/838eb512-b967-46e7-a865-0bf3651b02a1.gif "838eb512-b967-46e7-a865-0bf3651b02a1")</span><span class="sxs-lookup"><span data-stu-id="eb922-256">![Add a Specific Finder Method Instance](../../adapters-and-accelerators/adapter-sap/media/838eb512-b967-46e7-a865-0bf3651b02a1.gif "838eb512-b967-46e7-a865-0bf3651b02a1")</span></span>  
  
4.  <span data-ttu-id="eb922-257">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="eb922-257">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="eb922-258">在属性窗格中，键入**GetCustomerByNumber_Instance**为**名称**框。</span><span class="sxs-lookup"><span data-stu-id="eb922-258">In the Properties pane, type **GetCustomerByNumber_Instance** for the **Name** box.</span></span>  
  
     <span data-ttu-id="eb922-259">![指定方法实例的名称](../../adapters-and-accelerators/adapter-sap/media/970f543c-cd06-4921-86c9-c110abdc7994.gif "970f543c-cd06-4921-86c9-c110abdc7994")</span><span class="sxs-lookup"><span data-stu-id="eb922-259">![Specify a name for the method instance](../../adapters-and-accelerators/adapter-sap/media/970f543c-cd06-4921-86c9-c110abdc7994.gif "970f543c-cd06-4921-86c9-c110abdc7994")</span></span>  
  
### <a name="requirement-3-retrieve-sales-order-details-for-a-specific-customer-from-the-list-of-customers"></a><span data-ttu-id="eb922-260">要求 3： 检索客户列表从特定客户的销售订单详细信息</span><span class="sxs-lookup"><span data-stu-id="eb922-260">Requirement 3: Retrieve Sales Order Details for a Specific Customer from the List of Customers</span></span>  
 <span data-ttu-id="eb922-261">若要创建应用程序定义文件可以用于检索特定客户的销售订单详细信息，必须执行以下一组任务。</span><span class="sxs-lookup"><span data-stu-id="eb922-261">To create an application definition file that can be used to retrieve sales order details for a specific customer, you must perform the following set of tasks.</span></span>  
  
-   <span data-ttu-id="eb922-262">设置之间的关联**客户**和**SalesOrder**实体。</span><span class="sxs-lookup"><span data-stu-id="eb922-262">Set up an association between the **Customer** and **SalesOrder** entities.</span></span>  
  
-   <span data-ttu-id="eb922-263">创建**关联**BAPI_SALESORDER_GETLIST 方法的方法。</span><span class="sxs-lookup"><span data-stu-id="eb922-263">Create an **Association** method for the BAPI_SALESORDER_GETLIST method.</span></span>  
  
##### <a name="to-create-an-association-between-the-customer-and-salesorder-entities"></a><span data-ttu-id="eb922-264">若要创建客户和 SalesOrder 实体之间的关联</span><span class="sxs-lookup"><span data-stu-id="eb922-264">To create an association between the Customer and SalesOrder entities</span></span>  
  
1.  <span data-ttu-id="eb922-265">在元数据对象窗格中，展开**SalesOrder**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="eb922-265">In the Metadata Objects pane, expand the **SalesOrder** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="eb922-266">展开 BAPI_SALESORDER_GETLIST 方法，，然后展开**参数**节点。</span><span class="sxs-lookup"><span data-stu-id="eb922-266">Expand the BAPI_SALESORDER_GETLIST method, and then expand the **Parameters** node.</span></span>  
  
3.  <span data-ttu-id="eb922-267">展开**CUSTOMER_NUMBER**节点，然后单击第二个**CUSTOMER_NUMBER**节点。</span><span class="sxs-lookup"><span data-stu-id="eb922-267">Expand the **CUSTOMER_NUMBER** node, and then click the second **CUSTOMER_NUMBER** node.</span></span>  
  
4.  <span data-ttu-id="eb922-268">在属性窗格中，选择**CustomerID [Customer]**从**标识符**列表。</span><span class="sxs-lookup"><span data-stu-id="eb922-268">In the Properties pane, select **CustomerID[Customer]** from the **Identifier** list.</span></span>  
  
     <span data-ttu-id="eb922-269">![创建两个实体之间的关联](../../adapters-and-accelerators/adapter-sap/media/ae7e1e7a-a12b-4905-b002-2a04c7050848.gif "ae7e1e7a-a12b-4905-b002-2a04c7050848")</span><span class="sxs-lookup"><span data-stu-id="eb922-269">![Create association between the two entities](../../adapters-and-accelerators/adapter-sap/media/ae7e1e7a-a12b-4905-b002-2a04c7050848.gif "ae7e1e7a-a12b-4905-b002-2a04c7050848")</span></span>  
  
##### <a name="to-create-an-association-method-instance-for-the-bapisalesordergetlist-method"></a><span data-ttu-id="eb922-270">若要创建关联方法实例 BAPI_SALESORDER_GETLIST 方法</span><span class="sxs-lookup"><span data-stu-id="eb922-270">To create an Association method instance for the BAPI_SALESORDER_GETLIST method</span></span>  
  
1.  <span data-ttu-id="eb922-271">在元数据对象窗格中，展开**SalesOrder**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="eb922-271">In the Metadata Objects pane, expand the **SalesOrder** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="eb922-272">展开**BAPI_SALESORDER_GETLIST**节点，右键单击**实例**，然后选择**添加方法实例**以打开创建方法实例窗口。</span><span class="sxs-lookup"><span data-stu-id="eb922-272">Expand the **BAPI_SALESORDER_GETLIST** node, right-click **Instances**, and then select **Add Method Instance** to open the Create Method Instance window.</span></span>  
  
     <span data-ttu-id="eb922-273">![将一个关联方法实例添加](../../adapters-and-accelerators/adapter-sap/media/c62a0d01-d4f3-470e-92f1-8a5cf666f8da.gif "c62a0d01-d4f3-470e-92f1-8a5cf666f8da")</span><span class="sxs-lookup"><span data-stu-id="eb922-273">![Add an Association Method Instance](../../adapters-and-accelerators/adapter-sap/media/c62a0d01-d4f3-470e-92f1-8a5cf666f8da.gif "c62a0d01-d4f3-470e-92f1-8a5cf666f8da")</span></span>  
  
3.  <span data-ttu-id="eb922-274">在创建方法实例窗口中，选择**关联**为**方法实例类型**。</span><span class="sxs-lookup"><span data-stu-id="eb922-274">In the Create Method Instance window, select **Association** for **Method Instance Type**.</span></span>  
  
4.  <span data-ttu-id="eb922-275">在**源实体**列表中，选择**客户**。</span><span class="sxs-lookup"><span data-stu-id="eb922-275">In the **Source Entities** list, select **Customer**.</span></span>  
  
5.  <span data-ttu-id="eb922-276">在**返回 TypeDescriptor**列表中，选择**SALES_ORDERS**...</span><span class="sxs-lookup"><span data-stu-id="eb922-276">In the **Return TypeDescriptor** list, select **SALES_ORDERS**..</span></span>  
  
     <span data-ttu-id="eb922-277">![创建关联方法实例](../../adapters-and-accelerators/adapter-sap/media/15975b78-8932-41ce-8c10-41891fc1fb22.gif "15975b78-8932-41ce-8c10-41891fc1fb22")</span><span class="sxs-lookup"><span data-stu-id="eb922-277">![Create an Association Method Instance](../../adapters-and-accelerators/adapter-sap/media/15975b78-8932-41ce-8c10-41891fc1fb22.gif "15975b78-8932-41ce-8c10-41891fc1fb22")</span></span>  
  
6.  <span data-ttu-id="eb922-278">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="eb922-278">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="eb922-279">在属性窗格中，键入**SalesOrderForCustomer_Instance**为**名称**框。</span><span class="sxs-lookup"><span data-stu-id="eb922-279">In the Properties pane, type **SalesOrderForCustomer_Instance** for the **Name** box.</span></span>  
  
     <span data-ttu-id="eb922-280">![指定关联方法的名称](../../adapters-and-accelerators/adapter-sap/media/0f1d13e4-e5a3-49ec-92a7-6329c6db1eb0.gif "0f1d13e4-e5a3-49ec-92a7-6329c6db1eb0")</span><span class="sxs-lookup"><span data-stu-id="eb922-280">![Specify a name for the Association Method](../../adapters-and-accelerators/adapter-sap/media/0f1d13e4-e5a3-49ec-92a7-6329c6db1eb0.gif "0f1d13e4-e5a3-49ec-92a7-6329c6db1eb0")</span></span>  
  
### <a name="remove-parameters-of-systemnullable-type"></a><span data-ttu-id="eb922-281">删除 System.Nullable 类型参数</span><span class="sxs-lookup"><span data-stu-id="eb922-281">Remove Parameters of System.Nullable Type</span></span>  
 <span data-ttu-id="eb922-282">创建时**关联**方法实例作为 SALES_ORDERS 对于 BAPI_SALESORDER_GETLIST 方法中，选择的返回类型。</span><span class="sxs-lookup"><span data-stu-id="eb922-282">While creating the **Association** method instance for the BAPI_SALESORDER_GETLIST method, you selected the return type as SALES_ORDERS.</span></span> <span data-ttu-id="eb922-283">如果您展开 SALES_ORDER 参数，你会注意到某些参数的 System.Nullable 类型。</span><span class="sxs-lookup"><span data-stu-id="eb922-283">If you expand the SALES_ORDER parameter, you will notice some parameters are of System.Nullable type.</span></span> <span data-ttu-id="eb922-284">你可以看到通过选择参数在业务数据目录定义编辑器中，并查看的值类型的参数**TypeName**属性。</span><span class="sxs-lookup"><span data-stu-id="eb922-284">You can see the parameter type by selecting the parameter in the Business Data Catalog Definition Editor, and looking at the value for the **TypeName** property.</span></span>  
  
 <span data-ttu-id="eb922-285">对于此类参数，业务数据目录定义编辑器创建另一个参数具有相同名称但"指定"后缀。</span><span class="sxs-lookup"><span data-stu-id="eb922-285">For such parameters, the Business Data Catalog Definition Editor creates another parameter with the same name but with a “Specified” suffix.</span></span> <span data-ttu-id="eb922-286">例如，查看参数*ITM_NUMBER*和*ITM_NUMBERSpecified*。</span><span class="sxs-lookup"><span data-stu-id="eb922-286">For example, look at parameters *ITM_NUMBER* and *ITM_NUMBERSpecified*.</span></span> <span data-ttu-id="eb922-287">Microsoft Office SharePoint Server 不支持 System.Nullable 参数。</span><span class="sxs-lookup"><span data-stu-id="eb922-287">Microsoft Office SharePoint Server does not support System.Nullable parameters.</span></span> <span data-ttu-id="eb922-288">因此，当您尝试包含 System.Nullable 参数类型的记录，它会引发异常。</span><span class="sxs-lookup"><span data-stu-id="eb922-288">So, when you try records that contain the System.Nullable parameter type, it throws an exception.</span></span> <span data-ttu-id="eb922-289">因此，你必须删除这两个参数 （带以及不包含"指定"后缀和具有相同的名称） 从业务数据目录定义编辑器</span><span class="sxs-lookup"><span data-stu-id="eb922-289">Therefore, you must remove both the parameters (with and without the “Specified” suffix and having the same name) from the Business Data Catalog Definition Editor</span></span>  
  
##### <a name="to-remove-the-parameters-of-systemnullable-type"></a><span data-ttu-id="eb922-290">若要删除 System.Nullable 类型的参数</span><span class="sxs-lookup"><span data-stu-id="eb922-290">To remove the parameters of System.Nullable type</span></span>  
  
1.  <span data-ttu-id="eb922-291">在元数据对象窗格中，展开**SalesOrder**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="eb922-291">In the Metadata Objects pane, expand the **SalesOrder** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="eb922-292">展开**BAPI_SALESORDER_GETLIST**节点，然后展开**参数**节点。</span><span class="sxs-lookup"><span data-stu-id="eb922-292">Expand the **BAPI_SALESORDER_GETLIST** node, and then expand the **Parameters** node.</span></span>  
  
3.  <span data-ttu-id="eb922-293">展开**SALES_ORDERS**，展开第二个**SALES_ORDERS**，然后展开**项**。</span><span class="sxs-lookup"><span data-stu-id="eb922-293">Expand **SALES_ORDERS**, expand the second **SALES_ORDERS**, and then expand **Item**.</span></span>  
  
4.  <span data-ttu-id="eb922-294">右击包含在名称的"指定"后缀的参数，然后选择**删除**。</span><span class="sxs-lookup"><span data-stu-id="eb922-294">Right-click the parameter that contains the "Specified" suffix in the name, and then select **Delete**.</span></span>  
  
5.  <span data-ttu-id="eb922-295">右键单击具有相同的名称作为参数删除，而不使用后缀，该参数，然后选择**删除**。</span><span class="sxs-lookup"><span data-stu-id="eb922-295">Right-click the parameter that has the same name as the parameter you deleted, without the suffix, and then select **Delete**.</span></span> <span data-ttu-id="eb922-296">通常情况下，此参数是右之前具有"指定"后缀的参数。</span><span class="sxs-lookup"><span data-stu-id="eb922-296">Typically, this parameter is right before the parameter that has the "Specified" suffix.</span></span>  
  
### <a name="set-default-parameters"></a><span data-ttu-id="eb922-297">设置默认参数</span><span class="sxs-lookup"><span data-stu-id="eb922-297">Set Default Parameters</span></span>  
 <span data-ttu-id="eb922-298">BAPI_SALESORDER_GETLIST 采用两个参数。</span><span class="sxs-lookup"><span data-stu-id="eb922-298">The BAPI_SALESORDER_GETLIST takes two parameters.</span></span> <span data-ttu-id="eb922-299">其中一个参数，TRANSACTION_GROUP，是的默认参数。</span><span class="sxs-lookup"><span data-stu-id="eb922-299">One of these parameters, TRANSACTION_GROUP, is the default parameter.</span></span> <span data-ttu-id="eb922-300">因此，你必须设置此参数的默认值。</span><span class="sxs-lookup"><span data-stu-id="eb922-300">So, you must set the default value for this parameter.</span></span>  
  
##### <a name="to-set-the-default-value-for-transactiongroup"></a><span data-ttu-id="eb922-301">若要为 TRANSACTION_GROUP 设置默认值</span><span class="sxs-lookup"><span data-stu-id="eb922-301">To set the default value for TRANSACTION_GROUP</span></span>  
  
1.  <span data-ttu-id="eb922-302">在元数据对象窗格中，展开**SalesOrder**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="eb922-302">In the Metadata Objects pane, expand the **SalesOrder** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="eb922-303">展开**BAPI_SALESORDER_GETLIST**节点，然后展开**实例**节点。</span><span class="sxs-lookup"><span data-stu-id="eb922-303">Expand the **BAPI_SALESORDER_GETLIST** node, and then expand the **Instances** node.</span></span>  
  
3.  <span data-ttu-id="eb922-304">选择**SalesOrderForCustomer_Instance**方法实例，并在属性窗格中，单击省略号按钮 （…） 针对**DefaultValues**框。</span><span class="sxs-lookup"><span data-stu-id="eb922-304">Select the **SalesOrderForCustomer_Instance** method instance, and in the Properties pane, click the ellipsis button (…) against the **DefaultValues** box.</span></span>  
  
4.  <span data-ttu-id="eb922-305">在编辑窗口中，展开**TRANSACTION_GROUP**节点，并为**TRANSACTION_GROUP**框中，指定默认值 0。</span><span class="sxs-lookup"><span data-stu-id="eb922-305">In the Edit window, expand **TRANSACTION_GROUP** node, and for the **TRANSACTION_GROUP** box, specify the default value 0.</span></span>  
  
     <span data-ttu-id="eb922-306">![指定方法实例的默认值](../../adapters-and-accelerators/adapter-sap/media/86e0a42d-61c0-4d5d-ba3f-55b328f79576.gif "86e0a42d-61c0-4d5d-ba3f-55b328f79576")</span><span class="sxs-lookup"><span data-stu-id="eb922-306">![Specify a default value for the method instance](../../adapters-and-accelerators/adapter-sap/media/86e0a42d-61c0-4d5d-ba3f-55b328f79576.gif "86e0a42d-61c0-4d5d-ba3f-55b328f79576")</span></span>  
  
5.  <span data-ttu-id="eb922-307">单击 **“关闭”**。</span><span class="sxs-lookup"><span data-stu-id="eb922-307">Click **Close**.</span></span>  
  
### <a name="export-the-application-definition-to-a-file"></a><span data-ttu-id="eb922-308">将应用程序定义导出到文件</span><span class="sxs-lookup"><span data-stu-id="eb922-308">Export the Application Definition to a File</span></span>  
 <span data-ttu-id="eb922-309">现在已创建包含 SAP 系统实例元数据的应用程序定义。</span><span class="sxs-lookup"><span data-stu-id="eb922-309">You have now created an application definition that contains the SAP system instance metadata.</span></span> <span data-ttu-id="eb922-310">必须将此定义导出到一个 XML 文件，其中可以导入到 Microsoft Office SharePoint Server。</span><span class="sxs-lookup"><span data-stu-id="eb922-310">You must export this definition to an XML file, which can be imported into Microsoft Office SharePoint Server.</span></span>  
  
##### <a name="to-export-the-application-definition-to-a-file"></a><span data-ttu-id="eb922-311">若要将应用程序定义导出到文件</span><span class="sxs-lookup"><span data-stu-id="eb922-311">To export the application definition to a file</span></span>  
  
1.  <span data-ttu-id="eb922-312">在元数据对象窗格中，右键单击**Customer_Order**节点，，然后单击**导出**。</span><span class="sxs-lookup"><span data-stu-id="eb922-312">In the Metadata Objects pane, right-click the **Customer_Order** node, and then click **Export**.</span></span>  
  
2.  <span data-ttu-id="eb922-313">将文件保存为 Customer_Order.xml。</span><span class="sxs-lookup"><span data-stu-id="eb922-313">Save the file as Customer_Order.xml.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="eb922-314">后续步骤</span><span class="sxs-lookup"><span data-stu-id="eb922-314">Next Steps</span></span>  
 <span data-ttu-id="eb922-315">你现在必须创建一个 SharePoint 应用程序，来从某个 SAP 系统中检索数据。</span><span class="sxs-lookup"><span data-stu-id="eb922-315">You must now create a SharePoint application to retrieve data from an SAP system.</span></span> <span data-ttu-id="eb922-316">请参阅[步骤 3： 创建一个 SharePoint 应用程序检索数据从 SAP](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md)有关的说明。</span><span class="sxs-lookup"><span data-stu-id="eb922-316">See [Step 3: Create a SharePoint Application to Retrieve Data from SAP](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md) for instructions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb922-317">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb922-317">See Also</span></span>  
 [<span data-ttu-id="eb922-318">教程 1： 从 SharePoint 站点上的 SAP 系统提供数据</span><span class="sxs-lookup"><span data-stu-id="eb922-318">Tutorial 1: Presenting Data from an SAP System on a SharePoint Site</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)