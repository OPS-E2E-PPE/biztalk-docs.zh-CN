---
title: "步骤 3： 提交 3A2 请求 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: double action tutorial, submitting requests
ms.assetid: 09f22be8-6d7d-48bf-862b-73248bae0506
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 312e5980636d211f1e023331826e016eb141eb4b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="step-3-submitting-a-3a2-request"></a><span data-ttu-id="c94c0-102">步骤 3： 提交 3A2 请求</span><span class="sxs-lookup"><span data-stu-id="c94c0-102">Step 3: Submitting a 3A2 Request</span></span>
<span data-ttu-id="c94c0-103">在此步骤中，将使用 3A2 - 请求价格与可用性的合作伙伴接口流程 (PIP) 准备并提交请求。</span><span class="sxs-lookup"><span data-stu-id="c94c0-103">In this step, you prepare and submit a request using the Partner Interface Process (PIP) for a 3A2 - Request Price and Availability.</span></span> <span data-ttu-id="c94c0-104">通过此 PIP，买方组织可以获得有关特定产品的信息，如价格和可用单位数。</span><span class="sxs-lookup"><span data-stu-id="c94c0-104">This PIP enables a buyer organization to obtain information about a certain product, such as price and number of available units.</span></span> <span data-ttu-id="c94c0-105">然后，买方就可以通过业务规则对获得的信息进行处理，以便确定是否购买相应供应商的产品。</span><span class="sxs-lookup"><span data-stu-id="c94c0-105">The buyer can then process that information through business rules to determine whether to purchase the product from the supplier.</span></span>  
  
### <a name="to-submit-a-3a2---request-price-and-availability"></a><span data-ttu-id="c94c0-106">提交 3A2 - 请求价格与可用性</span><span class="sxs-lookup"><span data-stu-id="c94c0-106">To submit a 3A2 - Request Price and Availability</span></span>  
  
1.  <span data-ttu-id="c94c0-107">在 Fabrikam 计算机上的 Internet Explorer 中，找到并打开 http://localhost/LOBWebApplication/default.aspx。</span><span class="sxs-lookup"><span data-stu-id="c94c0-107">On the Fabrikam computer, in Internet Explorer, locate and open http://localhost/LOBWebApplication/default.aspx.</span></span>  
  
2.  <span data-ttu-id="c94c0-108">上**提交消息**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c94c0-108">On the **Submit Message** page, do the following:</span></span>  
  
    |<span data-ttu-id="c94c0-109">使用此选项</span><span class="sxs-lookup"><span data-stu-id="c94c0-109">Use this</span></span>|<span data-ttu-id="c94c0-110">执行的操作</span><span class="sxs-lookup"><span data-stu-id="c94c0-110">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="c94c0-111">**本组织**</span><span class="sxs-lookup"><span data-stu-id="c94c0-111">**Home Organization**</span></span>|<span data-ttu-id="c94c0-112">类型**FABRIKAM**。</span><span class="sxs-lookup"><span data-stu-id="c94c0-112">Type **FABRIKAM**.</span></span>|  
    |<span data-ttu-id="c94c0-113">**伙伴组织**</span><span class="sxs-lookup"><span data-stu-id="c94c0-113">**Partner Organization**</span></span>|<span data-ttu-id="c94c0-114">类型**Contoso**。</span><span class="sxs-lookup"><span data-stu-id="c94c0-114">Type **Contoso**.</span></span>|  
    |<span data-ttu-id="c94c0-115">**Pip 代码**</span><span class="sxs-lookup"><span data-stu-id="c94c0-115">**Pip Code**</span></span>|<span data-ttu-id="c94c0-116">类型**3A2**。</span><span class="sxs-lookup"><span data-stu-id="c94c0-116">Type **3A2**.</span></span> <span data-ttu-id="c94c0-117">**重要说明：**若要避免重复的消息 ID 错误，你必须确保**Pip**对于你提交每条消息是唯一的。</span><span class="sxs-lookup"><span data-stu-id="c94c0-117">**Important:**  To avoid duplicate message ID errors, you must make sure that the **Pip** is unique for each message that you submit.</span></span> <span data-ttu-id="c94c0-118">如果以后运行 3A2 测试，则必须更改本字段。</span><span class="sxs-lookup"><span data-stu-id="c94c0-118">If you run the 3A2 test in the future, you have to change this field.</span></span>|  
    |<span data-ttu-id="c94c0-119">**Pip 版本**</span><span class="sxs-lookup"><span data-stu-id="c94c0-119">**Pip Version**</span></span>|<span data-ttu-id="c94c0-120">类型**R02.00.00A**。</span><span class="sxs-lookup"><span data-stu-id="c94c0-120">Type **R02.00.00A**.</span></span>|  
    |<span data-ttu-id="c94c0-121">**Pip 实例 ID**</span><span class="sxs-lookup"><span data-stu-id="c94c0-121">**Pip Instance ID**</span></span>|<span data-ttu-id="c94c0-122">类型**3A2_Test**。</span><span class="sxs-lookup"><span data-stu-id="c94c0-122">Type **3A2_Test**.</span></span>|  
    |<span data-ttu-id="c94c0-123">**消息类别**</span><span class="sxs-lookup"><span data-stu-id="c94c0-123">**Message Category**</span></span>|<span data-ttu-id="c94c0-124">类型**操作**。</span><span class="sxs-lookup"><span data-stu-id="c94c0-124">Type **Action**.</span></span>|  
  
3.  <span data-ttu-id="c94c0-125">使用记事本或其他文本编辑器，打开在文件 3A2_Request.xml *\<驱动器\>*: \程序 Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances 文件夹，然后复制并粘贴到的内容**服务内容**字段LOBWebApplication。</span><span class="sxs-lookup"><span data-stu-id="c94c0-125">Using Notepad or another text editor, open the file 3A2_Request.xml in the *\<drive\>*:\ Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances folder, and then copy and paste the contents into the **Service Content** field in LOBWebApplication.</span></span>  
  
4.  <span data-ttu-id="c94c0-126">单击**提交**以提交到 Contoso 计算机 3A2 请求。</span><span class="sxs-lookup"><span data-stu-id="c94c0-126">Click **Submit** to submit the 3A2 request to the Contoso computer.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a><span data-ttu-id="c94c0-127">检验 Fabrikam 计算机上的通信是否成功</span><span class="sxs-lookup"><span data-stu-id="c94c0-127">To verify successful communication on the Fabrikam computer</span></span>  
  
-   <span data-ttu-id="c94c0-128">上**消息状态**LOBWebApplication 在页上，请验证是否接收两个传入消息。</span><span class="sxs-lookup"><span data-stu-id="c94c0-128">On the **Message Status** page in LOBWebApplication, verify that you receive two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c94c0-129">首先应收到一条类别为 25 的消息，该消息为 Contoso 计算机的确认回执。</span><span class="sxs-lookup"><span data-stu-id="c94c0-129">You should first receive a category 25 message signifying a receipt acknowledgement from the Contoso computer.</span></span> <span data-ttu-id="c94c0-130">然后，应收到一条类别为 50 的消息，该消息为 Contoso 计算机的响应消息。</span><span class="sxs-lookup"><span data-stu-id="c94c0-130">You should then receive a category 50 message that is the response message from the Contoso computer.</span></span> <span data-ttu-id="c94c0-131">类别为 -99 的消息表示发生错误。</span><span class="sxs-lookup"><span data-stu-id="c94c0-131">A category -99 message signifies an error.</span></span> <span data-ttu-id="c94c0-132">你可以使用**事件查看器**以确定实际错误消息。</span><span class="sxs-lookup"><span data-stu-id="c94c0-132">You can use **Event Viewer** to determine the actual error message.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a><span data-ttu-id="c94c0-133">检验 Contoso 计算机上的通信是否成功</span><span class="sxs-lookup"><span data-stu-id="c94c0-133">To verify successful communication on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="c94c0-134">单击**启动**，指向**所有程序**，指向**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="c94c0-134">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="c94c0-135">在**连接到服务器**对话框中，在**SQL Server**框中，键入**localhost**，选择**Windows 身份验证**，然后单击**连接**。</span><span class="sxs-lookup"><span data-stu-id="c94c0-135">In the **Connect to Server** dialog box, in the **SQL Server** box, type **localhost**, select **Windows Authentication**, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="c94c0-136">在 Microsoft SQL Server Management Studio 中，单击**新查询**。</span><span class="sxs-lookup"><span data-stu-id="c94c0-136">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="c94c0-137">在\<表\>文本框中，选择**BTARNDATA**从列表中。</span><span class="sxs-lookup"><span data-stu-id="c94c0-137">In the \<table\> text box, select **BTARNDATA** from the list.</span></span>  
  
5.  <span data-ttu-id="c94c0-138">在“SQL”窗口中，键入以下 SQL 语句：</span><span class="sxs-lookup"><span data-stu-id="c94c0-138">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  <span data-ttu-id="c94c0-139">单击**执行**运行 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="c94c0-139">Click **Execute** to run the SQL statement.</span></span>  
  
7.  <span data-ttu-id="c94c0-140">在“查询”窗口的“结果”窗格中，检验你是否看到两条传入消息。</span><span class="sxs-lookup"><span data-stu-id="c94c0-140">In the Query window, in the Results pane, verify that you see two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c94c0-141">首先应收到一条类别为 10 的消息，该消息代表 Fabrikam 计算机发送的原始请求。</span><span class="sxs-lookup"><span data-stu-id="c94c0-141">You should first receive a category 10 message that represents the original request sent by the Fabrikam computer.</span></span> <span data-ttu-id="c94c0-142">然后，应收到一条类别为 25 的消息，该消息为确认消息回执。</span><span class="sxs-lookup"><span data-stu-id="c94c0-142">You should then receive a category 25 message signifying the receipt acknowledgement message.</span></span>  
  
8.  <span data-ttu-id="c94c0-143">在“SQL”窗口中，键入以下 SQL 语句：</span><span class="sxs-lookup"><span data-stu-id="c94c0-143">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. <span data-ttu-id="c94c0-144">单击**执行**运行 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="c94c0-144">Click **Execute** to run the SQL statement.</span></span>  
  
10. <span data-ttu-id="c94c0-145">在“查询”窗口的“结果”窗格中，检验你是否看到一条传出消息。</span><span class="sxs-lookup"><span data-stu-id="c94c0-145">In the Query window, in the Results pane, verify that you see one outgoing message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c94c0-146">应看到类别为 25 的消息，该消息代表从 Contoso 计算机发送到 Fabrikam 计算机的确认回执。</span><span class="sxs-lookup"><span data-stu-id="c94c0-146">You should see a category 25 message that represents the receipt acknowledgement sent from Contoso to the Fabrikam computer.</span></span> <span data-ttu-id="c94c0-147">还应看到类别为 50 的消息，该消息代表从 Contoso 业务线 (LOB) 应用程序发送到 Fabrikam 计算机的响应。</span><span class="sxs-lookup"><span data-stu-id="c94c0-147">You should also see a category 50 message that represents the response sent from the Contoso line-of-business (LOB) application to the Fabrikam computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c94c0-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c94c0-148">See Also</span></span>  
 <span data-ttu-id="c94c0-149">[步骤 4： 提交 3A4 请求](../../adapters-and-accelerators/accelerator-rosettanet/step-4-submitting-a-3a4-request.md) </span><span class="sxs-lookup"><span data-stu-id="c94c0-149">[Step 4: Submitting a 3A4 Request](../../adapters-and-accelerators/accelerator-rosettanet/step-4-submitting-a-3a4-request.md) </span></span>  
 [<span data-ttu-id="c94c0-150">BTARN 中的消息流</span><span class="sxs-lookup"><span data-stu-id="c94c0-150">Message Flow in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)