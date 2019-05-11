---
title: 第 1 步：修改 vPrev BizTalk 项目使用 SQL 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 25ad959b-2818-47b8-9a09-3681abb75887
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b54953af2bf3e1a3783dd05f8a98b4ac6bfd32a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367843"
---
# <a name="step-1-modify-the-vprev-biztalk-project-using-the-sql-adapter"></a><span data-ttu-id="3b281-102">第 1 步：修改 vPrev BizTalk 项目使用 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="3b281-102">Step 1: Modify the vPrev BizTalk Project using the SQL adapter</span></span>
<span data-ttu-id="3b281-103">![3 的第 1 步](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span><span class="sxs-lookup"><span data-stu-id="3b281-103">![Step 1 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span></span>  
  
 <span data-ttu-id="3b281-104">**若要完成的时间：** 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="3b281-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="3b281-105">**目标：** 在此步骤中，向现有 vPrev BizTalk 项目进行以下更改：</span><span class="sxs-lookup"><span data-stu-id="3b281-105">**Objective:** In this step, you make the following changes to the existing vPrev BizTalk project:</span></span>  
  
- <span data-ttu-id="3b281-106">生成上使用基于 WCF 的 Customer 表的插入操作的元数据[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3b281-106">Generate metadata for the Insert operation on the Customer table using the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
- <span data-ttu-id="3b281-107">执行插入操作执行 Insert 操作使用基于 WCF 的使用 vPrev SQL 适配器添加到请求消息的请求消息映射[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3b281-107">Map the request message for performing an Insert operation using the vPrev SQL adapter to a request message for performing an Insert operation using the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
- <span data-ttu-id="3b281-108">使用基于 WCF 的接收响应消息映射[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]到使用 vPrev SQL 适配器接收响应消息。</span><span class="sxs-lookup"><span data-stu-id="3b281-108">Map the response message received using the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to the response message received using the vPrev SQL adapter.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3b281-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="3b281-109">Prerequisites</span></span>  
 <span data-ttu-id="3b281-110">必须具有 SQL Server 数据库中执行插入操作的客户表上的 vPrev BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="3b281-110">You must have a vPrev BizTalk project to perform an Insert operation on the Customer table in the SQL Server database.</span></span>  
  
### <a name="to-modify-the-vprev-biztalk-project"></a><span data-ttu-id="3b281-111">若要修改 vPrev BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="3b281-111">To modify the vPrev BizTalk project</span></span>  
  
1. <span data-ttu-id="3b281-112">生成上使用基于 WCF 的 Customer 表的插入操作的元数据[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3b281-112">Generate metadata for the Insert operation on the Customer table using the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="3b281-113">可以使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]生成元数据。</span><span class="sxs-lookup"><span data-stu-id="3b281-113">You can use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to generate metadata.</span></span>  
  
    <span data-ttu-id="3b281-114">有关如何生成元数据的说明，请参阅[获取元数据用于在 Visual Studio 中使用 SQL 适配器的 SQL Server 操作](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="3b281-114">For instructions on how to generate metadata, see [Get Metadata for SQL Server Operations in Visual Studio using the SQL adapter](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md).</span></span> <span data-ttu-id="3b281-115">生成架构后，具有类似名称的文件*TableOperation.dbo.Customer.xsd*添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="3b281-115">After the schema is generated, a file with the name similar to *TableOperation.dbo.Customer.xsd* is added to the BizTalk project.</span></span> <span data-ttu-id="3b281-116">此文件包含发送消息来使用基于 WCF 的在 SQL Server 数据库中执行插入操作在 Customer 表的架构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3b281-116">This file contains the schema for sending a message to perform an Insert operation on the Customer table in the SQL Server database using the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
2. <span data-ttu-id="3b281-117">生成插入操作的元数据还会创建端口绑定文件。</span><span class="sxs-lookup"><span data-stu-id="3b281-117">Generating the metadata for the Insert operation also creates a port binding file.</span></span> <span data-ttu-id="3b281-118">在下一步中，此绑定文件将用于创建 WCF 自定义发送端口将消息发送到 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="3b281-118">In the next step, this binding file will be used to create a WCF-Custom send port to send messages to the SQL Server database.</span></span> <span data-ttu-id="3b281-119">该操作的 SOAP 操作也设置为其生成元数据的操作。</span><span class="sxs-lookup"><span data-stu-id="3b281-119">The SOAP action for the operation is also set to the operation for which you generated metadata.</span></span> <span data-ttu-id="3b281-120">例如，如果生成插入操作的元数据，请在发送端口上的 SOAP 操作中的操作名称将"Insert"。</span><span class="sxs-lookup"><span data-stu-id="3b281-120">For example, if you generate metadata for the Insert operation, the operation name in the SOAP action on the send port will be “Insert”.</span></span> <span data-ttu-id="3b281-121">但是，该操作命名时创建的业务流程的一部分可能会有所不同，例如，在逻辑发送端口上"Operation_1"。</span><span class="sxs-lookup"><span data-stu-id="3b281-121">However, the operation name on the logical send port that you create as part of the orchestration could be different, for example, “Operation_1”.</span></span> <span data-ttu-id="3b281-122">因此时将消息发送到 SQL Server 数据库使用的发送端口，, 则会出错。</span><span class="sxs-lookup"><span data-stu-id="3b281-122">As a result, when you send messages to the SQL Server database using the send port, you get an error.</span></span> <span data-ttu-id="3b281-123">若要防止此情况，请确保发送端口在业务流程中的为其生成元数据的操作名称相同的操作名称上的逻辑。</span><span class="sxs-lookup"><span data-stu-id="3b281-123">To prevent this, make sure the operation name on the logical send port in your orchestration is the same as the operation name for which you generated metadata.</span></span>  
  
    <span data-ttu-id="3b281-124">因此，对于本教程中，由于生成插入操作的元数据，更改到"插入"的逻辑发送端口操作名称。</span><span class="sxs-lookup"><span data-stu-id="3b281-124">So, in case of this tutorial, because you generate metadata for the Insert operation, change the name of the logical send port operation to “Insert”.</span></span>  
  
3. <span data-ttu-id="3b281-125">请求消息映射使用 vPrev SQL 数据库适配器添加到使用基于 WCF 的生成的架构生成的架构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3b281-125">For the request message, map the schema generated using vPrev SQL database adapter to the schema generated using the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
   1. <span data-ttu-id="3b281-126">将 BizTalk 映射器添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="3b281-126">Add a BizTalk Mapper to the BizTalk project.</span></span> <span data-ttu-id="3b281-127">右键单击 BizTalk 项目，指向**外**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="3b281-127">Right-click the BizTalk project, point to **Add**, and then click **New Item**.</span></span>  
  
       <span data-ttu-id="3b281-128">在中**添加新项**对话框中的，从左窗格中，选择**映射文件**。</span><span class="sxs-lookup"><span data-stu-id="3b281-128">In the **Add New Item** dialog box, from the left pane, select **Map Files**.</span></span> <span data-ttu-id="3b281-129">从右窗格中，选择**映射**。</span><span class="sxs-lookup"><span data-stu-id="3b281-129">From the right pane, select **Map**.</span></span> <span data-ttu-id="3b281-130">指定映射的名称，如**RequestMap.btm**。</span><span class="sxs-lookup"><span data-stu-id="3b281-130">Specify a name for the map, such as **RequestMap.btm**.</span></span> <span data-ttu-id="3b281-131">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="3b281-131">Click **Add**.</span></span>  
  
   2. <span data-ttu-id="3b281-132">在源架构窗格中，单击**打开源架构**。</span><span class="sxs-lookup"><span data-stu-id="3b281-132">From the Source Schema pane, click **Open Source Schema**.</span></span>  
  
   3. <span data-ttu-id="3b281-133">在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，然后选择用于 vPrev SQL 适配器的请求消息架构。</span><span class="sxs-lookup"><span data-stu-id="3b281-133">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and then select the schema for the request message for the vPrev SQL adapter.</span></span> <span data-ttu-id="3b281-134">对于本教程中，选择*New_Migration.InsertCustomerService*，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3b281-134">For this tutorial, select *New_Migration.InsertCustomerService*, and then click **OK**.</span></span>  
  
   4. <span data-ttu-id="3b281-135">在中**源架构的根节点**对话框中，选择*插入*，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3b281-135">In the **Root Node for Source Schema** dialog box, select *Insert*, and then click **OK**.</span></span>  
  
   5. <span data-ttu-id="3b281-136">从目标架构窗格中，单击**打开目标架构**。</span><span class="sxs-lookup"><span data-stu-id="3b281-136">From the Destination Schema pane, click **Open Destination Schema**.</span></span>  
  
   6. <span data-ttu-id="3b281-137">在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，然后选择用于基于 WCF 的请求消息架构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3b281-137">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and then select the schema for the request message for the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="3b281-138">对于本教程中，选择*New_Migration.TableOperation.dbo.Customer*，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3b281-138">For this tutorial, select *New_Migration.TableOperation.dbo.Customer*, and then click **OK**.</span></span>  
  
   7. <span data-ttu-id="3b281-139">在中**目标架构的根节点**对话框中，选择*插入*，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3b281-139">In the **Root Node for Target Schema** dialog box, select *Insert*, and then click **OK**.</span></span>  
  
   8. <span data-ttu-id="3b281-140">下图中所示映射这两个架构中的相应元素。</span><span class="sxs-lookup"><span data-stu-id="3b281-140">Map the respective elements in both the schemas as illustrated in the following figure.</span></span>  
  
       <span data-ttu-id="3b281-141">![映射请求架构](../../adapters-and-accelerators/adapter-sql/media/850bbf52-fc3e-42c5-b879-51c6e39a502d.gif "850bbf52-fc3e-42c5-b879-51c6e39a502d")</span><span class="sxs-lookup"><span data-stu-id="3b281-141">![Map the request schemas](../../adapters-and-accelerators/adapter-sql/media/850bbf52-fc3e-42c5-b879-51c6e39a502d.gif "850bbf52-fc3e-42c5-b879-51c6e39a502d")</span></span>  
  
   9. <span data-ttu-id="3b281-142">保存该映射。</span><span class="sxs-lookup"><span data-stu-id="3b281-142">Save the map.</span></span>  
  
4. <span data-ttu-id="3b281-143">响应消息中，将映射生成使用 vPrev SQL 适配器添加到使用基于 WCF 的生成的架构的架构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3b281-143">For the response message, map the schema generated using vPrev SQL adapter to the schema generated using the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
   1. <span data-ttu-id="3b281-144">将 BizTalk 映射器添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="3b281-144">Add a BizTalk Mapper to the BizTalk project.</span></span> <span data-ttu-id="3b281-145">右键单击 BizTalk 项目，指向**外**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="3b281-145">Right-click the BizTalk project, point to **Add**, and click **New Item**.</span></span>  
  
       <span data-ttu-id="3b281-146">在中**添加新项**对话框中的，从左窗格中，选择**映射文件**。</span><span class="sxs-lookup"><span data-stu-id="3b281-146">In the **Add New Item** dialog box, from the left pane, select **Map Files**.</span></span> <span data-ttu-id="3b281-147">从右窗格中，选择**映射**。</span><span class="sxs-lookup"><span data-stu-id="3b281-147">From the right pane, select **Map**.</span></span> <span data-ttu-id="3b281-148">指定映射的名称，如**ResponseMap.btm**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="3b281-148">Specify a name for the map, such as **ResponseMap.btm**, and then click **Add**.</span></span>  
  
   2. <span data-ttu-id="3b281-149">在源架构窗格中，单击**打开源架构**。</span><span class="sxs-lookup"><span data-stu-id="3b281-149">From the Source Schema pane, click **Open Source Schema**.</span></span>  
  
   3. <span data-ttu-id="3b281-150">在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，然后选择用于基于 WCF 的响应消息架构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3b281-150">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and then select the schema for the response message for the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="3b281-151">对于本教程中，选择*New_Migration.TableOperation.dbo.Customer*，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3b281-151">For this tutorial, select *New_Migration.TableOperation.dbo.Customer*, and then click **OK**.</span></span>  
  
   4. <span data-ttu-id="3b281-152">在中**源架构的根节点**对话框中，选择*InsertResponse*，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3b281-152">In the **Root Node for Source Schema** dialog box, select *InsertResponse*, and then click **OK**.</span></span>  
  
   5. <span data-ttu-id="3b281-153">从目标架构窗格中，单击**打开目标架构**。</span><span class="sxs-lookup"><span data-stu-id="3b281-153">From the Destination Schema pane, click **Open Destination Schema**.</span></span>  
  
   6. <span data-ttu-id="3b281-154">在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，然后选择用于 vPrev 的响应消息架构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3b281-154">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and then select the schema for the response message for the vPrev [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="3b281-155">对于本教程中，选择*New_Migration.InsertCustomerService*，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3b281-155">For this tutorial, select *New_Migration.InsertCustomerService*, and then click **OK**.</span></span>  
  
   7. <span data-ttu-id="3b281-156">在中**目标架构的根节点**对话框中，选择*InsertResponse*，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3b281-156">In the **Root Node for Target Schema** dialog box, select *InsertResponse*, and then click **OK**.</span></span>  
  
   8. <span data-ttu-id="3b281-157">您会注意到一些差别的响应架构生成的两个适配器。</span><span class="sxs-lookup"><span data-stu-id="3b281-157">You will notice a few differences between the response schemas for generated by the two adapters.</span></span> <span data-ttu-id="3b281-158">可以按如下所示解释这些差异：</span><span class="sxs-lookup"><span data-stu-id="3b281-158">These differences can be explained as follows:</span></span>  
  
      - <span data-ttu-id="3b281-159">使用基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，如果插入的记录到表中包含主键 （并且也是标识字段） 的响应为插入操作将返回插入的行的标识字段的值。</span><span class="sxs-lookup"><span data-stu-id="3b281-159">Using the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], if you insert a record into a table that contains a primary key (and is also an identity field) the response for the Insert operation returns the value for the identity field for the inserted row.</span></span> <span data-ttu-id="3b281-160">因此，与基于 WCF 的响应消息的架构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]包含额外*InsertResult*元素。</span><span class="sxs-lookup"><span data-stu-id="3b281-160">So, the schema for the response message conforming to the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] contains an additional *InsertResult* element.</span></span> <span data-ttu-id="3b281-161">此元素包含一个数组，其中又包含用于插入的行的标识字段。</span><span class="sxs-lookup"><span data-stu-id="3b281-161">This element contains an array, which in turn contains the identity fields for the inserted rows.</span></span>  
  
      - <span data-ttu-id="3b281-162">使用 vPrev [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，如果表中插入一条记录，适配器仅返回空"成功"元素作为响应消息的一部分。</span><span class="sxs-lookup"><span data-stu-id="3b281-162">Using the vPrev [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], if you insert a record into a table, the adapter only returns an empty “Success” element as part of the response message.</span></span>  
  
        <span data-ttu-id="3b281-163">因此，架构映射的方式，从基于 WCF 的响应[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]包含标识字段的值"复制"为"成功"元素，它是来自 vPrev 的响应消息的一部分的一部分[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3b281-163">So, the schemas are mapped in such a way that the response from the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] containing the value for the identity fields is “copied” as part of the “Success” element, which is part of the response message from the vPrev [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="3b281-164">可以使用批量复制 functoid 将从一个架构的元素复制到另一个。</span><span class="sxs-lookup"><span data-stu-id="3b281-164">You can use the Mass Copy functoid to copy elements from one schema into another.</span></span>  
  
        <span data-ttu-id="3b281-165">若要从使用批量复制 functoid**工具箱**、 批量复制 functoid 拖放映射器网格。</span><span class="sxs-lookup"><span data-stu-id="3b281-165">To use the Mass Copy functoid, from the **Toolbox**, drag the Mass Copy functoid and drop it on the Mapper grid.</span></span> <span data-ttu-id="3b281-166">连接**InsertResult**至该 functoid 将源架构中的元素。</span><span class="sxs-lookup"><span data-stu-id="3b281-166">Connect the **InsertResult** element in the source schema to the functoid.</span></span> <span data-ttu-id="3b281-167">同样，连接**成功**functoid 到目标架构中的元素。</span><span class="sxs-lookup"><span data-stu-id="3b281-167">Similarly, connect the **Success** element in the destination schema to the functoid.</span></span> <span data-ttu-id="3b281-168">下图说明了如何通过提取 functoid 映射的两个元素。</span><span class="sxs-lookup"><span data-stu-id="3b281-168">The following figure illustrates how the two elements are mapped via the functoid.</span></span>  
  
        <span data-ttu-id="3b281-169">![映射响应架构](../../adapters-and-accelerators/adapter-sql/media/c4a347ae-8d2d-4357-b18d-37f36bef17c7.gif "c4a347ae-8d2d-4357-b18d-37f36bef17c7")</span><span class="sxs-lookup"><span data-stu-id="3b281-169">![Map the response schemas](../../adapters-and-accelerators/adapter-sql/media/c4a347ae-8d2d-4357-b18d-37f36bef17c7.gif "c4a347ae-8d2d-4357-b18d-37f36bef17c7")</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="3b281-170">有关批量复制 functoid 的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=119749 ](http://go.microsoft.com/fwlink/?LinkId=119749)。</span><span class="sxs-lookup"><span data-stu-id="3b281-170">For more information about the Mass Copy functoid, see [http://go.microsoft.com/fwlink/?LinkId=119749](http://go.microsoft.com/fwlink/?LinkId=119749).</span></span>  
  
   9. <span data-ttu-id="3b281-171">保存该映射。</span><span class="sxs-lookup"><span data-stu-id="3b281-171">Save the map.</span></span>  
  
5. <span data-ttu-id="3b281-172">保存并生成 BizTalk 解决方案。</span><span class="sxs-lookup"><span data-stu-id="3b281-172">Save and build the BizTalk solution.</span></span> <span data-ttu-id="3b281-173">右键单击解决方案，然后依次**生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="3b281-173">Right-click the solution, and then click **Build Solution**.</span></span>  
  
6. <span data-ttu-id="3b281-174">部署解决方案。</span><span class="sxs-lookup"><span data-stu-id="3b281-174">Deploy the solution.</span></span> <span data-ttu-id="3b281-175">右键单击解决方案，然后依次**部署解决方案**。</span><span class="sxs-lookup"><span data-stu-id="3b281-175">Right-click the solution, and then click **Deploy Solution**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="3b281-176">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3b281-176">Next Steps</span></span>  
 <span data-ttu-id="3b281-177">创建 WCF 自定义发送端口，并将其配置为使用在此步骤中创建的地图中所述[步骤 2:在使用 SQL 适配器的 BizTalk Server 管理控制台中配置业务流程](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-orchestration-to-use-the-sql-adapter-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="3b281-177">Create a WCF-custom send port, and configure it to use the maps you created in this step, as described in [Step 2: Configure the Orchestration in BizTalk Server Administration Console using the SQL adapter](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-orchestration-to-use-the-sql-adapter-in-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b281-178">请参阅</span><span class="sxs-lookup"><span data-stu-id="3b281-178">See Also</span></span>  
 [<span data-ttu-id="3b281-179">教程 1:将 BizTalk 项目迁移到 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="3b281-179">Tutorial 1: Migrate BizTalk Projects to the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/tutorial-1-migrate-biztalk-projects-to-the-sql-adapter.md)