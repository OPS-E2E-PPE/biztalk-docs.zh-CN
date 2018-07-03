---
title: 步骤 2： 为 Siebel 业务组件操作创建应用程序定义文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75d34c48-0f2a-42e4-a60b-e04bcf2404e1
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c017d5e71cdd2a4281849647727364520ad77784
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967614"
---
# <a name="step-2-create-an-application-definition-file-for-siebel-business-component-operations"></a><span data-ttu-id="164bd-102">步骤 2： 为 Siebel 业务组件操作创建应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="164bd-102">Step 2: Create an Application Definition File for Siebel Business Component Operations</span></span>
<span data-ttu-id="164bd-103">![步骤 2，共 4 步](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span><span class="sxs-lookup"><span data-stu-id="164bd-103">![Step 2 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span></span>  
  
 <span data-ttu-id="164bd-104">**完成时间：** 15 分钟</span><span class="sxs-lookup"><span data-stu-id="164bd-104">**Time to complete:** 15 minutes</span></span>  
  
 <span data-ttu-id="164bd-105">**目标：** 公开业务数据目录，并将业务 (LOB) 应用程序中的数据合并到门户。</span><span class="sxs-lookup"><span data-stu-id="164bd-105">**Objective:** The Business Data Catalog exposes and incorporates data from line-of-business (LOB) applications into portals.</span></span> <span data-ttu-id="164bd-106">若要将此数据合并到您的门户网站，必须生成可以使用 Microsoft Office SharePoint Server 应用程序定义文件。</span><span class="sxs-lookup"><span data-stu-id="164bd-106">To incorporate this data into your portal site, you must build an application definition file that Microsoft Office SharePoint Server can consume.</span></span>  
  
 <span data-ttu-id="164bd-107">Business Data Catalog Definition Editor 工具，可为业务数据目录中创建应用程序定义文件。</span><span class="sxs-lookup"><span data-stu-id="164bd-107">The Business Data Catalog Definition Editor tool enables you to create an application definition file for the Business Data Catalog.</span></span> <span data-ttu-id="164bd-108">此工具会自动生成的 XML 定义文件。</span><span class="sxs-lookup"><span data-stu-id="164bd-108">This tool automatically generates the XML for the definition file.</span></span> <span data-ttu-id="164bd-109">因此，无需手动创建该文件在 XML 编辑器。</span><span class="sxs-lookup"><span data-stu-id="164bd-109">Therefore, you do not have to manually create the file in an XML editor.</span></span>  
  
 <span data-ttu-id="164bd-110">要创建的 Microsoft Office SharePoint Server 应用程序的用途是执行要检索的记录列表帐户业务组件上的查询操作。</span><span class="sxs-lookup"><span data-stu-id="164bd-110">The purpose of the Microsoft Office SharePoint Server application that you are creating is to perform a Query operation on the Account business component to retrieve a list of records.</span></span> <span data-ttu-id="164bd-111">若要实现此目的，必须完成一组任务中 Business Data Catalog Definition Editor。</span><span class="sxs-lookup"><span data-stu-id="164bd-111">To achieve this, you must complete a set of tasks in the Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="164bd-112">本主题提供有关如何执行这些任务的说明。</span><span class="sxs-lookup"><span data-stu-id="164bd-112">This topic provides instructions on how to perform these tasks.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="164bd-113">必要條件</span><span class="sxs-lookup"><span data-stu-id="164bd-113">Prerequisites</span></span>  
  
-   <span data-ttu-id="164bd-114">您必须具有 Microsoft Office SharePoint Server 2007 SDK 的一部分安装 Business Data Catalog Definition Editor。</span><span class="sxs-lookup"><span data-stu-id="164bd-114">You must have the Business Data Catalog Definition Editor installed as part of the Microsoft Office SharePoint Server 2007 SDK.</span></span> <span data-ttu-id="164bd-115">你可以下载从 SDK [ http://go.microsoft.com/fwlink/?LinkId=104130 ](http://go.microsoft.com/fwlink/?LinkId=104130)。</span><span class="sxs-lookup"><span data-stu-id="164bd-115">You can download the SDK from [http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130).</span></span>  
  
-   <span data-ttu-id="164bd-116">您应已发布 WCF 服务，如中所述[步骤 1： 将 Siebel 业务组件操作作为 WCF 服务发布](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md)。</span><span class="sxs-lookup"><span data-stu-id="164bd-116">You should have published the WCF service, as described in [Step 1: Publish the Siebel Business Component Operations as a WCF Service](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md).</span></span>  
  
## <a name="creating-an-application-definition-file"></a><span data-ttu-id="164bd-117">创建应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="164bd-117">Creating an Application Definition File</span></span>  
 <span data-ttu-id="164bd-118">本部分提供分步说明来创建 WCF 服务应用程序定义文件。</span><span class="sxs-lookup"><span data-stu-id="164bd-118">This section provides step-by-step instructions to create an application definition file for the WCF service.</span></span>  
  
### <a name="connect-to-the-wcf-service-and-create-entities"></a><span data-ttu-id="164bd-119">连接到 WCF 服务，并创建实体</span><span class="sxs-lookup"><span data-stu-id="164bd-119">Connect to the WCF Service, and Create Entities</span></span>  
 <span data-ttu-id="164bd-120">您必须连接到 WCF 服务以提取 Web 服务描述语言 (WSDL) 服务。</span><span class="sxs-lookup"><span data-stu-id="164bd-120">You must connect to the WCF service to extract the Web Services Description Language (WSDL) for the service.</span></span> <span data-ttu-id="164bd-121">从 WSDL，Business Data Catalog Definition Editor 提取方法。</span><span class="sxs-lookup"><span data-stu-id="164bd-121">From the WSDL, the Business Data Catalog Definition Editor extracts the methods.</span></span> <span data-ttu-id="164bd-122">这些方法可以用于创建实体。</span><span class="sxs-lookup"><span data-stu-id="164bd-122">These methods can be used to create entities.</span></span> <span data-ttu-id="164bd-123">对于此示例中，必须创建帐户业务组件上查询操作的一个实体。</span><span class="sxs-lookup"><span data-stu-id="164bd-123">For this example, you must create one entity for the Query operation on the Account business component.</span></span>  
  
##### <a name="to-connect-to-the-wcf-service-and-create-entities"></a><span data-ttu-id="164bd-124">若要连接到 WCF 服务，并创建实体</span><span class="sxs-lookup"><span data-stu-id="164bd-124">To connect to the WCF service, and create entities</span></span>  
  
1.  <span data-ttu-id="164bd-125">启动 Business Data Catalog Definition Editor。</span><span class="sxs-lookup"><span data-stu-id="164bd-125">Start the Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="164bd-126">上**启动**菜单上，单击**Microsoft Business Data Catalog Definition Editor**。</span><span class="sxs-lookup"><span data-stu-id="164bd-126">On the **Start** menu, click **Microsoft Business Data Catalog Definition Editor**.</span></span>  
  
2.  <span data-ttu-id="164bd-127">在工具中，单击**添加 LOB 系统**。</span><span class="sxs-lookup"><span data-stu-id="164bd-127">In the tool, click **Add LOB System**.</span></span>  
  
3.  <span data-ttu-id="164bd-128">在添加 LOB 系统窗口中，单击**连接到 web 服务**。</span><span class="sxs-lookup"><span data-stu-id="164bd-128">In the Add LOB System window, click **Connect to Webservice**.</span></span>  
  
4.  <span data-ttu-id="164bd-129">在 URL 框中，键入 WCF 服务的 URL。</span><span class="sxs-lookup"><span data-stu-id="164bd-129">In the URL box, type the URL for the WCF service.</span></span> <span data-ttu-id="164bd-130">该 URL 必须采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="164bd-130">The URL must be in the following format:</span></span>  
  
    ```  
    https://<computer_name>/Siebel_Account/BusinessObjects_Account_Account_Operation.svc?wsdl  
    ```  
  
     <span data-ttu-id="164bd-131">其中，BusinessObjects_Account_Account_Operation.svc 是创建 Siebel 协定的服务文件。</span><span class="sxs-lookup"><span data-stu-id="164bd-131">where, BusinessObjects_Account_Account_Operation.svc is the service file created for the Siebel contract.</span></span>  
  
     <span data-ttu-id="164bd-132">当你测试是否成功，如中所述发布 WCF 服务时，必须键入的 URL 才可用[步骤 1： 将 Siebel 业务组件操作作为 WCF 服务发布](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md)。</span><span class="sxs-lookup"><span data-stu-id="164bd-132">The URL that you must type is available when you test whether the WCF service is published successfully, as described in [Step 1: Publish the Siebel Business Component Operations as a WCF Service](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md).</span></span>  
  
5.  <span data-ttu-id="164bd-133">单击 **“连接”**。</span><span class="sxs-lookup"><span data-stu-id="164bd-133">Click **Connect**.</span></span>  
  
6.  <span data-ttu-id="164bd-134">单击**添加 Web 方法**选项卡以查看你在 WCF 适配器服务开发向导中选择的操作。</span><span class="sxs-lookup"><span data-stu-id="164bd-134">Click the **Add Web Method** tab to see the operations you selected in the WCF Adapter Service Development Wizard.</span></span> <span data-ttu-id="164bd-135">你将看到**查询**方法。</span><span class="sxs-lookup"><span data-stu-id="164bd-135">You will see the **Query** method.</span></span>  
  
     <span data-ttu-id="164bd-136">![将 web 方法添加到 BDC 应用程序](../../adapters-and-accelerators/adapter-siebel/media/f9505cd3-67e3-4f99-b189-d010322a3137.gif "f9505cd3-67e3-4f99-b189-d010322a3137")</span><span class="sxs-lookup"><span data-stu-id="164bd-136">![Add web methods to BDC application](../../adapters-and-accelerators/adapter-siebel/media/f9505cd3-67e3-4f99-b189-d010322a3137.gif "f9505cd3-67e3-4f99-b189-d010322a3137")</span></span>  
  
7.  <span data-ttu-id="164bd-137">拖动**查询**方法为设计图面，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="164bd-137">Drag the **Query** method to the design surface and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="164bd-138">在中**输入 LOB 系统的名称**对话框中键入名称**LOB 系统名称**框。</span><span class="sxs-lookup"><span data-stu-id="164bd-138">In the **Enter the name for the LOB System** dialog box, type a name in the **LOB System Name** box.</span></span> <span data-ttu-id="164bd-139">对于此示例中，键入`Siebel_Account`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="164bd-139">For this example, type `Siebel_Account`, and then click **OK**.</span></span> <span data-ttu-id="164bd-140">一个实体， **Entity0**，创建在 Business Data Catalog Definition Editor。</span><span class="sxs-lookup"><span data-stu-id="164bd-140">An entity, **Entity0**, is created in the Business Data Catalog Definition Editor.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="164bd-141">Business Data Catalog Definition Editor 工具不处理枚举的数据类型。</span><span class="sxs-lookup"><span data-stu-id="164bd-141">The Business Data Catalog Definition Editor tool does not handle enumerated data types.</span></span> <span data-ttu-id="164bd-142">因此，Business Data Catalog Definition Editor 工具导入字段直到它遇到的枚举的数据类型，并忽略剩余的字段。</span><span class="sxs-lookup"><span data-stu-id="164bd-142">So, the Business Data Catalog Definition Editor tool imports the fields till it encounters an enumerated data type and ignores the remaining fields.</span></span> <span data-ttu-id="164bd-143">Business Data Catalog Definition Editor 工具还会出错。</span><span class="sxs-lookup"><span data-stu-id="164bd-143">The Business Data Catalog Definition Editor tool also gives an error.</span></span> <span data-ttu-id="164bd-144">可以忽略此错误，并单击确定以继续。</span><span class="sxs-lookup"><span data-stu-id="164bd-144">You can ignore this error and proceed by clicking OK.</span></span> <span data-ttu-id="164bd-145">您可以手动添加所需的字段在应用程序定义文件中在后面的阶段。</span><span class="sxs-lookup"><span data-stu-id="164bd-145">You can manually add the required fields in the application definition file at a later stage.</span></span>  
  
9. <span data-ttu-id="164bd-146">更改实体名称，以使用更友好的名称。</span><span class="sxs-lookup"><span data-stu-id="164bd-146">Change the entity names to use more friendly names.</span></span> <span data-ttu-id="164bd-147">对于此示例中，更改**Entity0**到**帐户**。</span><span class="sxs-lookup"><span data-stu-id="164bd-147">For this example, change **Entity0** to **Account**.</span></span>  
  
    1.  <span data-ttu-id="164bd-148">展开**Siebel_Account**节点，然后展开**实体**节点。</span><span class="sxs-lookup"><span data-stu-id="164bd-148">Expand the **Siebel_Account** node, and then expand the **Entities** node.</span></span>  
  
    2.  <span data-ttu-id="164bd-149">选择**Entity0**节点。</span><span class="sxs-lookup"><span data-stu-id="164bd-149">Select the **Entity0** node.</span></span>  
  
    3.  <span data-ttu-id="164bd-150">在属性窗格中，键入**帐户**中**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="164bd-150">In the Properties pane, type **Account** in the **Name** field.</span></span>  
  
         <span data-ttu-id="164bd-151">![重命名实体](../../adapters-and-accelerators/adapter-siebel/media/44eda1de-b348-4421-9c51-0355b51f4a90.gif "44eda1de-b348-4421-9c51-0355b51f4a90")</span><span class="sxs-lookup"><span data-stu-id="164bd-151">![Rename the entity](../../adapters-and-accelerators/adapter-siebel/media/44eda1de-b348-4421-9c51-0355b51f4a90.gif "44eda1de-b348-4421-9c51-0355b51f4a90")</span></span>  
  
### <a name="specify-user-name-and-password-headers-for-methods"></a><span data-ttu-id="164bd-152">为方法中指定用户名和密码标头</span><span class="sxs-lookup"><span data-stu-id="164bd-152">Specify User Name and Password Headers for Methods</span></span>  
 <span data-ttu-id="164bd-153">创建 WCF 服务时所选的业务组件操作的 Siebel 系统中，指定用户名称和密码标头为终结点行为配置的一部分 ([步骤 1： 发布 Siebel 业务组件操作为 WCF 服务](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md))。</span><span class="sxs-lookup"><span data-stu-id="164bd-153">When creating a WCF service for the selected business component operations in the Siebel system, you specified user name and password headers as part of the endpoint behavior configuration ([Step 1: Publish the Siebel Business Component Operations as a WCF Service](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md)).</span></span> <span data-ttu-id="164bd-154">必须指定方法属性相同的值。</span><span class="sxs-lookup"><span data-stu-id="164bd-154">You must specify the same values for the method properties.</span></span>  
  
##### <a name="to-specify-user-name-and-password-headers-for-the-query-method"></a><span data-ttu-id="164bd-155">若要指定用户名称和密码标头为该查询方法</span><span class="sxs-lookup"><span data-stu-id="164bd-155">To specify user name and password headers for the Query method</span></span>  
  
1.  <span data-ttu-id="164bd-156">在元数据对象窗格中，展开**帐户**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="164bd-156">In the Metadata Objects pane, expand the **Account** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="164bd-157">单击**查询**节点，并在属性窗格中单击省略号 （...） 按钮根据**属性**字段。</span><span class="sxs-lookup"><span data-stu-id="164bd-157">Click the **Query** node, and in the Properties pane click the ellipsis (…) button against the **Properties** field.</span></span>  
  
3.  <span data-ttu-id="164bd-158">在 PropertyView 集合编辑器对话框中，单击**外**，然后在属性窗格中，键入`HttpHeaderUserName`有关**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="164bd-158">In the PropertyView Collection Editor dialog box, click **Add**, and in the Properties pane, type `HttpHeaderUserName` for the **Name** field.</span></span> <span data-ttu-id="164bd-159">同样，键入`MyUserHeader`有关**PropertyValue**字段。</span><span class="sxs-lookup"><span data-stu-id="164bd-159">Similarly, type `MyUserHeader` for the **PropertyValue** field.</span></span> <span data-ttu-id="164bd-160">选择**System.String**有关**类型**字段。</span><span class="sxs-lookup"><span data-stu-id="164bd-160">Select **System.String** for the **Type** field.</span></span>  
  
     <span data-ttu-id="164bd-161">![将属性添加](../../adapters-and-accelerators/adapter-sap/media/9eef32ac-8a93-45dc-8d07-12b7dbf961ba.gif "9eef32ac-8a93-45dc-8d07-12b7dbf961ba")</span><span class="sxs-lookup"><span data-stu-id="164bd-161">![Add a property](../../adapters-and-accelerators/adapter-sap/media/9eef32ac-8a93-45dc-8d07-12b7dbf961ba.gif "9eef32ac-8a93-45dc-8d07-12b7dbf961ba")</span></span>  
  
4.  <span data-ttu-id="164bd-162">在 PropertyView 集合编辑器窗口中，单击**添加**，然后在属性窗格中，键入`HttpHeaderPassword`有关**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="164bd-162">In the PropertyView Collection Editor window, click **Add**, and in the Properties pane, type `HttpHeaderPassword` for the **Name** field.</span></span> <span data-ttu-id="164bd-163">同样，键入`MyPassHeader`有关**PropertyValue**字段。</span><span class="sxs-lookup"><span data-stu-id="164bd-163">Similarly, type `MyPassHeader` for the **PropertyValue** field.</span></span> <span data-ttu-id="164bd-164">选择**System.String**有关**类型**字段。</span><span class="sxs-lookup"><span data-stu-id="164bd-164">Select **System.String** for the **Type** field.</span></span>  
  
5.  <span data-ttu-id="164bd-165">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="164bd-165">Click **OK**.</span></span>  
  
### <a name="set-up-single-sign-on-for-connecting-to-a-siebel-system"></a><span data-ttu-id="164bd-166">为连接到 Siebel 系统设置了单一登录</span><span class="sxs-lookup"><span data-stu-id="164bd-166">Set up Single Sign-On for Connecting to a Siebel System</span></span>  
 <span data-ttu-id="164bd-167">执行本主题中的所有过程完成后，您将创建应用程序定义可以导入 SharePoint 应用程序的 XML。</span><span class="sxs-lookup"><span data-stu-id="164bd-167">After you have finished performing all the procedures in this topic, you will have created an application definition XML that can be imported into a SharePoint application.</span></span> <span data-ttu-id="164bd-168">从应用程序，将调用 Siebel 业务组件操作 （作为 Web 方法公开） 从 Siebel 系统中检索相关数据。</span><span class="sxs-lookup"><span data-stu-id="164bd-168">From the application, you will invoke the Siebel business component operations (exposed as Web methods) to retrieve relevant data from the Siebel system.</span></span> <span data-ttu-id="164bd-169">若要启用此功能，必须在 SharePoint 应用程序中创建 Siebel 系统中的用户和用户之间的映射。</span><span class="sxs-lookup"><span data-stu-id="164bd-169">To enable this, you must create a mapping between a user in the Siebel system and the user in the SharePoint application.</span></span> <span data-ttu-id="164bd-170">已导入应用程序定义 XML 后，可以在 SharePoint 管理中心网站中创建此映射。</span><span class="sxs-lookup"><span data-stu-id="164bd-170">You create this mapping in SharePoint Central Administration Web site after you have imported the application definition XML.</span></span>  
  
 <span data-ttu-id="164bd-171">但是，若要创建该映射必须设置属性**SecondarySsoApplicationId**中 Business Data Catalog Definition Editor。</span><span class="sxs-lookup"><span data-stu-id="164bd-171">However, to create the mapping you must set a property **SecondarySsoApplicationId** in the Business Data Catalog Definition Editor.</span></span>  
  
##### <a name="to-set-the-secondaryssoapplicationid-property"></a><span data-ttu-id="164bd-172">若要设置 SecondarySsoApplicationId 属性</span><span class="sxs-lookup"><span data-stu-id="164bd-172">To set the SecondarySsoApplicationId property</span></span>  
  
1.  <span data-ttu-id="164bd-173">在元数据对象窗格中，展开**Siebel_Account**节点，然后展开**实例**节点。</span><span class="sxs-lookup"><span data-stu-id="164bd-173">In the Metadata Objects pane, expand the **Siebel_Account** node, and then expand the **Instances** node.</span></span>  
  
2.  <span data-ttu-id="164bd-174">单击**Siebel_Account_Instance**和属性窗格中单击省略号 （...） 按钮根据**属性**字段。</span><span class="sxs-lookup"><span data-stu-id="164bd-174">Click **Siebel_Account_Instance** and in the Properties pane click the ellipsis (…) button against the **Properties** field.</span></span>  
  
3.  <span data-ttu-id="164bd-175">在 PropertyView 集合编辑器窗口中，单击**添加**，然后在属性窗格中，键入**SecondarySsoApplicationId**有关**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="164bd-175">In the PropertyView Collection Editor window, click **Add**, and in the Properties pane, type **SecondarySsoApplicationId** for the **Name** field.</span></span> <span data-ttu-id="164bd-176">同样，键入**SiebelSSO**有关**PropertyValue**字段。</span><span class="sxs-lookup"><span data-stu-id="164bd-176">Similarly, type **SiebelSSO** for the **PropertyValue** field.</span></span> <span data-ttu-id="164bd-177">选择**System.String**有关**类型**字段。</span><span class="sxs-lookup"><span data-stu-id="164bd-177">Select **System.String** for the **Type** field.</span></span>  
  
     <span data-ttu-id="164bd-178">![添加 SSO 属性](../../adapters-and-accelerators/adapter-siebel/media/59ce70eb-498f-406b-965d-c273c2d6ed14.gif "59ce70eb-498f-406b-965d-c273c2d6ed14")</span><span class="sxs-lookup"><span data-stu-id="164bd-178">![Add the SSO property](../../adapters-and-accelerators/adapter-siebel/media/59ce70eb-498f-406b-965d-c273c2d6ed14.gif "59ce70eb-498f-406b-965d-c273c2d6ed14")</span></span>  
  
4.  <span data-ttu-id="164bd-179">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="164bd-179">Click **OK**.</span></span>  
  
### <a name="requirement-perform-a-query-operation-on-the-account-business-component"></a><span data-ttu-id="164bd-180">要求： 执行帐户业务组件上的查询操作</span><span class="sxs-lookup"><span data-stu-id="164bd-180">Requirement: Perform a Query Operation on the Account Business Component</span></span>  
 <span data-ttu-id="164bd-181">此示例中的第一个要求是创建可用于执行查询操作帐户业务组件上的应用程序定义。</span><span class="sxs-lookup"><span data-stu-id="164bd-181">The first requirement of this example is to create an application definition that can be used to perform a Query operation on the Account business component.</span></span> <span data-ttu-id="164bd-182">若要实现此要求，必须执行以下一组任务：</span><span class="sxs-lookup"><span data-stu-id="164bd-182">To achieve this requirement, you must perform the following set of tasks:</span></span>  
  
-   <span data-ttu-id="164bd-183">在查询方法中，创建一个筛选器，并将其映射到其执行查询操作的参数。</span><span class="sxs-lookup"><span data-stu-id="164bd-183">In the Query method, create a filter, and map it to the parameter on which the Query operation is performed.</span></span> <span data-ttu-id="164bd-184">对于帐户业务组件，您将执行查询时使用**SearchExpr**参数。</span><span class="sxs-lookup"><span data-stu-id="164bd-184">For the Account business component, you will perform a query using the **SearchExpr** parameter.</span></span> <span data-ttu-id="164bd-185">因此，您将映射到筛选器**SearchExpr**参数。</span><span class="sxs-lookup"><span data-stu-id="164bd-185">So, you will map the filter to the **SearchExpr** parameter.</span></span>  
  
-   <span data-ttu-id="164bd-186">创建 Finder 方法实例的查询方法。</span><span class="sxs-lookup"><span data-stu-id="164bd-186">Create a Finder method instance for the Query method.</span></span> <span data-ttu-id="164bd-187">Finder 方法检索基于筛选器记录的列表。</span><span class="sxs-lookup"><span data-stu-id="164bd-187">A Finder method retrieves a list of records based on a filter.</span></span>  
  
##### <a name="to-create-a-filter-and-map-it-to-the-searchexpr-parameter"></a><span data-ttu-id="164bd-188">若要创建筛选器，并将其映射到 SearchExpr 参数</span><span class="sxs-lookup"><span data-stu-id="164bd-188">To create a filter, and map it to the SearchExpr parameter</span></span>  
  
1.  <span data-ttu-id="164bd-189">创建筛选器查询方法。</span><span class="sxs-lookup"><span data-stu-id="164bd-189">Create a filter for the Query method.</span></span>  
  
    1.  <span data-ttu-id="164bd-190">在元数据对象窗格中，展开**帐户**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="164bd-190">In the Metadata Objects pane, expand the **Account** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="164bd-191">展开查询方法中，右键单击**筛选器**，然后单击**添加筛选器**。</span><span class="sxs-lookup"><span data-stu-id="164bd-191">Expand the Query method, right-click **Filters**, and then click **Add Filter**.</span></span>  
  
         <span data-ttu-id="164bd-192">![向方法中添加筛选器](../../adapters-and-accelerators/adapter-siebel/media/9cf7ccfd-6da0-44b7-b522-df327a74e7a2.gif "9cf7ccfd-6da0-44b7-b522-df327a74e7a2")</span><span class="sxs-lookup"><span data-stu-id="164bd-192">![Add filter to a method](../../adapters-and-accelerators/adapter-siebel/media/9cf7ccfd-6da0-44b7-b522-df327a74e7a2.gif "9cf7ccfd-6da0-44b7-b522-df327a74e7a2")</span></span>  
  
    3.  <span data-ttu-id="164bd-193">在属性窗格中，键入`SearchExpression`有关**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="164bd-193">In the Properties pane, type `SearchExpression` for the **Name** field.</span></span>  
  
    4.  <span data-ttu-id="164bd-194">有关**FilterType**属性中，选择**等于**。</span><span class="sxs-lookup"><span data-stu-id="164bd-194">For the **FilterType** property, select **Equals**.</span></span>  
  
         <span data-ttu-id="164bd-195">![指定筛选器名称和类型](../../adapters-and-accelerators/adapter-siebel/media/9faa18e1-4d27-4ee4-960a-458f978812a7.gif "9faa18e1-4d27-4ee4-960a-458f978812a7")</span><span class="sxs-lookup"><span data-stu-id="164bd-195">![Specify a filter name and type](../../adapters-and-accelerators/adapter-siebel/media/9faa18e1-4d27-4ee4-960a-458f978812a7.gif "9faa18e1-4d27-4ee4-960a-458f978812a7")</span></span>  
  
2.  <span data-ttu-id="164bd-196">筛选器映射到**SearchExpr**查询方法中的参数。</span><span class="sxs-lookup"><span data-stu-id="164bd-196">Map the filter to the **SearchExpr** parameter in the Query method.</span></span>  
  
    1.  <span data-ttu-id="164bd-197">在元数据对象窗格中，展开**帐户**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="164bd-197">In the Metadata Objects pane, expand the **Account** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="164bd-198">展开查询方法，然后展开**参数**节点。</span><span class="sxs-lookup"><span data-stu-id="164bd-198">Expand the Query method, and then expand the **Parameters** node.</span></span>  
  
    3.  <span data-ttu-id="164bd-199">展开**AccountQueryInputRecord**节点，然后展开第二个**AccountQueryInputRecord**节点。</span><span class="sxs-lookup"><span data-stu-id="164bd-199">Expand the **AccountQueryInputRecord** node, and then expand the second **AccountQueryInputRecord** node.</span></span>  
  
    4.  <span data-ttu-id="164bd-200">单击**SearchExpr**节点，然后在属性窗格中选择**SearchExpression**从**FilterDescriptor**列表。</span><span class="sxs-lookup"><span data-stu-id="164bd-200">Click the **SearchExpr** node and in the Properties pane, select **SearchExpression** from the **FilterDescriptor**list.</span></span>  
  
         <span data-ttu-id="164bd-201">![将参数映射到筛选器](../../adapters-and-accelerators/adapter-siebel/media/199c8ba7-d0e8-4fb4-9d73-9cf548512498.gif "199c8ba7-d0e8-4fb4-9d73-9cf548512498")</span><span class="sxs-lookup"><span data-stu-id="164bd-201">![Map a parameter to a filter](../../adapters-and-accelerators/adapter-siebel/media/199c8ba7-d0e8-4fb4-9d73-9cf548512498.gif "199c8ba7-d0e8-4fb4-9d73-9cf548512498")</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="164bd-202">**AccountQueryInputRecord**还包含**QueryFields**节点，其中又包含**项**节点。</span><span class="sxs-lookup"><span data-stu-id="164bd-202">The **AccountQueryInputRecord** also contains a **QueryFields** node, which in turn contains an **Item** node.</span></span> <span data-ttu-id="164bd-203">必须删除**项**节点，否则帐户业务组件上的查询操作可能无法提供所需的结果。</span><span class="sxs-lookup"><span data-stu-id="164bd-203">You must delete the **Item** node, otherwise the Query operation on the Account business component might not give the desired results.</span></span> <span data-ttu-id="164bd-204">若要删除**项**节点，右键单击节点，然后选择**删除**。</span><span class="sxs-lookup"><span data-stu-id="164bd-204">To delete the **Item** node, right-click the node, and then select **Delete**.</span></span>  
  
##### <a name="to-create-a-finder-method-instance-for-query-method"></a><span data-ttu-id="164bd-205">若要创建 Finder 方法实例的查询方法</span><span class="sxs-lookup"><span data-stu-id="164bd-205">To create a Finder method instance for Query method</span></span>  
  
1.  <span data-ttu-id="164bd-206">在元数据对象窗格中，展开**帐户**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="164bd-206">In the Metadata Objects pane, expand the **Account** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="164bd-207">展开**查询**节点，右键单击**实例**，然后单击**添加方法实例**以打开创建方法实例窗口。</span><span class="sxs-lookup"><span data-stu-id="164bd-207">Expand the **Query** node, right-click **Instances**, and then click **Add Method Instance** to open the Create Method Instance window.</span></span>  
  
     <span data-ttu-id="164bd-208">![添加 Finder 方法实例](../../adapters-and-accelerators/adapter-siebel/media/c90e7784-4fb7-4eb5-baf5-efbefba4bb1f.gif "c90e7784-4fb7-4eb5-baf5-efbefba4bb1f")</span><span class="sxs-lookup"><span data-stu-id="164bd-208">![Add a Finder method instance](../../adapters-and-accelerators/adapter-siebel/media/c90e7784-4fb7-4eb5-baf5-efbefba4bb1f.gif "c90e7784-4fb7-4eb5-baf5-efbefba4bb1f")</span></span>  
  
3.  <span data-ttu-id="164bd-209">在创建方法实例窗口中，单击**Finder**有关**方法实例类型**。</span><span class="sxs-lookup"><span data-stu-id="164bd-209">In the Create Method Instance window, click **Finder** for the **Method Instance Type**.</span></span>  
  
4.  <span data-ttu-id="164bd-210">单击**返回**从**返回 TypeDescriptor**部分。</span><span class="sxs-lookup"><span data-stu-id="164bd-210">Click **Return** from **Return TypeDescriptor** section.</span></span>  
  
     <span data-ttu-id="164bd-211">![添加 Finder 方法实例](../../adapters-and-accelerators/adapter-siebel/media/e8343988-d7c1-4b04-85b0-ca7d07097490.gif "e8343988-d7c1-4b04-85b0-ca7d07097490")</span><span class="sxs-lookup"><span data-stu-id="164bd-211">![Add a Finder method instance](../../adapters-and-accelerators/adapter-siebel/media/e8343988-d7c1-4b04-85b0-ca7d07097490.gif "e8343988-d7c1-4b04-85b0-ca7d07097490")</span></span>  
  
5.  <span data-ttu-id="164bd-212">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="164bd-212">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="164bd-213">在属性窗格中，键入`QueryAccount`有关**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="164bd-213">In the Properties pane, type `QueryAccount` for the **Name** field.</span></span>  
  
     <span data-ttu-id="164bd-214">![指定方法实例的名称](../../adapters-and-accelerators/adapter-siebel/media/401223f3-806f-4010-8646-d5ac0c0e9f67.gif "401223f3-806f-4010-8646-d5ac0c0e9f67")</span><span class="sxs-lookup"><span data-stu-id="164bd-214">![Specify a name for the method instance](../../adapters-and-accelerators/adapter-siebel/media/401223f3-806f-4010-8646-d5ac0c0e9f67.gif "401223f3-806f-4010-8646-d5ac0c0e9f67")</span></span>  
  
### <a name="remove-the-parameters-of-systemnullable-type"></a><span data-ttu-id="164bd-215">删除 System.Nullable 类型的参数</span><span class="sxs-lookup"><span data-stu-id="164bd-215">Remove the Parameters of System.Nullable Type</span></span>  
 <span data-ttu-id="164bd-216">查询函数的返回参数可能包含属于 System.Nullable 类型的参数。</span><span class="sxs-lookup"><span data-stu-id="164bd-216">The return parameters for Query function may contain parameters that are of System.Nullable type.</span></span> <span data-ttu-id="164bd-217">由于应用程序定义中的这些参数存在，可能会对 SharePoint 门户网站中演示的 Siebel 数据时遇到错误。</span><span class="sxs-lookup"><span data-stu-id="164bd-217">Due to the presence of these parameters in the application definition, you might get an error while presenting Siebel data on a SharePoint portal.</span></span> <span data-ttu-id="164bd-218">因此，你必须从应用程序定义删除 System.Nullable 类型的参数。</span><span class="sxs-lookup"><span data-stu-id="164bd-218">So, you must remove the parameters of System.Nullable type from the application definition.</span></span>  
  
 <span data-ttu-id="164bd-219">此外，对于 System.Nullable 类型的每个参数，Business Data Catalog Definition Editor 创建 System.Boolean 类型的另一个参数，并将"Specified"追加到参数名称。</span><span class="sxs-lookup"><span data-stu-id="164bd-219">Also, for each parameter of System.Nullable type, the Business Data Catalog Definition Editor creates another parameter of System.Boolean type, and appends “Specified” to the parameter name.</span></span> <span data-ttu-id="164bd-220">例如，参数 AccountRole 为 System.Nullable 类型。</span><span class="sxs-lookup"><span data-stu-id="164bd-220">For example, the parameter AccountRole is of System.Nullable type.</span></span> <span data-ttu-id="164bd-221">因此，Business Data Catalog Definition Editor 将 AccountRoleSpecified 参数添加到参数的列表。</span><span class="sxs-lookup"><span data-stu-id="164bd-221">So, the Business Data Catalog Definition Editor adds an AccountRoleSpecified parameter to the list of parameters.</span></span> <span data-ttu-id="164bd-222">必须删除此类参数。</span><span class="sxs-lookup"><span data-stu-id="164bd-222">You must remove such parameters as well.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="164bd-223">您可以看到通过选择该参数在 Business Data Catalog Definition Editor，并查看的值类型的参数**TypeName**属性窗格中的属性。</span><span class="sxs-lookup"><span data-stu-id="164bd-223">You can see the parameter type by selecting the parameter in the Business Data Catalog Definition Editor, and looking at the value for the **TypeName** property in the Properties pane.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="164bd-224">如果应用程序不包含 System.Nullable 类型的任何参数，可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="164bd-224">You can skip this step if the application does not contain any parameters of System.Nullable type.</span></span>  
  
##### <a name="to-remove-the-parameters-of-systemnullable-type-for-the-query-method"></a><span data-ttu-id="164bd-225">若要删除的查询方法的 System.Nullable 类型参数</span><span class="sxs-lookup"><span data-stu-id="164bd-225">To remove the parameters of System.Nullable type for the Query method</span></span>  
  
1.  <span data-ttu-id="164bd-226">在元数据对象窗格中，展开**帐户**节点，然后展开**方法**节点。</span><span class="sxs-lookup"><span data-stu-id="164bd-226">In the Metadata Objects pane, expand the **Account** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="164bd-227">展开**查询**节点，然后展开**参数**节点。</span><span class="sxs-lookup"><span data-stu-id="164bd-227">Expand the **Query** node, and then expand the **Parameters** node.</span></span>  
  
3.  <span data-ttu-id="164bd-228">展开**返回**节点，然后展开第二个**返回**节点。</span><span class="sxs-lookup"><span data-stu-id="164bd-228">Expand the **Return** node, and then expand the second **Return** node.</span></span>  
  
4.  <span data-ttu-id="164bd-229">右键单击你想要删除，然后选择的参数**删除**。</span><span class="sxs-lookup"><span data-stu-id="164bd-229">Right-click the parameter you want to delete, and then select **Delete**.</span></span>  
  
5.  <span data-ttu-id="164bd-230">在对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="164bd-230">In the dialog box, click **OK**.</span></span>  
  
### <a name="export-the-application-definition-to-a-file"></a><span data-ttu-id="164bd-231">应用程序定义导出到文件</span><span class="sxs-lookup"><span data-stu-id="164bd-231">Export the Application Definition to a File</span></span>  
 <span data-ttu-id="164bd-232">现在已创建包含的 Siebel 系统实例元数据的应用程序定义。</span><span class="sxs-lookup"><span data-stu-id="164bd-232">You have now created an application definition that contains the Siebel system instance metadata.</span></span> <span data-ttu-id="164bd-233">必须将此定义导出到 XML 文件，可以导入到 Microsoft Office SharePoint Server。</span><span class="sxs-lookup"><span data-stu-id="164bd-233">You must export this definition to an XML file, which can be imported into Microsoft Office SharePoint Server.</span></span>  
  
##### <a name="to-export-the-application-definition-to-a-file"></a><span data-ttu-id="164bd-234">若要将应用程序定义导出到文件</span><span class="sxs-lookup"><span data-stu-id="164bd-234">To export the application definition to a file</span></span>  
  
1.  <span data-ttu-id="164bd-235">右键单击**Siebel_Account**节点在元数据对象窗格中，然后单击**导出**。</span><span class="sxs-lookup"><span data-stu-id="164bd-235">Right-click the **Siebel_Account** node in the Metadata Objects pane, and then click **Export**.</span></span>  
  
2.  <span data-ttu-id="164bd-236">将文件另存 Siebel_Account.xml。</span><span class="sxs-lookup"><span data-stu-id="164bd-236">Save the file as Siebel_Account.xml.</span></span>  
  
### <a name="modify-the-application-definition-file-to-include-specific-parameters"></a><span data-ttu-id="164bd-237">修改应用程序定义文件以包括特定的参数</span><span class="sxs-lookup"><span data-stu-id="164bd-237">Modify the Application Definition File to Include Specific Parameters</span></span>  
 <span data-ttu-id="164bd-238">如本主题前面所述，Business Data Catalog Definition Editor 工具不处理枚举的数据类型。</span><span class="sxs-lookup"><span data-stu-id="164bd-238">As mentioned earlier in this topic, the Business Data Catalog Definition Editor tool does not handle enumerated data types.</span></span> <span data-ttu-id="164bd-239">Business Data Catalog Definition Editor 工具导入字段，直到它遇到的枚举的数据类型，并忽略剩余的字段。</span><span class="sxs-lookup"><span data-stu-id="164bd-239">The Business Data Catalog Definition Editor tool imports the fields till it encounters an enumerated data type and ignores the remaining fields.</span></span> <span data-ttu-id="164bd-240">因此，你想在应用程序中的某些字段可能被取消。</span><span class="sxs-lookup"><span data-stu-id="164bd-240">So, certain fields that you want in your application might be omitted.</span></span> <span data-ttu-id="164bd-241">您可以手动编辑应用程序定义文件以包括这些字段。</span><span class="sxs-lookup"><span data-stu-id="164bd-241">You can manually edit the application definition file to include those fields.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="164bd-242">您必须确保要添加的参数是由 WCF 适配器服务开发向导中生成的.cs 文件中存在[步骤 1： 将 Siebel 业务组件操作作为 WCF 服务发布](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md)。</span><span class="sxs-lookup"><span data-stu-id="164bd-242">You must make sure the parameters you are adding are present in the .cs file generated by the WCF Adapter Service Development Wizard in [Step 1: Publish the Siebel Business Component Operations as a WCF Service](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md).</span></span>  
  
 <span data-ttu-id="164bd-243">在此应用程序定义文件中，您将添加或删除的返回参数**QueryAccount**方法。</span><span class="sxs-lookup"><span data-stu-id="164bd-243">In this application definition file, you will add or remove return parameters for the **QueryAccount** method.</span></span>  
  
##### <a name="to-modify-the-application-definition-file"></a><span data-ttu-id="164bd-244">若要修改应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="164bd-244">To modify the application definition file</span></span>  
  
1. <span data-ttu-id="164bd-245">使用打开的应用程序定义文件，Siebel_Account.xml，[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]或任何其他编辑器。</span><span class="sxs-lookup"><span data-stu-id="164bd-245">Open the application definition file, Siebel_Account.xml, by using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or any other editor.</span></span>  
  
2. <span data-ttu-id="164bd-246">修改应用程序定义文件，若要替换的参数**QueryAccount**方法。</span><span class="sxs-lookup"><span data-stu-id="164bd-246">Modify the application definition file to replace the parameters for the **QueryAccount** method.</span></span>  
  
   1.  <span data-ttu-id="164bd-247">在应用程序定义文件中，搜索以下：</span><span class="sxs-lookup"><span data-stu-id="164bd-247">Within the application definition file, search for the following:</span></span>  
  
       ```  
       <TypeDescriptor TypeName="BDC.AccountQueryRecord,Siebel_Account" Name="Item">  
       ```  
  
   2.  <span data-ttu-id="164bd-248">内`<TypeDescriptors>`标记中，替换现有`<TypeDescriptor>`具有以下元素：</span><span class="sxs-lookup"><span data-stu-id="164bd-248">Within the `<TypeDescriptors>` tag, replace the existing `<TypeDescriptor>` elements with the following:</span></span>  
  
       ```  
  
       <TypeDescriptor TypeName="System.String, mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=<token>" Name="Id" />  
       <TypeDescriptor TypeName="System.String, mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=<token>" Name="Country" />  
       <TypeDescriptor TypeName="System.String, mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=<token>" Name="Name" />  
       <TypeDescriptor TypeName="System.String, mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=<token>" Name="Location" />  
       ```  
  
   3.  <span data-ttu-id="164bd-249">保存并关闭该文件。</span><span class="sxs-lookup"><span data-stu-id="164bd-249">Save and close the file.</span></span>  
  
   > [!TIP]
   >  <span data-ttu-id="164bd-250">可以导入回中 Business Data Catalog Definition Editor 工具，可查看新添加的字段的更新的应用程序定义文件。</span><span class="sxs-lookup"><span data-stu-id="164bd-250">You can import the updated application definition file back in the Business Data Catalog Definition Editor tool to see the newly added fields.</span></span> <span data-ttu-id="164bd-251">但是，在导入之前你将需要从 Business Data Catalog Definition Editor 工具中删除现有"Siebel_Account"应用程序。</span><span class="sxs-lookup"><span data-stu-id="164bd-251">However, before importing you will have to remove the existing “Siebel_Account” application from the Business Data Catalog Definition Editor tool.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="164bd-252">后续步骤</span><span class="sxs-lookup"><span data-stu-id="164bd-252">Next Steps</span></span>  
 <span data-ttu-id="164bd-253">现在必须创建 SharePoint 应用程序以从 Siebel 系统中检索数据。</span><span class="sxs-lookup"><span data-stu-id="164bd-253">You must now create a SharePoint application to retrieve data from a Siebel system.</span></span> <span data-ttu-id="164bd-254">请参阅[第 3 步： 创建 SharePoint 应用程序检索的数据从 Siebel](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md)有关的说明。</span><span class="sxs-lookup"><span data-stu-id="164bd-254">See [Step 3: Create a SharePoint Application to Retrieve Data from Siebel](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md) for instructions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="164bd-255">请参阅</span><span class="sxs-lookup"><span data-stu-id="164bd-255">See Also</span></span>  
 [<span data-ttu-id="164bd-256">教程 1：在 SharePoint 站点上从 Siebel 系统提供数据</span><span class="sxs-lookup"><span data-stu-id="164bd-256">Tutorial 1: Presenting Data From a Siebel System on a SharePoint Site</span></span>](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)