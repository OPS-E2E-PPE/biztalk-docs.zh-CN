---
title: 步骤 2： 为 SAP 项目创建应用程序定义文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- application definition file, creating a
- Business Data Catalog Definition Editor
- Business Data Catalog
ms.assetid: d254b00e-dbeb-4167-ad57-6f0aa2e7a563
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92e97a54a6818456efd2f4ac55ca7e2fc5bc7c35
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970382"
---
# <a name="step-2-create-an-application-definition-file-for-the-sap-artifacts"></a><span data-ttu-id="bdb27-102">步骤 2： 为 SAP 项目创建应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="bdb27-102">Step 2: Create an Application Definition File for the SAP Artifacts</span></span>
<span data-ttu-id="bdb27-103">![步骤 2，共 4 步](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span><span class="sxs-lookup"><span data-stu-id="bdb27-103">![Step 2 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span></span>  
  
 <span data-ttu-id="bdb27-104">**完成时间：** 15 分钟</span><span class="sxs-lookup"><span data-stu-id="bdb27-104">**Time to complete:** 15 minutes</span></span>  
  
 <span data-ttu-id="bdb27-105">**目标：** Microsoft SharePoint Server 中的业务数据目录功能公开，并将业务 (LOB) 应用程序中的数据合并到门户。</span><span class="sxs-lookup"><span data-stu-id="bdb27-105">**Objective:** The Business Data Catalog feature in Microsoft SharePoint Server exposes and incorporates data from line-of-business (LOB) applications into portals.</span></span> <span data-ttu-id="bdb27-106">若要将此数据合并到您的门户网站，必须生成可以使用 Microsoft Office SharePoint Server 应用程序定义文件。</span><span class="sxs-lookup"><span data-stu-id="bdb27-106">To incorporate this data into your portal site, you must build an application definition file that Microsoft Office SharePoint Server can consume.</span></span>  
  
 <span data-ttu-id="bdb27-107">Microsoft Office SharePoint Server 2007 SDK 提供的 Business Data Catalog Definition Editor 工具，可为业务数据目录中创建应用程序定义文件。</span><span class="sxs-lookup"><span data-stu-id="bdb27-107">The Business Data Catalog Definition Editor tool, available with Microsoft Office SharePoint Server 2007 SDK,enables you to create an application definition file for the Business Data Catalog.</span></span> <span data-ttu-id="bdb27-108">此工具自动生成 XML 文件，以便定义文件中，因此不需要手动创建该文件在 XML 编辑器。</span><span class="sxs-lookup"><span data-stu-id="bdb27-108">This tool automatically generates an XML file for the definition file, so you do not need to manually create the file in an XML editor.</span></span>  
  
 <span data-ttu-id="bdb27-109">要创建的 Microsoft Office SharePoint Server 应用程序的目的是：</span><span class="sxs-lookup"><span data-stu-id="bdb27-109">The purpose of the Microsoft Office SharePoint Server application that you are creating is to:</span></span>  
  
- <span data-ttu-id="bdb27-110">基于客户名称上的 SAP 系统中搜索客户。</span><span class="sxs-lookup"><span data-stu-id="bdb27-110">Search for a customer in the SAP system based on a customer name.</span></span>  
  
- <span data-ttu-id="bdb27-111">从提取客户的列表中选择客户并检索客户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bdb27-111">Select a customer from the list of fetched customers and retrieve the details for the customer.</span></span>  
  
- <span data-ttu-id="bdb27-112">从提取客户的列表中选择客户并检索客户的销售订单。</span><span class="sxs-lookup"><span data-stu-id="bdb27-112">Select a customer from the list of fetched customers and retrieve the sales orders for the customer.</span></span>  
  
  <span data-ttu-id="bdb27-113">对于每个这些要求，必须完成一组 Business Data Catalog Definition Editor tool 中的任务。</span><span class="sxs-lookup"><span data-stu-id="bdb27-113">For each of these requirements, you must complete a set of tasks in the Business Data Catalog Definition Editor tool.</span></span> <span data-ttu-id="bdb27-114">本主题提供有关如何执行这些任务的说明。</span><span class="sxs-lookup"><span data-stu-id="bdb27-114">This topic provides instructions on how to perform these tasks.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bdb27-115">必要條件</span><span class="sxs-lookup"><span data-stu-id="bdb27-115">Prerequisites</span></span>  
  
-   <span data-ttu-id="bdb27-116">必须确保您具有 Microsoft Office SharePoint Server 2007 SDK 的一部分安装 Business Data Catalog Definition Editor。</span><span class="sxs-lookup"><span data-stu-id="bdb27-116">Be sure that you have the Business Data Catalog Definition Editor installed as part of the Microsoft Office SharePoint Server 2007 SDK.</span></span> <span data-ttu-id="bdb27-117">你可以下载从 SDK [ http://go.microsoft.com/fwlink/?LinkId=104130 ](http://go.microsoft.com/fwlink/?LinkId=104130)。</span><span class="sxs-lookup"><span data-stu-id="bdb27-117">You can download the SDK from [http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130).</span></span>  
  
-   <span data-ttu-id="bdb27-118">发布 WCF 服务，如中所述[步骤 1： 将 SAP 项目作为 WCF 服务发布](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md)。</span><span class="sxs-lookup"><span data-stu-id="bdb27-118">Publish the WCF service as described in [Step 1: Publish the SAP Artifacts as a WCF Service](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md).</span></span>  
  
## <a name="creating-an-application-definition-file"></a><span data-ttu-id="bdb27-119">创建应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="bdb27-119">Creating an Application Definition File</span></span>  
 <span data-ttu-id="bdb27-120">本主题提供创建 WCF 服务应用程序定义文件的分步说明。</span><span class="sxs-lookup"><span data-stu-id="bdb27-120">This topic provides step-by-step instructions to create an application definition file for the WCF service.</span></span>  
  
### <a name="connect-to-the-wcf-lob-service-and-create-entities"></a><span data-ttu-id="bdb27-121">连接到 WCF LOB 服务，并创建实体</span><span class="sxs-lookup"><span data-stu-id="bdb27-121">Connect to the WCF LOB Service, and Create Entities</span></span>  
 <span data-ttu-id="bdb27-122">您必须连接到 WCF 服务以提取 Web 服务描述语言 (WSDL) 服务。</span><span class="sxs-lookup"><span data-stu-id="bdb27-122">You must connect to the WCF service to extract the Web Services Description Language (WSDL) for the service.</span></span> <span data-ttu-id="bdb27-123">从 WSDL，Business Data Catalog Definition Editor 提取方法。</span><span class="sxs-lookup"><span data-stu-id="bdb27-123">From the WSDL, the Business Data Catalog Definition Editor extracts the methods.</span></span> <span data-ttu-id="bdb27-124">这些方法可以用于创建实体。</span><span class="sxs-lookup"><span data-stu-id="bdb27-124">These methods can be used to create entities.</span></span> <span data-ttu-id="bdb27-125">对于此示例中，两个实体创建，分别对应于客户和销售订单。</span><span class="sxs-lookup"><span data-stu-id="bdb27-125">For this example, two entities are created, one each for the customer and sales orders.</span></span>  
  
##### <a name="to-connect-to-the-wcf-service-and-create-entities"></a><span data-ttu-id="bdb27-126">若要连接到 WCF 服务并创建实体</span><span class="sxs-lookup"><span data-stu-id="bdb27-126">To connect to the WCF service and create entities</span></span>  
  
1. <span data-ttu-id="bdb27-127">启动 Business Data Catalog Definition Editor。</span><span class="sxs-lookup"><span data-stu-id="bdb27-127">Start the Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="bdb27-128">上**启动**菜单上，单击**Microsoft Business Data Catalog Definition Editor**。</span><span class="sxs-lookup"><span data-stu-id="bdb27-128">On the **Start** menu, click **Microsoft Business Data Catalog Definition Editor**.</span></span>  
  
2. <span data-ttu-id="bdb27-129">在工具栏上，单击**添加 LOB 系统**。</span><span class="sxs-lookup"><span data-stu-id="bdb27-129">On the toolbar, click **Add LOB System**.</span></span>  
  
3. <span data-ttu-id="bdb27-130">在添加 LOB 系统窗口中，单击**连接到 web 服务**。</span><span class="sxs-lookup"><span data-stu-id="bdb27-130">In the Add LOB System window, click **Connect to Webservice**.</span></span>  
  
4. <span data-ttu-id="bdb27-131">在中**URL**框中，键入 WCF 服务的 URL。</span><span class="sxs-lookup"><span data-stu-id="bdb27-131">In the **URL** box, type the URL for the WCF service.</span></span> <span data-ttu-id="bdb27-132">该 URL 必须采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="bdb27-132">The URL must be in the following format:</span></span>  
  
   ```  
   https://<computer_name>/Customer_Order/Rfc.svc?wsdl  
   ```  
  
    <span data-ttu-id="bdb27-133">其中 Rfc.svc 是 Rfc 协定创建的文件。</span><span class="sxs-lookup"><span data-stu-id="bdb27-133">where Rfc.svc is the file created for the Rfc contract.</span></span>  
  
    <span data-ttu-id="bdb27-134">当测试是否成功，如本主题中所述发布 WCF 服务时，该 URL 才可用[步骤 1： 将 SAP 项目作为 WCF 服务发布](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md)。</span><span class="sxs-lookup"><span data-stu-id="bdb27-134">The URL is available when you test whether the WCF service is published successfully, as described in the topic [Step 1: Publish the SAP Artifacts as a WCF Service](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md).</span></span>  
  
5. <span data-ttu-id="bdb27-135">单击 **“连接”**。</span><span class="sxs-lookup"><span data-stu-id="bdb27-135">Click **Connect**.</span></span>  
  
6. <span data-ttu-id="bdb27-136">若要查看你在 WCF 适配器服务开发向导中选择的操作，请单击**添加 Web 方法**选项卡。你将看到以下方法：</span><span class="sxs-lookup"><span data-stu-id="bdb27-136">To see the operations you selected in the WCF Adapter Service Development Wizard, click the **Add Web Method** tab. You will see the following methods:</span></span>  
  
   - <span data-ttu-id="bdb27-137">SD_RFC_CUSTOMER_GET</span><span class="sxs-lookup"><span data-stu-id="bdb27-137">SD_RFC_CUSTOMER_GET</span></span>  
  
   - <span data-ttu-id="bdb27-138">BAPI_SALESORDER_GETLIST</span><span class="sxs-lookup"><span data-stu-id="bdb27-138">BAPI_SALESORDER_GETLIST</span></span>  
  
      <span data-ttu-id="bdb27-139">![将 web 方法添加到 BDC 应用程序](../../adapters-and-accelerators/adapter-sap/media/ea411db2-5cf4-4486-83da-57d3fc332448.gif "ea411db2-5cf4-4486-83da-57d3fc332448")</span><span class="sxs-lookup"><span data-stu-id="bdb27-139">![Add web methods to the BDC application](../../adapters-and-accelerators/adapter-sap/media/ea411db2-5cf4-4486-83da-57d3fc332448.gif "ea411db2-5cf4-4486-83da-57d3fc332448")</span></span>  
  
     <span data-ttu-id="bdb27-140">将方法拖到设计图面。</span><span class="sxs-lookup"><span data-stu-id="bdb27-140">Drag the methods to the Design Surface.</span></span> <span data-ttu-id="bdb27-141">请确保将这两种操作拖动到不同的实体。</span><span class="sxs-lookup"><span data-stu-id="bdb27-141">Make sure you drag both operations to the different entities.</span></span>  
  
     <span data-ttu-id="bdb27-142">![为 web 方法创建实体](../../adapters-and-accelerators/adapter-sap/media/ce4e9bc3-1eae-43ae-8375-e44cf19aaffc.gif "ce4e9bc3-1eae-43ae-8375-e44cf19aaffc")</span><span class="sxs-lookup"><span data-stu-id="bdb27-142">![Create entities for the web methods](../../adapters-and-accelerators/adapter-sap/media/ce4e9bc3-1eae-43ae-8375-e44cf19aaffc.gif "ce4e9bc3-1eae-43ae-8375-e44cf19aaffc")</span></span>  
  
7. <span data-ttu-id="bdb27-143">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="bdb27-143">Click **OK**.</span></span>  
  
8. <span data-ttu-id="bdb27-144">在中**输入 LOB 系统的名称**对话框中键入名称**LOB 系统名称**框。</span><span class="sxs-lookup"><span data-stu-id="bdb27-144">In the **Enter the name for the LOB System** dialog box, type a name in the **LOB System Name** box.</span></span> <span data-ttu-id="bdb27-145">此示例中，称之为**Customer_Order**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="bdb27-145">For this example, call it **Customer_Order**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="bdb27-146">在 Business Data Catalog Definition Editor，两个实体被列为**Entity0**并**Entity1**。</span><span class="sxs-lookup"><span data-stu-id="bdb27-146">In the Business Data Catalog Definition Editor, the two entities are listed as **Entity0** and **Entity1**.</span></span> <span data-ttu-id="bdb27-147">为这些实体指定友好名称。</span><span class="sxs-lookup"><span data-stu-id="bdb27-147">Give these entities friendly names.</span></span> <span data-ttu-id="bdb27-148">为到 SD_RFC_CUSTOMER_GET 重命名实体**客户**，并为到 BAPI_SALESORDER_GETLIST 重命名实体**SalesOrder**。</span><span class="sxs-lookup"><span data-stu-id="bdb27-148">Rename the entity for SD_RFC_CUSTOMER_GET to **Customer**, and rename the entity for BAPI_SALESORDER_GETLIST to **SalesOrder**.</span></span> <span data-ttu-id="bdb27-149">执行以下步骤以重命名实体：</span><span class="sxs-lookup"><span data-stu-id="bdb27-149">Perform the following steps to rename the entities:</span></span>  
  
    1.  <span data-ttu-id="bdb27-150">展开**Customer_Order**节点，然后展开**实体**节点。</span><span class="sxs-lookup"><span data-stu-id="bdb27-150">Expand the **Customer_Order** node, and then expand the **Entities** node.</span></span>  
  
    2.  <span data-ttu-id="bdb27-151">选择**Entity0**节点。</span><span class="sxs-lookup"><span data-stu-id="bdb27-151">Select the **Entity0** node.</span></span>  
  
    3.  <span data-ttu-id="bdb27-152">在属性窗格中，键入**客户**中**名称**框。</span><span class="sxs-lookup"><span data-stu-id="bdb27-152">In the Properties pane, type **Customer** in the **Name** box.</span></span>  
  
         <span data-ttu-id="bdb27-153">![重命名实体](../../adapters-and-accelerators/adapter-sap/media/4e83a036-3ab7-4f74-9f67-420574219d3d.gif "4e83a036-3ab7-4f74-9f67-420574219d3d")</span><span class="sxs-lookup"><span data-stu-id="bdb27-153">![Rename the entity](../../adapters-and-accelerators/adapter-sap/media/4e83a036-3ab7-4f74-9f67-420574219d3d.gif "4e83a036-3ab7-4f74-9f67-420574219d3d")</span></span>  
  
    4.  <span data-ttu-id="bdb27-154">选择**Entity1**节点。</span><span class="sxs-lookup"><span data-stu-id="bdb27-154">Select the **Entity1** node.</span></span>  
  
    5.  <span data-ttu-id="bdb27-155">在属性窗格中，键入**SalesOrder**中**名称**框。</span><span class="sxs-lookup"><span data-stu-id="bdb27-155">In the Properties pane, type **SalesOrder** in the **Name** box.</span></span>  
  
### <a name="specify-user-name-and-password-headers-for-the-methods"></a><span data-ttu-id="bdb27-156">为方法中指定用户名和密码标头</span><span class="sxs-lookup"><span data-stu-id="bdb27-156">Specify User Name and Password Headers for the Methods</span></span>  
 <span data-ttu-id="bdb27-157">在 SAP 系统中创建所选 Rfc 的 WCF 服务，指定用户名称和密码标头为终结点行为配置的一部分。</span><span class="sxs-lookup"><span data-stu-id="bdb27-157">When creating a WCF service for the selected RFCs in the SAP system, you specified user name and password headers as part of the endpoint behavior configuration.</span></span> <span data-ttu-id="bdb27-158">请参阅[步骤 1： 将 SAP 项目作为 WCF 服务发布](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md)。</span><span class="sxs-lookup"><span data-stu-id="bdb27-158">See [Step 1: Publish the SAP Artifacts as a WCF Service](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md).</span></span> <span data-ttu-id="bdb27-159">必须指定方法属性相同的值。</span><span class="sxs-lookup"><span data-stu-id="bdb27-159">You must specify the same values for the method properties.</span></span>  
  
##### <a name="to-specify-user-name-and-password-headers"></a><span data-ttu-id="bdb27-160">若要指定用户名称和密码标头</span><span class="sxs-lookup"><span data-stu-id="bdb27-160">To specify user name and password headers</span></span>  
  
1.  <span data-ttu-id="bdb27-161">添加 SD_RFC_CUSTOMER_GET 方法的用户名称和密码标头。</span><span class="sxs-lookup"><span data-stu-id="bdb27-161">Add the user name and password headers for the SD_RFC_CUSTOMER_GET method.</span></span>  
  
    1.  <span data-ttu-id="bdb27-162">在元数据对象窗格中，展开**客户**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="bdb27-162">In the Metadata Objects pane, expand the **Customer** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="bdb27-163">单击 SD_RFC_CUSTOMER_GET 节点，然后在属性窗格中单击省略号 （...） 按钮根据**属性**框。</span><span class="sxs-lookup"><span data-stu-id="bdb27-163">Click the SD_RFC_CUSTOMER_GET node, and in the Properties pane click the ellipsis (…) button against the **Properties** box.</span></span>  
  
    3.  <span data-ttu-id="bdb27-164">在 PropertyView 集合编辑器窗口中，单击**外**，然后在属性窗格中，键入**HttpHeaderUserName**有关**名称**框。</span><span class="sxs-lookup"><span data-stu-id="bdb27-164">In the PropertyView Collection Editor window, click **Add**, and in the Property pane, type **HttpHeaderUserName** for the **Name** box.</span></span> <span data-ttu-id="bdb27-165">同样，键入**MyUserHeader**有关**PropertyValue**框。</span><span class="sxs-lookup"><span data-stu-id="bdb27-165">Similarly, type **MyUserHeader** for the **PropertyValue** box.</span></span> <span data-ttu-id="bdb27-166">选择**System.String**有关**类型**框。</span><span class="sxs-lookup"><span data-stu-id="bdb27-166">Select **System.String** for the **Type** box.</span></span>  
  
         <span data-ttu-id="bdb27-167">![将属性添加](../../adapters-and-accelerators/adapter-sap/media/9eef32ac-8a93-45dc-8d07-12b7dbf961ba.gif "9eef32ac-8a93-45dc-8d07-12b7dbf961ba")</span><span class="sxs-lookup"><span data-stu-id="bdb27-167">![Add a property](../../adapters-and-accelerators/adapter-sap/media/9eef32ac-8a93-45dc-8d07-12b7dbf961ba.gif "9eef32ac-8a93-45dc-8d07-12b7dbf961ba")</span></span>  
  
    4.  <span data-ttu-id="bdb27-168">在 PropertyView 集合编辑器窗口中，单击**外**，然后在属性窗格中，键入**HttpHeaderPassword**有关**名称**框。</span><span class="sxs-lookup"><span data-stu-id="bdb27-168">In the PropertyView Collection Editor window, click **Add**, and in the Property pane, type **HttpHeaderPassword** for the **Name** box.</span></span> <span data-ttu-id="bdb27-169">同样，键入**MyPassHeader**有关**PropertyValue**框。</span><span class="sxs-lookup"><span data-stu-id="bdb27-169">Similarly, type **MyPassHeader** for the **PropertyValue** box.</span></span> <span data-ttu-id="bdb27-170">选择**System.String**有关**类型**框。</span><span class="sxs-lookup"><span data-stu-id="bdb27-170">Select **System.String** for the **Type** box.</span></span>  
  
    5.  <span data-ttu-id="bdb27-171">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="bdb27-171">Click **OK**.</span></span>  
  
2.  <span data-ttu-id="bdb27-172">添加 BAPI_SALESORDER_GETLIST 方法的用户名称和密码标头。</span><span class="sxs-lookup"><span data-stu-id="bdb27-172">Add the user name and password headers for the BAPI_SALESORDER_GETLIST method.</span></span>  
  
    1.  <span data-ttu-id="bdb27-173">在元数据对象窗格中，展开**SalesOrder**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="bdb27-173">In the Metadata Objects pane, expand the **SalesOrder** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="bdb27-174">单击 BAPI_SALESORDER_GETLIST 节点，然后在属性窗格中单击省略号 （...） 按钮根据**属性**框。</span><span class="sxs-lookup"><span data-stu-id="bdb27-174">Click the BAPI_SALESORDER_GETLIST node, and in the Properties pane click the ellipsis (…) button against the **Properties** box.</span></span>  
  
    3.  <span data-ttu-id="bdb27-175">在 PropertyView 集合编辑器窗口中，单击**外**，然后在属性窗格中，键入**HttpHeaderUserName**有关**名称**框。</span><span class="sxs-lookup"><span data-stu-id="bdb27-175">In the PropertyView Collection Editor window, click **Add**, and in the Property pane, type **HttpHeaderUserName** for the **Name** box.</span></span> <span data-ttu-id="bdb27-176">同样，键入**MyUserHeader**有关**PropertyValue**框。</span><span class="sxs-lookup"><span data-stu-id="bdb27-176">Similarly, type **MyUserHeader** for the **PropertyValue** box.</span></span> <span data-ttu-id="bdb27-177">选择**System.String**有关**类型**框。</span><span class="sxs-lookup"><span data-stu-id="bdb27-177">Select **System.String** for the **Type** box.</span></span>  
  
    4.  <span data-ttu-id="bdb27-178">在 PropertyView 集合编辑器窗口中，单击**外**，然后在属性窗格中，键入**HttpHeaderPassword**有关**名称**框。</span><span class="sxs-lookup"><span data-stu-id="bdb27-178">In the PropertyView Collection Editor window, click **Add**, and in the Property pane, type **HttpHeaderPassword** for the **Name** box.</span></span> <span data-ttu-id="bdb27-179">同样，键入**MyPassHeader**有关**PropertyValue**框。</span><span class="sxs-lookup"><span data-stu-id="bdb27-179">Similarly, type **MyPassHeader** for the **PropertyValue** box.</span></span> <span data-ttu-id="bdb27-180">选择**System.String**有关**类型**框。</span><span class="sxs-lookup"><span data-stu-id="bdb27-180">Select **System.String** for the **Type** box.</span></span>  
  
    5.  <span data-ttu-id="bdb27-181">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="bdb27-181">Click **OK**.</span></span>  
  
### <a name="set-up-single-sign-on-for-connecting-to-the-sap-system"></a><span data-ttu-id="bdb27-182">为连接到 SAP 系统设置了单一登录</span><span class="sxs-lookup"><span data-stu-id="bdb27-182">Set up Single Sign-On for Connecting to the SAP System</span></span>  
 <span data-ttu-id="bdb27-183">执行本主题中的所有过程完成后，您将创建可导入 SharePoint 应用程序的应用程序定义文件。</span><span class="sxs-lookup"><span data-stu-id="bdb27-183">After you have finished performing all the procedures in this topic, you will have created an application definition file that can be imported into a SharePoint application.</span></span> <span data-ttu-id="bdb27-184">从应用程序，您调用以检索相关数据从 SAP 系统的 SAP 方法。</span><span class="sxs-lookup"><span data-stu-id="bdb27-184">From the application, you invoke the SAP methods to retrieve relevant data from the SAP system.</span></span> <span data-ttu-id="bdb27-185">若要启用此功能，必须在 SharePoint 应用程序中创建 SAP 系统中的用户和用户之间的映射。</span><span class="sxs-lookup"><span data-stu-id="bdb27-185">To enable this, you must create a mapping between a user in the SAP system and the user in the SharePoint application.</span></span> <span data-ttu-id="bdb27-186">在导入应用程序定义文件后，可以在 SharePoint 中心管理控制台中创建此映射。</span><span class="sxs-lookup"><span data-stu-id="bdb27-186">You create this mapping in SharePoint Central Administration console after you have imported the application definition file.</span></span>  
  
 <span data-ttu-id="bdb27-187">但是，若要创建该映射必须设置属性**SecondarySsoApplicationId**中 Business Data Catalog Definition Editor。</span><span class="sxs-lookup"><span data-stu-id="bdb27-187">However, to create the mapping you must set a property **SecondarySsoApplicationId** in the Business Data Catalog Definition Editor.</span></span>  
  
##### <a name="to-set-the-secondaryssoapplicationid-property"></a><span data-ttu-id="bdb27-188">若要设置 SecondarySsoApplicationId 属性</span><span class="sxs-lookup"><span data-stu-id="bdb27-188">To set the SecondarySsoApplicationId property</span></span>  
  
1.  <span data-ttu-id="bdb27-189">在元数据对象窗格中，展开**Customer_Order**节点，然后展开**实例**节点。</span><span class="sxs-lookup"><span data-stu-id="bdb27-189">In the Metadata Objects pane, expand the **Customer_Order** node, and then expand the **Instances** node.</span></span>  
  
2.  <span data-ttu-id="bdb27-190">单击**Customer_Order_Instance**，并在属性窗格中，单击省略号 （...） 按钮针对**属性**框。</span><span class="sxs-lookup"><span data-stu-id="bdb27-190">Click **Customer_Order_Instance**, and in the Properties pane, click the ellipsis (…) button against the **Properties** box.</span></span>  
  
3.  <span data-ttu-id="bdb27-191">在 PropertyView 集合编辑器窗口中，单击**外**，然后在属性窗格中，键入**SecondarySsoApplicationId**有关**名称**框。</span><span class="sxs-lookup"><span data-stu-id="bdb27-191">In the PropertyView Collection Editor window, click **Add**, and in the Property pane, type **SecondarySsoApplicationId** for the **Name** box.</span></span> <span data-ttu-id="bdb27-192">同样，键入**SAPSSO**有关**PropertyValue**框。</span><span class="sxs-lookup"><span data-stu-id="bdb27-192">Similarly, type **SAPSSO** for the **PropertyValue** box.</span></span> <span data-ttu-id="bdb27-193">选择**System.String**有关**类型**框。</span><span class="sxs-lookup"><span data-stu-id="bdb27-193">Select **System.String** for the **Type** box.</span></span>  
  
     <span data-ttu-id="bdb27-194">![添加 SSO 属性](../../adapters-and-accelerators/adapter-sap/media/1eb813e4-fed2-45c2-8902-9af5dd3369bf.gif "1eb813e4-fed2-45c2-8902-9af5dd3369bf")</span><span class="sxs-lookup"><span data-stu-id="bdb27-194">![Add the SSO property](../../adapters-and-accelerators/adapter-sap/media/1eb813e4-fed2-45c2-8902-9af5dd3369bf.gif "1eb813e4-fed2-45c2-8902-9af5dd3369bf")</span></span>  
  
4.  <span data-ttu-id="bdb27-195">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="bdb27-195">Click **OK**.</span></span>  
  
### <a name="requirement-1-search-for-customers-based-on-customer-name"></a><span data-ttu-id="bdb27-196">要求 1： 客户基于客户名称搜索</span><span class="sxs-lookup"><span data-stu-id="bdb27-196">Requirement 1: Search for Customers Based on Customer Name</span></span>  
 <span data-ttu-id="bdb27-197">若要创建可用于搜索客户基于客户名称的应用程序定义文件，必须执行以下一组任务。</span><span class="sxs-lookup"><span data-stu-id="bdb27-197">To create an application definition file that can be used to search for customers based on customer name, you must perform the following set of tasks.</span></span>  
  
-   <span data-ttu-id="bdb27-198">在 SD_RFC_CUSTOMER_GET 方法中，创建一个筛选器，并将其映射到存储的客户名称的参数。</span><span class="sxs-lookup"><span data-stu-id="bdb27-198">In the SD_RFC_CUSTOMER_GET method, create a filter and map it to the parameter that stores the customer name.</span></span>  
  
-   <span data-ttu-id="bdb27-199">创建**Finder** SD_RFC_CUSTOMER_GET 方法的方法实例。</span><span class="sxs-lookup"><span data-stu-id="bdb27-199">Create a **Finder** method instance for the SD_RFC_CUSTOMER_GET method.</span></span> <span data-ttu-id="bdb27-200">一个**Finder**方法检索基于筛选器记录的列表。</span><span class="sxs-lookup"><span data-stu-id="bdb27-200">A **Finder** method retrieves a list of records based on a filter.</span></span>  
  
##### <a name="to-create-a-filter-and-map-it-to-the-customer-name-parameter"></a><span data-ttu-id="bdb27-201">若要创建筛选器，并将其映射到的客户名称参数</span><span class="sxs-lookup"><span data-stu-id="bdb27-201">To create a filter, and map it to the customer name parameter</span></span>  
  
1.  <span data-ttu-id="bdb27-202">创建一个筛选器。</span><span class="sxs-lookup"><span data-stu-id="bdb27-202">Create a filter.</span></span>  
  
    1.  <span data-ttu-id="bdb27-203">在元数据对象窗格中，展开**客户**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="bdb27-203">In the Metadata Objects pane, expand the **Customer** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="bdb27-204">展开 SD_RFC_CUSTOMER_GET 方法中，右键单击**筛选器**，然后单击**添加筛选器**。</span><span class="sxs-lookup"><span data-stu-id="bdb27-204">Expand the SD_RFC_CUSTOMER_GET method, right-click **Filters**, and then click **Add Filter**.</span></span>  
  
         <span data-ttu-id="bdb27-205">![向方法中添加筛选器](../../adapters-and-accelerators/adapter-sap/media/23eaab24-66e4-486f-8f99-02a5e0fef984.gif "23eaab24-66e4-486f-8f99-02a5e0fef984")</span><span class="sxs-lookup"><span data-stu-id="bdb27-205">![Add filter to a method](../../adapters-and-accelerators/adapter-sap/media/23eaab24-66e4-486f-8f99-02a5e0fef984.gif "23eaab24-66e4-486f-8f99-02a5e0fef984")</span></span>  
  
    3.  <span data-ttu-id="bdb27-206">在属性窗格中，键入**CustomerName**中**名称**框。</span><span class="sxs-lookup"><span data-stu-id="bdb27-206">In the Properties pane, type **CustomerName** in the **Name** box.</span></span>  
  
         <span data-ttu-id="bdb27-207">![指定筛选器的名称](../../adapters-and-accelerators/adapter-sap/media/0a0d0f85-a16a-4969-a122-097355141c27.gif "0a0d0f85-a16a-4969-a122-097355141c27")</span><span class="sxs-lookup"><span data-stu-id="bdb27-207">![Specify a name for the filter](../../adapters-and-accelerators/adapter-sap/media/0a0d0f85-a16a-4969-a122-097355141c27.gif "0a0d0f85-a16a-4969-a122-097355141c27")</span></span>  
  
    4.  <span data-ttu-id="bdb27-208">有关**FilterType**属性中，选择**WildcardFilter**。</span><span class="sxs-lookup"><span data-stu-id="bdb27-208">For the **FilterType** property, select **WildcardFilter**.</span></span>  
  
2.  <span data-ttu-id="bdb27-209">筛选器映射到**NAME1** SD_RFC_CUSTOMER_GET 方法中的参数。</span><span class="sxs-lookup"><span data-stu-id="bdb27-209">Map the filter to the **NAME1** parameter in the SD_RFC_CUSTOMER_GET method.</span></span>  
  
    1.  <span data-ttu-id="bdb27-210">在元数据对象窗格中，展开**客户**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="bdb27-210">In the Metadata Objects pane, expand the **Customer** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="bdb27-211">展开 SD_RFC_CUSTOMER_GET 方法，然后展开**参数**节点。</span><span class="sxs-lookup"><span data-stu-id="bdb27-211">Expand the SD_RFC_CUSTOMER_GET method, and then expand the **Parameters** node.</span></span>  
  
    3.  <span data-ttu-id="bdb27-212">展开**NAME1**节点，然后单击第二个**NAME1**节点。</span><span class="sxs-lookup"><span data-stu-id="bdb27-212">Expand the **NAME1** node, and click the second **NAME1** node.</span></span> <span data-ttu-id="bdb27-213">**NAME1**参数包含客户的名称。</span><span class="sxs-lookup"><span data-stu-id="bdb27-213">The **NAME1** parameter contains the name of the customer.</span></span>  
  
    4.  <span data-ttu-id="bdb27-214">在属性窗格中选择**CustomerName**从**FilterDescriptor**列表。</span><span class="sxs-lookup"><span data-stu-id="bdb27-214">In the Properties pane, select **CustomerName** from the **FilterDescriptor** list.</span></span>  
  
         <span data-ttu-id="bdb27-215">![将筛选器映射到方法参数](../../adapters-and-accelerators/adapter-sap/media/6cc4ef85-503c-4847-95cb-633b902a715d.gif "6cc4ef85-503c-4847-95cb-633b902a715d")</span><span class="sxs-lookup"><span data-stu-id="bdb27-215">![Map the filter to a method parameter](../../adapters-and-accelerators/adapter-sap/media/6cc4ef85-503c-4847-95cb-633b902a715d.gif "6cc4ef85-503c-4847-95cb-633b902a715d")</span></span>  
  
##### <a name="to-create-a-finder-method-instance-for-the-sdrfccustomerget-method"></a><span data-ttu-id="bdb27-216">若要创建 Finder 方法实例 SD_RFC_CUSTOMER_GET 方法</span><span class="sxs-lookup"><span data-stu-id="bdb27-216">To create a Finder method instance for the SD_RFC_CUSTOMER_GET method</span></span>  
  
1.  <span data-ttu-id="bdb27-217">在元数据对象窗格中，展开**客户**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="bdb27-217">In the Metadata Objects pane, expand the **Customer** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="bdb27-218">展开**SD_RFC_CUSTOMER_GET**节点，右键单击**实例**，然后单击**添加方法实例**以打开创建方法实例窗口。</span><span class="sxs-lookup"><span data-stu-id="bdb27-218">Expand the **SD_RFC_CUSTOMER_GET** node, right-click **Instances**, and then click **Add Method Instance** to open the Create Method Instance window.</span></span>  
  
     <span data-ttu-id="bdb27-219">![添加方法实例](../../adapters-and-accelerators/adapter-sap/media/f583f8ef-e364-4665-8514-db033219ba0b.gif "f583f8ef-e364-4665-8514-db033219ba0b")</span><span class="sxs-lookup"><span data-stu-id="bdb27-219">![Add a method instance](../../adapters-and-accelerators/adapter-sap/media/f583f8ef-e364-4665-8514-db033219ba0b.gif "f583f8ef-e364-4665-8514-db033219ba0b")</span></span>  
  
3.  <span data-ttu-id="bdb27-220">在创建方法实例窗口中，单击**Finder**有关**方法实例类型**。</span><span class="sxs-lookup"><span data-stu-id="bdb27-220">In the Create Method Instance window, click **Finder** for **Method Instance Type**.</span></span> <span data-ttu-id="bdb27-221">选择**CUSTOMER_T**有关**的返回 TypeDescriptor**。</span><span class="sxs-lookup"><span data-stu-id="bdb27-221">Select **CUSTOMER_T** for **Return TypeDescriptor**.</span></span>  
  
     <span data-ttu-id="bdb27-222">![添加 Finder 方法实例](../../adapters-and-accelerators/adapter-sap/media/e9ae47f2-32f5-4586-8467-94e3713d2a06.gif "e9ae47f2-32f5-4586-8467-94e3713d2a06")</span><span class="sxs-lookup"><span data-stu-id="bdb27-222">![Add a Finder method instance](../../adapters-and-accelerators/adapter-sap/media/e9ae47f2-32f5-4586-8467-94e3713d2a06.gif "e9ae47f2-32f5-4586-8467-94e3713d2a06")</span></span>  
  
4.  <span data-ttu-id="bdb27-223">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="bdb27-223">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="bdb27-224">在属性窗格中，键入**GetCustomerByName_Instance**中**名称**框。</span><span class="sxs-lookup"><span data-stu-id="bdb27-224">In the Properties pane, type **GetCustomerByName_Instance** in the **Name** box.</span></span>  
  
     <span data-ttu-id="bdb27-225">![指定方法实例的名称](../../adapters-and-accelerators/adapter-sap/media/e44e02e8-b9fb-40ca-a55d-8bdc7ace02b5.gif "e44e02e8-b9fb-40ca-a55d-8bdc7ace02b5")</span><span class="sxs-lookup"><span data-stu-id="bdb27-225">![Specify a name for the method instance](../../adapters-and-accelerators/adapter-sap/media/e44e02e8-b9fb-40ca-a55d-8bdc7ace02b5.gif "e44e02e8-b9fb-40ca-a55d-8bdc7ace02b5")</span></span>  
  
### <a name="requirement-2-retrieve-details-for-a-specific-customer-from-the-list-of-customers"></a><span data-ttu-id="bdb27-226">要求 2： 检索客户列表从特定客户的详细信息</span><span class="sxs-lookup"><span data-stu-id="bdb27-226">Requirement 2: Retrieve Details for a Specific Customer from the List of Customers</span></span>  
 <span data-ttu-id="bdb27-227">若要创建可用于搜索客户基于客户名称的应用程序定义文件，必须执行以下一组任务。</span><span class="sxs-lookup"><span data-stu-id="bdb27-227">To create an application definition file that can be used to search for customers based on customer name, you must perform the following set of tasks.</span></span>  
  
-   <span data-ttu-id="bdb27-228">在 SD_RFC_CUSTOMER_GET 方法中，创建一个标识符，并将其映射到参数，用于存储的客户编号。</span><span class="sxs-lookup"><span data-stu-id="bdb27-228">In the SD_RFC_CUSTOMER_GET method, create an identifier, and map it to the parameter that stores the customer number.</span></span>  
  
-   <span data-ttu-id="bdb27-229">创建**特定的 Finder** SD_RFC_CUSTOMER_GET 方法的方法实例。</span><span class="sxs-lookup"><span data-stu-id="bdb27-229">Create a **Specific Finder** method instance for the SD_RFC_CUSTOMER_GET method.</span></span> <span data-ttu-id="bdb27-230">一个**特定的 Finder**方法查找基于标识符的特定记录。</span><span class="sxs-lookup"><span data-stu-id="bdb27-230">A **Specific Finder** method finds a specific record based on an identifier.</span></span>  
  
##### <a name="to-create-an-identifier-and-map-it-to-the-customer-number-parameter"></a><span data-ttu-id="bdb27-231">若要创建一个标识符，并将其映射到客户数字参数</span><span class="sxs-lookup"><span data-stu-id="bdb27-231">To create an identifier, and map it to the customer number parameter</span></span>  
  
1.  <span data-ttu-id="bdb27-232">创建标识符**客户**实体。</span><span class="sxs-lookup"><span data-stu-id="bdb27-232">Create an identifier for the **Customer** entity.</span></span>  
  
    1.  <span data-ttu-id="bdb27-233">在元数据对象窗格中，展开**客户**节点。</span><span class="sxs-lookup"><span data-stu-id="bdb27-233">In the Metadata Objects pane, expand the **Customer** node.</span></span>  
  
    2.  <span data-ttu-id="bdb27-234">右键单击**标识符**节点，并选择**添加标识符**。</span><span class="sxs-lookup"><span data-stu-id="bdb27-234">Right-click the **Identifiers** node, and then select **Add Identifier**.</span></span>  
  
         <span data-ttu-id="bdb27-235">![将标识符添加到方法](../../adapters-and-accelerators/adapter-sap/media/3adeeda3-426c-41fe-8d5c-5ca5863fb430.gif "3adeeda3-426c-41fe-8d5c-5ca5863fb430")</span><span class="sxs-lookup"><span data-stu-id="bdb27-235">![Add an identifier to a method](../../adapters-and-accelerators/adapter-sap/media/3adeeda3-426c-41fe-8d5c-5ca5863fb430.gif "3adeeda3-426c-41fe-8d5c-5ca5863fb430")</span></span>  
  
    3.  <span data-ttu-id="bdb27-236">在属性窗格中，键入**CustomerID**中**名称**框。</span><span class="sxs-lookup"><span data-stu-id="bdb27-236">In the Properties pane, type **CustomerID** in the **Name** box.</span></span>  
  
    4.  <span data-ttu-id="bdb27-237">选择**System.String**有关**类型**框。</span><span class="sxs-lookup"><span data-stu-id="bdb27-237">Select **System.String** for the **Type** box.</span></span>  
  
         <span data-ttu-id="bdb27-238">![指定的名称标识符](../../adapters-and-accelerators/adapter-sap/media/a2304bca-9a54-4d2b-ba9f-461cfaafccb0.gif "a2304bca-9a54-4d2b-ba9f-461cfaafccb0")</span><span class="sxs-lookup"><span data-stu-id="bdb27-238">![Specify a name for the identifier](../../adapters-and-accelerators/adapter-sap/media/a2304bca-9a54-4d2b-ba9f-461cfaafccb0.gif "a2304bca-9a54-4d2b-ba9f-461cfaafccb0")</span></span>  
  
2.  <span data-ttu-id="bdb27-239">将标识符映射到 SD_RFC_CUSTOMER_GET 方法的关键参数。</span><span class="sxs-lookup"><span data-stu-id="bdb27-239">Map the identifier to the key parameter for the SD_RFC_CUSTOMER_GET method.</span></span>  
  
    1.  <span data-ttu-id="bdb27-240">在元数据对象窗格中，展开**客户**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="bdb27-240">In the Metadata Objects pane, expand the **Customer** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="bdb27-241">展开 SD_RFC_CUSTOMER_GET 方法，然后展开**参数**节点。</span><span class="sxs-lookup"><span data-stu-id="bdb27-241">Expand the SD_RFC_CUSTOMER_GET method, and then expand the **Parameters** node.</span></span>  
  
    3.  <span data-ttu-id="bdb27-242">展开**应**参数，然后单击第二个**应**节点。</span><span class="sxs-lookup"><span data-stu-id="bdb27-242">Expand the **KUNNR** parameter, and then click the second **KUNNR** node.</span></span>  
  
    4.  <span data-ttu-id="bdb27-243">在属性窗格中选择**CustomerID [Customer]** 从**标识符**列表。</span><span class="sxs-lookup"><span data-stu-id="bdb27-243">In the Properties pane, select **CustomerID[Customer]** from the **Identifier** list.</span></span>  
  
         <span data-ttu-id="bdb27-244">![将标识符映射到参数](../../adapters-and-accelerators/adapter-sap/media/04ff6496-34a7-421b-ae9e-f9263895c153.gif "04ff6496-34a7-421b-ae9e-f9263895c153")</span><span class="sxs-lookup"><span data-stu-id="bdb27-244">![Map the identifier to a parameter](../../adapters-and-accelerators/adapter-sap/media/04ff6496-34a7-421b-ae9e-f9263895c153.gif "04ff6496-34a7-421b-ae9e-f9263895c153")</span></span>  
  
3.  <span data-ttu-id="bdb27-245">设置输入和返回参数之间的关联。</span><span class="sxs-lookup"><span data-stu-id="bdb27-245">Set up an association between input and return parameters.</span></span>  
  
    1.  <span data-ttu-id="bdb27-246">在元数据对象窗格中，展开**客户**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="bdb27-246">In the Metadata Objects pane, expand the **Customer** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="bdb27-247">展开 SD_RFC_CUSTOMER_GET 方法，然后展开**参数**节点。</span><span class="sxs-lookup"><span data-stu-id="bdb27-247">Expand the SD_RFC_CUSTOMER_GET method, and then expand the **Parameters** node.</span></span>  
  
    3.  <span data-ttu-id="bdb27-248">展开**CUSTOMER_T**节点，然后第二个**CUSTOMER_T**节点，然后**项**节点，并单击**应**节点。</span><span class="sxs-lookup"><span data-stu-id="bdb27-248">Expand the **CUSTOMER_T** node, then the second **CUSTOMER_T** node, then the **Item** node, and then click the **KUNNR** node.</span></span>  
  
    4.  <span data-ttu-id="bdb27-249">在属性窗格中选择**CustomerID [Customer]** 从**标识符**列表。</span><span class="sxs-lookup"><span data-stu-id="bdb27-249">In the Properties pane, select **CustomerID[Customer]** from the **Identifier** list.</span></span>  
  
##### <a name="to-create-a-specific-finder-method-instance-for-the-sdrfccustomerget-method"></a><span data-ttu-id="bdb27-250">若要创建 SD_RFC_CUSTOMER_GET 方法的特定的 Finder 方法实例</span><span class="sxs-lookup"><span data-stu-id="bdb27-250">To create a Specific Finder method instance for the SD_RFC_CUSTOMER_GET method</span></span>  
  
1.  <span data-ttu-id="bdb27-251">在元数据对象窗格中，展开**客户**节点，然后**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="bdb27-251">In the Metadata Objects pane, expand the **Customer** node, and then the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="bdb27-252">展开**SD_RFC_CUSTOMER_GET**节点，右键单击**实例**，然后选择**添加方法实例**以打开创建方法实例窗口。</span><span class="sxs-lookup"><span data-stu-id="bdb27-252">Expand the **SD_RFC_CUSTOMER_GET** node, right-click **Instances**, and then select **Add Method Instance** to open the Create Method Instance window.</span></span>  
  
     <span data-ttu-id="bdb27-253">![添加方法实例](../../adapters-and-accelerators/adapter-sap/media/f583f8ef-e364-4665-8514-db033219ba0b.gif "f583f8ef-e364-4665-8514-db033219ba0b")</span><span class="sxs-lookup"><span data-stu-id="bdb27-253">![Add a method instance](../../adapters-and-accelerators/adapter-sap/media/f583f8ef-e364-4665-8514-db033219ba0b.gif "f583f8ef-e364-4665-8514-db033219ba0b")</span></span>  
  
3.  <span data-ttu-id="bdb27-254">在创建方法实例窗口中，选择**特定的 Finder**有关**方法实例类型**。</span><span class="sxs-lookup"><span data-stu-id="bdb27-254">In the Create Method Instance window, select **Specific Finder** for **Method Instance Type**.</span></span> <span data-ttu-id="bdb27-255">同样，选择**CUSTOMER_T**有关**返回 TypeDescriptor**。</span><span class="sxs-lookup"><span data-stu-id="bdb27-255">Similarly, select **CUSTOMER_T** for **Return TypeDescriptor**.</span></span>  
  
     <span data-ttu-id="bdb27-256">![添加特定的 Finder 方法实例](../../adapters-and-accelerators/adapter-sap/media/838eb512-b967-46e7-a865-0bf3651b02a1.gif "838eb512-b967-46e7-a865-0bf3651b02a1")</span><span class="sxs-lookup"><span data-stu-id="bdb27-256">![Add a Specific Finder Method Instance](../../adapters-and-accelerators/adapter-sap/media/838eb512-b967-46e7-a865-0bf3651b02a1.gif "838eb512-b967-46e7-a865-0bf3651b02a1")</span></span>  
  
4.  <span data-ttu-id="bdb27-257">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="bdb27-257">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="bdb27-258">在属性窗格中，键入**GetCustomerByNumber_Instance**有关**名称**框。</span><span class="sxs-lookup"><span data-stu-id="bdb27-258">In the Properties pane, type **GetCustomerByNumber_Instance** for the **Name** box.</span></span>  
  
     <span data-ttu-id="bdb27-259">![指定方法实例的名称](../../adapters-and-accelerators/adapter-sap/media/970f543c-cd06-4921-86c9-c110abdc7994.gif "970f543c-cd06-4921-86c9-c110abdc7994")</span><span class="sxs-lookup"><span data-stu-id="bdb27-259">![Specify a name for the method instance](../../adapters-and-accelerators/adapter-sap/media/970f543c-cd06-4921-86c9-c110abdc7994.gif "970f543c-cd06-4921-86c9-c110abdc7994")</span></span>  
  
### <a name="requirement-3-retrieve-sales-order-details-for-a-specific-customer-from-the-list-of-customers"></a><span data-ttu-id="bdb27-260">要求 3： 检索客户列表从特定客户的销售订单详细信息</span><span class="sxs-lookup"><span data-stu-id="bdb27-260">Requirement 3: Retrieve Sales Order Details for a Specific Customer from the List of Customers</span></span>  
 <span data-ttu-id="bdb27-261">若要创建可用于检索特定客户的销售订单详细信息的应用程序定义文件，必须执行以下一组任务。</span><span class="sxs-lookup"><span data-stu-id="bdb27-261">To create an application definition file that can be used to retrieve sales order details for a specific customer, you must perform the following set of tasks.</span></span>  
  
-   <span data-ttu-id="bdb27-262">设置之间的关联**客户**并**SalesOrder**实体。</span><span class="sxs-lookup"><span data-stu-id="bdb27-262">Set up an association between the **Customer** and **SalesOrder** entities.</span></span>  
  
-   <span data-ttu-id="bdb27-263">创建**关联**BAPI_SALESORDER_GETLIST 方法方法。</span><span class="sxs-lookup"><span data-stu-id="bdb27-263">Create an **Association** method for the BAPI_SALESORDER_GETLIST method.</span></span>  
  
##### <a name="to-create-an-association-between-the-customer-and-salesorder-entities"></a><span data-ttu-id="bdb27-264">若要创建客户和 SalesOrder 实体之间的关联</span><span class="sxs-lookup"><span data-stu-id="bdb27-264">To create an association between the Customer and SalesOrder entities</span></span>  
  
1.  <span data-ttu-id="bdb27-265">在元数据对象窗格中，展开**SalesOrder**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="bdb27-265">In the Metadata Objects pane, expand the **SalesOrder** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="bdb27-266">展开 BAPI_SALESORDER_GETLIST 方法，然后展开**参数**节点。</span><span class="sxs-lookup"><span data-stu-id="bdb27-266">Expand the BAPI_SALESORDER_GETLIST method, and then expand the **Parameters** node.</span></span>  
  
3.  <span data-ttu-id="bdb27-267">展开**CUSTOMER_NUMBER**节点，然后单击第二个**CUSTOMER_NUMBER**节点。</span><span class="sxs-lookup"><span data-stu-id="bdb27-267">Expand the **CUSTOMER_NUMBER** node, and then click the second **CUSTOMER_NUMBER** node.</span></span>  
  
4.  <span data-ttu-id="bdb27-268">在属性窗格中选择**CustomerID [Customer]** 从**标识符**列表。</span><span class="sxs-lookup"><span data-stu-id="bdb27-268">In the Properties pane, select **CustomerID[Customer]** from the **Identifier** list.</span></span>  
  
     <span data-ttu-id="bdb27-269">![创建两个实体之间的关联](../../adapters-and-accelerators/adapter-sap/media/ae7e1e7a-a12b-4905-b002-2a04c7050848.gif "ae7e1e7a-a12b-4905-b002-2a04c7050848")</span><span class="sxs-lookup"><span data-stu-id="bdb27-269">![Create association between the two entities](../../adapters-and-accelerators/adapter-sap/media/ae7e1e7a-a12b-4905-b002-2a04c7050848.gif "ae7e1e7a-a12b-4905-b002-2a04c7050848")</span></span>  
  
##### <a name="to-create-an-association-method-instance-for-the-bapisalesordergetlist-method"></a><span data-ttu-id="bdb27-270">若要创建关联方法实例 BAPI_SALESORDER_GETLIST 方法</span><span class="sxs-lookup"><span data-stu-id="bdb27-270">To create an Association method instance for the BAPI_SALESORDER_GETLIST method</span></span>  
  
1.  <span data-ttu-id="bdb27-271">在元数据对象窗格中，展开**SalesOrder**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="bdb27-271">In the Metadata Objects pane, expand the **SalesOrder** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="bdb27-272">展开**BAPI_SALESORDER_GETLIST**节点，右键单击**实例**，然后选择**添加方法实例**以打开创建方法实例窗口。</span><span class="sxs-lookup"><span data-stu-id="bdb27-272">Expand the **BAPI_SALESORDER_GETLIST** node, right-click **Instances**, and then select **Add Method Instance** to open the Create Method Instance window.</span></span>  
  
     <span data-ttu-id="bdb27-273">![添加关联方法实例](../../adapters-and-accelerators/adapter-sap/media/c62a0d01-d4f3-470e-92f1-8a5cf666f8da.gif "c62a0d01-d4f3-470e-92f1-8a5cf666f8da")</span><span class="sxs-lookup"><span data-stu-id="bdb27-273">![Add an Association Method Instance](../../adapters-and-accelerators/adapter-sap/media/c62a0d01-d4f3-470e-92f1-8a5cf666f8da.gif "c62a0d01-d4f3-470e-92f1-8a5cf666f8da")</span></span>  
  
3.  <span data-ttu-id="bdb27-274">在创建方法实例窗口中，选择**关联**有关**方法实例类型**。</span><span class="sxs-lookup"><span data-stu-id="bdb27-274">In the Create Method Instance window, select **Association** for **Method Instance Type**.</span></span>  
  
4.  <span data-ttu-id="bdb27-275">在中**源实体**列表中，选择**客户**。</span><span class="sxs-lookup"><span data-stu-id="bdb27-275">In the **Source Entities** list, select **Customer**.</span></span>  
  
5.  <span data-ttu-id="bdb27-276">在中**返回 TypeDescriptor**列表中，选择**SALES_ORDERS**...</span><span class="sxs-lookup"><span data-stu-id="bdb27-276">In the **Return TypeDescriptor** list, select **SALES_ORDERS**..</span></span>  
  
     <span data-ttu-id="bdb27-277">![创建关联方法实例](../../adapters-and-accelerators/adapter-sap/media/15975b78-8932-41ce-8c10-41891fc1fb22.gif "15975b78-8932-41ce-8c10-41891fc1fb22")</span><span class="sxs-lookup"><span data-stu-id="bdb27-277">![Create an Association Method Instance](../../adapters-and-accelerators/adapter-sap/media/15975b78-8932-41ce-8c10-41891fc1fb22.gif "15975b78-8932-41ce-8c10-41891fc1fb22")</span></span>  
  
6.  <span data-ttu-id="bdb27-278">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="bdb27-278">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="bdb27-279">在属性窗格中，键入**SalesOrderForCustomer_Instance**有关**名称**框。</span><span class="sxs-lookup"><span data-stu-id="bdb27-279">In the Properties pane, type **SalesOrderForCustomer_Instance** for the **Name** box.</span></span>  
  
     <span data-ttu-id="bdb27-280">![指定关联方法的名称](../../adapters-and-accelerators/adapter-sap/media/0f1d13e4-e5a3-49ec-92a7-6329c6db1eb0.gif "0f1d13e4-e5a3-49ec-92a7-6329c6db1eb0")</span><span class="sxs-lookup"><span data-stu-id="bdb27-280">![Specify a name for the Association Method](../../adapters-and-accelerators/adapter-sap/media/0f1d13e4-e5a3-49ec-92a7-6329c6db1eb0.gif "0f1d13e4-e5a3-49ec-92a7-6329c6db1eb0")</span></span>  
  
### <a name="remove-parameters-of-systemnullable-type"></a><span data-ttu-id="bdb27-281">删除 System.Nullable 类型的参数</span><span class="sxs-lookup"><span data-stu-id="bdb27-281">Remove Parameters of System.Nullable Type</span></span>  
 <span data-ttu-id="bdb27-282">创建时**关联**方法实例作为 SALES_ORDERS BAPI_SALESORDER_GETLIST 方法中，选择返回的类型。</span><span class="sxs-lookup"><span data-stu-id="bdb27-282">While creating the **Association** method instance for the BAPI_SALESORDER_GETLIST method, you selected the return type as SALES_ORDERS.</span></span> <span data-ttu-id="bdb27-283">如果展开 SALES_ORDER 参数，你会注意到某些参数的 System.Nullable 类型。</span><span class="sxs-lookup"><span data-stu-id="bdb27-283">If you expand the SALES_ORDER parameter, you will notice some parameters are of System.Nullable type.</span></span> <span data-ttu-id="bdb27-284">您可以看到通过选择该参数在 Business Data Catalog Definition Editor，并查看的值类型的参数**TypeName**属性。</span><span class="sxs-lookup"><span data-stu-id="bdb27-284">You can see the parameter type by selecting the parameter in the Business Data Catalog Definition Editor, and looking at the value for the **TypeName** property.</span></span>  
  
 <span data-ttu-id="bdb27-285">对于此类参数，Business Data Catalog Definition Editor 创建另一个参数具有相同名称但具有"Specified"后缀。</span><span class="sxs-lookup"><span data-stu-id="bdb27-285">For such parameters, the Business Data Catalog Definition Editor creates another parameter with the same name but with a “Specified” suffix.</span></span> <span data-ttu-id="bdb27-286">例如，看一下参数*ITM_NUMBER*并*ITM_NUMBERSpecified*。</span><span class="sxs-lookup"><span data-stu-id="bdb27-286">For example, look at parameters *ITM_NUMBER* and *ITM_NUMBERSpecified*.</span></span> <span data-ttu-id="bdb27-287">Microsoft Office SharePoint Server 不支持 System.Nullable 参数。</span><span class="sxs-lookup"><span data-stu-id="bdb27-287">Microsoft Office SharePoint Server does not support System.Nullable parameters.</span></span> <span data-ttu-id="bdb27-288">因此，当您尝试记录，其中包含 System.Nullable 参数类型，则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="bdb27-288">So, when you try records that contain the System.Nullable parameter type, it throws an exception.</span></span> <span data-ttu-id="bdb27-289">因此，必须删除从 Business Data Catalog Definition Editor 这两个参数 （使用或不包含"Specified"后缀和具有相同名称）</span><span class="sxs-lookup"><span data-stu-id="bdb27-289">Therefore, you must remove both the parameters (with and without the “Specified” suffix and having the same name) from the Business Data Catalog Definition Editor</span></span>  
  
##### <a name="to-remove-the-parameters-of-systemnullable-type"></a><span data-ttu-id="bdb27-290">若要删除 System.Nullable 类型的参数</span><span class="sxs-lookup"><span data-stu-id="bdb27-290">To remove the parameters of System.Nullable type</span></span>  
  
1.  <span data-ttu-id="bdb27-291">在元数据对象窗格中，展开**SalesOrder**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="bdb27-291">In the Metadata Objects pane, expand the **SalesOrder** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="bdb27-292">展开**BAPI_SALESORDER_GETLIST**节点，然后展开**参数**节点。</span><span class="sxs-lookup"><span data-stu-id="bdb27-292">Expand the **BAPI_SALESORDER_GETLIST** node, and then expand the **Parameters** node.</span></span>  
  
3.  <span data-ttu-id="bdb27-293">展开**SALES_ORDERS**，展开第二个**SALES_ORDERS**，然后展开**项**。</span><span class="sxs-lookup"><span data-stu-id="bdb27-293">Expand **SALES_ORDERS**, expand the second **SALES_ORDERS**, and then expand **Item**.</span></span>  
  
4.  <span data-ttu-id="bdb27-294">右键单击包含在名称的"Specified"后缀的参数，然后选择**删除**。</span><span class="sxs-lookup"><span data-stu-id="bdb27-294">Right-click the parameter that contains the "Specified" suffix in the name, and then select **Delete**.</span></span>  
  
5.  <span data-ttu-id="bdb27-295">右键单击已删除，而不使用后缀，该参数与同名的参数，然后选择**删除**。</span><span class="sxs-lookup"><span data-stu-id="bdb27-295">Right-click the parameter that has the same name as the parameter you deleted, without the suffix, and then select **Delete**.</span></span> <span data-ttu-id="bdb27-296">通常情况下，此参数是前面有"Specified"后缀的参数正确。</span><span class="sxs-lookup"><span data-stu-id="bdb27-296">Typically, this parameter is right before the parameter that has the "Specified" suffix.</span></span>  
  
### <a name="set-default-parameters"></a><span data-ttu-id="bdb27-297">设置默认参数</span><span class="sxs-lookup"><span data-stu-id="bdb27-297">Set Default Parameters</span></span>  
 <span data-ttu-id="bdb27-298">BAPI_SALESORDER_GETLIST 采用两个参数。</span><span class="sxs-lookup"><span data-stu-id="bdb27-298">The BAPI_SALESORDER_GETLIST takes two parameters.</span></span> <span data-ttu-id="bdb27-299">其中一个参数，TRANSACTION_GROUP，是默认参数。</span><span class="sxs-lookup"><span data-stu-id="bdb27-299">One of these parameters, TRANSACTION_GROUP, is the default parameter.</span></span> <span data-ttu-id="bdb27-300">因此，必须设置此参数的默认值。</span><span class="sxs-lookup"><span data-stu-id="bdb27-300">So, you must set the default value for this parameter.</span></span>  
  
##### <a name="to-set-the-default-value-for-transactiongroup"></a><span data-ttu-id="bdb27-301">若要为 TRANSACTION_GROUP 设置默认值</span><span class="sxs-lookup"><span data-stu-id="bdb27-301">To set the default value for TRANSACTION_GROUP</span></span>  
  
1.  <span data-ttu-id="bdb27-302">在元数据对象窗格中，展开**SalesOrder**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="bdb27-302">In the Metadata Objects pane, expand the **SalesOrder** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="bdb27-303">展开**BAPI_SALESORDER_GETLIST**节点，然后展开**实例**节点。</span><span class="sxs-lookup"><span data-stu-id="bdb27-303">Expand the **BAPI_SALESORDER_GETLIST** node, and then expand the **Instances** node.</span></span>  
  
3.  <span data-ttu-id="bdb27-304">选择**SalesOrderForCustomer_Instance**方法实例，并在属性窗格中，单击省略号按钮 （...） 针对**DefaultValues**框。</span><span class="sxs-lookup"><span data-stu-id="bdb27-304">Select the **SalesOrderForCustomer_Instance** method instance, and in the Properties pane, click the ellipsis button (…) against the **DefaultValues** box.</span></span>  
  
4.  <span data-ttu-id="bdb27-305">在编辑窗口中，展开**TRANSACTION_GROUP**节点，并为**TRANSACTION_GROUP**框中，指定默认值 0。</span><span class="sxs-lookup"><span data-stu-id="bdb27-305">In the Edit window, expand **TRANSACTION_GROUP** node, and for the **TRANSACTION_GROUP** box, specify the default value 0.</span></span>  
  
     <span data-ttu-id="bdb27-306">![指定方法实例的默认值](../../adapters-and-accelerators/adapter-sap/media/86e0a42d-61c0-4d5d-ba3f-55b328f79576.gif "86e0a42d-61c0-4d5d-ba3f-55b328f79576")</span><span class="sxs-lookup"><span data-stu-id="bdb27-306">![Specify a default value for the method instance](../../adapters-and-accelerators/adapter-sap/media/86e0a42d-61c0-4d5d-ba3f-55b328f79576.gif "86e0a42d-61c0-4d5d-ba3f-55b328f79576")</span></span>  
  
5.  <span data-ttu-id="bdb27-307">单击 **“关闭”**。</span><span class="sxs-lookup"><span data-stu-id="bdb27-307">Click **Close**.</span></span>  
  
### <a name="export-the-application-definition-to-a-file"></a><span data-ttu-id="bdb27-308">应用程序定义导出到文件</span><span class="sxs-lookup"><span data-stu-id="bdb27-308">Export the Application Definition to a File</span></span>  
 <span data-ttu-id="bdb27-309">现在已创建包含 SAP 系统实例元数据的应用程序定义。</span><span class="sxs-lookup"><span data-stu-id="bdb27-309">You have now created an application definition that contains the SAP system instance metadata.</span></span> <span data-ttu-id="bdb27-310">必须将此定义导出到 XML 文件，可以导入到 Microsoft Office SharePoint Server。</span><span class="sxs-lookup"><span data-stu-id="bdb27-310">You must export this definition to an XML file, which can be imported into Microsoft Office SharePoint Server.</span></span>  
  
##### <a name="to-export-the-application-definition-to-a-file"></a><span data-ttu-id="bdb27-311">若要将应用程序定义导出到文件</span><span class="sxs-lookup"><span data-stu-id="bdb27-311">To export the application definition to a file</span></span>  
  
1.  <span data-ttu-id="bdb27-312">在元数据对象窗格中，右键单击**Customer_Order**节点，并单击**导出**。</span><span class="sxs-lookup"><span data-stu-id="bdb27-312">In the Metadata Objects pane, right-click the **Customer_Order** node, and then click **Export**.</span></span>  
  
2.  <span data-ttu-id="bdb27-313">将文件另存 Customer_Order.xml。</span><span class="sxs-lookup"><span data-stu-id="bdb27-313">Save the file as Customer_Order.xml.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="bdb27-314">后续步骤</span><span class="sxs-lookup"><span data-stu-id="bdb27-314">Next Steps</span></span>  
 <span data-ttu-id="bdb27-315">现在必须创建 SharePoint 应用程序以从 SAP 系统中检索数据。</span><span class="sxs-lookup"><span data-stu-id="bdb27-315">You must now create a SharePoint application to retrieve data from an SAP system.</span></span> <span data-ttu-id="bdb27-316">请参阅[第 3 步： 创建 SharePoint 应用程序检索的数据从 SAP](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md)有关的说明。</span><span class="sxs-lookup"><span data-stu-id="bdb27-316">See [Step 3: Create a SharePoint Application to Retrieve Data from SAP](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md) for instructions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdb27-317">请参阅</span><span class="sxs-lookup"><span data-stu-id="bdb27-317">See Also</span></span>  
 [<span data-ttu-id="bdb27-318">教程 1：在 SharePoint 上提供来自 SAP 系统的数据</span><span class="sxs-lookup"><span data-stu-id="bdb27-318">Tutorial 1: Presenting Data from an SAP System on a SharePoint Site</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)