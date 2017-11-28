---
title: "步骤 1： 修改与 Siebel 适配器 vPrev BizTalk 项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b7bd95e2-bd51-420f-8156-6f17cc0e91d6
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5465a80fd7b75dcbf7ec864b196d2fd5033cb003
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-modify-the-vprev-biztalk-project-with-the-siebel-adapter"></a><span data-ttu-id="af133-102">步骤 1： 修改与 Siebel 适配器 vPrev BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="af133-102">Step 1: Modify the vPrev BizTalk Project with the Siebel adapter</span></span>
<span data-ttu-id="af133-103">![步骤 1，共 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span><span class="sxs-lookup"><span data-stu-id="af133-103">![Step 1 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span></span>  
  
 <span data-ttu-id="af133-104">**完成时间：** 10 分钟</span><span class="sxs-lookup"><span data-stu-id="af133-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="af133-105">**目标：**向现有 vPrev BizTalk 项目在此步骤中，进行以下更改：</span><span class="sxs-lookup"><span data-stu-id="af133-105">**Objective:** In this step, you make the following changes to the existing vPrev BizTalk project:</span></span>  
  
-   <span data-ttu-id="af133-106">生成使用基于 WCF 的帐户在业务组件上的插入操作的元数据[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="af133-106">Generate metadata for the Insert operation on the Account business component using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
-   <span data-ttu-id="af133-107">用于执行插入操作执行使用基于 WCF 的插入操作使用请求消息的 vPrev Siebel 适配器将请求消息映射[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="af133-107">Map the request message for performing an Insert operation using the vPrev Siebel adapter to a request message for performing an Insert operation using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
-   <span data-ttu-id="af133-108">将使用基于 WCF 的接收响应消息映射[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]到 vPrev Siebel 适配器的响应消息。</span><span class="sxs-lookup"><span data-stu-id="af133-108">Map the response message received using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] to the response message for the vPrev Siebel adapter.</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="af133-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="af133-109">Prerequisite</span></span>  
  
-   <span data-ttu-id="af133-110">你必须具有要在 Siebel 系统中执行插入操作帐户在业务组件上的 vPrev BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="af133-110">You must have a vPrev BizTalk project to perform an Insert operation on the Account business component in the Siebel system.</span></span>  
  
### <a name="to-modify-the-vprev-biztalk-project"></a><span data-ttu-id="af133-111">若要修改 vPrev BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="af133-111">To modify the vPrev BizTalk project</span></span>  
  
1.  <span data-ttu-id="af133-112">生成使用基于 WCF 的帐户在业务组件上的插入操作的元数据[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="af133-112">Generate metadata for the Insert operation on the Account business component using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="af133-113">你可以使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]生成的元数据。</span><span class="sxs-lookup"><span data-stu-id="af133-113">You can use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to generate metadata.</span></span>  
  
     <span data-ttu-id="af133-114">有关如何生成元数据的说明，请参阅[获取 Visual Studio 中的 Siebel 操作的元数据](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="af133-114">For instructions on how to generate metadata, see [Get Metadata for Siebel Operations in Visual Studio](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md).</span></span> <span data-ttu-id="af133-115">生成架构后，其名称类似于文件*SiebelBindingSchema.xsd*添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="af133-115">After the schema is generated, a file with the name similar to *SiebelBindingSchema.xsd* is added to the BizTalk project.</span></span> <span data-ttu-id="af133-116">此文件包含发送一条消息，执行使用基于 WCF 的帐户在业务组件上的插入操作的架构[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="af133-116">This file contains the schema for sending a message to perform the Insert operation on the Account business component using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
2.  <span data-ttu-id="af133-117">生成插入操作的元数据还会创建端口绑定文件。</span><span class="sxs-lookup"><span data-stu-id="af133-117">Generating the metadata for the Insert operation also creates a port binding file.</span></span> <span data-ttu-id="af133-118">在下一步的步骤中，此绑定文件将用于创建 WCF 自定义发送端口将消息发送到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="af133-118">In the next step, this binding file will be used to create a WCF-Custom send port to send messages to the Siebel system.</span></span> <span data-ttu-id="af133-119">该操作的 SOAP 操作也设置为其生成元数据的操作。</span><span class="sxs-lookup"><span data-stu-id="af133-119">The SOAP action for the operation is also set to the operation for which you generated metadata.</span></span> <span data-ttu-id="af133-120">例如，如果生成用于插入操作的元数据，请在发送端口上的 SOAP 操作中的操作名称将"插入"。</span><span class="sxs-lookup"><span data-stu-id="af133-120">For example, if you generate metadata for the Insert operation, the operation name in the SOAP action on the send port will be “Insert”.</span></span> <span data-ttu-id="af133-121">但是，该操作将在你为业务流程的一部分可能不同，例如，创建的逻辑发送端口上"Operation_1"。</span><span class="sxs-lookup"><span data-stu-id="af133-121">However, the operation name on the logical send port that you create as part of the orchestration could be different, for example, “Operation_1”.</span></span> <span data-ttu-id="af133-122">结果是，当消息发送到 Siebel 系统使用发送端口时，你将收到错误。</span><span class="sxs-lookup"><span data-stu-id="af133-122">As a result, when you send messages to the Siebel system using the send port, you get an error.</span></span> <span data-ttu-id="af133-123">若要防止此情况，请确保发送端口业务流程中的是为其生成元数据的操作名称相同的逻辑上的操作名称。</span><span class="sxs-lookup"><span data-stu-id="af133-123">To prevent this, make sure the operation name on the logical send port in your orchestration is the same as the operation name for which you generated metadata.</span></span>  
  
     <span data-ttu-id="af133-124">因此，本教程中，如果由于生成用于插入操作的元数据，更改到"插入"的逻辑发送端口操作的名称。</span><span class="sxs-lookup"><span data-stu-id="af133-124">So, in case of this tutorial, because you generate metadata for the Insert operation, change the name of the logical send port operation to “Insert”.</span></span>  
  
3.  <span data-ttu-id="af133-125">对于请求消息中，生成使用生成使用基于 WCF 的架构 vPrev Siebel 适配器将架构映射[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="af133-125">For the request message, map the schema generated using vPrev Siebel adapter to the schema generated using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
    1.  <span data-ttu-id="af133-126">将 BizTalk 映射程序添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="af133-126">Add a BizTalk mapper to the BizTalk project.</span></span> <span data-ttu-id="af133-127">右键单击 BizTalk 项目，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="af133-127">Right-click the BizTalk project, point to **Add**, and click **New Item**.</span></span>  
  
         <span data-ttu-id="af133-128">在**添加新项**对话框中，从左侧的窗格中，选择**映射文件**。</span><span class="sxs-lookup"><span data-stu-id="af133-128">In the **Add New Item** dialog box, from the left pane, select **Map Files**.</span></span> <span data-ttu-id="af133-129">从右窗格中，选择**映射**。</span><span class="sxs-lookup"><span data-stu-id="af133-129">From the right pane, select **Map**.</span></span> <span data-ttu-id="af133-130">指定的名称映射，如**RequestMap.btm**。</span><span class="sxs-lookup"><span data-stu-id="af133-130">Specify a name for the map, such as **RequestMap.btm**.</span></span> <span data-ttu-id="af133-131">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="af133-131">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="af133-132">从源架构窗格中，单击**打开源架构**。</span><span class="sxs-lookup"><span data-stu-id="af133-132">From the Source Schema pane, click **Open Source Schema**.</span></span>  
  
    3.  <span data-ttu-id="af133-133">在**BizTalk 类型选取器**对话框框中，展开的项目名称，展开**架构**，然后选择 vPrev Siebel 适配器请求消息的架构。</span><span class="sxs-lookup"><span data-stu-id="af133-133">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the request message for the vPrev Siebel adapter.</span></span> <span data-ttu-id="af133-134">对于本教程中，选择*Siebel_BussComp_Migration.AccountService_Account_x5d*。</span><span class="sxs-lookup"><span data-stu-id="af133-134">For this tutorial, select *Siebel_BussComp_Migration.AccountService_Account_x5d*.</span></span> <span data-ttu-id="af133-135">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="af133-135">Click **OK**.</span></span>  
  
    4.  <span data-ttu-id="af133-136">在**源架构的根节点**对话框中，选择*插入*，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="af133-136">In the **Root Node for Source Schema** dialog box, select *Insert*, and then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="af133-137">从目标架构窗格中，单击**打开目标架构**。</span><span class="sxs-lookup"><span data-stu-id="af133-137">From the Destination Schema pane, click **Open Destination Schema**.</span></span>  
  
    6.  <span data-ttu-id="af133-138">在**BizTalk 类型选取器**对话框框中，展开的项目名称，展开**架构**，并选择基于 WCF 的请求消息的架构[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="af133-138">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the request message for the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="af133-139">对于本教程中，选择*Siebel_BussComp_Migration.SiebelDBBindingSchema*，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="af133-139">For this tutorial, select *Siebel_BussComp_Migration.SiebelDBBindingSchema*, and then click **OK**.</span></span>  
  
    7.  <span data-ttu-id="af133-140">在**目标架构的根节点**对话框中，选择*插入*，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="af133-140">In the **Root Node for Target Schema** dialog box, select *Insert*, and then click **OK**.</span></span>  
  
    8.  <span data-ttu-id="af133-141">映射这两个架构中的以下元素： **Currency_Code**， **Current_Volume**， **Customer_Account_Group**，**位置**，**Main_Phone_Number**，**名称**， **Party_Name**， **Primary_Address_Id**，</span><span class="sxs-lookup"><span data-stu-id="af133-141">Map the following elements in both the schemas: **Currency_Code**, **Current_Volume**, **Customer_Account_Group**, **Location**, **Main_Phone_Number**, **Name**, **Party_Name**, **Primary_Address_Id**,</span></span>  
  
    9. <span data-ttu-id="af133-142">保存映射。</span><span class="sxs-lookup"><span data-stu-id="af133-142">Save the map.</span></span>  
  
4.  <span data-ttu-id="af133-143">响应消息中，生成使用生成使用基于 WCF 的架构 vPrev Siebel 适配器将架构映射[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="af133-143">For the response message, map the schema generated using the vPrev Siebel adapter to the schema generated using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
    1.  <span data-ttu-id="af133-144">将 BizTalk 映射程序添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="af133-144">Add a BizTalk mapper to the BizTalk project.</span></span> <span data-ttu-id="af133-145">右键单击 BizTalk 项目，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="af133-145">Right-click the BizTalk project, point to **Add**, and click **New Item**.</span></span>  
  
         <span data-ttu-id="af133-146">在添加新项对话框中，从左窗格中，选择**映射文件**。</span><span class="sxs-lookup"><span data-stu-id="af133-146">In the Add New Item dialog box, from the left pane, select **Map Files**.</span></span> <span data-ttu-id="af133-147">从右窗格中，选择**映射**。</span><span class="sxs-lookup"><span data-stu-id="af133-147">From the right pane, select **Map**.</span></span> <span data-ttu-id="af133-148">指定的名称映射，如**ResponseMap.btm**。</span><span class="sxs-lookup"><span data-stu-id="af133-148">Specify a name for the map, such as **ResponseMap.btm**.</span></span> <span data-ttu-id="af133-149">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="af133-149">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="af133-150">从源架构窗格中，单击**打开源架构**。</span><span class="sxs-lookup"><span data-stu-id="af133-150">From the Source Schema pane, click **Open Source Schema**.</span></span>  
  
    3.  <span data-ttu-id="af133-151">在**BizTalk 类型选取器**对话框框中，展开的项目名称，展开**架构**，并选择基于 WCF 的响应消息的架构[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="af133-151">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the response message for the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="af133-152">对于本教程中，选择*Siebel_BussComp_Migration.SiebelDBBindingSchema*。</span><span class="sxs-lookup"><span data-stu-id="af133-152">For this tutorial, select *Siebel_BussComp_Migration.SiebelDBBindingSchema*.</span></span> <span data-ttu-id="af133-153">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="af133-153">Click **OK**.</span></span>  
  
    4.  <span data-ttu-id="af133-154">在**源架构的根节点**对话框中，选择*InsertResponse*单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="af133-154">In the **Root Node for Source Schema** dialog box, select *InsertResponse* and click **OK**.</span></span>  
  
    5.  <span data-ttu-id="af133-155">从目标架构窗格中，单击**打开目标架构**。</span><span class="sxs-lookup"><span data-stu-id="af133-155">From the Destination Schema pane, click **Open Destination Schema**.</span></span>  
  
    6.  <span data-ttu-id="af133-156">在**BizTalk 类型选取器**对话框框中，展开的项目名称，展开**架构**，然后选择 vPrev Siebel 适配器的响应消息的架构。</span><span class="sxs-lookup"><span data-stu-id="af133-156">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the response message for the vPrev Siebel adapter.</span></span> <span data-ttu-id="af133-157">对于本教程中，选择*Siebel_BussComp_Migration.AccountService_Account_x5d*。</span><span class="sxs-lookup"><span data-stu-id="af133-157">For this tutorial, select *Siebel_BussComp_Migration.AccountService_Account_x5d*.</span></span> <span data-ttu-id="af133-158">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="af133-158">Click **OK**.</span></span>  
  
    7.  <span data-ttu-id="af133-159">在**目标架构的根节点**对话框中，选择*InsertResponse*单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="af133-159">In the **Root Node for Target Schema** dialog box, select *InsertResponse* and click **OK**.</span></span>  
  
    8.  <span data-ttu-id="af133-160">映射**数组： 字符串**到源架构中的元素**公开： 字符串**在目标架构中下, 图中所示的元素。</span><span class="sxs-lookup"><span data-stu-id="af133-160">Map the **array:string** element in the source schema to the **exposed:string** element in the destination schema, as illustrated in the following figure.</span></span>  
  
         <span data-ttu-id="af133-161">![映射适配器版本之间的响应消息](../../adapters-and-accelerators/adapter-siebel/media/6352035b-79c0-4850-a8f7-e4f6581c8532.gif "6352035b-79c0-4850-a8f7-e4f6581c8532")</span><span class="sxs-lookup"><span data-stu-id="af133-161">![Map the response messages between adapter versions](../../adapters-and-accelerators/adapter-siebel/media/6352035b-79c0-4850-a8f7-e4f6581c8532.gif "6352035b-79c0-4850-a8f7-e4f6581c8532")</span></span>  
  
    9. <span data-ttu-id="af133-162">保存映射。</span><span class="sxs-lookup"><span data-stu-id="af133-162">Save the map.</span></span>  
  
5.  <span data-ttu-id="af133-163">保存并生成 BizTalk 解决方案。</span><span class="sxs-lookup"><span data-stu-id="af133-163">Save and build the BizTalk solution.</span></span> <span data-ttu-id="af133-164">右键单击解决方案，并依次**生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="af133-164">Right-click the solution, and then click **Build Solution**.</span></span>  
  
6.  <span data-ttu-id="af133-165">部署该解决方案。</span><span class="sxs-lookup"><span data-stu-id="af133-165">Deploy the solution.</span></span> <span data-ttu-id="af133-166">右键单击解决方案，并依次**部署解决方案**。</span><span class="sxs-lookup"><span data-stu-id="af133-166">Right-click the solution, and then click **Deploy Solution**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="af133-167">后续步骤</span><span class="sxs-lookup"><span data-stu-id="af133-167">Next Steps</span></span>  
 <span data-ttu-id="af133-168">创建 WCF 自定义发送端口并将其配置为使用你在此步骤中创建的图中所述[步骤 2： 在 BizTalk Server 管理控制台，以使用 Oracle 数据库适配器中配置业务流程](../../adapters-and-accelerators/adapter-oracle-database/step-2-configure-an-orchestration-to-use-the-oracle-db-adapter-in-biztalk.md)。</span><span class="sxs-lookup"><span data-stu-id="af133-168">Create a WCF-custom send port and configure it to use the maps you created in this step, as described in [Step 2: Configure the Orchestration in BizTalk Server Administration Console to use the Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/step-2-configure-an-orchestration-to-use-the-oracle-db-adapter-in-biztalk.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af133-169">另请参阅</span><span class="sxs-lookup"><span data-stu-id="af133-169">See Also</span></span>  
 [<span data-ttu-id="af133-170">教程 2： 迁移中 Siebel 的 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="af133-170">Tutorial 2: Migrating BizTalk Projects in Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/tutorial-2-migrating-biztalk-projects-in-siebel.md)