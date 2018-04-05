---
title: 步骤 4： 提交 3A4 请求 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, submitting requests
ms.assetid: 2d812cbc-51bc-48d5-b0b2-3698d33664ec
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff36b6181b167d70340a65913e1e85e7acfeeaf4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="step-4-submitting-a-3a4-request"></a><span data-ttu-id="71970-102">步骤 4： 提交 3A4 请求</span><span class="sxs-lookup"><span data-stu-id="71970-102">Step 4: Submitting a 3A4 Request</span></span>
<span data-ttu-id="71970-103">在此步骤中，你将使用“3A4 - 请求采购订单”的合作伙伴接口流程 (PIP) 准备并提交请求。</span><span class="sxs-lookup"><span data-stu-id="71970-103">In this step, you prepare and submit a request using the Partner Interface Process (PIP) for a 3A4 - Request Purchase Order.</span></span> <span data-ttu-id="71970-104">此 PIP 可使买方组织向供应商提交采购订单请求。</span><span class="sxs-lookup"><span data-stu-id="71970-104">This PIP enables a buyer organization to submit a purchase order request to a supplier.</span></span> <span data-ttu-id="71970-105">一般情况下，在运行使用“3A2 - 请求价格和可用性”PIP 的产品可用性查询之后请求“3A4 - 请求采购订单”。</span><span class="sxs-lookup"><span data-stu-id="71970-105">Generally, you request the 3A4 - Request Purchase Order after running a product availability query using the 3A2 - Request Price and Availability PIP.</span></span> <span data-ttu-id="71970-106">3A4 PIP 是一个发送确认回执的异步 PIP。</span><span class="sxs-lookup"><span data-stu-id="71970-106">The 3A4 PIP is an asynchronous PIP that sends receipt acknowledgements.</span></span>  
  
 <span data-ttu-id="71970-107">![&#60;无更改 &#62;] (../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-intro-eetut-3a4flow.gif "RN3_Intro_EETut_3A4Flow")</span><span class="sxs-lookup"><span data-stu-id="71970-107">![&#60;No Change&#62;](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-intro-eetut-3a4flow.gif "RN3_Intro_EETut_3A4Flow")</span></span>  
  
### <a name="to-submit-a-3a4---request-purchase-order"></a><span data-ttu-id="71970-108">提交“3A4 - 请求采购订单”</span><span class="sxs-lookup"><span data-stu-id="71970-108">To submit a 3A4 - Request Purchase Order</span></span>  
  
1.  <span data-ttu-id="71970-109">在 Fabrikam 计算机上的 Internet Explorer 中，找到并打开 http://localhost/LOBWebApplication/default.aspx。</span><span class="sxs-lookup"><span data-stu-id="71970-109">On the Fabrikam computer, in Internet Explorer, locate and open http://localhost/LOBWebApplication/default.aspx.</span></span>  
  
2.  <span data-ttu-id="71970-110">上**提交消息**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="71970-110">On the **Submit Message** page, do the following:</span></span>  
  
    |<span data-ttu-id="71970-111">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="71970-111">**Use this**</span></span>|<span data-ttu-id="71970-112">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="71970-112">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="71970-113">**本组织**</span><span class="sxs-lookup"><span data-stu-id="71970-113">**Home Organization**</span></span>|<span data-ttu-id="71970-114">类型**FABRIKAM**。</span><span class="sxs-lookup"><span data-stu-id="71970-114">Type **FABRIKAM**.</span></span>|  
    |<span data-ttu-id="71970-115">**伙伴组织**</span><span class="sxs-lookup"><span data-stu-id="71970-115">**Partner Organization**</span></span>|<span data-ttu-id="71970-116">类型**Contoso**。</span><span class="sxs-lookup"><span data-stu-id="71970-116">Type **Contoso**.</span></span>|  
    |<span data-ttu-id="71970-117">**Pip 代码**</span><span class="sxs-lookup"><span data-stu-id="71970-117">**Pip Code**</span></span>|<span data-ttu-id="71970-118">类型**3A4**。</span><span class="sxs-lookup"><span data-stu-id="71970-118">Type **3A4**.</span></span>|  
    |<span data-ttu-id="71970-119">**Pip 版本**</span><span class="sxs-lookup"><span data-stu-id="71970-119">**Pip Version**</span></span>|<span data-ttu-id="71970-120">类型**V02.02.00**。</span><span class="sxs-lookup"><span data-stu-id="71970-120">Type **V02.02.00**.</span></span>|  
    |<span data-ttu-id="71970-121">**Pip 实例 ID**</span><span class="sxs-lookup"><span data-stu-id="71970-121">**Pip Instance ID**</span></span>|<span data-ttu-id="71970-122">类型**3A4_Test**。</span><span class="sxs-lookup"><span data-stu-id="71970-122">Type **3A4_Test**.</span></span> <span data-ttu-id="71970-123">**重要说明：**若要避免重复的消息 ID 错误，你必须确保**Pip 实例 ID**对于你提交每条消息是唯一的。</span><span class="sxs-lookup"><span data-stu-id="71970-123">**Important:**  To avoid duplicate message ID errors, you must make sure that the **Pip Instance ID** is unique for each message that you submit.</span></span> <span data-ttu-id="71970-124">如果以后运行 3A4 测试，则必须更改本字段。</span><span class="sxs-lookup"><span data-stu-id="71970-124">If you run the 3A4 test in the future, you will have to change this field.</span></span>|  
    |<span data-ttu-id="71970-125">**消息类别**</span><span class="sxs-lookup"><span data-stu-id="71970-125">**Message Category**</span></span>|<span data-ttu-id="71970-126">类型**操作**。</span><span class="sxs-lookup"><span data-stu-id="71970-126">Type **Action**.</span></span>|  
  
3.  <span data-ttu-id="71970-127">使用记事本或其他文本编辑器中打开该 3A4_Request.xml 文件\<*驱动器*\>: files\microsoft BizTalk\<版本\>RosettaNet\SDK\ 快捷键LOBApplication\SampleInstances 文件夹，然后复制并粘贴到的内容**服务内容**LOBWebApplication 字段。</span><span class="sxs-lookup"><span data-stu-id="71970-127">Using Notepad or another text editor, open the 3A4_Request.xml file in the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances folder, and then copy and paste the contents into the **Service Content** field in LOBWebApplication.</span></span>  
  
4.  <span data-ttu-id="71970-128">单击**提交**以提交到 Contoso 计算机 3A4 请求。</span><span class="sxs-lookup"><span data-stu-id="71970-128">Click **Submit** to submit the 3A4 request to the Contoso computer.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a><span data-ttu-id="71970-129">检验 Fabrikam 计算机上的通信是否成功</span><span class="sxs-lookup"><span data-stu-id="71970-129">To verify successful communication on the Fabrikam computer</span></span>  
  
-   <span data-ttu-id="71970-130">上**消息状态**LOBWebApplication 在页上，请验证是否接收两个传入消息。</span><span class="sxs-lookup"><span data-stu-id="71970-130">On the **Message Status** page in LOBWebApplication, verify that you receive two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="71970-131">首先应收到一条类别为 25 的消息，该消息为 Contoso 计算机的确认回执。</span><span class="sxs-lookup"><span data-stu-id="71970-131">You should first receive a category 25 message signifying a receipt acknowledgement from the Contoso computer.</span></span> <span data-ttu-id="71970-132">然后，应收到一条类别为 50 的消息，该消息为 Contoso 计算机的响应消息。</span><span class="sxs-lookup"><span data-stu-id="71970-132">You should then receive a category 50 message that is the response message from the Contoso computer.</span></span> <span data-ttu-id="71970-133">类别为 -99 的消息表示发生错误。</span><span class="sxs-lookup"><span data-stu-id="71970-133">A category -99 message signifies an error.</span></span> <span data-ttu-id="71970-134">你可以使用**事件查看器**以确定实际错误消息。</span><span class="sxs-lookup"><span data-stu-id="71970-134">You can use **Event Viewer** to determine the actual error message.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a><span data-ttu-id="71970-135">检验 Contoso 计算机上的通信是否成功</span><span class="sxs-lookup"><span data-stu-id="71970-135">To verify successful communication on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="71970-136">单击**启动**，指向**所有程序**，指向**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="71970-136">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="71970-137">在**连接到服务器**对话框中，在**SQL Server**框中，键入**localhost**，选择**Windows 身份验证**，然后单击**连接**。</span><span class="sxs-lookup"><span data-stu-id="71970-137">In the **Connect to Server** dialog box, in the **SQL Server** box, type **localhost**, select **Windows Authentication**, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="71970-138">在 Microsoft SQL Server Management Studio 中，单击**新查询**。</span><span class="sxs-lookup"><span data-stu-id="71970-138">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="71970-139">在\<表\>文本对话框中，选择**BTARNDATA**从列表中。</span><span class="sxs-lookup"><span data-stu-id="71970-139">In the \<table\> text dialog box, select **BTARNDATA** from the list.</span></span>  
  
5.  <span data-ttu-id="71970-140">在“SQL”窗口中，键入以下 SQL 语句：</span><span class="sxs-lookup"><span data-stu-id="71970-140">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  <span data-ttu-id="71970-141">单击**执行**运行 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="71970-141">Click **Execute** to run the SQL statement.</span></span>  
  
7.  <span data-ttu-id="71970-142">在“查询”窗口的“结果”窗格中，检验你是否看到两条传入消息。</span><span class="sxs-lookup"><span data-stu-id="71970-142">In the Query window, in the Results pane, verify that you see two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="71970-143">首先应收到一条类别为 10 的消息，该消息代表 Fabrikam 计算机发送的原始请求。</span><span class="sxs-lookup"><span data-stu-id="71970-143">You should first receive a category 10 message that represents the original request sent by the Fabrikam computer.</span></span> <span data-ttu-id="71970-144">然后，您应收到表明回执 acknowledegment 消息类别 25 消息。</span><span class="sxs-lookup"><span data-stu-id="71970-144">You should then receive a category 25 message signifying the receipt acknowledegment message.</span></span>  
  
8.  <span data-ttu-id="71970-145">在“SQL”窗口中，键入以下 SQL 语句：</span><span class="sxs-lookup"><span data-stu-id="71970-145">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. <span data-ttu-id="71970-146">单击**执行**运行 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="71970-146">Click **Execute** to run the SQL statement.</span></span>  
  
10. <span data-ttu-id="71970-147">在查询窗口中，在**结果**窗格中，确认你看到一个传出消息。</span><span class="sxs-lookup"><span data-stu-id="71970-147">In the Query window, in the **Results** pane, verify that you see one outgoing message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="71970-148">应看到类别为 25 的消息，该消息代表从 Contoso 计算机发送到 Fabrikam 计算机的确认回执。</span><span class="sxs-lookup"><span data-stu-id="71970-148">You should see a category 25 message that represents the receipt acknowledgement sent from Contoso to the Fabrikam computer.</span></span> <span data-ttu-id="71970-149">还应看到类别为 50 的消息，该消息代表从 Contoso 业务线 (LOB) 应用程序发送到 Fabrikam 计算机的响应。</span><span class="sxs-lookup"><span data-stu-id="71970-149">You should also see a category 50 message that represents the response sent from the Contoso line-of-business (LOB) application to the Fabrikam computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71970-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="71970-150">See Also</span></span>  
 <span data-ttu-id="71970-151">[Double 操作教程](../../adapters-and-accelerators/accelerator-rosettanet/double-action-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="71970-151">[Double Action Tutorial](../../adapters-and-accelerators/accelerator-rosettanet/double-action-tutorial.md) </span></span>  
 [<span data-ttu-id="71970-152">BTARN 中的消息流</span><span class="sxs-lookup"><span data-stu-id="71970-152">Message Flow in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)