---
title: 步骤 1： 修改 vPrev Oracle 数据库中的 BizTalk 项目 |Microsoft 文档
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
ms.openlocfilehash: 4f8911a31eeec34a5508d29ff598a2f7624e5cd6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216189"
---
# <a name="step-1-modify-the-vprev-biztalk-project-in-oracle-database"></a><span data-ttu-id="8e424-102">步骤 1： 修改 vPrev Oracle 数据库中的 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="8e424-102">Step 1: Modify the vPrev BizTalk Project in Oracle Database</span></span>
<span data-ttu-id="8e424-103">![步骤 1，共 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span><span class="sxs-lookup"><span data-stu-id="8e424-103">![Step 1 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span></span>  
  
 <span data-ttu-id="8e424-104">**完成时间：** 10 分钟</span><span class="sxs-lookup"><span data-stu-id="8e424-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="8e424-105">**目标：** 向现有 vPrev BizTalk 项目在此步骤中，进行以下更改：</span><span class="sxs-lookup"><span data-stu-id="8e424-105">**Objective:** In this step, you make the following changes to the existing vPrev BizTalk project:</span></span>  
  
-   <span data-ttu-id="8e424-106">生成 SCOTT 上的插入操作的元数据。使用基于 WCF 的 CUSTOMER 表[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8e424-106">Generate metadata for the Insert operation on the SCOTT.CUSTOMER table using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
-   <span data-ttu-id="8e424-107">用于执行插入操作执行使用基于 WCF 的插入操作使用请求消息的 vPrev Oracle 数据库适配器将请求消息映射[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8e424-107">Map the request message for performing an Insert operation using the vPrev Oracle database adapter to a request message for performing an Insert operation using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
-   <span data-ttu-id="8e424-108">将使用基于 WCF 的接收响应消息映射[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]到 vPrev Oracle 数据库适配器的响应消息。</span><span class="sxs-lookup"><span data-stu-id="8e424-108">Map the response message received using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to the response message for the vPrev Oracle database adapter.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8e424-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="8e424-109">Prerequisites</span></span>  
  
-   <span data-ttu-id="8e424-110">你必须具有 vPrev BizTalk 项目，以执行插入操作上 SCOTT。Oracle 数据库中的 CUSTOMER 表。</span><span class="sxs-lookup"><span data-stu-id="8e424-110">You must have a vPrev BizTalk project to perform an Insert operation on the SCOTT.CUSTOMER table in the Oracle database.</span></span>  
  
## <a name="modify-the-vprev-biztalk-project"></a><span data-ttu-id="8e424-111">修改 vPrev BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="8e424-111">Modify the vPrev BizTalk project</span></span>  
  
1.  <span data-ttu-id="8e424-112">生成 SCOTT 上的插入操作的元数据。使用基于 WCF 的 CUSTOMER 表[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8e424-112">Generate metadata for the Insert operation on the SCOTT.CUSTOMER table using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="8e424-113">你可以使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]生成的元数据。</span><span class="sxs-lookup"><span data-stu-id="8e424-113">You can use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to generate metadata.</span></span>  
  
     <span data-ttu-id="8e424-114">有关如何生成元数据的说明，请参阅[为 Visual Studio 中的 Oracle 数据库操作获取元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="8e424-114">For instructions on how to generate metadata, see [Get metadata for Oracle Database operations in Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md).</span></span> <span data-ttu-id="8e424-115">生成架构后，其名称类似于文件*OracleDBBindingSchema.xsd*添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="8e424-115">After the schema is generated, a file with the name similar to *OracleDBBindingSchema.xsd* is added to the BizTalk project.</span></span> <span data-ttu-id="8e424-116">此文件包含用于发送一条消息，执行插入操作上 SCOTT 架构。使用基于 WCF 的 Oracle 数据库中的 CUSTOMER 表[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8e424-116">This file contains the schema for sending a message to perform an Insert operation on the SCOTT.CUSTOMER table in the Oracle database using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
2.  <span data-ttu-id="8e424-117">生成插入操作的元数据还会创建端口绑定文件。</span><span class="sxs-lookup"><span data-stu-id="8e424-117">Generating the metadata for the Insert operation also creates a port binding file.</span></span> <span data-ttu-id="8e424-118">在下一步的步骤中，此绑定文件将用于创建 WCF 自定义发送端口将消息发送到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="8e424-118">In the next step, this binding file will be used to create a WCF-Custom send port to send messages to the Oracle database.</span></span> <span data-ttu-id="8e424-119">该操作的 SOAP 操作也设置为其生成元数据的操作。</span><span class="sxs-lookup"><span data-stu-id="8e424-119">The SOAP action for the operation is also set to the operation for which you generated metadata.</span></span> <span data-ttu-id="8e424-120">例如，如果生成用于插入操作的元数据，请在发送端口上的 SOAP 操作中的操作名称将"插入"。</span><span class="sxs-lookup"><span data-stu-id="8e424-120">For example, if you generate metadata for the Insert operation, the operation name in the SOAP action on the send port will be “Insert”.</span></span> <span data-ttu-id="8e424-121">但是，该操作将在你为业务流程的一部分可能不同，例如，创建的逻辑发送端口上"Operation_1"。</span><span class="sxs-lookup"><span data-stu-id="8e424-121">However, the operation name on the logical send port that you create as part of the orchestration could be different, for example, “Operation_1”.</span></span> <span data-ttu-id="8e424-122">结果是，当消息发送到使用发送端口的 Oracle 数据库时，你将收到错误。</span><span class="sxs-lookup"><span data-stu-id="8e424-122">As a result, when you send messages to the Oracle database using the send port, you get an error.</span></span> <span data-ttu-id="8e424-123">若要防止此情况，请确保发送端口业务流程中的是为其生成元数据的操作名称相同的逻辑上的操作名称。</span><span class="sxs-lookup"><span data-stu-id="8e424-123">To prevent this, make sure the operation name on the logical send port in your orchestration is the same as the operation name for which you generated metadata.</span></span>  
  
     <span data-ttu-id="8e424-124">因此，本教程中，如果由于生成用于插入操作的元数据，更改到"插入"的逻辑发送端口操作的名称。</span><span class="sxs-lookup"><span data-stu-id="8e424-124">So, in case of this tutorial, because you generate metadata for the Insert operation, change the name of the logical send port operation to “Insert”.</span></span>  
  
3.  <span data-ttu-id="8e424-125">对于请求消息中，生成使用 vPrev 到生成使用基于 WCF 的架构的 Oracle 数据库适配器将架构映射[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8e424-125">For the request message, map the schema generated using vPrev Oracle database adapter to the schema generated using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
    1.  <span data-ttu-id="8e424-126">将 BizTalk 映射程序添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="8e424-126">Add a BizTalk mapper to the BizTalk project.</span></span> <span data-ttu-id="8e424-127">右键单击 BizTalk 项目，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="8e424-127">Right-click the BizTalk project, point to **Add**, and click **New Item**.</span></span>  
  
         <span data-ttu-id="8e424-128">在**添加新项**对话框中，从左侧的窗格中，选择**映射文件**。</span><span class="sxs-lookup"><span data-stu-id="8e424-128">In the **Add New Item** dialog box, from the left pane, select **Map Files**.</span></span> <span data-ttu-id="8e424-129">从右窗格中，选择**映射**。</span><span class="sxs-lookup"><span data-stu-id="8e424-129">From the right pane, select **Map**.</span></span> <span data-ttu-id="8e424-130">指定的名称映射，如**RequestMap.btm**。</span><span class="sxs-lookup"><span data-stu-id="8e424-130">Specify a name for the map, such as **RequestMap.btm**.</span></span> <span data-ttu-id="8e424-131">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="8e424-131">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="8e424-132">从源架构窗格中，单击**打开源架构**。</span><span class="sxs-lookup"><span data-stu-id="8e424-132">From the Source Schema pane, click **Open Source Schema**.</span></span>  
  
    3.  <span data-ttu-id="8e424-133">在**BizTalk 类型选取器**对话框框中，展开的项目名称，展开**架构**，然后选择 vPrev Oracle 数据库适配器请求消息的架构。</span><span class="sxs-lookup"><span data-stu-id="8e424-133">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the request message for the vPrev Oracle database adapter.</span></span> <span data-ttu-id="8e424-134">对于本教程中，选择*Oracle_Migration.CUSTOMERService_CUSTOMER_x5d*。</span><span class="sxs-lookup"><span data-stu-id="8e424-134">For this tutorial, select *Oracle_Migration.CUSTOMERService_CUSTOMER_x5d*.</span></span> <span data-ttu-id="8e424-135">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="8e424-135">Click **OK**.</span></span>  
  
    4.  <span data-ttu-id="8e424-136">在**源架构的根节点**对话框中，选择*插入*单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8e424-136">In the **Root Node for Source Schema** dialog box, select *Insert* and click **OK**.</span></span>  
  
    5.  <span data-ttu-id="8e424-137">从目标架构窗格中，单击**打开目标架构**。</span><span class="sxs-lookup"><span data-stu-id="8e424-137">From the Destination Schema pane, click **Open Destination Schema**.</span></span>  
  
    6.  <span data-ttu-id="8e424-138">在**BizTalk 类型选取器**对话框框中，展开的项目名称，展开**架构**，并选择基于 WCF 的请求消息的架构[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8e424-138">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the request message for the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="8e424-139">对于本教程中，选择*Oracle_Migration.OracleDBBindingSchema*。</span><span class="sxs-lookup"><span data-stu-id="8e424-139">For this tutorial, select *Oracle_Migration.OracleDBBindingSchema*.</span></span> <span data-ttu-id="8e424-140">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="8e424-140">Click **OK**.</span></span>  
  
    7.  <span data-ttu-id="8e424-141">在**目标架构的根节点**对话框中，选择*插入*单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8e424-141">In the **Root Node for Target Schema** dialog box, select *Insert* and click **OK**.</span></span>  
  
    8.  <span data-ttu-id="8e424-142">下图中所示映射这两个架构中的相应元素。</span><span class="sxs-lookup"><span data-stu-id="8e424-142">Map the respective elements in both the schemas as illustrated in the following figure.</span></span>  
  
         <span data-ttu-id="8e424-143">![映射到 Oracle 数据库发送的请求](../../adapters-and-accelerators/adapter-oracle-database/media/4cb59338-40d1-4eb1-bd89-b5a3183959e1.gif "4cb59338-40d1-4eb1-bd89-b5a3183959e1")</span><span class="sxs-lookup"><span data-stu-id="8e424-143">![Map the request sent to the Oracle database](../../adapters-and-accelerators/adapter-oracle-database/media/4cb59338-40d1-4eb1-bd89-b5a3183959e1.gif "4cb59338-40d1-4eb1-bd89-b5a3183959e1")</span></span>  
  
    9. <span data-ttu-id="8e424-144">保存映射。</span><span class="sxs-lookup"><span data-stu-id="8e424-144">Save the map.</span></span>  
  
4.  <span data-ttu-id="8e424-145">响应消息中，生成使用 vPrev 到生成使用基于 WCF 的架构的 Oracle 数据库适配器将架构映射[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8e424-145">For the response message, map the schema generated using vPrev Oracle database adapter to the schema generated using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
    1.  <span data-ttu-id="8e424-146">将 BizTalk 映射程序添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="8e424-146">Add a BizTalk mapper to the BizTalk project.</span></span> <span data-ttu-id="8e424-147">右键单击 BizTalk 项目，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="8e424-147">Right-click the BizTalk project, point to **Add**, and click **New Item**.</span></span>  
  
         <span data-ttu-id="8e424-148">在**添加新项**对话框中，从左侧的窗格中，选择**映射文件**。</span><span class="sxs-lookup"><span data-stu-id="8e424-148">In the **Add New Item** dialog box, from the left pane, select **Map Files**.</span></span> <span data-ttu-id="8e424-149">从右窗格中，选择**映射**。</span><span class="sxs-lookup"><span data-stu-id="8e424-149">From the right pane, select **Map**.</span></span> <span data-ttu-id="8e424-150">指定的名称映射，如**ResponseMap.btm**。</span><span class="sxs-lookup"><span data-stu-id="8e424-150">Specify a name for the map, such as **ResponseMap.btm**.</span></span> <span data-ttu-id="8e424-151">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="8e424-151">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="8e424-152">从源架构窗格中，单击**打开源架构**。</span><span class="sxs-lookup"><span data-stu-id="8e424-152">From the Source Schema pane, click **Open Source Schema**.</span></span>  
  
    3.  <span data-ttu-id="8e424-153">在**BizTalk 类型选取器**对话框框中，展开的项目名称，展开**架构**，并选择基于 WCF 的响应消息的架构[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8e424-153">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the response message for the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="8e424-154">对于本教程中，选择*Oracle_Migration.OracleDBBindingSchema*。</span><span class="sxs-lookup"><span data-stu-id="8e424-154">For this tutorial, select *Oracle_Migration.OracleDBBindingSchema*.</span></span> <span data-ttu-id="8e424-155">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="8e424-155">Click **OK**.</span></span>  
  
    4.  <span data-ttu-id="8e424-156">在**源架构的根节点**对话框中，选择*InsertResponse*单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8e424-156">In the **Root Node for Source Schema** dialog box, select *InsertResponse* and click **OK**.</span></span>  
  
    5.  <span data-ttu-id="8e424-157">从目标架构窗格中，单击**打开目标架构**。</span><span class="sxs-lookup"><span data-stu-id="8e424-157">From the Destination Schema pane, click **Open Destination Schema**.</span></span>  
  
    6.  <span data-ttu-id="8e424-158">在**BizTalk 类型选取器**对话框框中，展开的项目名称，展开**架构**，然后选择 vPrev Oracle 数据库适配器的响应消息的架构。</span><span class="sxs-lookup"><span data-stu-id="8e424-158">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the response message for the vPrev Oracle database adapter.</span></span> <span data-ttu-id="8e424-159">对于本教程中，选择*Oracle_Migration.CUSTOMERService_CUSTOMER_x5d*。</span><span class="sxs-lookup"><span data-stu-id="8e424-159">For this tutorial, select *Oracle_Migration.CUSTOMERService_CUSTOMER_x5d*.</span></span> <span data-ttu-id="8e424-160">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="8e424-160">Click **OK**.</span></span>  
  
    7.  <span data-ttu-id="8e424-161">在**目标架构的根节点**对话框中，选择*InsertResponse*，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8e424-161">In the **Root Node for Target Schema** dialog box, select *InsertResponse*, and then click **OK**.</span></span>  
  
    8.  <span data-ttu-id="8e424-162">你将注意到，符合基于 WCF 的响应消息的架构[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]包含附加*InsertResult*元素。</span><span class="sxs-lookup"><span data-stu-id="8e424-162">You will notice that the schema for the response message conforming to the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] contains an additional *InsertResult* element.</span></span> <span data-ttu-id="8e424-163">你必须从架构和映射中删除此*InsertResponse*这两个架构中的元素。</span><span class="sxs-lookup"><span data-stu-id="8e424-163">You must remove this from the schema and map the *InsertResponse* element in both the schemas.</span></span>  
  
         <span data-ttu-id="8e424-164">为此，请从**工具箱**，拖动**字符串左侧 Trim** functoid 并将其放映射器网格。</span><span class="sxs-lookup"><span data-stu-id="8e424-164">To do so, from the **Toolbox**, drag the **String Left Trim** functoid and drop it on the mapper grid.</span></span> <span data-ttu-id="8e424-165">连接**InsertResponse** functoid 源架构中的元素。</span><span class="sxs-lookup"><span data-stu-id="8e424-165">Connect the **InsertResponse** element in the source schema to the functoid.</span></span> <span data-ttu-id="8e424-166">同样，连接**InsertResponse** functoid 到目标架构中的元素。</span><span class="sxs-lookup"><span data-stu-id="8e424-166">Similarly, connect the **InsertResponse** element in the destination schema to the functoid.</span></span> <span data-ttu-id="8e424-167">下图说明了如何通过提取 functoid 映射的两个元素。</span><span class="sxs-lookup"><span data-stu-id="8e424-167">The following figure illustrates how the two elements are mapped via the functoid.</span></span>  
  
         <span data-ttu-id="8e424-168">![从 Oracle 数据库接收的响应映射](../../adapters-and-accelerators/adapter-oracle-database/media/7fe18f5b-100f-4fe2-ac92-c111629d7fe9.gif "7fe18f5b-100f-4fe2-ac92-c111629d7fe9")</span><span class="sxs-lookup"><span data-stu-id="8e424-168">![Map the response received from Oracle database](../../adapters-and-accelerators/adapter-oracle-database/media/7fe18f5b-100f-4fe2-ac92-c111629d7fe9.gif "7fe18f5b-100f-4fe2-ac92-c111629d7fe9")</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="8e424-169">有关详细信息，请参阅**字符串左侧 Trim Functoid** [!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="8e424-169">For more information, see the **String Left Trim Functoid** [!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)].</span></span>
  
    9. <span data-ttu-id="8e424-170">保存映射。</span><span class="sxs-lookup"><span data-stu-id="8e424-170">Save the map.</span></span>  
  
5.  <span data-ttu-id="8e424-171">保存并生成 BizTalk 解决方案。</span><span class="sxs-lookup"><span data-stu-id="8e424-171">Save and build the BizTalk solution.</span></span> <span data-ttu-id="8e424-172">右键单击解决方案，并依次**生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="8e424-172">Right-click the solution, and then click **Build Solution**.</span></span>  
  
6.  <span data-ttu-id="8e424-173">部署该解决方案。</span><span class="sxs-lookup"><span data-stu-id="8e424-173">Deploy the solution.</span></span> <span data-ttu-id="8e424-174">右键单击解决方案，并依次**部署解决方案**。</span><span class="sxs-lookup"><span data-stu-id="8e424-174">Right-click the solution, and then click **Deploy Solution**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8e424-175">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8e424-175">Next Steps</span></span>  
 <span data-ttu-id="8e424-176">创建 WCF 自定义发送端口并将其配置为使用你在此步骤中创建的图中所述[步骤 2： 在 Biztalk Server 管理控制台中使用的 SQL 适配器配置业务流程](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-orchestration-to-use-the-sql-adapter-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="8e424-176">Create a WCF-custom send port and configure it to use the maps you created in this step, as described in [Step 2: Configure the Orchestration in Biztalk Server Administration Console using the SQL adapter](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-orchestration-to-use-the-sql-adapter-in-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e424-177">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e424-177">See Also</span></span>  
 <span data-ttu-id="8e424-178">[教程： 迁移 BizTalk 项目](https://msdn.microsoft.com/library/dd788186(v=bts.80).aspx)</span><span class="sxs-lookup"><span data-stu-id="8e424-178">[Tutorial: Migrating BizTalk Projects](https://msdn.microsoft.com/library/dd788186(v=bts.80).aspx)</span></span>