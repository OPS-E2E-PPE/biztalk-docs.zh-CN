---
title: 步骤 4：提交 3A4 请求 |Microsoft Docs
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
ms.openlocfilehash: 6589a46665edf6e446483b673fd4228dd471bbd3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280929"
---
# <a name="step-4-submitting-a-3a4-request"></a><span data-ttu-id="84920-102">步骤 4：提交 3A4 请求</span><span class="sxs-lookup"><span data-stu-id="84920-102">Step 4: Submitting a 3A4 Request</span></span>
<span data-ttu-id="84920-103">在此步骤中，将准备和提交 3a4-请求采购订单使用合作伙伴接口流程 (PIP) 的请求。</span><span class="sxs-lookup"><span data-stu-id="84920-103">In this step, you prepare and submit a request using the Partner Interface Process (PIP) for a 3A4 - Request Purchase Order.</span></span> <span data-ttu-id="84920-104">此 PIP，买方组织提交给供应商的采购订单请求。</span><span class="sxs-lookup"><span data-stu-id="84920-104">This PIP enables a buyer organization to submit a purchase order request to a supplier.</span></span> <span data-ttu-id="84920-105">通常情况下，你请求 3A4-请求采购订单在运行使用 3A2-请求价格与可用性 PIP 的产品可用性查询之后。</span><span class="sxs-lookup"><span data-stu-id="84920-105">Generally, you request the 3A4 - Request Purchase Order after running a product availability query using the 3A2 - Request Price and Availability PIP.</span></span> <span data-ttu-id="84920-106">3A4 PIP 是发送确认回执的异步 PIP。</span><span class="sxs-lookup"><span data-stu-id="84920-106">The 3A4 PIP is an asynchronous PIP that sends receipt acknowledgements.</span></span>  
  
 <span data-ttu-id="84920-107">![&#60;No Change&#62;](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-intro-eetut-3a4flow.gif "RN3_Intro_EETut_3A4Flow")</span><span class="sxs-lookup"><span data-stu-id="84920-107">![&#60;No Change&#62;](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-intro-eetut-3a4flow.gif "RN3_Intro_EETut_3A4Flow")</span></span>  
  
### <a name="to-submit-a-3a4---request-purchase-order"></a><span data-ttu-id="84920-108">若要提交 3A4-请求采购订单</span><span class="sxs-lookup"><span data-stu-id="84920-108">To submit a 3A4 - Request Purchase Order</span></span>  
  
1.  <span data-ttu-id="84920-109">在 Fabrikam 计算机上，在 Internet Explorer 中，找到并打开 http://localhost/LOBWebApplication/default.aspx。</span><span class="sxs-lookup"><span data-stu-id="84920-109">On the Fabrikam computer, in Internet Explorer, locate and open http://localhost/LOBWebApplication/default.aspx.</span></span>  
  
2.  <span data-ttu-id="84920-110">上**提交消息**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="84920-110">On the **Submit Message** page, do the following:</span></span>  
  
    |<span data-ttu-id="84920-111">**使用此**</span><span class="sxs-lookup"><span data-stu-id="84920-111">**Use this**</span></span>|<span data-ttu-id="84920-112">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="84920-112">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="84920-113">**本组织**</span><span class="sxs-lookup"><span data-stu-id="84920-113">**Home Organization**</span></span>|<span data-ttu-id="84920-114">类型**FABRIKAM**。</span><span class="sxs-lookup"><span data-stu-id="84920-114">Type **FABRIKAM**.</span></span>|  
    |<span data-ttu-id="84920-115">**合作伙伴组织**</span><span class="sxs-lookup"><span data-stu-id="84920-115">**Partner Organization**</span></span>|<span data-ttu-id="84920-116">类型**Contoso**。</span><span class="sxs-lookup"><span data-stu-id="84920-116">Type **Contoso**.</span></span>|  
    |<span data-ttu-id="84920-117">**Pip 代码**</span><span class="sxs-lookup"><span data-stu-id="84920-117">**Pip Code**</span></span>|<span data-ttu-id="84920-118">类型**3A4**。</span><span class="sxs-lookup"><span data-stu-id="84920-118">Type **3A4**.</span></span>|  
    |<span data-ttu-id="84920-119">**Pip 版本**</span><span class="sxs-lookup"><span data-stu-id="84920-119">**Pip Version**</span></span>|<span data-ttu-id="84920-120">类型**V02.02.00**。</span><span class="sxs-lookup"><span data-stu-id="84920-120">Type **V02.02.00**.</span></span>|  
    |<span data-ttu-id="84920-121">**Pip 实例 ID**</span><span class="sxs-lookup"><span data-stu-id="84920-121">**Pip Instance ID**</span></span>|<span data-ttu-id="84920-122">类型**3A4_Test**。</span><span class="sxs-lookup"><span data-stu-id="84920-122">Type **3A4_Test**.</span></span> <span data-ttu-id="84920-123">**重要提示：** 若要避免重复消息 ID 错误，您必须确保**Pip 实例 ID**是唯一的提交的每条消息。</span><span class="sxs-lookup"><span data-stu-id="84920-123">**Important:**  To avoid duplicate message ID errors, you must make sure that the **Pip Instance ID** is unique for each message that you submit.</span></span> <span data-ttu-id="84920-124">如果在以后运行 3A4 测试，将需要更改此字段。</span><span class="sxs-lookup"><span data-stu-id="84920-124">If you run the 3A4 test in the future, you will have to change this field.</span></span>|  
    |<span data-ttu-id="84920-125">**消息类别**</span><span class="sxs-lookup"><span data-stu-id="84920-125">**Message Category**</span></span>|<span data-ttu-id="84920-126">类型**操作**。</span><span class="sxs-lookup"><span data-stu-id="84920-126">Type **Action**.</span></span>|  
  
3.  <span data-ttu-id="84920-127">使用记事本或其他文本编辑器打开中的 3A4_Request.xml 文件\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances 文件夹，然后复制并粘贴到**服务内容**LOBWebApplication 中的字段。</span><span class="sxs-lookup"><span data-stu-id="84920-127">Using Notepad or another text editor, open the 3A4_Request.xml file in the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances folder, and then copy and paste the contents into the **Service Content** field in LOBWebApplication.</span></span>  
  
4.  <span data-ttu-id="84920-128">单击**提交**3A4 请求提交给 Contoso 计算机。</span><span class="sxs-lookup"><span data-stu-id="84920-128">Click **Submit** to submit the 3A4 request to the Contoso computer.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a><span data-ttu-id="84920-129">若要验证 Fabrikam 计算机上的成功通信</span><span class="sxs-lookup"><span data-stu-id="84920-129">To verify successful communication on the Fabrikam computer</span></span>  
  
-   <span data-ttu-id="84920-130">上**消息状态**LOBWebApplication 中的页上，确认已收到两条传入消息。</span><span class="sxs-lookup"><span data-stu-id="84920-130">On the **Message Status** page in LOBWebApplication, verify that you receive two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="84920-131">首先应收到类别 25 消息表明 Contoso 计算机的确认回执。</span><span class="sxs-lookup"><span data-stu-id="84920-131">You should first receive a category 25 message signifying a receipt acknowledgement from the Contoso computer.</span></span> <span data-ttu-id="84920-132">然后，应收到一类别 50 条消息，是从 Contoso 计算机的响应消息。</span><span class="sxs-lookup"><span data-stu-id="84920-132">You should then receive a category 50 message that is the response message from the Contoso computer.</span></span> <span data-ttu-id="84920-133">类别-99 之间消息表示发生错误。</span><span class="sxs-lookup"><span data-stu-id="84920-133">A category -99 message signifies an error.</span></span> <span data-ttu-id="84920-134">可以使用**事件查看器**来确定实际的错误消息。</span><span class="sxs-lookup"><span data-stu-id="84920-134">You can use **Event Viewer** to determine the actual error message.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a><span data-ttu-id="84920-135">若要验证 Contoso 计算机上的成功通信</span><span class="sxs-lookup"><span data-stu-id="84920-135">To verify successful communication on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="84920-136">单击**启动**，依次指向**所有程序**，指向**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="84920-136">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="84920-137">在中**连接到服务器**对话框中**SQL Server**框中，键入**localhost**，选择**Windows 身份验证**，然后单击**连接**。</span><span class="sxs-lookup"><span data-stu-id="84920-137">In the **Connect to Server** dialog box, in the **SQL Server** box, type **localhost**, select **Windows Authentication**, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="84920-138">在 Microsoft SQL Server Management Studio 中，单击**新查询**。</span><span class="sxs-lookup"><span data-stu-id="84920-138">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="84920-139">在中\<表\>文本对话框中，选择**BTARNDATA**从列表中。</span><span class="sxs-lookup"><span data-stu-id="84920-139">In the \<table\> text dialog box, select **BTARNDATA** from the list.</span></span>  
  
5.  <span data-ttu-id="84920-140">在 SQL 窗口中，键入以下 SQL 语句：</span><span class="sxs-lookup"><span data-stu-id="84920-140">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  <span data-ttu-id="84920-141">单击**Execute**运行 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="84920-141">Click **Execute** to run the SQL statement.</span></span>  
  
7.  <span data-ttu-id="84920-142">在查询窗口中，在结果窗格中，验证看到两条传入消息。</span><span class="sxs-lookup"><span data-stu-id="84920-142">In the Query window, in the Results pane, verify that you see two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="84920-143">首先应收到一类别为 10 条消息，代表 Fabrikam 计算机发送的原始请求。</span><span class="sxs-lookup"><span data-stu-id="84920-143">You should first receive a category 10 message that represents the original request sent by the Fabrikam computer.</span></span> <span data-ttu-id="84920-144">然后，应收到表明回执 acknowledegment 消息一类别 25 条消息。</span><span class="sxs-lookup"><span data-stu-id="84920-144">You should then receive a category 25 message signifying the receipt acknowledegment message.</span></span>  
  
8.  <span data-ttu-id="84920-145">在 SQL 窗口中，键入以下 SQL 语句：</span><span class="sxs-lookup"><span data-stu-id="84920-145">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. <span data-ttu-id="84920-146">单击**Execute**运行 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="84920-146">Click **Execute** to run the SQL statement.</span></span>  
  
10. <span data-ttu-id="84920-147">在查询窗口中，在**结果**窗格中，验证是否能看到一条传出消息。</span><span class="sxs-lookup"><span data-stu-id="84920-147">In the Query window, in the **Results** pane, verify that you see one outgoing message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="84920-148">应看到类别 25 消息，表示从 Contoso 发送到 Fabrikam 计算机的确认回执消息。</span><span class="sxs-lookup"><span data-stu-id="84920-148">You should see a category 25 message that represents the receipt acknowledgement sent from Contoso to the Fabrikam computer.</span></span> <span data-ttu-id="84920-149">您应看到类别为 50 的消息，表示从 Contoso 业务线 (LOB) 应用程序到 Fabrikam 计算机发送的响应。</span><span class="sxs-lookup"><span data-stu-id="84920-149">You should also see a category 50 message that represents the response sent from the Contoso line-of-business (LOB) application to the Fabrikam computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84920-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="84920-150">See Also</span></span>  
 <span data-ttu-id="84920-151">[双操作教程](../../adapters-and-accelerators/accelerator-rosettanet/double-action-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="84920-151">[Double Action Tutorial](../../adapters-and-accelerators/accelerator-rosettanet/double-action-tutorial.md) </span></span>  
 [<span data-ttu-id="84920-152">BTARN 中的消息流</span><span class="sxs-lookup"><span data-stu-id="84920-152">Message Flow in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)