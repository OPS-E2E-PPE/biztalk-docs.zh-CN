---
title: "步骤 2： 创建 Oracle E-business Suite 项目的应用程序定义文件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2665afde-0337-4795-ab4c-6223d39fdf9c
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ed4340893d351d8406212b585e6216de19c634c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-create-an-application-definition-file-for-the-oracle-e-business-suite-artifacts"></a><span data-ttu-id="eb8c7-102">步骤 2： 创建 Oracle E-business Suite 项目的应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="eb8c7-102">Step 2: Create an application definition file for the Oracle E-Business Suite artifacts</span></span>
<span data-ttu-id="eb8c7-103">![步骤 2 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span><span class="sxs-lookup"><span data-stu-id="eb8c7-103">![Step 2 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span></span>  
  
 <span data-ttu-id="eb8c7-104">**完成时间：** 15 分钟</span><span class="sxs-lookup"><span data-stu-id="eb8c7-104">**Time to complete:** 15 minutes</span></span>  
  
 <span data-ttu-id="eb8c7-105">**目标：** Microsoft SharePoint Server 中的业务数据目录功能公开，并将从-的业务线 (LOB) 应用程序的数据合并到门户。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-105">**Objective:** The Business Data Catalog feature in Microsoft SharePoint Server exposes and incorporates data from line-of-business (LOB) applications into portals.</span></span> <span data-ttu-id="eb8c7-106">若要将此数据合并到您的门户网站，必须在生成应用程序定义文件，可以使用 Microsoft Office SharePoint Server。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-106">To incorporate this data into your portal site, you must build an application definition file that Microsoft Office SharePoint Server can consume.</span></span>  
  
 <span data-ttu-id="eb8c7-107">业务数据目录定义编辑器工具，适用于 Microsoft Office SharePoint Server 2007 SDK，可为业务数据目录中创建应用程序定义文件。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-107">The Business Data Catalog Definition Editor tool, available with Microsoft Office SharePoint Server 2007 SDK, enables you to create an application definition file for the Business Data Catalog.</span></span> <span data-ttu-id="eb8c7-108">此工具自动生成一个 XML 文件定义文件中，因此不需要手动创建该文件在 XML 编辑器。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-108">This tool automatically generates an XML file for the definition file, so you do not need to manually create the file in an XML editor.</span></span>  
  
 <span data-ttu-id="eb8c7-109">要创建 Microsoft Office SharePoint Server 应用程序的目的是：</span><span class="sxs-lookup"><span data-stu-id="eb8c7-109">The purpose of the Microsoft Office SharePoint Server application that you are creating is to:</span></span>  
  
-   <span data-ttu-id="eb8c7-110">查询中使用业务数据列表 Web 部件 MS_SAMPLE_EMPLOYEE 接口表员工的基于雇员姓名。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-110">Query for an employee in the MS_SAMPLE_EMPLOYEE interface table using a Business Data List Web Part based on an employee name.</span></span>  
  
-   <span data-ttu-id="eb8c7-111">执行从 Microsoft Office SharePoint Server 上 MS_SAMPLE_EMPLOYEE 接口表的全文搜索。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-111">Perform a full-text search from Microsoft Office SharePoint Server on the MS_SAMPLE_EMPLOYEE interface table.</span></span>  
  
 <span data-ttu-id="eb8c7-112">对于每个这些要求，你必须完成一组在业务数据目录定义编辑器工具中的任务。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-112">For each of these requirements, you must complete a set of tasks in the Business Data Catalog Definition Editor tool.</span></span> <span data-ttu-id="eb8c7-113">本主题提供有关如何执行这些任务的说明。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-113">This topic provides instructions on how to perform these tasks.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="eb8c7-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="eb8c7-114">Prerequisites</span></span>  
  
-   <span data-ttu-id="eb8c7-115">请确保已安装 Microsoft Office SharePoint Server 2007 SDK 的一部分业务数据目录定义编辑器。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-115">Be sure that you have the Business Data Catalog Definition Editor installed as part of the Microsoft Office SharePoint Server 2007 SDK.</span></span> <span data-ttu-id="eb8c7-116">你可以下载 SDK 从[http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130)。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-116">You can download the SDK from [http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130).</span></span>  
  
-   <span data-ttu-id="eb8c7-117">将 WCF 服务发布中所述[步骤 1： 使用 Oracle E-business 适配器创建和发布 WCF 服务](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md)。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-117">Publish the WCF service as described in [Step 1: Use the Oracle E-Business Adapter to Create and Publish a WCF Service](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md).</span></span>  
  

  
##  <a name="Connect"></a><span data-ttu-id="eb8c7-118">连接到 WCF LOB 服务并创建实体</span><span class="sxs-lookup"><span data-stu-id="eb8c7-118">Connect to the WCF LOB Service and Create Entity</span></span>  
 <span data-ttu-id="eb8c7-119">你必须连接到要提取 Web 服务描述语言 (WSDL) 服务的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-119">You must connect to the WCF service to extract the Web Services Description Language (WSDL) for the service.</span></span> <span data-ttu-id="eb8c7-120">从 WSDL，业务数据目录定义编辑器中提取方法。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-120">From the WSDL, the Business Data Catalog Definition Editor extracts the methods.</span></span> <span data-ttu-id="eb8c7-121">这些方法可以用于创建实体。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-121">These methods can be used to create entities.</span></span> <span data-ttu-id="eb8c7-122">对于本教程中，创建实体。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-122">For this tutorial, an entity is created.</span></span>  
  
#### <a name="to-connect-to-the-wcf-service-and-create-entities"></a><span data-ttu-id="eb8c7-123">若要连接到 WCF 服务并创建实体</span><span class="sxs-lookup"><span data-stu-id="eb8c7-123">To connect to the WCF service and create entities</span></span>  
  
1.  <span data-ttu-id="eb8c7-124">启动业务数据目录定义编辑器。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-124">Start the Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="eb8c7-125">上**启动**菜单上，单击**Microsoft 业务数据目录定义编辑器**。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-125">On the **Start** menu, click **Microsoft Business Data Catalog Definition Editor**.</span></span>  
  
2.  <span data-ttu-id="eb8c7-126">在工具栏上，单击**添加 LOB 系统**。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-126">On the toolbar, click **Add LOB System**.</span></span>  
  
3.  <span data-ttu-id="eb8c7-127">在添加 LOB 系统窗口中，单击**连接到 web 服务**。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-127">In the Add LOB System window, click **Connect to Webservice**.</span></span>  
  
4.  <span data-ttu-id="eb8c7-128">在**URL**框中，键入 WCF 服务的 URL。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-128">In the **URL** box, type the URL for the WCF service.</span></span> <span data-ttu-id="eb8c7-129">对于本教程，则 URL 将为：</span><span class="sxs-lookup"><span data-stu-id="eb8c7-129">For this tutorial, the URL will be:</span></span>  
  
    ```  
    https://<COMPUTER_NAME>:<PORT_NUMBER>/MS_SAMPLE_EMPLOYEE/InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE.svc  
    ```  
  
     <span data-ttu-id="eb8c7-130">当你测试是否成功中, 所述发布 WCF 服务时，才可用 URL[步骤 1： 使用 Oracle E-business 适配器创建和发布 WCF 服务](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md)。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-130">The URL is available when you test whether the WCF service is published successfully, as described in [Step 1: Use the Oracle E-Business Adapter to Create and Publish a WCF Service](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md).</span></span>  
  
5.  <span data-ttu-id="eb8c7-131">单击 **“连接”**。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-131">Click **Connect**.</span></span>  
  
6.  <span data-ttu-id="eb8c7-132">若要查看在 WCF 适配器服务开发向导中选择的操作，请单击**添加 Web 方法**选项卡。你将看到以下方法：**选择**。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-132">To see the operations you selected in the WCF Adapter Service Development Wizard, click the **Add Web Method** tab. You will see the following method: **Select**.</span></span>  
  
7.  <span data-ttu-id="eb8c7-133">拖动**选择**到设计图面上的方法。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-133">Drag the **Select** methods to the Design Surface.</span></span> <span data-ttu-id="eb8c7-134">将方法拖到设计图面中，创建实体时，和方法将成为该实体的一部分。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-134">As you drag the method to the Design Surface, an entity is created, and the method becomes part of that entity.</span></span>  
  
     <span data-ttu-id="eb8c7-135">![将选择的方法添加到设计图面](../../adapters-and-accelerators/adapter-oracle-ebs/media/05-add-lob-system.gif "05_Add_LOB_System")</span><span class="sxs-lookup"><span data-stu-id="eb8c7-135">![Add Select method to the Design Surface](../../adapters-and-accelerators/adapter-oracle-ebs/media/05-add-lob-system.gif "05_Add_LOB_System")</span></span>  
  
8.  <span data-ttu-id="eb8c7-136">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-136">Click **OK**.</span></span>  
  
9. <span data-ttu-id="eb8c7-137">在**输入 LOB 系统的名称**对话框中，键入一个名称中**LOB 系统名称**框。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-137">In the **Enter the name for the LOB System** dialog box, type a name in the **LOB System Name** box.</span></span> <span data-ttu-id="eb8c7-138">此示例中，称之为**MS_SAMPLE_EMPLOYEE**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-138">For this example, call it **MS_SAMPLE_EMPLOYEE**, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="eb8c7-139">在业务数据目录定义编辑器中，新创建的实体被列为**Entity0**。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-139">In the Business Data Catalog Definition Editor, the newly created entity is listed as **Entity0**.</span></span> <span data-ttu-id="eb8c7-140">重命名该实体，**员工**。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-140">Rename the entity to **Employee**.</span></span> <span data-ttu-id="eb8c7-141">执行以下步骤以重命名实体：</span><span class="sxs-lookup"><span data-stu-id="eb8c7-141">Perform the following steps to rename the entity:</span></span>  
  
    1.  <span data-ttu-id="eb8c7-142">展开**MS_SAMPLE_EMPLOYEE**节点，然后展开**实体**节点。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-142">Expand the **MS_SAMPLE_EMPLOYEE** node, and then expand the **Entities** node.</span></span>  
  
    2.  <span data-ttu-id="eb8c7-143">选择**Entity0**节点。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-143">Select the **Entity0** node.</span></span>  
  
    3.  <span data-ttu-id="eb8c7-144">在属性窗格中，键入**员工**中**名称**框。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-144">In the Properties pane, type **Employee** in the **Name** box.</span></span>  
  
         <span data-ttu-id="eb8c7-145">![重命名实体](../../adapters-and-accelerators/adapter-oracle-ebs/media/06-entity-name.gif "06_Entity_Name")</span><span class="sxs-lookup"><span data-stu-id="eb8c7-145">![Rename the entity](../../adapters-and-accelerators/adapter-oracle-ebs/media/06-entity-name.gif "06_Entity_Name")</span></span>  
  
##  <a name="Headers"></a><span data-ttu-id="eb8c7-146">为方法中指定用户名和密码标头</span><span class="sxs-lookup"><span data-stu-id="eb8c7-146">Specify User Name and Password Headers for the Methods</span></span>  
 <span data-ttu-id="eb8c7-147">如果创建 Oracle E-business Suite MS_SAMPLE_EMPLOYEE 接口表上的选择操作的 WCF 服务，请指定用户名称和密码标头中的终结点行为配置的一部分[步骤 1： 使用 Oracle创建和发布 WCF 服务的电子商务适配器](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md)。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-147">When creating a WCF service for the Select operation on the MS_SAMPLE_EMPLOYEE interface table in Oracle E-Business Suite, you specified user name and password headers as part of the endpoint behavior configuration in [Step 1: Use the Oracle E-Business Adapter to Create and Publish a WCF Service](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md).</span></span> <span data-ttu-id="eb8c7-148">必须指定 Select 方法属性的相同值。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-148">You must specify the same values for the Select method property.</span></span>  
  
#### <a name="to-specify-user-name-and-password-headers-for-the-select-method"></a><span data-ttu-id="eb8c7-149">若要指定用户名称和密码标头的选择方法</span><span class="sxs-lookup"><span data-stu-id="eb8c7-149">To specify user name and password headers for the Select method</span></span>  
  
1.  <span data-ttu-id="eb8c7-150">在元数据对象窗格中，展开**员工**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-150">In the Metadata Objects pane, expand the **Employee** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="eb8c7-151">单击**选择**节点，然后在属性窗格中单击针对省略号 （...） 按钮**属性**框。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-151">Click the **Select** node, and in the Properties pane click the ellipsis (…) button against the **Properties** box.</span></span>  
  
3.  <span data-ttu-id="eb8c7-152">在 PropertyView 集合编辑器窗口中，单击**添加**，然后在属性窗格中，键入**HttpHeaderUserName**为**名称**框。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-152">In the PropertyView Collection Editor window, click **Add**, and in the Property pane, type **HttpHeaderUserName** for the **Name** box.</span></span> <span data-ttu-id="eb8c7-153">类型**MyUserHeader**为**PropertyValue**框。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-153">Type **MyUserHeader** for the **PropertyValue** box.</span></span> <span data-ttu-id="eb8c7-154">选择**System.String**为**类型**框。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-154">Select **System.String** for the **Type** box.</span></span>  
  
4.  <span data-ttu-id="eb8c7-155">在 PropertyView 集合编辑器窗口中，单击**添加**，然后在属性窗格中，键入**HttpHeaderPassword**为**名称**框。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-155">In the PropertyView Collection Editor window, click **Add**, and in the Property pane, type **HttpHeaderPassword** for the **Name** box.</span></span> <span data-ttu-id="eb8c7-156">同样，键入**MyPasswordHeader**为**PropertyValue**框。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-156">Similarly, type **MyPasswordHeader** for the **PropertyValue** box.</span></span> <span data-ttu-id="eb8c7-157">选择**System.String**为**类型**框。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-157">Select **System.String** for the **Type** box.</span></span>  
  
     <span data-ttu-id="eb8c7-158">![将属性添加](../../adapters-and-accelerators/adapter-oracle-ebs/media/07-propertviewcollection-editor.gif "07_PropertViewCollection_Editor")</span><span class="sxs-lookup"><span data-stu-id="eb8c7-158">![Add a property](../../adapters-and-accelerators/adapter-oracle-ebs/media/07-propertviewcollection-editor.gif "07_PropertViewCollection_Editor")</span></span>  
  
5.  <span data-ttu-id="eb8c7-159">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-159">Click **OK**.</span></span>  
  
##  <a name="Scenario1"></a><span data-ttu-id="eb8c7-160">使用业务数据列表 Web 部件的员工的方案 1： 查询</span><span class="sxs-lookup"><span data-stu-id="eb8c7-160">Scenario 1: Query for Employees using a Business Data List Web Part</span></span>  
 <span data-ttu-id="eb8c7-161">若要创建可用于搜索业务数据列表 Web 部件的员工和基于员工名称的应用程序定义文件，必须执行以下一组任务。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-161">To create an application definition file that can be used to search for employees from a Business Data List Web Part and based on employee name, you must perform the following set of tasks.</span></span>  
  
1.  <span data-ttu-id="eb8c7-162">在**选择**方法，创建筛选器，并将其映射到**筛选器**参数。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-162">In the **Select** method, create a filter and map it to the **FILTER** parameter.</span></span>  
  
2.  <span data-ttu-id="eb8c7-163">创建**Finder**方法实例**选择**方法。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-163">Create a **Finder** method instance for the **Select** method.</span></span> <span data-ttu-id="eb8c7-164">A **Finder**方法检索基于筛选器的记录的列表。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-164">A **Finder** method retrieves a list of records based on a filter.</span></span>  
  
#### <a name="to-create-a-filter-and-map-it-to-the-filter-parameter"></a><span data-ttu-id="eb8c7-165">创建筛选器，并将其映射到筛选器参数</span><span class="sxs-lookup"><span data-stu-id="eb8c7-165">To create a filter, and map it to the FILTER parameter</span></span>  
  
1.  <span data-ttu-id="eb8c7-166">创建筛选器。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-166">Create a filter.</span></span>  
  
    1.  <span data-ttu-id="eb8c7-167">在元数据对象窗格中，展开**员工**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-167">In the Metadata Objects pane, expand the **Employee** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="eb8c7-168">展开**选择**方法中，右键单击**筛选器**，然后单击**添加筛选器**。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-168">Expand the **Select** method, right-click **Filters**, and then click **Add Filter**.</span></span>  
  
         <span data-ttu-id="eb8c7-169">![将筛选器添加到选择的方法](../../adapters-and-accelerators/adapter-oracle-ebs/media/08-add-filter.gif "08_Add_Filter")</span><span class="sxs-lookup"><span data-stu-id="eb8c7-169">![Add a filter to the SELECT method](../../adapters-and-accelerators/adapter-oracle-ebs/media/08-add-filter.gif "08_Add_Filter")</span></span>  
  
    3.  <span data-ttu-id="eb8c7-170">在属性窗格中，为**FilterType**属性中，选择**等于**。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-170">In the Properties pane, for the **FilterType** property, select **Equals**.</span></span>  
  
    4.  <span data-ttu-id="eb8c7-171">在属性窗格中，键入**员工姓名**中**名称**框。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-171">In the Properties pane, type **EmployeeName** in the **Name** box.</span></span>  
  
         <span data-ttu-id="eb8c7-172">![指定筛选器属性](../../adapters-and-accelerators/adapter-oracle-ebs/media/09-filter-properties.gif "09_Filter_Properties")</span><span class="sxs-lookup"><span data-stu-id="eb8c7-172">![Specify filter properties](../../adapters-and-accelerators/adapter-oracle-ebs/media/09-filter-properties.gif "09_Filter_Properties")</span></span>  
  
2.  <span data-ttu-id="eb8c7-173">映射到筛选器**筛选器**中的参数**选择**方法。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-173">Map the filter to the **FILTER** parameter in the **Select** method.</span></span>  
  
    1.  <span data-ttu-id="eb8c7-174">在元数据对象窗格中，展开**员工**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-174">In the Metadata Objects pane, expand the **Employee** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="eb8c7-175">展开**选择**方法，然后展开**参数**节点。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-175">Expand the **Select** method, and then expand the **Parameters** node.</span></span>  
  
    3.  <span data-ttu-id="eb8c7-176">展开**筛选器**节点，然后单击第二个**筛选器**节点。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-176">Expand the **FILTER** node, and click the second **FILTER** node.</span></span>  
  
    4.  <span data-ttu-id="eb8c7-177">在属性窗格中，选择**员工姓名**从**FilterDescriptor**列表。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-177">In the Properties pane, select **EmployeeName** from the **FilterDescriptor** list.</span></span>  
  
         <span data-ttu-id="eb8c7-178">![映射到选择的方法参数的筛选器](../../adapters-and-accelerators/adapter-oracle-ebs/media/10-map-filter.gif "10_Map_Filter")</span><span class="sxs-lookup"><span data-stu-id="eb8c7-178">![Map the filter to the Select method parameter](../../adapters-and-accelerators/adapter-oracle-ebs/media/10-map-filter.gif "10_Map_Filter")</span></span>  
  
#### <a name="to-create-a-finder-method-instance-for-the-select-method"></a><span data-ttu-id="eb8c7-179">若要创建 Select 方法的 Finder 方法实例</span><span class="sxs-lookup"><span data-stu-id="eb8c7-179">To create a Finder method instance for the Select method</span></span>  
  
1.  <span data-ttu-id="eb8c7-180">在元数据对象窗格中，展开**员工**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-180">In the Metadata Objects pane, expand the **Employee** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="eb8c7-181">展开**选择**节点，右键单击**实例**，然后单击**添加方法实例**。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-181">Expand the **Select** node, right-click **Instances**, and then click **Add Method Instance**.</span></span>  
  
     <span data-ttu-id="eb8c7-182">![添加方法实例](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11_Add_Method_Instance")</span><span class="sxs-lookup"><span data-stu-id="eb8c7-182">![Add a method instance](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11_Add_Method_Instance")</span></span>  
  
3.  <span data-ttu-id="eb8c7-183">在创建方法实例窗口中，单击**Finder**为**方法实例类型**。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-183">In the Create Method Instance window, click **Finder** for **Method Instance Type**.</span></span> <span data-ttu-id="eb8c7-184">选择**返回**为**返回 TypeDescriptor**。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-184">Select **Return** for **Return TypeDescriptor**.</span></span>  
  
     <span data-ttu-id="eb8c7-185">![创建 Finder 方法实例](../../adapters-and-accelerators/adapter-oracle-ebs/media/12-create-method-instance.gif "12_Create_Method_Instance")</span><span class="sxs-lookup"><span data-stu-id="eb8c7-185">![Create a Finder method instance](../../adapters-and-accelerators/adapter-oracle-ebs/media/12-create-method-instance.gif "12_Create_Method_Instance")</span></span>  
  
4.  <span data-ttu-id="eb8c7-186">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-186">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="eb8c7-187">在属性窗格中，键入**Finder_Instance**中**名称**框。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-187">In the Properties pane, type **Finder_Instance** in the **Name** box.</span></span>  
  
     <span data-ttu-id="eb8c7-188">![指定的 Finder 方法实例的名称](../../adapters-and-accelerators/adapter-oracle-ebs/media/13-instance-property.gif "13_Instance_Property")</span><span class="sxs-lookup"><span data-stu-id="eb8c7-188">![Specify a name for the Finder method instance](../../adapters-and-accelerators/adapter-oracle-ebs/media/13-instance-property.gif "13_Instance_Property")</span></span>  
  
##  <a name="Scenario2"></a><span data-ttu-id="eb8c7-189">方案 2： 从 Microsoft Office SharePoint Server MS_SAMPLE_EMPLOYEE 接口表上的全文搜索</span><span class="sxs-lookup"><span data-stu-id="eb8c7-189">Scenario 2: Full-Text Search on MS_SAMPLE_EMPLOYEE Interface Table from Microsoft Office SharePoint Server</span></span>  
 <span data-ttu-id="eb8c7-190">若要创建应用程序定义文件可以用于从 Microsoft Office SharePoint Server MS_SAMPLE_EMPLOYEE 接口表上执行全文搜索，必须执行以下一组任务。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-190">To create an application definition file that can be used to perform a full-text search on MS_SAMPLE_EMPLOYEE interface table from Microsoft Office SharePoint Server, you must perform the following set of tasks.</span></span>  
  
-   <span data-ttu-id="eb8c7-191">在**选择**方法，创建一个标识符，并将其映射到筛选器参数和返回值，用于存储员工姓名。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-191">In the **Select** method, create an identifier, and map it to the FILTER parameter and the return value that stores the employee name.</span></span>  
  
-   <span data-ttu-id="eb8c7-192">创建**特定的 Finder**方法实例**选择**。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-192">Create a **Specific Finder** method instance for the **Select**.</span></span> <span data-ttu-id="eb8c7-193">**特定的 Finder**方法将查找特定记录基于标识符，即雇员姓名。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-193">The **Specific Finder** method will find a specific record based on the identifier, that is, an employee name.</span></span>  
  
-   <span data-ttu-id="eb8c7-194">创建一个 ID 枚举数方法实例。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-194">Create an ID Enumerator method instance.</span></span>  
  
#### <a name="to-create-an-identifier-and-map-it-to-the-filter-parameter-and-employee-name-return-value"></a><span data-ttu-id="eb8c7-195">创建一个标识符，并将其映射到筛选器参数和员工名称返回值</span><span class="sxs-lookup"><span data-stu-id="eb8c7-195">To create an identifier, and map it to the FILTER parameter and employee name return value</span></span>  
  
1.  <span data-ttu-id="eb8c7-196">创建的标识符**员工**实体。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-196">Create an identifier for the **Employee** entity.</span></span>  
  
    1.  <span data-ttu-id="eb8c7-197">在元数据对象窗格中，展开**员工**节点。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-197">In the Metadata Objects pane, expand the **Employee** node.</span></span>  
  
    2.  <span data-ttu-id="eb8c7-198">右键单击**标识符**节点，，然后选择**添加标识符**。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-198">Right-click the **Identifiers** node, and then select **Add Identifier**.</span></span>  
  
         <span data-ttu-id="eb8c7-199">![创建一个标识符](../../adapters-and-accelerators/adapter-oracle-ebs/media/14-create-identifier.gif "14_Create_Identifier")</span><span class="sxs-lookup"><span data-stu-id="eb8c7-199">![Create an Identifier](../../adapters-and-accelerators/adapter-oracle-ebs/media/14-create-identifier.gif "14_Create_Identifier")</span></span>  
  
    3.  <span data-ttu-id="eb8c7-200">在属性窗格中，键入**员工姓名**中**名称**框。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-200">In the Properties pane, type **EmployeeName** in the **Name** box.</span></span>  
  
    4.  <span data-ttu-id="eb8c7-201">选择**System.String**为**类型**框。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-201">Select **System.String** for the **Type** box.</span></span>  
  
         <span data-ttu-id="eb8c7-202">![指定标识符属性](../../adapters-and-accelerators/adapter-oracle-ebs/media/15-identifier-properties.gif "15_Identifier_Properties")</span><span class="sxs-lookup"><span data-stu-id="eb8c7-202">![Specify identifier properties](../../adapters-and-accelerators/adapter-oracle-ebs/media/15-identifier-properties.gif "15_Identifier_Properties")</span></span>  
  
2.  <span data-ttu-id="eb8c7-203">标识符映射到的筛选器参数**选择**方法。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-203">Map the identifier to the FILTER parameter for the **Select** method.</span></span>  
  
    1.  <span data-ttu-id="eb8c7-204">在元数据对象窗格中，展开**员工**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-204">In the Metadata Objects pane, expand the **Employee** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="eb8c7-205">展开**选择**方法，然后展开**参数**节点。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-205">Expand the **Select** method, and then expand the **Parameters** node.</span></span>  
  
    3.  <span data-ttu-id="eb8c7-206">展开**筛选器**参数，然后单击第二个**筛选器**节点。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-206">Expand the **FILTER** parameter, and then click the second **FILTER** node.</span></span>  
  
    4.  <span data-ttu-id="eb8c7-207">在属性窗格中，选择**员工姓名 [员工]**从**标识符**列表。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-207">In the Properties pane, select **EmployeeName[Employee]** from the **Identifier** list.</span></span>  
  
         <span data-ttu-id="eb8c7-208">![设置筛选器参数标识符](../../adapters-and-accelerators/adapter-oracle-ebs/media/16-set-identifier.gif "16_Set_Identifier")</span><span class="sxs-lookup"><span data-stu-id="eb8c7-208">![Setting identifier for the FILTER parameter](../../adapters-and-accelerators/adapter-oracle-ebs/media/16-set-identifier.gif "16_Set_Identifier")</span></span>  
  
3.  <span data-ttu-id="eb8c7-209">将标识符映射到的员工名称返回值。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-209">Map the identifier to the employee name return value.</span></span>  
  
    1.  <span data-ttu-id="eb8c7-210">在元数据对象窗格中，展开**员工**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-210">In the Metadata Objects pane, expand the **Employee** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="eb8c7-211">展开**选择**方法，然后展开**参数**节点。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-211">Expand the **Select** method, and then expand the **Parameters** node.</span></span>  
  
    3.  <span data-ttu-id="eb8c7-212">展开**返回**节点，然后第二个**返回**节点，则**项**节点，，然后单击**名称**节点。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-212">Expand the **Return** node, then the second **Return** node, then the **Item** node, and then click the **Name** node.</span></span>  
  
    4.  <span data-ttu-id="eb8c7-213">在属性窗格中，选择**员工姓名 [员工]**从**标识符**列表。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-213">In the Properties pane, select **EmployeeName[Employee]** from the **Identifier** list.</span></span>  
  
#### <a name="to-create-a-specific-finder-method-instance-for-the-select-method"></a><span data-ttu-id="eb8c7-214">若要创建特定的 Finder 方法实例选择的方法</span><span class="sxs-lookup"><span data-stu-id="eb8c7-214">To create a Specific Finder method instance for the Select method</span></span>  
  
1.  <span data-ttu-id="eb8c7-215">在元数据对象窗格中，展开**员工**节点，然后**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-215">In the Metadata Objects pane, expand the **Employee** node, and then the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="eb8c7-216">展开**选择**节点，右键单击**实例**，然后选择**添加方法实例**以打开创建方法实例窗口。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-216">Expand the **Select** node, right-click **Instances**, and then select **Add Method Instance** to open the Create Method Instance window.</span></span>  
  
     <span data-ttu-id="eb8c7-217">![添加方法实例](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11_Add_Method_Instance")</span><span class="sxs-lookup"><span data-stu-id="eb8c7-217">![Add a method instance](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11_Add_Method_Instance")</span></span>  
  
3.  <span data-ttu-id="eb8c7-218">在创建方法实例窗口中，选择**特定的 Finder**为**方法实例类型**。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-218">In the Create Method Instance window, select **Specific Finder** for **Method Instance Type**.</span></span> <span data-ttu-id="eb8c7-219">选择**返回**为**返回 TypeDescriptor**。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-219">Select **Return** for **Return TypeDescriptor**.</span></span>  
  
     <span data-ttu-id="eb8c7-220">![添加特定的 Finder 方法实例](../../adapters-and-accelerators/adapter-oracle-ebs/media/17-specific-finder.gif "17_Specific_Finder")</span><span class="sxs-lookup"><span data-stu-id="eb8c7-220">![Add a Specific Finder method instance](../../adapters-and-accelerators/adapter-oracle-ebs/media/17-specific-finder.gif "17_Specific_Finder")</span></span>  
  
4.  <span data-ttu-id="eb8c7-221">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-221">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="eb8c7-222">在属性窗格中，键入**SpeciFinder_Instance**为**名称**框。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-222">In the Properties pane, type **SpeciFinder_Instance** for the **Name** box.</span></span>  
  
#### <a name="to-create-an-id-enumerator-method-instance-for-the-select-method"></a><span data-ttu-id="eb8c7-223">若要创建 Select 方法 Id 枚举方法实例</span><span class="sxs-lookup"><span data-stu-id="eb8c7-223">To create an Id Enumerator method instance for the Select method</span></span>  
  
1.  <span data-ttu-id="eb8c7-224">在元数据对象窗格中，展开**员工**节点，然后**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-224">In the Metadata Objects pane, expand the **Employee** node, and then the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="eb8c7-225">展开**选择**节点，右键单击**实例**，然后选择**添加方法实例**以打开创建方法实例窗口。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-225">Expand the **Select** node, right-click **Instances**, and then select **Add Method Instance** to open the Create Method Instance window.</span></span>  
  
     <span data-ttu-id="eb8c7-226">![添加方法实例](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11_Add_Method_Instance")</span><span class="sxs-lookup"><span data-stu-id="eb8c7-226">![Add a method instance](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11_Add_Method_Instance")</span></span>  
  
3.  <span data-ttu-id="eb8c7-227">在创建方法实例窗口中，选择**Id 枚举器**为**方法实例类型**。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-227">In the Create Method Instance window, select **Id Enumerator** for **Method Instance Type**.</span></span> <span data-ttu-id="eb8c7-228">选择**返回**为**返回 TypeDescriptor**。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-228">Select **Return** for **Return TypeDescriptor**.</span></span>  
  
     <span data-ttu-id="eb8c7-229">![创建一个 Id 枚举数方法实例](../../adapters-and-accelerators/adapter-oracle-ebs/media/18-id-enumerator.gif "18_ID_Enumerator")</span><span class="sxs-lookup"><span data-stu-id="eb8c7-229">![Create an Id Enumerator method instance](../../adapters-and-accelerators/adapter-oracle-ebs/media/18-id-enumerator.gif "18_ID_Enumerator")</span></span>  
  
4.  <span data-ttu-id="eb8c7-230">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-230">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="eb8c7-231">在属性窗格中，键入**IDEnumerator_Instance**为**名称**框。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-231">In the Properties pane, type **IDEnumerator_Instance** for the **Name** box.</span></span>  
  
##  <a name="Defaults"></a><span data-ttu-id="eb8c7-232">设置默认参数的方法实例</span><span class="sxs-lookup"><span data-stu-id="eb8c7-232">Set Default Parameters for the Method Instances</span></span>  
 <span data-ttu-id="eb8c7-233">Select 方法要求你指定的列名称。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-233">The Select method requires you to specify the column names.</span></span> <span data-ttu-id="eb8c7-234">因此，你需要指定的默认值**COLUMN_NAMES**前面创建的 Finder、 特定的 Finder 和 Id 枚举器的方法实例的参数。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-234">Therefore, you need to specify a default value for the **COLUMN_NAMES** parameter for the Finder, Specific Finder, and Id Enumerator method instances created earlier.</span></span> <span data-ttu-id="eb8c7-235">此外，还应指定的默认值**筛选器**Id 枚举器方法实例的参数。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-235">Additionally, you should also specify a default value for the **FILTER** parameter for the Id Enumerator method instance.</span></span>  
  
#### <a name="to-set-the-default-parameters-for-the-method-instances"></a><span data-ttu-id="eb8c7-236">若要设置的方法实例的默认参数</span><span class="sxs-lookup"><span data-stu-id="eb8c7-236">To set the default parameters for the method instances</span></span>  
  
1.  <span data-ttu-id="eb8c7-237">在元数据对象窗格中，展开**员工**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-237">In the Metadata Objects pane, expand the **Employee** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="eb8c7-238">展开**选择**节点，然后展开**参数**节点。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-238">Expand the **Select** node, and then expand the **Parameters** node.</span></span>  
  
3.  <span data-ttu-id="eb8c7-239">展开**COLUMN_NAMES**节点，，然后选择**COLUMN_NAMES**参数。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-239">Expand the **COLUMN_NAMES** node, and then select the **COLUMN_NAMES** parameter.</span></span>  
  
4.  <span data-ttu-id="eb8c7-240">在属性窗格中，单击省略号按钮 （…） 针对**DefaultValues**框。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-240">In the Properties pane, click the ellipsis button (…) against the **DefaultValues** box.</span></span>  
  
5.  <span data-ttu-id="eb8c7-241">在**DefaultValueView 集合编辑器**对话框中，单击**添加**，在属性窗格中，单击**Finder_Instance**中**SelectMethodInstance**列表。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-241">In the **DefaultValueView Collection Editor** dialog box, click **Add**, and in the property pane, click **Finder_Instance** in the **SelectMethodInstance** list.</span></span>  
  
     <span data-ttu-id="eb8c7-242">![指定默认值为 Finder 实例](../../adapters-and-accelerators/adapter-oracle-ebs/media/19-finderinstance-defaults.gif "19_FinderInstance_Defaults")</span><span class="sxs-lookup"><span data-stu-id="eb8c7-242">![Specifying default value for the Finder instance](../../adapters-and-accelerators/adapter-oracle-ebs/media/19-finderinstance-defaults.gif "19_FinderInstance_Defaults")</span></span>  
  
6.  <span data-ttu-id="eb8c7-243">类型`*`中**值**框。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-243">Type `*` in the **Value** box.</span></span>  
  
7.  <span data-ttu-id="eb8c7-244">同样，重复步骤 5 和 6 以添加默认值**SpecificFinder_Instance**和**IDEnumerator_Instance**方法实例。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-244">Similarly, repeat steps 5 and 6 to add default values for the **SpecificFinder_Instance** and **IDEnumerator_Instance** method instances.</span></span>  
  
8.  <span data-ttu-id="eb8c7-245">在**DefaultValueView 集合编辑器**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-245">In the **DefaultValueView Collection Editor** dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="eb8c7-246">接下来，添加的默认值**筛选器**参数**IDEnumerator_Instance**方法实例。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-246">Next, add a default value for the **FILTER** parameter for the **IDEnumerator_Instance** method instance.</span></span> <span data-ttu-id="eb8c7-247">展开**筛选器**节点，，然后选择**筛选器**参数。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-247">Expand the **FILTER** node, and then select the **FILTER** parameter.</span></span>  
  
10. <span data-ttu-id="eb8c7-248">在属性窗格中，单击省略号按钮 （…） 针对**DefaultValues**框。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-248">In the Properties pane, click the ellipsis button (…) against the **DefaultValues** box.</span></span>  
  
11. <span data-ttu-id="eb8c7-249">在**DefaultValueView 集合编辑器**对话框中，单击**添加**，在属性窗格中，单击**IDEnumerator_Instance**中**SelectMethodInstance**列表。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-249">In the **DefaultValueView Collection Editor** dialog box, click **Add**, and in the property pane, click **IDEnumerator_Instance** in the **SelectMethodInstance** list.</span></span>  
  
12. <span data-ttu-id="eb8c7-250">类型`%`中**值**框。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-250">Type `%` in the **Value** box.</span></span>  
  
     <span data-ttu-id="eb8c7-251">![Id 枚举器实例的默认值](../../adapters-and-accelerators/adapter-oracle-ebs/media/20-idenumeratorinstance-defaults.gif "20_IDEnumeratorInstance_Defaults")</span><span class="sxs-lookup"><span data-stu-id="eb8c7-251">![Default values for the Id Enumerator instance](../../adapters-and-accelerators/adapter-oracle-ebs/media/20-idenumeratorinstance-defaults.gif "20_IDEnumeratorInstance_Defaults")</span></span>  
  
13. <span data-ttu-id="eb8c7-252">在**DefaultValueView 集合编辑器**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-252">In the **DefaultValueView Collection Editor** dialog box, click **OK**.</span></span>  
  
##  <a name="SSO"></a><span data-ttu-id="eb8c7-253">为连接到 Oracle E-business Suite 向上上单一登录设置</span><span class="sxs-lookup"><span data-stu-id="eb8c7-253">Set up Single Sign-On for Connecting to Oracle E-Business Suite</span></span>  
 <span data-ttu-id="eb8c7-254">在本主题中执行的所有过程完成后，你将创建可以导入 SharePoint 应用程序的应用程序定义文件。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-254">After you have finished performing all the procedures in this topic, you will have created an application definition file that can be imported into a SharePoint application.</span></span> <span data-ttu-id="eb8c7-255">从应用程序，你调用的方法从 Oracle E-business Suite 检索相关数据。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-255">From the application, you invoke the methods to retrieve relevant data from Oracle E-Business Suite.</span></span> <span data-ttu-id="eb8c7-256">若要启用此功能，必须在 SharePoint 应用程序中创建 Oracle E-business Suite 中的用户和用户之间的映射。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-256">To enable this, you must create a mapping between a user in the Oracle E-Business Suite and the user in the SharePoint application.</span></span> <span data-ttu-id="eb8c7-257">已导入的应用程序定义文件后，可以在 SharePoint 管理中心控制台中创建此映射。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-257">You create this mapping in SharePoint Central Administration console after you have imported the application definition file.</span></span>  
  
 <span data-ttu-id="eb8c7-258">但是，若要创建映射必须设置一个属性**SecondarySsoApplicationId**在业务数据目录定义编辑器中。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-258">However, to create the mapping you must set a property **SecondarySsoApplicationId** in the Business Data Catalog Definition Editor.</span></span>  
  
#### <a name="to-set-the-secondaryssoapplicationid-property"></a><span data-ttu-id="eb8c7-259">若要设置 SecondarySsoApplicationId 属性</span><span class="sxs-lookup"><span data-stu-id="eb8c7-259">To set the SecondarySsoApplicationId property</span></span>  
  
1.  <span data-ttu-id="eb8c7-260">在元数据对象窗格中，展开**MS_SAMPLE_EMPLOYEE**节点，然后展开**实例**节点。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-260">In the Metadata Objects pane, expand the **MS_SAMPLE_EMPLOYEE** node, and then expand the **Instances** node.</span></span>  
  
2.  <span data-ttu-id="eb8c7-261">单击**MS_SAMPLE_EMPLOYEE_Instance**，然后在属性窗格中，单击针对省略号 （...） 按钮**属性**框。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-261">Click **MS_SAMPLE_EMPLOYEE_Instance**, and in the Properties pane, click the ellipsis (…) button against the **Properties** box.</span></span>  
  
3.  <span data-ttu-id="eb8c7-262">在**PropertyView 集合编辑器**对话框中，单击**添加**，然后在属性窗格中，键入**SecondarySsoApplicationId**为**名称**框。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-262">In the **PropertyView Collection Editor** dialog box, click **Add**, and in the Property pane, type **SecondarySsoApplicationId** for the **Name** box.</span></span> <span data-ttu-id="eb8c7-263">同样，键入**OracleSSO**为**PropertyValue**框。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-263">Similarly, type **OracleSSO** for the **PropertyValue** box.</span></span> <span data-ttu-id="eb8c7-264">选择**System.String**为**类型**框。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-264">Select **System.String** for the **Type** box.</span></span>  
  
     <span data-ttu-id="eb8c7-265">![添加 SSO 属性](../../adapters-and-accelerators/adapter-oracle-ebs/media/21-sso.gif "21_SSO")</span><span class="sxs-lookup"><span data-stu-id="eb8c7-265">![Add the SSO Property](../../adapters-and-accelerators/adapter-oracle-ebs/media/21-sso.gif "21_SSO")</span></span>  
  
4.  <span data-ttu-id="eb8c7-266">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-266">Click **OK**.</span></span>  
  
##  <a name="Export"></a><span data-ttu-id="eb8c7-267">将应用程序定义导出到文件</span><span class="sxs-lookup"><span data-stu-id="eb8c7-267">Export the Application Definition to a File</span></span>  
 <span data-ttu-id="eb8c7-268">现在已创建包含 Oracle E-business Suite 实例元数据的应用程序定义。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-268">You have now created an application definition that contains Oracle E-Business Suite instance metadata.</span></span> <span data-ttu-id="eb8c7-269">必须将此定义导出到一个 XML 文件，其中可以导入到 Microsoft Office SharePoint Server。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-269">You must export this definition to an XML file, which can be imported into Microsoft Office SharePoint Server.</span></span>  
  
#### <a name="to-export-the-application-definition-to-a-file"></a><span data-ttu-id="eb8c7-270">若要将应用程序定义导出到文件</span><span class="sxs-lookup"><span data-stu-id="eb8c7-270">To export the application definition to a file</span></span>  
  
1.  <span data-ttu-id="eb8c7-271">在元数据对象窗格中，右键单击**MS_SAMPLE_EMPLOYEE**节点，，然后单击**导出**。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-271">In the Metadata Objects pane, right-click the **MS_SAMPLE_EMPLOYEE** node, and then click **Export**.</span></span>  
  
2.  <span data-ttu-id="eb8c7-272">将文件保存为 Employee.xml。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-272">Save the file as Employee.xml.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="eb8c7-273">后续步骤</span><span class="sxs-lookup"><span data-stu-id="eb8c7-273">Next Steps</span></span>  
 <span data-ttu-id="eb8c7-274">你现在必须创建 SharePoint 应用程序从 Oracle E-business Suite 检索数据。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-274">You must now create a SharePoint application to retrieve data from Oracle E-Business Suite.</span></span> <span data-ttu-id="eb8c7-275">有关说明，请参阅[步骤 3： 创建一个 SharePoint 应用程序检索数据从 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md)。</span><span class="sxs-lookup"><span data-stu-id="eb8c7-275">For instructions, see [Step 3: Create a SharePoint Application to Retrieve Data from Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb8c7-276">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb8c7-276">See Also</span></span>  
 [<span data-ttu-id="eb8c7-277">教程： 从 SharePoint 站点上的 Oracle E-business Suite 显示数据</span><span class="sxs-lookup"><span data-stu-id="eb8c7-277">Tutorial: Present Data from Oracle E-Business Suite on a SharePoint Site</span></span>](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)