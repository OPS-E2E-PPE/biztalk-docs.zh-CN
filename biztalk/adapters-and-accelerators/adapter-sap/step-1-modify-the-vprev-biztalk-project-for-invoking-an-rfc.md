---
title: "步骤 1： 用于调用 RFC 修改 vPrev BizTalk 项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- migration, modifying previous version of BizTalk project for invoking an RFC
- migration
ms.assetid: 2d4a6cd7-d216-4e0f-8f82-41e044cd325b
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1f967a268d8baca3ab12f29bbac4b9eccc3cd75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-modify-the-vprev-biztalk-project-for-invoking-an-rfc"></a><span data-ttu-id="7aa39-102">步骤 1： 用于调用 RFC 修改 vPrev BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="7aa39-102">Step 1: Modify the vPrev BizTalk Project for Invoking an RFC</span></span>
<span data-ttu-id="7aa39-103">![步骤 1，共 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span><span class="sxs-lookup"><span data-stu-id="7aa39-103">![Step 1 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span></span>  
  
 <span data-ttu-id="7aa39-104">**完成时间：** 10 分钟</span><span class="sxs-lookup"><span data-stu-id="7aa39-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="7aa39-105">**目标：**向现有 vPrev BizTalk 项目在此步骤中，进行以下更改：</span><span class="sxs-lookup"><span data-stu-id="7aa39-105">**Objective:** In this step, you make the following changes to the existing vPrev BizTalk project:</span></span>  
  
-   <span data-ttu-id="7aa39-106">为使用基于 WCF 的 SD_RFC_CUSTOMER_GET RFC 生成元数据[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7aa39-106">Generate metadata for the SD_RFC_CUSTOMER_GET RFC using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
-   <span data-ttu-id="7aa39-107">用于调用的调用使用基于 WCF 的 RFC 使用请求消息的 vPrev SAP 适配器的 RFC 将请求消息映射[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7aa39-107">Map the request message for invoking the RFC using the vPrev SAP adapter to a request message for invoking the RFC using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
-   <span data-ttu-id="7aa39-108">将使用基于 WCF 的接收响应消息映射[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]到 vPrev SAP 适配器的响应消息。</span><span class="sxs-lookup"><span data-stu-id="7aa39-108">Map the response message received using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to the response message for the vPrev SAP adapter.</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="7aa39-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="7aa39-109">Prerequisite</span></span>  
  
-   <span data-ttu-id="7aa39-110">你必须具有 vPrev BizTalk 项目来调用 SD_RFC_CUSTOMER_GET RFC SAP 系统中。</span><span class="sxs-lookup"><span data-stu-id="7aa39-110">You must have a vPrev BizTalk project to invoke the SD_RFC_CUSTOMER_GET RFC in the SAP system.</span></span>  
  
### <a name="to-modify-the-vprev-biztalk-project"></a><span data-ttu-id="7aa39-111">若要修改 vPrev BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="7aa39-111">To modify the vPrev BizTalk project</span></span>  
  
1.  <span data-ttu-id="7aa39-112">为使用基于 WCF 的 SD_RFC_CUSTOMER_GET RFC 生成元数据[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7aa39-112">Generate metadata for the SD_RFC_CUSTOMER_GET RFC using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="7aa39-113">你可以使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]生成的元数据。</span><span class="sxs-lookup"><span data-stu-id="7aa39-113">You can use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to generate metadata.</span></span>  
  
     <span data-ttu-id="7aa39-114">有关如何为 Rfc 生成元数据的说明，请参阅[浏览、 搜索和 get 元数据在 SAP 中的 RFC 操作](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="7aa39-114">For instructions on how to generate metadata for RFCs, see [Browse, search and get metadata for RFC operations in SAP](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md).</span></span> <span data-ttu-id="7aa39-115">生成架构后，其名称类似于文件*SapBindingSchema.xsd*添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="7aa39-115">After the schema is generated, a file with the name similar to *SapBindingSchema.xsd* is added to the BizTalk project.</span></span> <span data-ttu-id="7aa39-116">此文件包含用于调用使用基于 WCF 的 SD_RFC_CUSTOMER_GET 架构[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7aa39-116">This file contains the schema for invoking the SD_RFC_CUSTOMER_GET using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
2.  <span data-ttu-id="7aa39-117">为 SD_RFC_CUSTOMER_GET RFC 生成元数据还会创建端口绑定文件。</span><span class="sxs-lookup"><span data-stu-id="7aa39-117">Generating the metadata for the SD_RFC_CUSTOMER_GET RFC also creates a port binding file.</span></span> <span data-ttu-id="7aa39-118">在下一步的步骤中，此绑定文件将用于创建 WCF 自定义发送端口将消息发送到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="7aa39-118">In the next step, this binding file will be used to create a WCF-Custom send port to send messages to the SAP system.</span></span> <span data-ttu-id="7aa39-119">该操作的 SOAP 操作也设置为其生成元数据的操作。</span><span class="sxs-lookup"><span data-stu-id="7aa39-119">The SOAP action for the operation is also set to the operation for which you generated metadata.</span></span> <span data-ttu-id="7aa39-120">例如，如果为 SD_RFC_CUSTOMER_GET RFC 生成元数据，则在发送端口上的 SOAP 操作中的操作名称将"SD_RFC_CUSTOMER_GET"。</span><span class="sxs-lookup"><span data-stu-id="7aa39-120">For example, if you generate metadata for the SD_RFC_CUSTOMER_GET RFC, the operation name in the SOAP action on the send port will be “SD_RFC_CUSTOMER_GET”.</span></span> <span data-ttu-id="7aa39-121">但是，该操作将在你为业务流程的一部分可能不同，例如，创建的逻辑发送端口上"Operation_1"。</span><span class="sxs-lookup"><span data-stu-id="7aa39-121">However, the operation name on the logical send port that you create as part of the orchestration could be different, for example, “Operation_1”.</span></span> <span data-ttu-id="7aa39-122">结果是，当消息发送到使用发送端口的 SAP 系统时，你将收到错误。</span><span class="sxs-lookup"><span data-stu-id="7aa39-122">As a result, when you send messages to the SAP system using the send port, you get an error.</span></span> <span data-ttu-id="7aa39-123">若要防止此情况，请确保发送端口业务流程中的是为其生成元数据的操作名称相同的逻辑上的操作名称。</span><span class="sxs-lookup"><span data-stu-id="7aa39-123">To prevent this, make sure the operation name on the logical send port in your orchestration is the same as the operation name for which you generated metadata.</span></span>  
  
     <span data-ttu-id="7aa39-124">因此，对于本教程中，由于为 SD_RFC_CUSTOMER_GET RFC 生成元数据，更改到"SD_RFC_CUSTOMER_GET"的逻辑发送端口操作的名称。</span><span class="sxs-lookup"><span data-stu-id="7aa39-124">So, in the case of this tutorial, because you generate metadata for the SD_RFC_CUSTOMER_GET RFC, change the name of the logical send port operation to “SD_RFC_CUSTOMER_GET”.</span></span>  
  
3.  <span data-ttu-id="7aa39-125">对于请求消息中，使用架构生成使用基于 WCF 的 vPrev SAP 适配器生成将架构映射[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7aa39-125">For the request message, map the schema generated using vPrev SAP adapter to the schema generated using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
    1.  <span data-ttu-id="7aa39-126">将 BizTalk 映射程序添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="7aa39-126">Add a BizTalk mapper to the BizTalk project.</span></span> <span data-ttu-id="7aa39-127">右键单击 BizTalk 项目，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="7aa39-127">Right-click the BizTalk project, point to **Add**, and then click **New Item**.</span></span>  
  
         <span data-ttu-id="7aa39-128">在**添加新项**对话框中，从左侧的窗格中，选择**映射文件**。</span><span class="sxs-lookup"><span data-stu-id="7aa39-128">In the **Add New Item** dialog box, from the left pane, select **Map Files**.</span></span> <span data-ttu-id="7aa39-129">从右窗格中，选择**映射**。</span><span class="sxs-lookup"><span data-stu-id="7aa39-129">From the right pane, select **Map**.</span></span> <span data-ttu-id="7aa39-130">指定的名称映射，如**RequestMap.btm**。</span><span class="sxs-lookup"><span data-stu-id="7aa39-130">Specify a name for the map, such as **RequestMap.btm**.</span></span> <span data-ttu-id="7aa39-131">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="7aa39-131">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="7aa39-132">从源架构窗格中，单击**打开源架构**。</span><span class="sxs-lookup"><span data-stu-id="7aa39-132">From the Source Schema pane, click **Open Source Schema**.</span></span>  
  
    3.  <span data-ttu-id="7aa39-133">在**BizTalk 类型选取器**对话框框中，展开的项目名称，展开**架构**，然后选择 vPrev SAP 适配器请求消息的架构。</span><span class="sxs-lookup"><span data-stu-id="7aa39-133">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the request message for the vPrev SAP adapter.</span></span> <span data-ttu-id="7aa39-134">对于本教程中，选择*SAP_Migration.SD_RFC_CUSTOMER_GET__x32003*，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7aa39-134">For this tutorial, select *SAP_Migration.SD_RFC_CUSTOMER_GET__x32003*,and then click **OK**.</span></span>  
  
    4.  <span data-ttu-id="7aa39-135">在**源架构的根节点**对话框中，选择*SD_RFC_CUSTOMER_GET_Request*，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7aa39-135">In the **Root Node for Source Schema** dialog box, select *SD_RFC_CUSTOMER_GET_Request*, and then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="7aa39-136">从目标架构窗格中，单击**打开目标架构**。</span><span class="sxs-lookup"><span data-stu-id="7aa39-136">From the Destination Schema pane, click **Open Destination Schema**.</span></span>  
  
    6.  <span data-ttu-id="7aa39-137">在**BizTalk 类型选取器**对话框框中，展开的项目名称，展开**架构**，并选择基于 WCF 的请求消息的架构[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7aa39-137">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the request message for the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="7aa39-138">对于本教程中，选择*SAP_Migration.SapBindingSchema*，然后单击确定。</span><span class="sxs-lookup"><span data-stu-id="7aa39-138">For this tutorial, select *SAP_Migration.SapBindingSchema*, and then click OK.</span></span>  
  
    7.  <span data-ttu-id="7aa39-139">在**目标架构的根节点**对话框中，选择*SD_RFC_CUSTOMER_GET*，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7aa39-139">In the **Root Node for Target Schema** dialog box, select *SD_RFC_CUSTOMER_GET*, and then click **OK**.</span></span>  
  
         <span data-ttu-id="7aa39-140">下图中所示映射这两个架构中的相应元素。</span><span class="sxs-lookup"><span data-stu-id="7aa39-140">Map the respective elements in both the schemas as illustrated in the following figure.</span></span> <span data-ttu-id="7aa39-141">将使用字符串左侧 Trim functoid CUSTOMER_T 元素的映射。</span><span class="sxs-lookup"><span data-stu-id="7aa39-141">Map the CUSTOMER_T element using a String Left Trim functoid.</span></span> <span data-ttu-id="7aa39-142">为此，请从**工具箱**，拖动**字符串左侧 Trim** functoid 并将其放映射器网格。</span><span class="sxs-lookup"><span data-stu-id="7aa39-142">To do so, from the **Toolbox**, drag the **String Left Trim** functoid and drop it on the mapper grid.</span></span> <span data-ttu-id="7aa39-143">连接**CUSTOMER_T** functoid 源架构中的元素。</span><span class="sxs-lookup"><span data-stu-id="7aa39-143">Connect the **CUSTOMER_T** element in the source schema to the functoid.</span></span> <span data-ttu-id="7aa39-144">同样，连接**CUSTOMER_T** functoid 到目标架构中的元素。</span><span class="sxs-lookup"><span data-stu-id="7aa39-144">Similarly, connect the **CUSTOMER_T** element in the destination schema to the functoid.</span></span> <span data-ttu-id="7aa39-145">下图说明了如何通过提取 functoid 映射的两个元素。</span><span class="sxs-lookup"><span data-stu-id="7aa39-145">The following figure illustrates how the two elements are mapped via the functoid.</span></span>  
  
         <span data-ttu-id="7aa39-146">![适配器版本之间的请求消息映射](../../adapters-and-accelerators/adapter-sap/media/f12f280d-766f-4647-bced-435354206fb9.gif "f12f280d-766f-4647-bced-435354206fb9")</span><span class="sxs-lookup"><span data-stu-id="7aa39-146">![Map the request messages between adapter versions](../../adapters-and-accelerators/adapter-sap/media/f12f280d-766f-4647-bced-435354206fb9.gif "f12f280d-766f-4647-bced-435354206fb9")</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="7aa39-147">有关字符串左侧 Trim functoid 的详细信息，请参阅"字符串左侧 Trim Functoid"网址[http://go.microsoft.com/fwlink/?LinkId=105774](http://go.microsoft.com/fwlink/?LinkId=105774)。</span><span class="sxs-lookup"><span data-stu-id="7aa39-147">For more information about the String Left Trim functoid, see "String Left Trim Functoid" at [http://go.microsoft.com/fwlink/?LinkId=105774](http://go.microsoft.com/fwlink/?LinkId=105774).</span></span>  
  
    8.  <span data-ttu-id="7aa39-148">保存映射。</span><span class="sxs-lookup"><span data-stu-id="7aa39-148">Save the map.</span></span>  
  
4.  <span data-ttu-id="7aa39-149">响应消息中，使用架构生成使用基于 WCF 的 vPrev SAP 适配器生成将架构映射[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7aa39-149">For the response message, map the schema generated using vPrev SAP adapter to the schema generated using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
    1.  <span data-ttu-id="7aa39-150">将 BizTalk 映射程序添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="7aa39-150">Add a BizTalk mapper to the BizTalk project.</span></span> <span data-ttu-id="7aa39-151">右键单击 BizTalk 项目，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="7aa39-151">Right-click the BizTalk project, point to **Add**, and click **New Item**.</span></span>  
  
         <span data-ttu-id="7aa39-152">在**添加新项**对话框中，从左侧的窗格中，选择**映射文件**。</span><span class="sxs-lookup"><span data-stu-id="7aa39-152">In the **Add New Item** dialog box, from the left pane, select **Map Files**.</span></span> <span data-ttu-id="7aa39-153">从右窗格中，选择**映射**。</span><span class="sxs-lookup"><span data-stu-id="7aa39-153">From the right pane, select **Map**.</span></span> <span data-ttu-id="7aa39-154">指定的名称映射，如**ResponseMap.btm**。</span><span class="sxs-lookup"><span data-stu-id="7aa39-154">Specify a name for the map, such as **ResponseMap.btm**.</span></span> <span data-ttu-id="7aa39-155">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="7aa39-155">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="7aa39-156">从源架构窗格中，单击**打开源架构**。</span><span class="sxs-lookup"><span data-stu-id="7aa39-156">From the Source Schema pane, click **Open Source Schema**.</span></span>  
  
    3.  <span data-ttu-id="7aa39-157">在**BizTalk 类型选取器**对话框框中，展开的项目名称，展开**架构**，并选择基于 WCF 的响应消息的架构[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7aa39-157">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the response message for the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="7aa39-158">对于本教程中，选择*SAP_Migration.SapBindingSchema*，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7aa39-158">For this tutorial, select *SAP_Migration.SapBindingSchema*, and then click **OK**.</span></span>  
  
    4.  <span data-ttu-id="7aa39-159">在**源架构的根节点**对话框中，选择*SD_RFC_CUSTOMER_GETResponse*，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7aa39-159">In the **Root Node for Source Schema** dialog box, select *SD_RFC_CUSTOMER_GETResponse*, and then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="7aa39-160">从目标架构窗格中，单击**打开目标架构**。</span><span class="sxs-lookup"><span data-stu-id="7aa39-160">From the Destination Schema pane, click **Open Destination Schema**.</span></span>  
  
    6.  <span data-ttu-id="7aa39-161">在**BizTalk 类型选取器**对话框框中，展开的项目名称，展开**架构**，然后选择 vPrev SAP 适配器的响应消息的架构。</span><span class="sxs-lookup"><span data-stu-id="7aa39-161">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the response message for the vPrev SAP adapter.</span></span> <span data-ttu-id="7aa39-162">对于本教程中，选择*SAP_Migration.SD_RFC_CUSTOMER_GET__x32003*，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7aa39-162">For this tutorial, select *SAP_Migration.SD_RFC_CUSTOMER_GET__x32003*, and then click **OK**.</span></span>  
  
    7.  <span data-ttu-id="7aa39-163">在**目标架构的根节点**对话框中，选择*SD_RFC_CUSTOMER_GET_Response*，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7aa39-163">In the **Root Node for Target Schema** dialog box, select *SD_RFC_CUSTOMER_GET_Response*, and then click **OK**.</span></span>  
  
    8.  <span data-ttu-id="7aa39-164">下图中所示映射这两个架构中的相应元素。</span><span class="sxs-lookup"><span data-stu-id="7aa39-164">Map the respective elements in both the schemas as illustrated in the following figure.</span></span>  
  
         <span data-ttu-id="7aa39-165">![映射适配器版本之间的响应消息](../../adapters-and-accelerators/adapter-sap/media/d8dddaba-d978-4159-bcc6-6a6bfee36564.gif "d8dddaba-d978-4159-bcc6-6a6bfee36564")</span><span class="sxs-lookup"><span data-stu-id="7aa39-165">![Map the response messages between adapter versions](../../adapters-and-accelerators/adapter-sap/media/d8dddaba-d978-4159-bcc6-6a6bfee36564.gif "d8dddaba-d978-4159-bcc6-6a6bfee36564")</span></span>  
  
    9. <span data-ttu-id="7aa39-166">保存映射。</span><span class="sxs-lookup"><span data-stu-id="7aa39-166">Save the map.</span></span>  
  
5.  <span data-ttu-id="7aa39-167">保存并生成 BizTalk 解决方案。</span><span class="sxs-lookup"><span data-stu-id="7aa39-167">Save and build the BizTalk solution.</span></span> <span data-ttu-id="7aa39-168">右键单击解决方案，并依次**生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="7aa39-168">Right-click the solution, and then click **Build Solution**.</span></span>  
  
6.  <span data-ttu-id="7aa39-169">部署该解决方案。</span><span class="sxs-lookup"><span data-stu-id="7aa39-169">Deploy the solution.</span></span> <span data-ttu-id="7aa39-170">右键单击解决方案，并依次**部署解决方案**。</span><span class="sxs-lookup"><span data-stu-id="7aa39-170">Right-click the solution, and then click **Deploy Solution**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7aa39-171">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7aa39-171">Next Steps</span></span>  
 <span data-ttu-id="7aa39-172">创建 WCF 自定义发送端口，并将其配置为使用你在此步骤中创建的图中所述[步骤 2： 在 BizTalk Server 管理控制台中配置业务流程](../../adapters-and-accelerators/adapter-sap/step-2-configure-the-orchestration-in-biztalk-server-administration-console1.md)。</span><span class="sxs-lookup"><span data-stu-id="7aa39-172">Create a WCF-Custom send port, and configure it to use the maps you created in this step, as described in [Step 2: Configure the Orchestration in BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/step-2-configure-the-orchestration-in-biztalk-server-administration-console1.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aa39-173">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7aa39-173">See Also</span></span>  
 [<span data-ttu-id="7aa39-174">教程 2： 迁移 SAP RFC BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="7aa39-174">Tutorial 2: Migrating an SAP RFC BizTalk Project</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-2-migrating-an-sap-rfc-biztalk-project.md)