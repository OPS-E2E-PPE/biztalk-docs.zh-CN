---
title: "步骤 2： 为 Siebel 业务组件操作创建应用程序定义文件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75d34c48-0f2a-42e4-a60b-e04bcf2404e1
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3bd1eaac434f4fc6bda55f6ab290740147d91997
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-create-an-application-definition-file-for-siebel-business-component-operations"></a><span data-ttu-id="bd368-102">步骤 2： 为 Siebel 业务组件操作创建应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="bd368-102">Step 2: Create an Application Definition File for Siebel Business Component Operations</span></span>
<span data-ttu-id="bd368-103">![步骤 2 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span><span class="sxs-lookup"><span data-stu-id="bd368-103">![Step 2 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span></span>  
  
 <span data-ttu-id="bd368-104">**完成时间：** 15 分钟</span><span class="sxs-lookup"><span data-stu-id="bd368-104">**Time to complete:** 15 minutes</span></span>  
  
 <span data-ttu-id="bd368-105">**目标：**业务数据目录公开，并将从-的业务线 (LOB) 应用程序的数据合并到门户。</span><span class="sxs-lookup"><span data-stu-id="bd368-105">**Objective:** The Business Data Catalog exposes and incorporates data from line-of-business (LOB) applications into portals.</span></span> <span data-ttu-id="bd368-106">若要将此数据合并到您的门户网站，必须在生成应用程序定义文件，可以使用 Microsoft Office SharePoint Server。</span><span class="sxs-lookup"><span data-stu-id="bd368-106">To incorporate this data into your portal site, you must build an application definition file that Microsoft Office SharePoint Server can consume.</span></span>  
  
 <span data-ttu-id="bd368-107">业务数据目录定义编辑器工具，可为业务数据目录中创建应用程序定义文件。</span><span class="sxs-lookup"><span data-stu-id="bd368-107">The Business Data Catalog Definition Editor tool enables you to create an application definition file for the Business Data Catalog.</span></span> <span data-ttu-id="bd368-108">此工具会自动生成的 XML 定义文件。</span><span class="sxs-lookup"><span data-stu-id="bd368-108">This tool automatically generates the XML for the definition file.</span></span> <span data-ttu-id="bd368-109">因此，无需手动创建该文件在 XML 编辑器。</span><span class="sxs-lookup"><span data-stu-id="bd368-109">Therefore, you do not have to manually create the file in an XML editor.</span></span>  
  
 <span data-ttu-id="bd368-110">要创建 Microsoft Office SharePoint Server 应用程序的目的是对执行查询操作帐户在业务组件，若要检索的记录列表。</span><span class="sxs-lookup"><span data-stu-id="bd368-110">The purpose of the Microsoft Office SharePoint Server application that you are creating is to perform a Query operation on the Account business component to retrieve a list of records.</span></span> <span data-ttu-id="bd368-111">若要实现此目的，必须完成一的组任务在业务数据目录定义编辑器中。</span><span class="sxs-lookup"><span data-stu-id="bd368-111">To achieve this, you must complete a set of tasks in the Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="bd368-112">本主题提供有关如何执行这些任务的说明。</span><span class="sxs-lookup"><span data-stu-id="bd368-112">This topic provides instructions on how to perform these tasks.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bd368-113">先决条件</span><span class="sxs-lookup"><span data-stu-id="bd368-113">Prerequisites</span></span>  
  
-   <span data-ttu-id="bd368-114">你必须作为 Microsoft Office SharePoint Server 2007 SDK 的一部分安装的业务数据目录定义编辑器。</span><span class="sxs-lookup"><span data-stu-id="bd368-114">You must have the Business Data Catalog Definition Editor installed as part of the Microsoft Office SharePoint Server 2007 SDK.</span></span> <span data-ttu-id="bd368-115">你可以下载 SDK 从[http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130)。</span><span class="sxs-lookup"><span data-stu-id="bd368-115">You can download the SDK from [http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130).</span></span>  
  
-   <span data-ttu-id="bd368-116">你应已发布 WCF 服务中所述[步骤 1： 发布 Siebel 业务组件操作作为 WCF 服务](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md)。</span><span class="sxs-lookup"><span data-stu-id="bd368-116">You should have published the WCF service, as described in [Step 1: Publish the Siebel Business Component Operations as a WCF Service](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md).</span></span>  
  
## <a name="creating-an-application-definition-file"></a><span data-ttu-id="bd368-117">创建应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="bd368-117">Creating an Application Definition File</span></span>  
 <span data-ttu-id="bd368-118">本部分提供分步说明来创建 WCF 服务应用程序定义文件。</span><span class="sxs-lookup"><span data-stu-id="bd368-118">This section provides step-by-step instructions to create an application definition file for the WCF service.</span></span>  
  
### <a name="connect-to-the-wcf-service-and-create-entities"></a><span data-ttu-id="bd368-119">连接到 WCF 服务，并创建实体</span><span class="sxs-lookup"><span data-stu-id="bd368-119">Connect to the WCF Service, and Create Entities</span></span>  
 <span data-ttu-id="bd368-120">你必须连接到要提取 Web 服务描述语言 (WSDL) 服务的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="bd368-120">You must connect to the WCF service to extract the Web Services Description Language (WSDL) for the service.</span></span> <span data-ttu-id="bd368-121">从 WSDL，业务数据目录定义编辑器中提取方法。</span><span class="sxs-lookup"><span data-stu-id="bd368-121">From the WSDL, the Business Data Catalog Definition Editor extracts the methods.</span></span> <span data-ttu-id="bd368-122">这些方法可以用于创建实体。</span><span class="sxs-lookup"><span data-stu-id="bd368-122">These methods can be used to create entities.</span></span> <span data-ttu-id="bd368-123">对于此示例中，你必须创建查询操作帐户在业务组件上的一个实体。</span><span class="sxs-lookup"><span data-stu-id="bd368-123">For this example, you must create one entity for the Query operation on the Account business component.</span></span>  
  
##### <a name="to-connect-to-the-wcf-service-and-create-entities"></a><span data-ttu-id="bd368-124">若要连接到 WCF 服务，并创建实体</span><span class="sxs-lookup"><span data-stu-id="bd368-124">To connect to the WCF service, and create entities</span></span>  
  
1.  <span data-ttu-id="bd368-125">启动业务数据目录定义编辑器。</span><span class="sxs-lookup"><span data-stu-id="bd368-125">Start the Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="bd368-126">上**启动**菜单上，单击**Microsoft 业务数据目录定义编辑器**。</span><span class="sxs-lookup"><span data-stu-id="bd368-126">On the **Start** menu, click **Microsoft Business Data Catalog Definition Editor**.</span></span>  
  
2.  <span data-ttu-id="bd368-127">在工具中，单击**添加 LOB 系统**。</span><span class="sxs-lookup"><span data-stu-id="bd368-127">In the tool, click **Add LOB System**.</span></span>  
  
3.  <span data-ttu-id="bd368-128">在添加 LOB 系统窗口中，单击**连接到 web 服务**。</span><span class="sxs-lookup"><span data-stu-id="bd368-128">In the Add LOB System window, click **Connect to Webservice**.</span></span>  
  
4.  <span data-ttu-id="bd368-129">在 URL 框中，键入 WCF 服务的 URL。</span><span class="sxs-lookup"><span data-stu-id="bd368-129">In the URL box, type the URL for the WCF service.</span></span> <span data-ttu-id="bd368-130">该 URL 必须采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="bd368-130">The URL must be in the following format:</span></span>  
  
    ```  
    https://<computer_name>/Siebel_Account/BusinessObjects_Account_Account_Operation.svc?wsdl  
    ```  
  
     <span data-ttu-id="bd368-131">其中，BusinessObjects_Account_Account_Operation.svc 是创建 Siebel 协定的服务文件。</span><span class="sxs-lookup"><span data-stu-id="bd368-131">where, BusinessObjects_Account_Account_Operation.svc is the service file created for the Siebel contract.</span></span>  
  
     <span data-ttu-id="bd368-132">当你测试是否成功中, 所述发布 WCF 服务时，必须键入的 URL 才可用[步骤 1： 发布 Siebel 业务组件操作作为 WCF 服务](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md)。</span><span class="sxs-lookup"><span data-stu-id="bd368-132">The URL that you must type is available when you test whether the WCF service is published successfully, as described in [Step 1: Publish the Siebel Business Component Operations as a WCF Service](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md).</span></span>  
  
5.  <span data-ttu-id="bd368-133">单击 **“连接”**。</span><span class="sxs-lookup"><span data-stu-id="bd368-133">Click **Connect**.</span></span>  
  
6.  <span data-ttu-id="bd368-134">单击**添加 Web 方法**选项卡以查看在 WCF 适配器服务开发向导中选择的操作。</span><span class="sxs-lookup"><span data-stu-id="bd368-134">Click the **Add Web Method** tab to see the operations you selected in the WCF Adapter Service Development Wizard.</span></span> <span data-ttu-id="bd368-135">你将看到**查询**方法。</span><span class="sxs-lookup"><span data-stu-id="bd368-135">You will see the **Query** method.</span></span>  
  
     <span data-ttu-id="bd368-136">![将 web 方法添加到 BDC 应用程序](../../adapters-and-accelerators/adapter-siebel/media/f9505cd3-67e3-4f99-b189-d010322a3137.gif "f9505cd3-67e3-4f99-b189-d010322a3137")</span><span class="sxs-lookup"><span data-stu-id="bd368-136">![Add web methods to BDC application](../../adapters-and-accelerators/adapter-siebel/media/f9505cd3-67e3-4f99-b189-d010322a3137.gif "f9505cd3-67e3-4f99-b189-d010322a3137")</span></span>  
  
7.  <span data-ttu-id="bd368-137">拖动**查询**方法到设计图面，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="bd368-137">Drag the **Query** method to the design surface and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="bd368-138">在**输入 LOB 系统的名称**对话框中，键入一个名称中**LOB 系统名称**框。</span><span class="sxs-lookup"><span data-stu-id="bd368-138">In the **Enter the name for the LOB System** dialog box, type a name in the **LOB System Name** box.</span></span> <span data-ttu-id="bd368-139">对于此示例中，键入`Siebel_Account`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="bd368-139">For this example, type `Siebel_Account`, and then click **OK**.</span></span> <span data-ttu-id="bd368-140">一个实体， **Entity0**，创建在业务数据目录定义编辑器中。</span><span class="sxs-lookup"><span data-stu-id="bd368-140">An entity, **Entity0**, is created in the Business Data Catalog Definition Editor.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="bd368-141">业务数据目录定义编辑器工具并不处理枚举的数据类型。</span><span class="sxs-lookup"><span data-stu-id="bd368-141">The Business Data Catalog Definition Editor tool does not handle enumerated data types.</span></span> <span data-ttu-id="bd368-142">因此，业务数据目录定义编辑器工具导入字段直到它遇到枚举的数据类型，并忽略其余的字段。</span><span class="sxs-lookup"><span data-stu-id="bd368-142">So, the Business Data Catalog Definition Editor tool imports the fields till it encounters an enumerated data type and ignores the remaining fields.</span></span> <span data-ttu-id="bd368-143">业务数据目录定义编辑器工具还提供了一个错误。</span><span class="sxs-lookup"><span data-stu-id="bd368-143">The Business Data Catalog Definition Editor tool also gives an error.</span></span> <span data-ttu-id="bd368-144">你可以忽略此错误，然后通过单击确定继续。</span><span class="sxs-lookup"><span data-stu-id="bd368-144">You can ignore this error and proceed by clicking OK.</span></span> <span data-ttu-id="bd368-145">你可以手动添加必填的字段在应用程序定义文件中在更高版本的阶段。</span><span class="sxs-lookup"><span data-stu-id="bd368-145">You can manually add the required fields in the application definition file at a later stage.</span></span>  
  
9. <span data-ttu-id="bd368-146">更改要使用更多的友好名称的实体名称。</span><span class="sxs-lookup"><span data-stu-id="bd368-146">Change the entity names to use more friendly names.</span></span> <span data-ttu-id="bd368-147">对于此示例中，更改**Entity0**到**帐户**。</span><span class="sxs-lookup"><span data-stu-id="bd368-147">For this example, change **Entity0** to **Account**.</span></span>  
  
    1.  <span data-ttu-id="bd368-148">展开**Siebel_Account**节点，然后展开**实体**节点。</span><span class="sxs-lookup"><span data-stu-id="bd368-148">Expand the **Siebel_Account** node, and then expand the **Entities** node.</span></span>  
  
    2.  <span data-ttu-id="bd368-149">选择**Entity0**节点。</span><span class="sxs-lookup"><span data-stu-id="bd368-149">Select the **Entity0** node.</span></span>  
  
    3.  <span data-ttu-id="bd368-150">在属性窗格中，键入**帐户**中**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="bd368-150">In the Properties pane, type **Account** in the **Name** field.</span></span>  
  
         <span data-ttu-id="bd368-151">![重命名实体](../../adapters-and-accelerators/adapter-siebel/media/44eda1de-b348-4421-9c51-0355b51f4a90.gif "44eda1de-b348-4421-9c51-0355b51f4a90")</span><span class="sxs-lookup"><span data-stu-id="bd368-151">![Rename the entity](../../adapters-and-accelerators/adapter-siebel/media/44eda1de-b348-4421-9c51-0355b51f4a90.gif "44eda1de-b348-4421-9c51-0355b51f4a90")</span></span>  
  
### <a name="specify-user-name-and-password-headers-for-methods"></a><span data-ttu-id="bd368-152">为方法中指定用户名和密码标头</span><span class="sxs-lookup"><span data-stu-id="bd368-152">Specify User Name and Password Headers for Methods</span></span>  
 <span data-ttu-id="bd368-153">当 Siebel 系统中创建所选的业务组件操作的 WCF 服务，你指定用户名称和密码标头为终结点行为配置的一部分 ([步骤 1： 发布 Siebel 业务组件操作作为 WCF 服务](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md))。</span><span class="sxs-lookup"><span data-stu-id="bd368-153">When creating a WCF service for the selected business component operations in the Siebel system, you specified user name and password headers as part of the endpoint behavior configuration ([Step 1: Publish the Siebel Business Component Operations as a WCF Service](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md)).</span></span> <span data-ttu-id="bd368-154">必须指定方法属性的相同值。</span><span class="sxs-lookup"><span data-stu-id="bd368-154">You must specify the same values for the method properties.</span></span>  
  
##### <a name="to-specify-user-name-and-password-headers-for-the-query-method"></a><span data-ttu-id="bd368-155">若要指定用户名称和密码标头的查询方法</span><span class="sxs-lookup"><span data-stu-id="bd368-155">To specify user name and password headers for the Query method</span></span>  
  
1.  <span data-ttu-id="bd368-156">在元数据对象窗格中，展开**帐户**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="bd368-156">In the Metadata Objects pane, expand the **Account** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="bd368-157">单击**查询**节点，然后在属性窗格中单击针对省略号 （...） 按钮**属性**字段。</span><span class="sxs-lookup"><span data-stu-id="bd368-157">Click the **Query** node, and in the Properties pane click the ellipsis (…) button against the **Properties** field.</span></span>  
  
3.  <span data-ttu-id="bd368-158">在 PropertyView 集合编辑器对话框中，单击**添加**，然后在属性窗格中，键入`HttpHeaderUserName`为**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="bd368-158">In the PropertyView Collection Editor dialog box, click **Add**, and in the Properties pane, type `HttpHeaderUserName` for the **Name** field.</span></span> <span data-ttu-id="bd368-159">同样，键入`MyUserHeader`为**PropertyValue**字段。</span><span class="sxs-lookup"><span data-stu-id="bd368-159">Similarly, type `MyUserHeader` for the **PropertyValue** field.</span></span> <span data-ttu-id="bd368-160">选择**System.String**为**类型**字段。</span><span class="sxs-lookup"><span data-stu-id="bd368-160">Select **System.String** for the **Type** field.</span></span>  
  
     <span data-ttu-id="bd368-161">![将属性添加](../../adapters-and-accelerators/adapter-sap/media/9eef32ac-8a93-45dc-8d07-12b7dbf961ba.gif "9eef32ac-8a93-45dc-8d07-12b7dbf961ba")</span><span class="sxs-lookup"><span data-stu-id="bd368-161">![Add a property](../../adapters-and-accelerators/adapter-sap/media/9eef32ac-8a93-45dc-8d07-12b7dbf961ba.gif "9eef32ac-8a93-45dc-8d07-12b7dbf961ba")</span></span>  
  
4.  <span data-ttu-id="bd368-162">在 PropertyView 集合编辑器窗口中，单击**添加**，然后在属性窗格中，键入`HttpHeaderPassword`为**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="bd368-162">In the PropertyView Collection Editor window, click **Add**, and in the Properties pane, type `HttpHeaderPassword` for the **Name** field.</span></span> <span data-ttu-id="bd368-163">同样，键入`MyPassHeader`为**PropertyValue**字段。</span><span class="sxs-lookup"><span data-stu-id="bd368-163">Similarly, type `MyPassHeader` for the **PropertyValue** field.</span></span> <span data-ttu-id="bd368-164">选择**System.String**为**类型**字段。</span><span class="sxs-lookup"><span data-stu-id="bd368-164">Select **System.String** for the **Type** field.</span></span>  
  
5.  <span data-ttu-id="bd368-165">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="bd368-165">Click **OK**.</span></span>  
  
### <a name="set-up-single-sign-on-for-connecting-to-a-siebel-system"></a><span data-ttu-id="bd368-166">为连接到 Siebel 系统上单一登录设置</span><span class="sxs-lookup"><span data-stu-id="bd368-166">Set up Single Sign-On for Connecting to a Siebel System</span></span>  
 <span data-ttu-id="bd368-167">在本主题中执行的所有过程完成后，你将创建的应用程序定义可导入 SharePoint 应用程序的 XML。</span><span class="sxs-lookup"><span data-stu-id="bd368-167">After you have finished performing all the procedures in this topic, you will have created an application definition XML that can be imported into a SharePoint application.</span></span> <span data-ttu-id="bd368-168">从应用程序，将调用 （作为 Web 方法公开） 的 Siebel 业务组件操作从 Siebel 系统中检索相关数据。</span><span class="sxs-lookup"><span data-stu-id="bd368-168">From the application, you will invoke the Siebel business component operations (exposed as Web methods) to retrieve relevant data from the Siebel system.</span></span> <span data-ttu-id="bd368-169">若要启用此功能，必须在 SharePoint 应用程序中创建 Siebel 系统中的用户和用户之间的映射。</span><span class="sxs-lookup"><span data-stu-id="bd368-169">To enable this, you must create a mapping between a user in the Siebel system and the user in the SharePoint application.</span></span> <span data-ttu-id="bd368-170">已导入的应用程序定义 XML 后，可以在 SharePoint 管理中心网站中创建此映射。</span><span class="sxs-lookup"><span data-stu-id="bd368-170">You create this mapping in SharePoint Central Administration Web site after you have imported the application definition XML.</span></span>  
  
 <span data-ttu-id="bd368-171">但是，若要创建映射必须设置一个属性**SecondarySsoApplicationId**在业务数据目录定义编辑器中。</span><span class="sxs-lookup"><span data-stu-id="bd368-171">However, to create the mapping you must set a property **SecondarySsoApplicationId** in the Business Data Catalog Definition Editor.</span></span>  
  
##### <a name="to-set-the-secondaryssoapplicationid-property"></a><span data-ttu-id="bd368-172">若要设置 SecondarySsoApplicationId 属性</span><span class="sxs-lookup"><span data-stu-id="bd368-172">To set the SecondarySsoApplicationId property</span></span>  
  
1.  <span data-ttu-id="bd368-173">在元数据对象窗格中，展开**Siebel_Account**节点，然后展开**实例**节点。</span><span class="sxs-lookup"><span data-stu-id="bd368-173">In the Metadata Objects pane, expand the **Siebel_Account** node, and then expand the **Instances** node.</span></span>  
  
2.  <span data-ttu-id="bd368-174">单击**Siebel_Account_Instance**在属性窗格中单击省略号 （…） 按钮针对**属性**字段。</span><span class="sxs-lookup"><span data-stu-id="bd368-174">Click **Siebel_Account_Instance** and in the Properties pane click the ellipsis (…) button against the **Properties** field.</span></span>  
  
3.  <span data-ttu-id="bd368-175">在 PropertyView 集合编辑器窗口中，单击**添加**，然后在属性窗格中，键入**SecondarySsoApplicationId**为**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="bd368-175">In the PropertyView Collection Editor window, click **Add**, and in the Properties pane, type **SecondarySsoApplicationId** for the **Name** field.</span></span> <span data-ttu-id="bd368-176">同样，键入**SiebelSSO**为**PropertyValue**字段。</span><span class="sxs-lookup"><span data-stu-id="bd368-176">Similarly, type **SiebelSSO** for the **PropertyValue** field.</span></span> <span data-ttu-id="bd368-177">选择**System.String**为**类型**字段。</span><span class="sxs-lookup"><span data-stu-id="bd368-177">Select **System.String** for the **Type** field.</span></span>  
  
     <span data-ttu-id="bd368-178">![添加 SSO 属性](../../adapters-and-accelerators/adapter-siebel/media/59ce70eb-498f-406b-965d-c273c2d6ed14.gif "59ce70eb-498f-406b-965d-c273c2d6ed14")</span><span class="sxs-lookup"><span data-stu-id="bd368-178">![Add the SSO property](../../adapters-and-accelerators/adapter-siebel/media/59ce70eb-498f-406b-965d-c273c2d6ed14.gif "59ce70eb-498f-406b-965d-c273c2d6ed14")</span></span>  
  
4.  <span data-ttu-id="bd368-179">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="bd368-179">Click **OK**.</span></span>  
  
### <a name="requirement-perform-a-query-operation-on-the-account-business-component"></a><span data-ttu-id="bd368-180">要求： 执行帐户在业务组件上的查询操作</span><span class="sxs-lookup"><span data-stu-id="bd368-180">Requirement: Perform a Query Operation on the Account Business Component</span></span>  
 <span data-ttu-id="bd368-181">此示例的第一个要求是创建用于执行查询操作帐户在业务组件上的应用程序定义。</span><span class="sxs-lookup"><span data-stu-id="bd368-181">The first requirement of this example is to create an application definition that can be used to perform a Query operation on the Account business component.</span></span> <span data-ttu-id="bd368-182">若要实现此要求，必须执行以下一组任务：</span><span class="sxs-lookup"><span data-stu-id="bd368-182">To achieve this requirement, you must perform the following set of tasks:</span></span>  
  
-   <span data-ttu-id="bd368-183">在查询方法中，创建筛选器，并将其映射到对其执行查询操作的参数。</span><span class="sxs-lookup"><span data-stu-id="bd368-183">In the Query method, create a filter, and map it to the parameter on which the Query operation is performed.</span></span> <span data-ttu-id="bd368-184">对于帐户业务组件，你将执行查询时使用**SearchExpr**参数。</span><span class="sxs-lookup"><span data-stu-id="bd368-184">For the Account business component, you will perform a query using the **SearchExpr** parameter.</span></span> <span data-ttu-id="bd368-185">因此，将映射到筛选器**SearchExpr**参数。</span><span class="sxs-lookup"><span data-stu-id="bd368-185">So, you will map the filter to the **SearchExpr** parameter.</span></span>  
  
-   <span data-ttu-id="bd368-186">创建查询方法的 Finder 方法实例。</span><span class="sxs-lookup"><span data-stu-id="bd368-186">Create a Finder method instance for the Query method.</span></span> <span data-ttu-id="bd368-187">Finder 方法检索基于筛选器的记录的列表。</span><span class="sxs-lookup"><span data-stu-id="bd368-187">A Finder method retrieves a list of records based on a filter.</span></span>  
  
##### <a name="to-create-a-filter-and-map-it-to-the-searchexpr-parameter"></a><span data-ttu-id="bd368-188">创建筛选器，并将其映射到 SearchExpr 参数</span><span class="sxs-lookup"><span data-stu-id="bd368-188">To create a filter, and map it to the SearchExpr parameter</span></span>  
  
1.  <span data-ttu-id="bd368-189">创建筛选器的查询方法。</span><span class="sxs-lookup"><span data-stu-id="bd368-189">Create a filter for the Query method.</span></span>  
  
    1.  <span data-ttu-id="bd368-190">在元数据对象窗格中，展开**帐户**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="bd368-190">In the Metadata Objects pane, expand the **Account** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="bd368-191">展开的查询方法中，右键单击**筛选器**，然后单击**添加筛选器**。</span><span class="sxs-lookup"><span data-stu-id="bd368-191">Expand the Query method, right-click **Filters**, and then click **Add Filter**.</span></span>  
  
         <span data-ttu-id="bd368-192">![向方法添加筛选器](../../adapters-and-accelerators/adapter-siebel/media/9cf7ccfd-6da0-44b7-b522-df327a74e7a2.gif "9cf7ccfd-6da0-44b7-b522-df327a74e7a2")</span><span class="sxs-lookup"><span data-stu-id="bd368-192">![Add filter to a method](../../adapters-and-accelerators/adapter-siebel/media/9cf7ccfd-6da0-44b7-b522-df327a74e7a2.gif "9cf7ccfd-6da0-44b7-b522-df327a74e7a2")</span></span>  
  
    3.  <span data-ttu-id="bd368-193">在属性窗格中，键入`SearchExpression`为**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="bd368-193">In the Properties pane, type `SearchExpression` for the **Name** field.</span></span>  
  
    4.  <span data-ttu-id="bd368-194">有关**FilterType**属性中，选择**等于**。</span><span class="sxs-lookup"><span data-stu-id="bd368-194">For the **FilterType** property, select **Equals**.</span></span>  
  
         <span data-ttu-id="bd368-195">![指定筛选器名称和类型](../../adapters-and-accelerators/adapter-siebel/media/9faa18e1-4d27-4ee4-960a-458f978812a7.gif "9faa18e1-4d27-4ee4-960a-458f978812a7")</span><span class="sxs-lookup"><span data-stu-id="bd368-195">![Specify a filter name and type](../../adapters-and-accelerators/adapter-siebel/media/9faa18e1-4d27-4ee4-960a-458f978812a7.gif "9faa18e1-4d27-4ee4-960a-458f978812a7")</span></span>  
  
2.  <span data-ttu-id="bd368-196">映射到筛选器**SearchExpr**查询方法中的参数。</span><span class="sxs-lookup"><span data-stu-id="bd368-196">Map the filter to the **SearchExpr** parameter in the Query method.</span></span>  
  
    1.  <span data-ttu-id="bd368-197">在元数据对象窗格中，展开**帐户**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="bd368-197">In the Metadata Objects pane, expand the **Account** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="bd368-198">展开查询方法，然后展开**参数**节点。</span><span class="sxs-lookup"><span data-stu-id="bd368-198">Expand the Query method, and then expand the **Parameters** node.</span></span>  
  
    3.  <span data-ttu-id="bd368-199">展开**AccountQueryInputRecord**节点，然后展开第二个**AccountQueryInputRecord**节点。</span><span class="sxs-lookup"><span data-stu-id="bd368-199">Expand the **AccountQueryInputRecord** node, and then expand the second **AccountQueryInputRecord** node.</span></span>  
  
    4.  <span data-ttu-id="bd368-200">单击**SearchExpr**节点，然后在属性窗格中，选择**SearchExpression**从**FilterDescriptor**列表。</span><span class="sxs-lookup"><span data-stu-id="bd368-200">Click the **SearchExpr** node and in the Properties pane, select **SearchExpression** from the **FilterDescriptor**list.</span></span>  
  
         <span data-ttu-id="bd368-201">![将参数映射到筛选器](../../adapters-and-accelerators/adapter-siebel/media/199c8ba7-d0e8-4fb4-9d73-9cf548512498.gif "199c8ba7-d0e8-4fb4-9d73-9cf548512498")</span><span class="sxs-lookup"><span data-stu-id="bd368-201">![Map a parameter to a filter](../../adapters-and-accelerators/adapter-siebel/media/199c8ba7-d0e8-4fb4-9d73-9cf548512498.gif "199c8ba7-d0e8-4fb4-9d73-9cf548512498")</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="bd368-202">**AccountQueryInputRecord**还包含**QueryFields**节点，后者又包含**项**节点。</span><span class="sxs-lookup"><span data-stu-id="bd368-202">The **AccountQueryInputRecord** also contains a **QueryFields** node, which in turn contains an **Item** node.</span></span> <span data-ttu-id="bd368-203">你必须删除**项**节点，否则帐户在业务组件上的查询操作可能不会得到所需的结果。</span><span class="sxs-lookup"><span data-stu-id="bd368-203">You must delete the **Item** node, otherwise the Query operation on the Account business component might not give the desired results.</span></span> <span data-ttu-id="bd368-204">若要删除**项**节点，右键单击该节点，然后选择**删除**。</span><span class="sxs-lookup"><span data-stu-id="bd368-204">To delete the **Item** node, right-click the node, and then select **Delete**.</span></span>  
  
##### <a name="to-create-a-finder-method-instance-for-query-method"></a><span data-ttu-id="bd368-205">若要创建查询方法的 Finder 方法实例</span><span class="sxs-lookup"><span data-stu-id="bd368-205">To create a Finder method instance for Query method</span></span>  
  
1.  <span data-ttu-id="bd368-206">在元数据对象窗格中，展开**帐户**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="bd368-206">In the Metadata Objects pane, expand the **Account** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="bd368-207">展开**查询**节点，右键单击**实例**，然后单击**添加方法实例**以打开创建方法实例窗口。</span><span class="sxs-lookup"><span data-stu-id="bd368-207">Expand the **Query** node, right-click **Instances**, and then click **Add Method Instance** to open the Create Method Instance window.</span></span>  
  
     <span data-ttu-id="bd368-208">![添加 Finder 方法实例](../../adapters-and-accelerators/adapter-siebel/media/c90e7784-4fb7-4eb5-baf5-efbefba4bb1f.gif "c90e7784-4fb7-4eb5-baf5-efbefba4bb1f")</span><span class="sxs-lookup"><span data-stu-id="bd368-208">![Add a Finder method instance](../../adapters-and-accelerators/adapter-siebel/media/c90e7784-4fb7-4eb5-baf5-efbefba4bb1f.gif "c90e7784-4fb7-4eb5-baf5-efbefba4bb1f")</span></span>  
  
3.  <span data-ttu-id="bd368-209">在创建方法实例窗口中，单击**Finder**为**方法实例类型**。</span><span class="sxs-lookup"><span data-stu-id="bd368-209">In the Create Method Instance window, click **Finder** for the **Method Instance Type**.</span></span>  
  
4.  <span data-ttu-id="bd368-210">单击**返回**从**返回 TypeDescriptor**部分。</span><span class="sxs-lookup"><span data-stu-id="bd368-210">Click **Return** from **Return TypeDescriptor** section.</span></span>  
  
     <span data-ttu-id="bd368-211">![添加 Finder 方法实例](../../adapters-and-accelerators/adapter-siebel/media/e8343988-d7c1-4b04-85b0-ca7d07097490.gif "e8343988-d7c1-4b04-85b0-ca7d07097490")</span><span class="sxs-lookup"><span data-stu-id="bd368-211">![Add a Finder method instance](../../adapters-and-accelerators/adapter-siebel/media/e8343988-d7c1-4b04-85b0-ca7d07097490.gif "e8343988-d7c1-4b04-85b0-ca7d07097490")</span></span>  
  
5.  <span data-ttu-id="bd368-212">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="bd368-212">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="bd368-213">在属性窗格中，键入`QueryAccount`为**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="bd368-213">In the Properties pane, type `QueryAccount` for the **Name** field.</span></span>  
  
     <span data-ttu-id="bd368-214">![指定方法实例的名称](../../adapters-and-accelerators/adapter-siebel/media/401223f3-806f-4010-8646-d5ac0c0e9f67.gif "401223f3-806f-4010-8646-d5ac0c0e9f67")</span><span class="sxs-lookup"><span data-stu-id="bd368-214">![Specify a name for the method instance](../../adapters-and-accelerators/adapter-siebel/media/401223f3-806f-4010-8646-d5ac0c0e9f67.gif "401223f3-806f-4010-8646-d5ac0c0e9f67")</span></span>  
  
### <a name="remove-the-parameters-of-systemnullable-type"></a><span data-ttu-id="bd368-215">删除 System.Nullable 类型的参数</span><span class="sxs-lookup"><span data-stu-id="bd368-215">Remove the Parameters of System.Nullable Type</span></span>  
 <span data-ttu-id="bd368-216">查询函数的返回参数可能包含属于 System.Nullable 类型的参数。</span><span class="sxs-lookup"><span data-stu-id="bd368-216">The return parameters for Query function may contain parameters that are of System.Nullable type.</span></span> <span data-ttu-id="bd368-217">由于这些参数中的应用程序定义的可能会显示在 SharePoint 门户网站上的 Siebel 数据时遇到错误。</span><span class="sxs-lookup"><span data-stu-id="bd368-217">Due to the presence of these parameters in the application definition, you might get an error while presenting Siebel data on a SharePoint portal.</span></span> <span data-ttu-id="bd368-218">因此，你必须从应用程序定义删除 System.Nullable 类型的参数。</span><span class="sxs-lookup"><span data-stu-id="bd368-218">So, you must remove the parameters of System.Nullable type from the application definition.</span></span>  
  
 <span data-ttu-id="bd368-219">此外，对于 System.Nullable 类型的每个参数，业务数据目录定义编辑器创建 System.Boolean 类型的另一个参数，并将"指定"追加到的参数名称。</span><span class="sxs-lookup"><span data-stu-id="bd368-219">Also, for each parameter of System.Nullable type, the Business Data Catalog Definition Editor creates another parameter of System.Boolean type, and appends “Specified” to the parameter name.</span></span> <span data-ttu-id="bd368-220">例如，该参数 AccountRole 属于 System.Nullable 类型。</span><span class="sxs-lookup"><span data-stu-id="bd368-220">For example, the parameter AccountRole is of System.Nullable type.</span></span> <span data-ttu-id="bd368-221">因此，业务数据目录定义编辑器将 AccountRoleSpecified 参数添加到的参数的列表。</span><span class="sxs-lookup"><span data-stu-id="bd368-221">So, the Business Data Catalog Definition Editor adds an AccountRoleSpecified parameter to the list of parameters.</span></span> <span data-ttu-id="bd368-222">你必须删除以及此类参数。</span><span class="sxs-lookup"><span data-stu-id="bd368-222">You must remove such parameters as well.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bd368-223">你可以看到通过选择参数在业务数据目录定义编辑器中，并查看的值类型的参数**TypeName**在属性窗格中的属性。</span><span class="sxs-lookup"><span data-stu-id="bd368-223">You can see the parameter type by selecting the parameter in the Business Data Catalog Definition Editor, and looking at the value for the **TypeName** property in the Properties pane.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bd368-224">如果应用程序不包含 System.Nullable 类型的任何参数，则可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="bd368-224">You can skip this step if the application does not contain any parameters of System.Nullable type.</span></span>  
  
##### <a name="to-remove-the-parameters-of-systemnullable-type-for-the-query-method"></a><span data-ttu-id="bd368-225">若要删除的查询方法的 System.Nullable 类型的参数</span><span class="sxs-lookup"><span data-stu-id="bd368-225">To remove the parameters of System.Nullable type for the Query method</span></span>  
  
1.  <span data-ttu-id="bd368-226">在元数据对象窗格中，展开**帐户**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="bd368-226">In the Metadata Objects pane, expand the **Account** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="bd368-227">展开**查询**节点，然后展开**参数**节点。</span><span class="sxs-lookup"><span data-stu-id="bd368-227">Expand the **Query** node, and then expand the **Parameters** node.</span></span>  
  
3.  <span data-ttu-id="bd368-228">展开**返回**节点，然后展开第二个**返回**节点。</span><span class="sxs-lookup"><span data-stu-id="bd368-228">Expand the **Return** node, and then expand the second **Return** node.</span></span>  
  
4.  <span data-ttu-id="bd368-229">右键单击你想要删除，然后选择的参数**删除**。</span><span class="sxs-lookup"><span data-stu-id="bd368-229">Right-click the parameter you want to delete, and then select **Delete**.</span></span>  
  
5.  <span data-ttu-id="bd368-230">在对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="bd368-230">In the dialog box, click **OK**.</span></span>  
  
### <a name="export-the-application-definition-to-a-file"></a><span data-ttu-id="bd368-231">将应用程序定义导出到文件</span><span class="sxs-lookup"><span data-stu-id="bd368-231">Export the Application Definition to a File</span></span>  
 <span data-ttu-id="bd368-232">现在已创建包含 Siebel 系统实例元数据的应用程序定义。</span><span class="sxs-lookup"><span data-stu-id="bd368-232">You have now created an application definition that contains the Siebel system instance metadata.</span></span> <span data-ttu-id="bd368-233">必须将此定义导出到一个 XML 文件，其中可以导入到 Microsoft Office SharePoint Server。</span><span class="sxs-lookup"><span data-stu-id="bd368-233">You must export this definition to an XML file, which can be imported into Microsoft Office SharePoint Server.</span></span>  
  
##### <a name="to-export-the-application-definition-to-a-file"></a><span data-ttu-id="bd368-234">若要将应用程序定义导出到文件</span><span class="sxs-lookup"><span data-stu-id="bd368-234">To export the application definition to a file</span></span>  
  
1.  <span data-ttu-id="bd368-235">右键单击**Siebel_Account**在元数据对象窗格中，然后单击的节点**导出**。</span><span class="sxs-lookup"><span data-stu-id="bd368-235">Right-click the **Siebel_Account** node in the Metadata Objects pane, and then click **Export**.</span></span>  
  
2.  <span data-ttu-id="bd368-236">将文件保存为 Siebel_Account.xml。</span><span class="sxs-lookup"><span data-stu-id="bd368-236">Save the file as Siebel_Account.xml.</span></span>  
  
### <a name="modify-the-application-definition-file-to-include-specific-parameters"></a><span data-ttu-id="bd368-237">修改要包含特定参数的应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="bd368-237">Modify the Application Definition File to Include Specific Parameters</span></span>  
 <span data-ttu-id="bd368-238">如本主题中前面所述，业务数据目录定义编辑器工具将不处理枚举的数据类型。</span><span class="sxs-lookup"><span data-stu-id="bd368-238">As mentioned earlier in this topic, the Business Data Catalog Definition Editor tool does not handle enumerated data types.</span></span> <span data-ttu-id="bd368-239">业务数据目录定义编辑器工具导入字段，直到它遇到枚举的数据类型，并忽略其余的字段。</span><span class="sxs-lookup"><span data-stu-id="bd368-239">The Business Data Catalog Definition Editor tool imports the fields till it encounters an enumerated data type and ignores the remaining fields.</span></span> <span data-ttu-id="bd368-240">因此，您要在你的应用程序中的某些字段可能被取消。</span><span class="sxs-lookup"><span data-stu-id="bd368-240">So, certain fields that you want in your application might be omitted.</span></span> <span data-ttu-id="bd368-241">你可以手动编辑要包括这些字段的应用程序定义文件。</span><span class="sxs-lookup"><span data-stu-id="bd368-241">You can manually edit the application definition file to include those fields.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bd368-242">你必须确保要添加的参数是由 WCF 适配器服务开发向导在生成的.cs 文件中存在[步骤 1： 发布 Siebel 业务组件操作作为 WCF 服务](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md)。</span><span class="sxs-lookup"><span data-stu-id="bd368-242">You must make sure the parameters you are adding are present in the .cs file generated by the WCF Adapter Service Development Wizard in [Step 1: Publish the Siebel Business Component Operations as a WCF Service](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md).</span></span>  
  
 <span data-ttu-id="bd368-243">在此应用程序定义文件中，你将添加或删除返回参数**QueryAccount**方法。</span><span class="sxs-lookup"><span data-stu-id="bd368-243">In this application definition file, you will add or remove return parameters for the **QueryAccount** method.</span></span>  
  
##### <a name="to-modify-the-application-definition-file"></a><span data-ttu-id="bd368-244">若要修改的应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="bd368-244">To modify the application definition file</span></span>  
  
1.  <span data-ttu-id="bd368-245">通过使用打开应用程序定义文件，Siebel_Account.xml，[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]或任何其他编辑器中。</span><span class="sxs-lookup"><span data-stu-id="bd368-245">Open the application definition file, Siebel_Account.xml, by using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or any other editor.</span></span>  
  
2.  <span data-ttu-id="bd368-246">修改要替换的参数的应用程序定义文件**QueryAccount**方法。</span><span class="sxs-lookup"><span data-stu-id="bd368-246">Modify the application definition file to replace the parameters for the **QueryAccount** method.</span></span>  
  
    1.  <span data-ttu-id="bd368-247">在应用程序定义文件中，搜索以下：</span><span class="sxs-lookup"><span data-stu-id="bd368-247">Within the application definition file, search for the following:</span></span>  
  
        ```  
        <TypeDescriptor TypeName="BDC.AccountQueryRecord,Siebel_Account" Name="Item">  
        ```  
  
    2.  <span data-ttu-id="bd368-248">在`<TypeDescriptors>`标记中，将现有`<TypeDescriptor>`替换为以下元素：</span><span class="sxs-lookup"><span data-stu-id="bd368-248">Within the `<TypeDescriptors>` tag, replace the existing `<TypeDescriptor>` elements with the following:</span></span>  
  
        ```  
  
        <TypeDescriptor TypeName="System.String, mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=<token>" Name="Id" />  
        <TypeDescriptor TypeName="System.String, mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=<token>" Name="Country" />  
        <TypeDescriptor TypeName="System.String, mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=<token>" Name="Name" />  
        <TypeDescriptor TypeName="System.String, mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=<token>" Name="Location" />  
        ```  
  
    3.  <span data-ttu-id="bd368-249">保存并关闭该文件。</span><span class="sxs-lookup"><span data-stu-id="bd368-249">Save and close the file.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="bd368-250">你可以导入回中才能看到新添加的字段的业务数据目录定义编辑器工具的更新的应用程序定义文件。</span><span class="sxs-lookup"><span data-stu-id="bd368-250">You can import the updated application definition file back in the Business Data Catalog Definition Editor tool to see the newly added fields.</span></span> <span data-ttu-id="bd368-251">但是，在导入之前你将需要从业务数据目录定义编辑器工具删除现有的"Siebel_Account"应用程序。</span><span class="sxs-lookup"><span data-stu-id="bd368-251">However, before importing you will have to remove the existing “Siebel_Account” application from the Business Data Catalog Definition Editor tool.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="bd368-252">后续步骤</span><span class="sxs-lookup"><span data-stu-id="bd368-252">Next Steps</span></span>  
 <span data-ttu-id="bd368-253">你现在必须创建 SharePoint 应用程序从 Siebel 系统检索数据。</span><span class="sxs-lookup"><span data-stu-id="bd368-253">You must now create a SharePoint application to retrieve data from a Siebel system.</span></span> <span data-ttu-id="bd368-254">请参阅[步骤 3： 创建一个 SharePoint 应用程序检索数据从 Siebel](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md)有关的说明。</span><span class="sxs-lookup"><span data-stu-id="bd368-254">See [Step 3: Create a SharePoint Application to Retrieve Data from Siebel](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md) for instructions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd368-255">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bd368-255">See Also</span></span>  
 [<span data-ttu-id="bd368-256">教程 1： 从 SharePoint 站点上的 Siebel 系统提供数据</span><span class="sxs-lookup"><span data-stu-id="bd368-256">Tutorial 1: Presenting Data From a Siebel System on a SharePoint Site</span></span>](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)