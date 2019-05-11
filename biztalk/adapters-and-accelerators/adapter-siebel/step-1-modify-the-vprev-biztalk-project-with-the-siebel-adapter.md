---
title: 第 1 步：修改 vPrev BizTalk 项目使用 Siebel 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7bd95e2-bd51-420f-8156-6f17cc0e91d6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68a3bc43e3f8f946652b75768c1846a388a28c13
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370899"
---
# <a name="step-1-modify-the-vprev-biztalk-project-with-the-siebel-adapter"></a><span data-ttu-id="dd13d-102">第 1 步：修改 vPrev BizTalk 项目使用 Siebel 适配器</span><span class="sxs-lookup"><span data-stu-id="dd13d-102">Step 1: Modify the vPrev BizTalk Project with the Siebel adapter</span></span>
<span data-ttu-id="dd13d-103">![3 的第 1 步](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span><span class="sxs-lookup"><span data-stu-id="dd13d-103">![Step 1 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span></span>  
  
 <span data-ttu-id="dd13d-104">**若要完成的时间：** 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="dd13d-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="dd13d-105">**目标：** 在此步骤中，向现有 vPrev BizTalk 项目进行以下更改：</span><span class="sxs-lookup"><span data-stu-id="dd13d-105">**Objective:** In this step, you make the following changes to the existing vPrev BizTalk project:</span></span>  
  
- <span data-ttu-id="dd13d-106">为使用基于 WCF 的帐户业务组件上的插入操作生成元数据[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="dd13d-106">Generate metadata for the Insert operation on the Account business component using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
- <span data-ttu-id="dd13d-107">执行插入操作执行 Insert 操作使用基于 WCF 的使用 vPrev Siebel 适配器添加到请求消息的请求消息映射[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="dd13d-107">Map the request message for performing an Insert operation using the vPrev Siebel adapter to a request message for performing an Insert operation using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
- <span data-ttu-id="dd13d-108">使用基于 WCF 的接收响应消息映射[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]到 vPrev Siebel 适配器的响应消息。</span><span class="sxs-lookup"><span data-stu-id="dd13d-108">Map the response message received using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] to the response message for the vPrev Siebel adapter.</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="dd13d-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="dd13d-109">Prerequisite</span></span>  
  
-   <span data-ttu-id="dd13d-110">必须具有要在 Siebel 系统中执行插入操作帐户业务组件上的 vPrev BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="dd13d-110">You must have a vPrev BizTalk project to perform an Insert operation on the Account business component in the Siebel system.</span></span>  
  
### <a name="to-modify-the-vprev-biztalk-project"></a><span data-ttu-id="dd13d-111">若要修改 vPrev BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="dd13d-111">To modify the vPrev BizTalk project</span></span>  
  
1. <span data-ttu-id="dd13d-112">为使用基于 WCF 的帐户业务组件上的插入操作生成元数据[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="dd13d-112">Generate metadata for the Insert operation on the Account business component using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="dd13d-113">可以使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]生成元数据。</span><span class="sxs-lookup"><span data-stu-id="dd13d-113">You can use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to generate metadata.</span></span>  
  
    <span data-ttu-id="dd13d-114">有关如何生成元数据的说明，请参阅[获取 Siebel 操作在 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="dd13d-114">For instructions on how to generate metadata, see [Get Metadata for Siebel Operations in Visual Studio](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md).</span></span> <span data-ttu-id="dd13d-115">生成架构后，具有类似名称的文件*SiebelBindingSchema.xsd*添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="dd13d-115">After the schema is generated, a file with the name similar to *SiebelBindingSchema.xsd* is added to the BizTalk project.</span></span> <span data-ttu-id="dd13d-116">此文件包含发送消息来执行插入操作中使用基于 WCF 的帐户业务组件上的架构[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="dd13d-116">This file contains the schema for sending a message to perform the Insert operation on the Account business component using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
2. <span data-ttu-id="dd13d-117">生成插入操作的元数据还会创建端口绑定文件。</span><span class="sxs-lookup"><span data-stu-id="dd13d-117">Generating the metadata for the Insert operation also creates a port binding file.</span></span> <span data-ttu-id="dd13d-118">在下一步中，此绑定文件将用于创建 WCF 自定义发送端口将消息发送到 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="dd13d-118">In the next step, this binding file will be used to create a WCF-Custom send port to send messages to the Siebel system.</span></span> <span data-ttu-id="dd13d-119">该操作的 SOAP 操作也设置为其生成元数据的操作。</span><span class="sxs-lookup"><span data-stu-id="dd13d-119">The SOAP action for the operation is also set to the operation for which you generated metadata.</span></span> <span data-ttu-id="dd13d-120">例如，如果生成插入操作的元数据，请在发送端口上的 SOAP 操作中的操作名称将"Insert"。</span><span class="sxs-lookup"><span data-stu-id="dd13d-120">For example, if you generate metadata for the Insert operation, the operation name in the SOAP action on the send port will be “Insert”.</span></span> <span data-ttu-id="dd13d-121">但是，该操作命名时创建的业务流程的一部分可能会有所不同，例如，在逻辑发送端口上"Operation_1"。</span><span class="sxs-lookup"><span data-stu-id="dd13d-121">However, the operation name on the logical send port that you create as part of the orchestration could be different, for example, “Operation_1”.</span></span> <span data-ttu-id="dd13d-122">因此时将消息发送到 Siebel 系统使用的发送端口，, 则会出错。</span><span class="sxs-lookup"><span data-stu-id="dd13d-122">As a result, when you send messages to the Siebel system using the send port, you get an error.</span></span> <span data-ttu-id="dd13d-123">若要防止此情况，请确保发送端口在业务流程中的为其生成元数据的操作名称相同的操作名称上的逻辑。</span><span class="sxs-lookup"><span data-stu-id="dd13d-123">To prevent this, make sure the operation name on the logical send port in your orchestration is the same as the operation name for which you generated metadata.</span></span>  
  
    <span data-ttu-id="dd13d-124">因此，对于本教程中，由于生成插入操作的元数据，更改到"插入"的逻辑发送端口操作名称。</span><span class="sxs-lookup"><span data-stu-id="dd13d-124">So, in case of this tutorial, because you generate metadata for the Insert operation, change the name of the logical send port operation to “Insert”.</span></span>  
  
3. <span data-ttu-id="dd13d-125">请求消息映射使用 vPrev Siebel 适配器添加到使用基于 WCF 的生成的架构生成的架构[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="dd13d-125">For the request message, map the schema generated using vPrev Siebel adapter to the schema generated using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
   1. <span data-ttu-id="dd13d-126">将 BizTalk 映射器添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="dd13d-126">Add a BizTalk mapper to the BizTalk project.</span></span> <span data-ttu-id="dd13d-127">右键单击 BizTalk 项目，指向**外**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="dd13d-127">Right-click the BizTalk project, point to **Add**, and click **New Item**.</span></span>  
  
       <span data-ttu-id="dd13d-128">在中**添加新项**对话框中的，从左窗格中，选择**映射文件**。</span><span class="sxs-lookup"><span data-stu-id="dd13d-128">In the **Add New Item** dialog box, from the left pane, select **Map Files**.</span></span> <span data-ttu-id="dd13d-129">从右窗格中，选择**映射**。</span><span class="sxs-lookup"><span data-stu-id="dd13d-129">From the right pane, select **Map**.</span></span> <span data-ttu-id="dd13d-130">指定映射的名称，如**RequestMap.btm**。</span><span class="sxs-lookup"><span data-stu-id="dd13d-130">Specify a name for the map, such as **RequestMap.btm**.</span></span> <span data-ttu-id="dd13d-131">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="dd13d-131">Click **Add**.</span></span>  
  
   2. <span data-ttu-id="dd13d-132">在源架构窗格中，单击**打开源架构**。</span><span class="sxs-lookup"><span data-stu-id="dd13d-132">From the Source Schema pane, click **Open Source Schema**.</span></span>  
  
   3. <span data-ttu-id="dd13d-133">在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，并选择 vPrev Siebel 适配器的请求消息的架构。</span><span class="sxs-lookup"><span data-stu-id="dd13d-133">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the request message for the vPrev Siebel adapter.</span></span> <span data-ttu-id="dd13d-134">对于本教程中，选择*Siebel_BussComp_Migration.AccountService_Account_x5d*。</span><span class="sxs-lookup"><span data-stu-id="dd13d-134">For this tutorial, select *Siebel_BussComp_Migration.AccountService_Account_x5d*.</span></span> <span data-ttu-id="dd13d-135">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="dd13d-135">Click **OK**.</span></span>  
  
   4. <span data-ttu-id="dd13d-136">在中**源架构的根节点**对话框中，选择*插入*，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="dd13d-136">In the **Root Node for Source Schema** dialog box, select *Insert*, and then click **OK**.</span></span>  
  
   5. <span data-ttu-id="dd13d-137">从目标架构窗格中，单击**打开目标架构**。</span><span class="sxs-lookup"><span data-stu-id="dd13d-137">From the Destination Schema pane, click **Open Destination Schema**.</span></span>  
  
   6. <span data-ttu-id="dd13d-138">在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，然后选择的基于 WCF 的请求消息的架构[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="dd13d-138">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the request message for the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="dd13d-139">对于本教程中，选择*Siebel_BussComp_Migration.SiebelDBBindingSchema*，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="dd13d-139">For this tutorial, select *Siebel_BussComp_Migration.SiebelDBBindingSchema*, and then click **OK**.</span></span>  
  
   7. <span data-ttu-id="dd13d-140">在中**目标架构的根节点**对话框中，选择*插入*，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="dd13d-140">In the **Root Node for Target Schema** dialog box, select *Insert*, and then click **OK**.</span></span>  
  
   8. <span data-ttu-id="dd13d-141">映射这两个架构中的下列元素：**Currency_Code**， **Current_Volume**， **Customer_Account_Group**，**位置**， **Main_Phone_Number**， **名称**， **Party_Name**， **Primary_Address_Id**，</span><span class="sxs-lookup"><span data-stu-id="dd13d-141">Map the following elements in both the schemas: **Currency_Code**, **Current_Volume**, **Customer_Account_Group**, **Location**, **Main_Phone_Number**, **Name**, **Party_Name**, **Primary_Address_Id**,</span></span>  
  
   9. <span data-ttu-id="dd13d-142">保存该映射。</span><span class="sxs-lookup"><span data-stu-id="dd13d-142">Save the map.</span></span>  
  
4. <span data-ttu-id="dd13d-143">响应消息中，将映射生成使用 vPrev Siebel 适配器添加到使用基于 WCF 的生成的架构的架构[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="dd13d-143">For the response message, map the schema generated using the vPrev Siebel adapter to the schema generated using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
   1. <span data-ttu-id="dd13d-144">将 BizTalk 映射器添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="dd13d-144">Add a BizTalk mapper to the BizTalk project.</span></span> <span data-ttu-id="dd13d-145">右键单击 BizTalk 项目，指向**外**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="dd13d-145">Right-click the BizTalk project, point to **Add**, and click **New Item**.</span></span>  
  
       <span data-ttu-id="dd13d-146">在添加新项对话框中，从左窗格中，选择**地图文件**。</span><span class="sxs-lookup"><span data-stu-id="dd13d-146">In the Add New Item dialog box, from the left pane, select **Map Files**.</span></span> <span data-ttu-id="dd13d-147">从右窗格中，选择**映射**。</span><span class="sxs-lookup"><span data-stu-id="dd13d-147">From the right pane, select **Map**.</span></span> <span data-ttu-id="dd13d-148">指定映射的名称，如**ResponseMap.btm**。</span><span class="sxs-lookup"><span data-stu-id="dd13d-148">Specify a name for the map, such as **ResponseMap.btm**.</span></span> <span data-ttu-id="dd13d-149">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="dd13d-149">Click **Add**.</span></span>  
  
   2. <span data-ttu-id="dd13d-150">在源架构窗格中，单击**打开源架构**。</span><span class="sxs-lookup"><span data-stu-id="dd13d-150">From the Source Schema pane, click **Open Source Schema**.</span></span>  
  
   3. <span data-ttu-id="dd13d-151">在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，然后选择的基于 WCF 的响应消息的架构[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="dd13d-151">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the response message for the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="dd13d-152">对于本教程中，选择*Siebel_BussComp_Migration.SiebelDBBindingSchema*。</span><span class="sxs-lookup"><span data-stu-id="dd13d-152">For this tutorial, select *Siebel_BussComp_Migration.SiebelDBBindingSchema*.</span></span> <span data-ttu-id="dd13d-153">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="dd13d-153">Click **OK**.</span></span>  
  
   4. <span data-ttu-id="dd13d-154">在中**源架构的根节点**对话框中，选择*InsertResponse*然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="dd13d-154">In the **Root Node for Source Schema** dialog box, select *InsertResponse* and click **OK**.</span></span>  
  
   5. <span data-ttu-id="dd13d-155">从目标架构窗格中，单击**打开目标架构**。</span><span class="sxs-lookup"><span data-stu-id="dd13d-155">From the Destination Schema pane, click **Open Destination Schema**.</span></span>  
  
   6. <span data-ttu-id="dd13d-156">在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，并选择 vPrev Siebel 适配器的响应消息的架构。</span><span class="sxs-lookup"><span data-stu-id="dd13d-156">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the response message for the vPrev Siebel adapter.</span></span> <span data-ttu-id="dd13d-157">对于本教程中，选择*Siebel_BussComp_Migration.AccountService_Account_x5d*。</span><span class="sxs-lookup"><span data-stu-id="dd13d-157">For this tutorial, select *Siebel_BussComp_Migration.AccountService_Account_x5d*.</span></span> <span data-ttu-id="dd13d-158">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="dd13d-158">Click **OK**.</span></span>  
  
   7. <span data-ttu-id="dd13d-159">在中**目标架构的根节点**对话框中，选择*InsertResponse*然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="dd13d-159">In the **Root Node for Target Schema** dialog box, select *InsertResponse* and click **OK**.</span></span>  
  
   8. <span data-ttu-id="dd13d-160">地图**数组： 字符串**到源架构中的元素**公开： 字符串**在目标架构中下, 图中所示的元素。</span><span class="sxs-lookup"><span data-stu-id="dd13d-160">Map the **array:string** element in the source schema to the **exposed:string** element in the destination schema, as illustrated in the following figure.</span></span>  
  
       <span data-ttu-id="dd13d-161">![映射响应消息在适配器各版本之间](../../adapters-and-accelerators/adapter-siebel/media/6352035b-79c0-4850-a8f7-e4f6581c8532.gif "6352035b-79c0-4850-a8f7-e4f6581c8532")</span><span class="sxs-lookup"><span data-stu-id="dd13d-161">![Map the response messages between adapter versions](../../adapters-and-accelerators/adapter-siebel/media/6352035b-79c0-4850-a8f7-e4f6581c8532.gif "6352035b-79c0-4850-a8f7-e4f6581c8532")</span></span>  
  
   9. <span data-ttu-id="dd13d-162">保存该映射。</span><span class="sxs-lookup"><span data-stu-id="dd13d-162">Save the map.</span></span>  
  
5. <span data-ttu-id="dd13d-163">保存并生成 BizTalk 解决方案。</span><span class="sxs-lookup"><span data-stu-id="dd13d-163">Save and build the BizTalk solution.</span></span> <span data-ttu-id="dd13d-164">右键单击解决方案，然后依次**生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="dd13d-164">Right-click the solution, and then click **Build Solution**.</span></span>  
  
6. <span data-ttu-id="dd13d-165">部署解决方案。</span><span class="sxs-lookup"><span data-stu-id="dd13d-165">Deploy the solution.</span></span> <span data-ttu-id="dd13d-166">右键单击解决方案，然后依次**部署解决方案**。</span><span class="sxs-lookup"><span data-stu-id="dd13d-166">Right-click the solution, and then click **Deploy Solution**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="dd13d-167">后续步骤</span><span class="sxs-lookup"><span data-stu-id="dd13d-167">Next Steps</span></span>  
 <span data-ttu-id="dd13d-168">创建一个 WCF 自定义发送端口并将其配置为使用在此步骤中创建的地图中所述[步骤 2:若要使用 Oracle 数据库适配器的 BizTalk Server 管理控制台中配置业务流程](../../adapters-and-accelerators/adapter-oracle-database/step-2-configure-an-orchestration-to-use-the-oracle-db-adapter-in-biztalk.md)。</span><span class="sxs-lookup"><span data-stu-id="dd13d-168">Create a WCF-custom send port and configure it to use the maps you created in this step, as described in [Step 2: Configure the Orchestration in BizTalk Server Administration Console to use the Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/step-2-configure-an-orchestration-to-use-the-oracle-db-adapter-in-biztalk.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd13d-169">请参阅</span><span class="sxs-lookup"><span data-stu-id="dd13d-169">See Also</span></span>  
 [<span data-ttu-id="dd13d-170">教程 2：在 Siebel 的 BizTalk 项目迁移</span><span class="sxs-lookup"><span data-stu-id="dd13d-170">Tutorial 2: Migrating BizTalk Projects in Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/tutorial-2-migrating-biztalk-projects-in-siebel.md)