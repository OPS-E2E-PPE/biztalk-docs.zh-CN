---
title: 步骤 1： 修改 vPrev BizTalk 项目以调用 RFC |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migration, modifying previous version of BizTalk project for invoking an RFC
- migration
ms.assetid: 2d4a6cd7-d216-4e0f-8f82-41e044cd325b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e2624ede6d2710db2d82311c2f452f8be372aa2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969646"
---
# <a name="step-1-modify-the-vprev-biztalk-project-for-invoking-an-rfc"></a><span data-ttu-id="97e0c-102">步骤 1： 修改 vPrev BizTalk 项目以调用 RFC</span><span class="sxs-lookup"><span data-stu-id="97e0c-102">Step 1: Modify the vPrev BizTalk Project for Invoking an RFC</span></span>
<span data-ttu-id="97e0c-103">![3 的第 1 步](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span><span class="sxs-lookup"><span data-stu-id="97e0c-103">![Step 1 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span></span>  
  
 <span data-ttu-id="97e0c-104">**完成时间：** 10 分钟</span><span class="sxs-lookup"><span data-stu-id="97e0c-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="97e0c-105">**目标：** 到现有 vPrev BizTalk 项目，在此步骤中，进行以下更改：</span><span class="sxs-lookup"><span data-stu-id="97e0c-105">**Objective:** In this step, you make the following changes to the existing vPrev BizTalk project:</span></span>  
  
- <span data-ttu-id="97e0c-106">为使用基于 WCF 的 SD_RFC_CUSTOMER_GET RFC 生成元数据[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="97e0c-106">Generate metadata for the SD_RFC_CUSTOMER_GET RFC using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
- <span data-ttu-id="97e0c-107">用于调用 RFC 调用使用基于 WCF 的在 RFC 使用 vPrev SAP 适配器添加到请求消息请求消息映射[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="97e0c-107">Map the request message for invoking the RFC using the vPrev SAP adapter to a request message for invoking the RFC using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
- <span data-ttu-id="97e0c-108">使用基于 WCF 的接收响应消息映射[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]到 vPrev SAP 适配器的响应消息。</span><span class="sxs-lookup"><span data-stu-id="97e0c-108">Map the response message received using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to the response message for the vPrev SAP adapter.</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="97e0c-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="97e0c-109">Prerequisite</span></span>  
  
-   <span data-ttu-id="97e0c-110">必须具有 vPrev BizTalk 项目以调用 SD_RFC_CUSTOMER_GET RFC，SAP 系统中。</span><span class="sxs-lookup"><span data-stu-id="97e0c-110">You must have a vPrev BizTalk project to invoke the SD_RFC_CUSTOMER_GET RFC in the SAP system.</span></span>  
  
### <a name="to-modify-the-vprev-biztalk-project"></a><span data-ttu-id="97e0c-111">若要修改 vPrev BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="97e0c-111">To modify the vPrev BizTalk project</span></span>  
  
1. <span data-ttu-id="97e0c-112">为使用基于 WCF 的 SD_RFC_CUSTOMER_GET RFC 生成元数据[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="97e0c-112">Generate metadata for the SD_RFC_CUSTOMER_GET RFC using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="97e0c-113">可以使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]生成元数据。</span><span class="sxs-lookup"><span data-stu-id="97e0c-113">You can use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to generate metadata.</span></span>  
  
    <span data-ttu-id="97e0c-114">有关如何为 Rfc 生成元数据的说明，请参阅[浏览、 搜索和获取 RFC 操作在 SAP 中的元数据](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="97e0c-114">For instructions on how to generate metadata for RFCs, see [Browse, search and get metadata for RFC operations in SAP](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md).</span></span> <span data-ttu-id="97e0c-115">生成架构后，具有类似名称的文件*SapBindingSchema.xsd*添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="97e0c-115">After the schema is generated, a file with the name similar to *SapBindingSchema.xsd* is added to the BizTalk project.</span></span> <span data-ttu-id="97e0c-116">此文件包含用于调用使用基于 WCF 的 SD_RFC_CUSTOMER_GET 架构[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="97e0c-116">This file contains the schema for invoking the SD_RFC_CUSTOMER_GET using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
2. <span data-ttu-id="97e0c-117">正在为 SD_RFC_CUSTOMER_GET RFC 生成元数据还会创建端口绑定文件。</span><span class="sxs-lookup"><span data-stu-id="97e0c-117">Generating the metadata for the SD_RFC_CUSTOMER_GET RFC also creates a port binding file.</span></span> <span data-ttu-id="97e0c-118">在下一步中，此绑定文件将用于创建 WCF 自定义发送端口将消息发送到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="97e0c-118">In the next step, this binding file will be used to create a WCF-Custom send port to send messages to the SAP system.</span></span> <span data-ttu-id="97e0c-119">该操作的 SOAP 操作也设置为其生成元数据的操作。</span><span class="sxs-lookup"><span data-stu-id="97e0c-119">The SOAP action for the operation is also set to the operation for which you generated metadata.</span></span> <span data-ttu-id="97e0c-120">例如，如果为 SD_RFC_CUSTOMER_GET RFC 生成元数据，请在发送端口上的 SOAP 操作中的操作名称将"SD_RFC_CUSTOMER_GET"。</span><span class="sxs-lookup"><span data-stu-id="97e0c-120">For example, if you generate metadata for the SD_RFC_CUSTOMER_GET RFC, the operation name in the SOAP action on the send port will be “SD_RFC_CUSTOMER_GET”.</span></span> <span data-ttu-id="97e0c-121">但是，该操作命名时创建的业务流程的一部分可能会有所不同，例如，在逻辑发送端口上"Operation_1"。</span><span class="sxs-lookup"><span data-stu-id="97e0c-121">However, the operation name on the logical send port that you create as part of the orchestration could be different, for example, “Operation_1”.</span></span> <span data-ttu-id="97e0c-122">因此时将消息发送到 SAP 系统使用的发送端口，, 则会出错。</span><span class="sxs-lookup"><span data-stu-id="97e0c-122">As a result, when you send messages to the SAP system using the send port, you get an error.</span></span> <span data-ttu-id="97e0c-123">若要防止此情况，请确保发送端口在业务流程中的为其生成元数据的操作名称相同的操作名称上的逻辑。</span><span class="sxs-lookup"><span data-stu-id="97e0c-123">To prevent this, make sure the operation name on the logical send port in your orchestration is the same as the operation name for which you generated metadata.</span></span>  
  
    <span data-ttu-id="97e0c-124">因此，对于本教程中，由于为 SD_RFC_CUSTOMER_GET RFC 生成元数据，请更改到"SD_RFC_CUSTOMER_GET"的逻辑发送端口操作的名称。</span><span class="sxs-lookup"><span data-stu-id="97e0c-124">So, in the case of this tutorial, because you generate metadata for the SD_RFC_CUSTOMER_GET RFC, change the name of the logical send port operation to “SD_RFC_CUSTOMER_GET”.</span></span>  
  
3. <span data-ttu-id="97e0c-125">请求消息映射使用 vPrev SAP 适配器添加到使用基于 WCF 的生成的架构生成的架构[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="97e0c-125">For the request message, map the schema generated using vPrev SAP adapter to the schema generated using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
   1. <span data-ttu-id="97e0c-126">将 BizTalk 映射器添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="97e0c-126">Add a BizTalk mapper to the BizTalk project.</span></span> <span data-ttu-id="97e0c-127">右键单击 BizTalk 项目，指向**外**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="97e0c-127">Right-click the BizTalk project, point to **Add**, and then click **New Item**.</span></span>  
  
       <span data-ttu-id="97e0c-128">在中**添加新项**对话框中的，从左窗格中，选择**映射文件**。</span><span class="sxs-lookup"><span data-stu-id="97e0c-128">In the **Add New Item** dialog box, from the left pane, select **Map Files**.</span></span> <span data-ttu-id="97e0c-129">从右窗格中，选择**映射**。</span><span class="sxs-lookup"><span data-stu-id="97e0c-129">From the right pane, select **Map**.</span></span> <span data-ttu-id="97e0c-130">指定映射的名称，如**RequestMap.btm**。</span><span class="sxs-lookup"><span data-stu-id="97e0c-130">Specify a name for the map, such as **RequestMap.btm**.</span></span> <span data-ttu-id="97e0c-131">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="97e0c-131">Click **Add**.</span></span>  
  
   2. <span data-ttu-id="97e0c-132">在源架构窗格中，单击**打开源架构**。</span><span class="sxs-lookup"><span data-stu-id="97e0c-132">From the Source Schema pane, click **Open Source Schema**.</span></span>  
  
   3. <span data-ttu-id="97e0c-133">在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，并选择 vPrev SAP 适配器的请求消息的架构。</span><span class="sxs-lookup"><span data-stu-id="97e0c-133">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the request message for the vPrev SAP adapter.</span></span> <span data-ttu-id="97e0c-134">对于本教程中，选择*SAP_Migration.SD_RFC_CUSTOMER_GET__x32003*，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="97e0c-134">For this tutorial, select *SAP_Migration.SD_RFC_CUSTOMER_GET__x32003*,and then click **OK**.</span></span>  
  
   4. <span data-ttu-id="97e0c-135">在中**源架构的根节点**对话框中，选择*SD_RFC_CUSTOMER_GET_Request*，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="97e0c-135">In the **Root Node for Source Schema** dialog box, select *SD_RFC_CUSTOMER_GET_Request*, and then click **OK**.</span></span>  
  
   5. <span data-ttu-id="97e0c-136">从目标架构窗格中，单击**打开目标架构**。</span><span class="sxs-lookup"><span data-stu-id="97e0c-136">From the Destination Schema pane, click **Open Destination Schema**.</span></span>  
  
   6. <span data-ttu-id="97e0c-137">在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，然后选择的基于 WCF 的请求消息的架构[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="97e0c-137">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the request message for the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="97e0c-138">对于本教程中，选择*SAP_Migration.SapBindingSchema*，然后单击确定。</span><span class="sxs-lookup"><span data-stu-id="97e0c-138">For this tutorial, select *SAP_Migration.SapBindingSchema*, and then click OK.</span></span>  
  
   7. <span data-ttu-id="97e0c-139">在中**目标架构的根节点**对话框中，选择*SD_RFC_CUSTOMER_GET*，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="97e0c-139">In the **Root Node for Target Schema** dialog box, select *SD_RFC_CUSTOMER_GET*, and then click **OK**.</span></span>  
  
       <span data-ttu-id="97e0c-140">下图中所示映射这两个架构中的相应元素。</span><span class="sxs-lookup"><span data-stu-id="97e0c-140">Map the respective elements in both the schemas as illustrated in the following figure.</span></span> <span data-ttu-id="97e0c-141">使用字符串左侧空格裁剪 functoid 将 CUSTOMER_T 元素映射。</span><span class="sxs-lookup"><span data-stu-id="97e0c-141">Map the CUSTOMER_T element using a String Left Trim functoid.</span></span> <span data-ttu-id="97e0c-142">为此，请从**工具箱**，拖动**字符串左侧空格裁剪**functoid 并将其放在映射器网格。</span><span class="sxs-lookup"><span data-stu-id="97e0c-142">To do so, from the **Toolbox**, drag the **String Left Trim** functoid and drop it on the mapper grid.</span></span> <span data-ttu-id="97e0c-143">连接**CUSTOMER_T**至该 functoid 将源架构中的元素。</span><span class="sxs-lookup"><span data-stu-id="97e0c-143">Connect the **CUSTOMER_T** element in the source schema to the functoid.</span></span> <span data-ttu-id="97e0c-144">同样，连接**CUSTOMER_T** functoid 到目标架构中的元素。</span><span class="sxs-lookup"><span data-stu-id="97e0c-144">Similarly, connect the **CUSTOMER_T** element in the destination schema to the functoid.</span></span> <span data-ttu-id="97e0c-145">下图说明了如何通过提取 functoid 映射的两个元素。</span><span class="sxs-lookup"><span data-stu-id="97e0c-145">The following figure illustrates how the two elements are mapped via the functoid.</span></span>  
  
       <span data-ttu-id="97e0c-146">![将在适配器各版本之间的请求消息映射](../../adapters-and-accelerators/adapter-sap/media/f12f280d-766f-4647-bced-435354206fb9.gif "f12f280d-766f-4647-bced-435354206fb9")</span><span class="sxs-lookup"><span data-stu-id="97e0c-146">![Map the request messages between adapter versions](../../adapters-and-accelerators/adapter-sap/media/f12f280d-766f-4647-bced-435354206fb9.gif "f12f280d-766f-4647-bced-435354206fb9")</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="97e0c-147">有关字符串左侧空格裁剪 functoid 的详细信息，请参阅"字符串左剪裁 ' Functoid"网址[ http://go.microsoft.com/fwlink/?LinkId=105774 ](http://go.microsoft.com/fwlink/?LinkId=105774)。</span><span class="sxs-lookup"><span data-stu-id="97e0c-147">For more information about the String Left Trim functoid, see "String Left Trim Functoid" at [http://go.microsoft.com/fwlink/?LinkId=105774](http://go.microsoft.com/fwlink/?LinkId=105774).</span></span>  
  
   8. <span data-ttu-id="97e0c-148">保存映射。</span><span class="sxs-lookup"><span data-stu-id="97e0c-148">Save the map.</span></span>  
  
4. <span data-ttu-id="97e0c-149">响应消息中，将映射生成使用 vPrev SAP 适配器添加到使用基于 WCF 的生成的架构的架构[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="97e0c-149">For the response message, map the schema generated using vPrev SAP adapter to the schema generated using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
   1. <span data-ttu-id="97e0c-150">将 BizTalk 映射器添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="97e0c-150">Add a BizTalk mapper to the BizTalk project.</span></span> <span data-ttu-id="97e0c-151">右键单击 BizTalk 项目，指向**外**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="97e0c-151">Right-click the BizTalk project, point to **Add**, and click **New Item**.</span></span>  
  
       <span data-ttu-id="97e0c-152">在中**添加新项**对话框中的，从左窗格中，选择**映射文件**。</span><span class="sxs-lookup"><span data-stu-id="97e0c-152">In the **Add New Item** dialog box, from the left pane, select **Map Files**.</span></span> <span data-ttu-id="97e0c-153">从右窗格中，选择**映射**。</span><span class="sxs-lookup"><span data-stu-id="97e0c-153">From the right pane, select **Map**.</span></span> <span data-ttu-id="97e0c-154">指定映射的名称，如**ResponseMap.btm**。</span><span class="sxs-lookup"><span data-stu-id="97e0c-154">Specify a name for the map, such as **ResponseMap.btm**.</span></span> <span data-ttu-id="97e0c-155">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="97e0c-155">Click **Add**.</span></span>  
  
   2. <span data-ttu-id="97e0c-156">在源架构窗格中，单击**打开源架构**。</span><span class="sxs-lookup"><span data-stu-id="97e0c-156">From the Source Schema pane, click **Open Source Schema**.</span></span>  
  
   3. <span data-ttu-id="97e0c-157">在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，然后选择的基于 WCF 的响应消息的架构[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="97e0c-157">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the response message for the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="97e0c-158">对于本教程中，选择*SAP_Migration.SapBindingSchema*，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="97e0c-158">For this tutorial, select *SAP_Migration.SapBindingSchema*, and then click **OK**.</span></span>  
  
   4. <span data-ttu-id="97e0c-159">在中**源架构的根节点**对话框中，选择*SD_RFC_CUSTOMER_GETResponse*，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="97e0c-159">In the **Root Node for Source Schema** dialog box, select *SD_RFC_CUSTOMER_GETResponse*, and then click **OK**.</span></span>  
  
   5. <span data-ttu-id="97e0c-160">从目标架构窗格中，单击**打开目标架构**。</span><span class="sxs-lookup"><span data-stu-id="97e0c-160">From the Destination Schema pane, click **Open Destination Schema**.</span></span>  
  
   6. <span data-ttu-id="97e0c-161">在中**BizTalk 类型选取器**对话框框中，展开项目名称，展开**架构**，并选择 vPrev SAP 适配器的响应消息的架构。</span><span class="sxs-lookup"><span data-stu-id="97e0c-161">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the response message for the vPrev SAP adapter.</span></span> <span data-ttu-id="97e0c-162">对于本教程中，选择*SAP_Migration.SD_RFC_CUSTOMER_GET__x32003*，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="97e0c-162">For this tutorial, select *SAP_Migration.SD_RFC_CUSTOMER_GET__x32003*, and then click **OK**.</span></span>  
  
   7. <span data-ttu-id="97e0c-163">在中**目标架构的根节点**对话框中，选择*SD_RFC_CUSTOMER_GET_Response*，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="97e0c-163">In the **Root Node for Target Schema** dialog box, select *SD_RFC_CUSTOMER_GET_Response*, and then click **OK**.</span></span>  
  
   8. <span data-ttu-id="97e0c-164">下图中所示映射这两个架构中的相应元素。</span><span class="sxs-lookup"><span data-stu-id="97e0c-164">Map the respective elements in both the schemas as illustrated in the following figure.</span></span>  
  
       <span data-ttu-id="97e0c-165">![映射响应消息在适配器各版本之间](../../adapters-and-accelerators/adapter-sap/media/d8dddaba-d978-4159-bcc6-6a6bfee36564.gif "d8dddaba-d978-4159-bcc6-6a6bfee36564")</span><span class="sxs-lookup"><span data-stu-id="97e0c-165">![Map the response messages between adapter versions](../../adapters-and-accelerators/adapter-sap/media/d8dddaba-d978-4159-bcc6-6a6bfee36564.gif "d8dddaba-d978-4159-bcc6-6a6bfee36564")</span></span>  
  
   9. <span data-ttu-id="97e0c-166">保存映射。</span><span class="sxs-lookup"><span data-stu-id="97e0c-166">Save the map.</span></span>  
  
5. <span data-ttu-id="97e0c-167">保存并生成 BizTalk 解决方案。</span><span class="sxs-lookup"><span data-stu-id="97e0c-167">Save and build the BizTalk solution.</span></span> <span data-ttu-id="97e0c-168">右键单击解决方案，然后依次**生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="97e0c-168">Right-click the solution, and then click **Build Solution**.</span></span>  
  
6. <span data-ttu-id="97e0c-169">部署该解决方案。</span><span class="sxs-lookup"><span data-stu-id="97e0c-169">Deploy the solution.</span></span> <span data-ttu-id="97e0c-170">右键单击解决方案，然后依次**部署解决方案**。</span><span class="sxs-lookup"><span data-stu-id="97e0c-170">Right-click the solution, and then click **Deploy Solution**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="97e0c-171">后续步骤</span><span class="sxs-lookup"><span data-stu-id="97e0c-171">Next Steps</span></span>  
 <span data-ttu-id="97e0c-172">创建 WCF 自定义发送端口，并将其配置为使用在此步骤中创建的地图中所述[步骤 2： 在 BizTalk Server 管理控制台中配置业务流程](../../adapters-and-accelerators/adapter-sap/step-2-configure-the-orchestration-in-biztalk-server-administration-console1.md)。</span><span class="sxs-lookup"><span data-stu-id="97e0c-172">Create a WCF-Custom send port, and configure it to use the maps you created in this step, as described in [Step 2: Configure the Orchestration in BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/step-2-configure-the-orchestration-in-biztalk-server-administration-console1.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97e0c-173">请参阅</span><span class="sxs-lookup"><span data-stu-id="97e0c-173">See Also</span></span>  
 [<span data-ttu-id="97e0c-174">教程 2：迁移 SAP RFC BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="97e0c-174">Tutorial 2: Migrating an SAP RFC BizTalk Project</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-2-migrating-an-sap-rfc-biztalk-project.md)