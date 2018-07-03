---
title: 步骤 1： 修改 vPrev BizTalk 项目中 Oracle 数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e3e22ac-126b-46ec-a6dc-3421ad721392
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5d55a5535d1f3f2234198d08393a314b1a304e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010566"
---
# <a name="step-1-modify-the-vprev-biztalk-project-in-oracle-database"></a><span data-ttu-id="e3660-102">步骤 1： 修改 vPrev BizTalk 项目中 Oracle 数据库</span><span class="sxs-lookup"><span data-stu-id="e3660-102">Step 1: Modify the vPrev BizTalk Project in Oracle Database</span></span>
<span data-ttu-id="e3660-103">![3 的第 1 步](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span><span class="sxs-lookup"><span data-stu-id="e3660-103">![Step 1 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span></span>  
  
 <span data-ttu-id="e3660-104">**完成时间：** 10 分钟</span><span class="sxs-lookup"><span data-stu-id="e3660-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="e3660-105">**目标：** 到现有 vPrev BizTalk 项目，在此步骤中，进行以下更改：</span><span class="sxs-lookup"><span data-stu-id="e3660-105">**Objective:** In this step, you make the following changes to the existing vPrev BizTalk project:</span></span>  
  
- <span data-ttu-id="e3660-106">生成 SCOTT 上的插入操作的元数据。使用基于 WCF 的 CUSTOMER 表[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e3660-106">Generate metadata for the Insert operation on the SCOTT.CUSTOMER table using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
- <span data-ttu-id="e3660-107">执行插入操作执行 Insert 操作使用基于 WCF 的使用 vPrev Oracle 数据库适配器为请求消息的请求消息映射[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e3660-107">Map the request message for performing an Insert operation using the vPrev Oracle database adapter to a request message for performing an Insert operation using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
- <span data-ttu-id="e3660-108">使用基于 WCF 的接收响应消息映射[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]到 vPrev Oracle 数据库适配器的响应消息。</span><span class="sxs-lookup"><span data-stu-id="e3660-108">Map the response message received using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to the response message for the vPrev Oracle database adapter.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e3660-109">必要條件</span><span class="sxs-lookup"><span data-stu-id="e3660-109">Prerequisites</span></span>  
  
-   <span data-ttu-id="e3660-110">必须具有 vPrev BizTalk 项目，以执行插入操作 SCOTT。Oracle 数据库中的 CUSTOMER 表。</span><span class="sxs-lookup"><span data-stu-id="e3660-110">You must have a vPrev BizTalk project to perform an Insert operation on the SCOTT.CUSTOMER table in the Oracle database.</span></span>  
  
## <a name="modify-the-vprev-biztalk-project"></a><span data-ttu-id="e3660-111">修改 vPrev BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="e3660-111">Modify the vPrev BizTalk project</span></span>  
  
1. <span data-ttu-id="e3660-112">生成 SCOTT 上的插入操作的元数据。使用基于 WCF 的 CUSTOMER 表[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e3660-112">Generate metadata for the Insert operation on the SCOTT.CUSTOMER table using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="e3660-113">可以使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]生成元数据。</span><span class="sxs-lookup"><span data-stu-id="e3660-113">You can use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to generate metadata.</span></span>  
  
    <span data-ttu-id="e3660-114">有关如何生成元数据的说明，请参阅[获取 Visual Studio 中的 Oracle 数据库操作的元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="e3660-114">For instructions on how to generate metadata, see [Get metadata for Oracle Database operations in Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md).</span></span> <span data-ttu-id="e3660-115">生成架构后，具有类似名称的文件*OracleDBBindingSchema.xsd*添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="e3660-115">After the schema is generated, a file with the name similar to *OracleDBBindingSchema.xsd* is added to the BizTalk project.</span></span> <span data-ttu-id="e3660-116">此文件包含发送消息来执行插入操作 SCOTT 的架构。使用基于 WCF 的 Oracle 数据库中的 CUSTOMER 表[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e3660-116">This file contains the schema for sending a message to perform an Insert operation on the SCOTT.CUSTOMER table in the Oracle database using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
2. <span data-ttu-id="e3660-117">生成插入操作的元数据还会创建端口绑定文件。</span><span class="sxs-lookup"><span data-stu-id="e3660-117">Generating the metadata for the Insert operation also creates a port binding file.</span></span> <span data-ttu-id="e3660-118">在下一步中，此绑定文件将用于创建 WCF 自定义发送端口将消息发送到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="e3660-118">In the next step, this binding file will be used to create a WCF-Custom send port to send messages to the Oracle database.</span></span> <span data-ttu-id="e3660-119">该操作的 SOAP 操作也设置为其生成元数据的操作。</span><span class="sxs-lookup"><span data-stu-id="e3660-119">The SOAP action for the operation is also set to the operation for which you generated metadata.</span></span> <span data-ttu-id="e3660-120">例如，如果生成插入操作的元数据，请在发送端口上的 SOAP 操作中的操作名称将"Insert"。</span><span class="sxs-lookup"><span data-stu-id="e3660-120">For example, if you generate metadata for the Insert operation, the operation name in the SOAP action on the send port will be “Insert”.</span></span> <span data-ttu-id="e3660-121">但是，该操作命名时创建的业务流程的一部分可能会有所不同，例如，在逻辑发送端口上"Operation_1"。</span><span class="sxs-lookup"><span data-stu-id="e3660-121">However, the operation name on the logical send port that you create as part of the orchestration could be different, for example, “Operation_1”.</span></span> <span data-ttu-id="e3660-122">因此时将消息发送到 Oracle 数据库使用的发送端口，, 则会出错。</span><span class="sxs-lookup"><span data-stu-id="e3660-122">As a result, when you send messages to the Oracle database using the send port, you get an error.</span></span> <span data-ttu-id="e3660-123">若要防止此情况，请确保发送端口在业务流程中的为其生成元数据的操作名称相同的操作名称上的逻辑。</span><span class="sxs-lookup"><span data-stu-id="e3660-123">To prevent this, make sure the operation name on the logical send port in your orchestration is the same as the operation name for which you generated metadata.</span></span>  
  
    <span data-ttu-id="e3660-124">因此，对于本教程中，由于生成插入操作的元数据，更改到"插入"的逻辑发送端口操作名称。</span><span class="sxs-lookup"><span data-stu-id="e3660-124">So, in case of this tutorial, because you generate metadata for the Insert operation, change the name of the logical send port operation to “Insert”.</span></span>  
  
3. <span data-ttu-id="e3660-125">请求消息映射使用 vPrev Oracle 数据库适配器添加到使用基于 WCF 的生成的架构生成的架构[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e3660-125">For the request message, map the schema generated using vPrev Oracle database adapter to the schema generated using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
   1. <span data-ttu-id="e3660-126">将 BizTalk 映射器添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="e3660-126">Add a BizTalk mapper to the BizTalk project.</span></span> <span data-ttu-id="e3660-127">右键单击 BizTalk 项目，指向**外**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="e3660-127">Right-click the BizTalk project, point to **Add**, and click **New Item**.</span></span>  
  
       <span data-ttu-id="e3660-128">在中**添加新项**对话框中的，从左窗格中，选择**映射文件**。</span><span class="sxs-lookup"><span data-stu-id="e3660-128">In the **Add New Item** dialog box, from the left pane, select **Map Files**.</span></span> <span data-ttu-id="e3660-129">从右窗格中，选择**映射**。</span><span class="sxs-lookup"><span data-stu-id="e3660-129">From the right pane, select **Map**.</span></span> <span data-ttu-id="e3660-130">指定映射的名称，如**RequestMap.btm**。</span><span class="sxs-lookup"><span data-stu-id="e3660-130">Specify a name for the map, such as **RequestMap.btm**.</span></span> <span data-ttu-id="e3660-131">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="e3660-131">Click **Add**.</span></span>  
  
   2. <span data-ttu-id="e3660-132">在源架构窗格中，单击**打开源架构**。</span><span class="sxs-lookup"><span data-stu-id="e3660-132">From the Source Schema pane, click **Open Source Schema**.</span></span>  
  
   3. <span data-ttu-id="e3660-133">在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，并选择 vPrev Oracle 数据库适配器的请求消息的架构。</span><span class="sxs-lookup"><span data-stu-id="e3660-133">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the request message for the vPrev Oracle database adapter.</span></span> <span data-ttu-id="e3660-134">对于本教程中，选择*Oracle_Migration.CUSTOMERService_CUSTOMER_x5d*。</span><span class="sxs-lookup"><span data-stu-id="e3660-134">For this tutorial, select *Oracle_Migration.CUSTOMERService_CUSTOMER_x5d*.</span></span> <span data-ttu-id="e3660-135">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="e3660-135">Click **OK**.</span></span>  
  
   4. <span data-ttu-id="e3660-136">在中**源架构的根节点**对话框中，选择*插入*然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e3660-136">In the **Root Node for Source Schema** dialog box, select *Insert* and click **OK**.</span></span>  
  
   5. <span data-ttu-id="e3660-137">从目标架构窗格中，单击**打开目标架构**。</span><span class="sxs-lookup"><span data-stu-id="e3660-137">From the Destination Schema pane, click **Open Destination Schema**.</span></span>  
  
   6. <span data-ttu-id="e3660-138">在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，然后选择的基于 WCF 的请求消息的架构[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e3660-138">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the request message for the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="e3660-139">对于本教程中，选择*Oracle_Migration.OracleDBBindingSchema*。</span><span class="sxs-lookup"><span data-stu-id="e3660-139">For this tutorial, select *Oracle_Migration.OracleDBBindingSchema*.</span></span> <span data-ttu-id="e3660-140">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="e3660-140">Click **OK**.</span></span>  
  
   7. <span data-ttu-id="e3660-141">在中**目标架构的根节点**对话框中，选择*插入*然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e3660-141">In the **Root Node for Target Schema** dialog box, select *Insert* and click **OK**.</span></span>  
  
   8. <span data-ttu-id="e3660-142">下图中所示映射这两个架构中的相应元素。</span><span class="sxs-lookup"><span data-stu-id="e3660-142">Map the respective elements in both the schemas as illustrated in the following figure.</span></span>  
  
       <span data-ttu-id="e3660-143">![将映射到 Oracle 数据库发送的请求](../../adapters-and-accelerators/adapter-oracle-database/media/4cb59338-40d1-4eb1-bd89-b5a3183959e1.gif "4cb59338-40d1-4eb1-bd89-b5a3183959e1")</span><span class="sxs-lookup"><span data-stu-id="e3660-143">![Map the request sent to the Oracle database](../../adapters-and-accelerators/adapter-oracle-database/media/4cb59338-40d1-4eb1-bd89-b5a3183959e1.gif "4cb59338-40d1-4eb1-bd89-b5a3183959e1")</span></span>  
  
   9. <span data-ttu-id="e3660-144">保存映射。</span><span class="sxs-lookup"><span data-stu-id="e3660-144">Save the map.</span></span>  
  
4. <span data-ttu-id="e3660-145">响应消息中，将映射生成使用 vPrev Oracle 数据库适配器添加到使用基于 WCF 的生成的架构的架构[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e3660-145">For the response message, map the schema generated using vPrev Oracle database adapter to the schema generated using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
   1. <span data-ttu-id="e3660-146">将 BizTalk 映射器添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="e3660-146">Add a BizTalk mapper to the BizTalk project.</span></span> <span data-ttu-id="e3660-147">右键单击 BizTalk 项目，指向**外**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="e3660-147">Right-click the BizTalk project, point to **Add**, and click **New Item**.</span></span>  
  
       <span data-ttu-id="e3660-148">在中**添加新项**对话框中的，从左窗格中，选择**映射文件**。</span><span class="sxs-lookup"><span data-stu-id="e3660-148">In the **Add New Item** dialog box, from the left pane, select **Map Files**.</span></span> <span data-ttu-id="e3660-149">从右窗格中，选择**映射**。</span><span class="sxs-lookup"><span data-stu-id="e3660-149">From the right pane, select **Map**.</span></span> <span data-ttu-id="e3660-150">指定映射的名称，如**ResponseMap.btm**。</span><span class="sxs-lookup"><span data-stu-id="e3660-150">Specify a name for the map, such as **ResponseMap.btm**.</span></span> <span data-ttu-id="e3660-151">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="e3660-151">Click **Add**.</span></span>  
  
   2. <span data-ttu-id="e3660-152">在源架构窗格中，单击**打开源架构**。</span><span class="sxs-lookup"><span data-stu-id="e3660-152">From the Source Schema pane, click **Open Source Schema**.</span></span>  
  
   3. <span data-ttu-id="e3660-153">在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，然后选择的基于 WCF 的响应消息的架构[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e3660-153">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the response message for the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="e3660-154">对于本教程中，选择*Oracle_Migration.OracleDBBindingSchema*。</span><span class="sxs-lookup"><span data-stu-id="e3660-154">For this tutorial, select *Oracle_Migration.OracleDBBindingSchema*.</span></span> <span data-ttu-id="e3660-155">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="e3660-155">Click **OK**.</span></span>  
  
   4. <span data-ttu-id="e3660-156">在中**源架构的根节点**对话框中，选择*InsertResponse*然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e3660-156">In the **Root Node for Source Schema** dialog box, select *InsertResponse* and click **OK**.</span></span>  
  
   5. <span data-ttu-id="e3660-157">从目标架构窗格中，单击**打开目标架构**。</span><span class="sxs-lookup"><span data-stu-id="e3660-157">From the Destination Schema pane, click **Open Destination Schema**.</span></span>  
  
   6. <span data-ttu-id="e3660-158">在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，并选择 vPrev Oracle 数据库适配器的响应消息的架构。</span><span class="sxs-lookup"><span data-stu-id="e3660-158">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the response message for the vPrev Oracle database adapter.</span></span> <span data-ttu-id="e3660-159">对于本教程中，选择*Oracle_Migration.CUSTOMERService_CUSTOMER_x5d*。</span><span class="sxs-lookup"><span data-stu-id="e3660-159">For this tutorial, select *Oracle_Migration.CUSTOMERService_CUSTOMER_x5d*.</span></span> <span data-ttu-id="e3660-160">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="e3660-160">Click **OK**.</span></span>  
  
   7. <span data-ttu-id="e3660-161">在中**目标架构的根节点**对话框中，选择*InsertResponse*，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e3660-161">In the **Root Node for Target Schema** dialog box, select *InsertResponse*, and then click **OK**.</span></span>  
  
   8. <span data-ttu-id="e3660-162">您将注意到，与基于 WCF 的响应消息的架构[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]包含额外*InsertResult*元素。</span><span class="sxs-lookup"><span data-stu-id="e3660-162">You will notice that the schema for the response message conforming to the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] contains an additional *InsertResult* element.</span></span> <span data-ttu-id="e3660-163">你必须从架构和映射中删除这*InsertResponse*这两个架构中的元素。</span><span class="sxs-lookup"><span data-stu-id="e3660-163">You must remove this from the schema and map the *InsertResponse* element in both the schemas.</span></span>  
  
       <span data-ttu-id="e3660-164">为此，请从**工具箱**，拖动**字符串左侧空格裁剪**functoid 并将其放在映射器网格。</span><span class="sxs-lookup"><span data-stu-id="e3660-164">To do so, from the **Toolbox**, drag the **String Left Trim** functoid and drop it on the mapper grid.</span></span> <span data-ttu-id="e3660-165">连接**InsertResponse**至该 functoid 将源架构中的元素。</span><span class="sxs-lookup"><span data-stu-id="e3660-165">Connect the **InsertResponse** element in the source schema to the functoid.</span></span> <span data-ttu-id="e3660-166">同样，连接**InsertResponse** functoid 到目标架构中的元素。</span><span class="sxs-lookup"><span data-stu-id="e3660-166">Similarly, connect the **InsertResponse** element in the destination schema to the functoid.</span></span> <span data-ttu-id="e3660-167">下图说明了如何通过提取 functoid 映射的两个元素。</span><span class="sxs-lookup"><span data-stu-id="e3660-167">The following figure illustrates how the two elements are mapped via the functoid.</span></span>  
  
       <span data-ttu-id="e3660-168">![将映射从 Oracle 数据库接收的响应](../../adapters-and-accelerators/adapter-oracle-database/media/7fe18f5b-100f-4fe2-ac92-c111629d7fe9.gif "7fe18f5b-100f-4fe2-ac92-c111629d7fe9")</span><span class="sxs-lookup"><span data-stu-id="e3660-168">![Map the response received from Oracle database](../../adapters-and-accelerators/adapter-oracle-database/media/7fe18f5b-100f-4fe2-ac92-c111629d7fe9.gif "7fe18f5b-100f-4fe2-ac92-c111629d7fe9")</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="e3660-169">有关详细信息，请参阅**字符串左剪裁 Functoid** [!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="e3660-169">For more information, see the **String Left Trim Functoid** [!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)].</span></span>
  
   9. <span data-ttu-id="e3660-170">保存映射。</span><span class="sxs-lookup"><span data-stu-id="e3660-170">Save the map.</span></span>  
  
5. <span data-ttu-id="e3660-171">保存并生成 BizTalk 解决方案。</span><span class="sxs-lookup"><span data-stu-id="e3660-171">Save and build the BizTalk solution.</span></span> <span data-ttu-id="e3660-172">右键单击解决方案，然后依次**生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="e3660-172">Right-click the solution, and then click **Build Solution**.</span></span>  
  
6. <span data-ttu-id="e3660-173">部署该解决方案。</span><span class="sxs-lookup"><span data-stu-id="e3660-173">Deploy the solution.</span></span> <span data-ttu-id="e3660-174">右键单击解决方案，然后依次**部署解决方案**。</span><span class="sxs-lookup"><span data-stu-id="e3660-174">Right-click the solution, and then click **Deploy Solution**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e3660-175">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e3660-175">Next Steps</span></span>  
 <span data-ttu-id="e3660-176">创建一个 WCF 自定义发送端口并将其配置为使用在此步骤中创建的地图中所述[步骤 2： 使用 SQL 适配器的 Biztalk Server 管理控制台中配置业务流程](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-orchestration-to-use-the-sql-adapter-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="e3660-176">Create a WCF-custom send port and configure it to use the maps you created in this step, as described in [Step 2: Configure the Orchestration in Biztalk Server Administration Console using the SQL adapter](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-orchestration-to-use-the-sql-adapter-in-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3660-177">请参阅</span><span class="sxs-lookup"><span data-stu-id="e3660-177">See Also</span></span>  
 <span data-ttu-id="e3660-178">[教程： 迁移 BizTalk 项目](https://msdn.microsoft.com/library/dd788186(v=bts.80).aspx)</span><span class="sxs-lookup"><span data-stu-id="e3660-178">[Tutorial: Migrating BizTalk Projects](https://msdn.microsoft.com/library/dd788186(v=bts.80).aspx)</span></span>