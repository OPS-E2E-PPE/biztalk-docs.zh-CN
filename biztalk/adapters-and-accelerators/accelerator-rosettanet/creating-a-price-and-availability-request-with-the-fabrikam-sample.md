---
title: 创建价格和可用性请求 Fabrikam 示例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating requests
ms.assetid: 6e4f4589-8f01-4b9e-93ee-c9371f32e04a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d0619dc77496fd1547505221ff2f437bf486fb8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="creating-a-price-and-availability-request-with-the-fabrikam-sample"></a><span data-ttu-id="0ecb8-102">创建具有 Fabrikam 示例的价格和可用性请求</span><span class="sxs-lookup"><span data-stu-id="0ecb8-102">Creating a Price and Availability Request with the Fabrikam Sample</span></span>
<span data-ttu-id="0ecb8-103">在此步骤中，将使用 LOBWebApplication 工具创建 3A2 价格与可用性请求。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-103">In this step, you create a 3A2 Price and Availability request using the LOBWebApplication tool.</span></span>  
  
### <a name="to-submit-a-3a2-price-and-availability-request-to-contoso"></a><span data-ttu-id="0ecb8-104">向 Contoso 提交 3A2 价格与可用性请求</span><span class="sxs-lookup"><span data-stu-id="0ecb8-104">To submit a 3A2 Price and Availability request to Contoso</span></span>  
  
1.  <span data-ttu-id="0ecb8-105">在 Internet Explorer 中，移动到 http://\<*fabrikam_computername*\>/LOBWebApplication/default.aspx。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-105">In Internet Explorer, move to http://\<*fabrikam_computername*\>/LOBWebApplication/default.aspx.</span></span>  
  
2.  <span data-ttu-id="0ecb8-106">上**LOBWebApplication**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0ecb8-106">On the **LOBWebApplication** page, do the following:</span></span>  
  
    |<span data-ttu-id="0ecb8-107">使用此选项</span><span class="sxs-lookup"><span data-stu-id="0ecb8-107">Use this</span></span>|<span data-ttu-id="0ecb8-108">执行的操作</span><span class="sxs-lookup"><span data-stu-id="0ecb8-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="0ecb8-109">**本组织**</span><span class="sxs-lookup"><span data-stu-id="0ecb8-109">**Home Organization**</span></span>|<span data-ttu-id="0ecb8-110">类型**FABRIKAM**。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-110">Type **FABRIKAM**.</span></span>|  
    |<span data-ttu-id="0ecb8-111">**伙伴组织**</span><span class="sxs-lookup"><span data-stu-id="0ecb8-111">**Partner Organization**</span></span>|<span data-ttu-id="0ecb8-112">类型**CONTOSO**。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-112">Type **CONTOSO**.</span></span>|  
    |<span data-ttu-id="0ecb8-113">**PIP 代码**</span><span class="sxs-lookup"><span data-stu-id="0ecb8-113">**PIP Code**</span></span>|<span data-ttu-id="0ecb8-114">类型**3A2**。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-114">Type **3A2**.</span></span>|  
    |<span data-ttu-id="0ecb8-115">**PIP 版本**</span><span class="sxs-lookup"><span data-stu-id="0ecb8-115">**PIP Version**</span></span>|<span data-ttu-id="0ecb8-116">类型**R02.00.00A**。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-116">Type **R02.00.00A**.</span></span>|  
    |<span data-ttu-id="0ecb8-117">**消息类别**</span><span class="sxs-lookup"><span data-stu-id="0ecb8-117">**Message Category**</span></span>|<span data-ttu-id="0ecb8-118">类型**操作**。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-118">Type **Action**.</span></span>|  
  
3.  <span data-ttu-id="0ecb8-119">使用记事本或其他文本编辑器，打开**3A2_Request.xml**文件在 C:\Program Files\Microsoft BizTalk\<版本\>RosettaNet\SDK\LOBApplication\SampleInstancesfolder 快捷键复制并粘贴到文本**服务内容**字段 LOBWebApplication 工具。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-119">Using Notepad or another text editor, open the **3A2_Request.xml** file in the C:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstancesfolder and copy and paste the text into the **Service Content** field in the LOBWebApplication tool.</span></span>  
  
4.  <span data-ttu-id="0ecb8-120">单击**提交**以提交到 Contoso 3A2 请求。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-120">Click **Submit** to submit the 3A2 request to Contoso.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a><span data-ttu-id="0ecb8-121">检验 Fabrikam 计算机上的通信是否成功</span><span class="sxs-lookup"><span data-stu-id="0ecb8-121">To verify successful communication on the Fabrikam computer</span></span>  
  
1.  <span data-ttu-id="0ecb8-122">上**消息状态**LOBWebApplication 在页上，请验证是否接收两个传入消息。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-122">On the **Message Status** page in LOBWebApplication, verify that you receive two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0ecb8-123">首先应收到一条类别为 25 的消息，该消息为 Contoso 计算机的确认回执。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-123">You should first receive a category 25 message signifying a receipt acknowledgement from the Contoso computer.</span></span> <span data-ttu-id="0ecb8-124">然后，应收到一条类别为 50 的消息，该消息为 Contoso 计算机的响应消息。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-124">You should then receive a category 50 message that is the response message from the Contoso computer.</span></span> <span data-ttu-id="0ecb8-125">类别为 -99 的消息表示发生错误。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-125">A category -99 message signifies an error.</span></span> <span data-ttu-id="0ecb8-126">你可以使用**事件查看器**以确定实际错误消息。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-126">You can use **Event Viewer** to determine the actual error message.</span></span>  
  
2.  <span data-ttu-id="0ecb8-127">单击**启动**，指向**所有程序**，指向**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-127">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
3.  <span data-ttu-id="0ecb8-128">在连接到服务器对话框中，在**SQL Server**框中，键入**localhost**，选择**Windows 身份验证**，然后单击**连接**.</span><span class="sxs-lookup"><span data-stu-id="0ecb8-128">In the Connect to Server dialog box, in the **SQL Server** box, type **localhost**, select **Windows Authentication**, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="0ecb8-129">在 Microsoft SQL Server Management Studio 中，单击**新查询**。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-129">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
5.  <span data-ttu-id="0ecb8-130">在**\<表\>文本**对话框中，选择**BTARNDATA**从列表中。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-130">In the **\<table\> text** dialog box, select **BTARNDATA** from the list.</span></span>  
  
6.  <span data-ttu-id="0ecb8-131">在**SQL**窗口中，键入以下 SQL 语句：</span><span class="sxs-lookup"><span data-stu-id="0ecb8-131">In the **SQL** window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
7.  <span data-ttu-id="0ecb8-132">单击**执行**运行 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-132">Click **Execute** to run the SQL statement.</span></span>  
  
8.  <span data-ttu-id="0ecb8-133">在“查询”窗口的“结果”窗格中，检验你是否看到两条传入消息。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-133">In the Query window, in the Results pane, verify that you see two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0ecb8-134">应看到类别为 25 的消息，该消息代表从 Contoso 计算机发送到 Fabrikam 计算机的确认回执。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-134">You should see a category 25 message that represents the receipt acknowledgement sent from Contoso to the Fabrikam computer.</span></span> <span data-ttu-id="0ecb8-135">还应看到类别为 50 的消息，该消息代表从 Contoso 业务线 (LOB) 应用程序发送到 Fabrikam 计算机的响应。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-135">You should also see a category 50 message that represents the response sent from the Contoso line-of-business (LOB) application to the Fabrikam computer.</span></span> <span data-ttu-id="0ecb8-136">还可以使用 ServiceContent 字段来验证响应。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-136">You can also use the ServiceContent field to verify the response.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a><span data-ttu-id="0ecb8-137">检验 Contoso 计算机上的通信是否成功</span><span class="sxs-lookup"><span data-stu-id="0ecb8-137">To verify successful communication on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="0ecb8-138">单击**启动**，指向**所有程序**，指向**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-138">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="0ecb8-139">在连接到服务器对话框中，在**SQL Server**框中，键入**localhost**，选择**Windows 身份验证**，然后单击**连接**.</span><span class="sxs-lookup"><span data-stu-id="0ecb8-139">In the Connect to Server dialog box, in the **SQL Server** box, type **localhost**, select **Windows Authentication**, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="0ecb8-140">在 Microsoft SQL Server Management Studio 中，单击**新查询**。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-140">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="0ecb8-141">在**\<表\>文本**对话框中，选择**BTARNDATA**从列表中。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-141">In the **\<table\> text** dialog box, select **BTARNDATA** from the list.</span></span>  
  
5.  <span data-ttu-id="0ecb8-142">在**SQL**窗口中，键入以下 SQL 语句：</span><span class="sxs-lookup"><span data-stu-id="0ecb8-142">In the **SQL** window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  <span data-ttu-id="0ecb8-143">单击**执行**运行 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-143">Click **Execute** to run the SQL statement.</span></span>  
  
7.  <span data-ttu-id="0ecb8-144">在“查询”窗口的“结果”窗格中，检验你是否看到两条传入消息。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-144">In the Query window, in the Results pane, verify that you see two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0ecb8-145">首先应收到一条类别为 10 的消息，该消息代表 Fabrikam 计算机发送的原始请求。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-145">You should first receive a category 10 message that represents the original request sent by the Fabrikam computer.</span></span> <span data-ttu-id="0ecb8-146">然后，应收到一条类别为 25 的消息，该消息为确认消息回执。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-146">You should then receive a category 25 message signifying the receipt acknowledgement message.</span></span>  
  
8.  <span data-ttu-id="0ecb8-147">在**SQL**窗口中，键入以下 SQL 语句：</span><span class="sxs-lookup"><span data-stu-id="0ecb8-147">In the **SQL** window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. <span data-ttu-id="0ecb8-148">单击**执行**运行 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-148">Click **Execute** to run the SQL statement.</span></span>  
  
10. <span data-ttu-id="0ecb8-149">在“查询”窗口的“结果”窗格中，检验你是否看到一条传出消息。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-149">In the Query window, in the Results pane, verify that you see one outgoing message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0ecb8-150">应看到类别为 25 的消息，该消息代表从 Contoso 计算机发送到 Fabrikam 计算机的确认回执。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-150">You should see a category 25 message that represents the receipt acknowledgement sent from Contoso to the Fabrikam computer.</span></span> <span data-ttu-id="0ecb8-151">还应看到类别为 50 的消息，该消息代表从 Contoso 业务线 (LOB) 应用程序发送到 Fabrikam 计算机的响应。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-151">You should also see a category 50 message that represents the response sent from the Contoso line-of-business (LOB) application to the Fabrikam computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ecb8-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0ecb8-152">See Also</span></span>  
 [<span data-ttu-id="0ecb8-153">私有流程教程</span><span class="sxs-lookup"><span data-stu-id="0ecb8-153">Private Process Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/private-process-tutorial.md)