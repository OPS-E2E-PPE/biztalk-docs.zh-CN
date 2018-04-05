---
title: 步骤 1： 提交 0 C 2 请求 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, submitting requests
ms.assetid: 698c4a43-20b9-46b7-ab66-1dfa24232024
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f05aa5200bd1df6207a962849cd776a03fe71805
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="step-1-submitting-a-0c2-request"></a><span data-ttu-id="2d9ab-102">步骤 1： 提交 0 C 2 请求</span><span class="sxs-lookup"><span data-stu-id="2d9ab-102">Step 1: Submitting a 0C2 Request</span></span>
<span data-ttu-id="2d9ab-103">在此步骤中，将使用 0C2 - 异步测试请求的合作伙伴接口流程 (PIP) 准备并提交请求。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-103">In this step, you prepare and submit a request using the Partner Interface Process (PIP) for an 0C2 - Asynchronous Test Request.</span></span> <span data-ttu-id="2d9ab-104">此 PIP 可确保两个不同组织间的异步通信通道能够正常运转。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-104">This PIP ensures that an asynchronous communication channel is working correctly between two different organizations.</span></span> <span data-ttu-id="2d9ab-105">此 PIP 遵循与其他异步双操作 PIP（例如，“3A4 - 请求采购订单 PIP”）相同的模式。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-105">This PIP follows the same pattern as other asynchronous double action PIPs, such as the 3A4 - Request Purchase Order PIP.</span></span>  
  
### <a name="to-submit-a-0c2---asynchronous-test-request"></a><span data-ttu-id="2d9ab-106">提交 0C2 - 异步测试请求</span><span class="sxs-lookup"><span data-stu-id="2d9ab-106">To submit a 0C2 - Asynchronous Test Request</span></span>  
  
1.  <span data-ttu-id="2d9ab-107">在 Fabrikam 计算机上的 Internet Explorer 中，找到并打开 http://localhost/LOBWebApplication/default.aspx。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-107">On the Fabrikam computer, in Internet Explorer, locate and open http://localhost/LOBWebApplication/default.aspx.</span></span>  
  
2.  <span data-ttu-id="2d9ab-108">上**提交消息**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2d9ab-108">On the **Submit Message** page, do the following:</span></span>  
  
    |<span data-ttu-id="2d9ab-109">使用此选项</span><span class="sxs-lookup"><span data-stu-id="2d9ab-109">Use this</span></span>|<span data-ttu-id="2d9ab-110">执行的操作</span><span class="sxs-lookup"><span data-stu-id="2d9ab-110">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="2d9ab-111">**本组织**</span><span class="sxs-lookup"><span data-stu-id="2d9ab-111">**Home Organization**</span></span>|<span data-ttu-id="2d9ab-112">类型**FABRIKAM**。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-112">Type **FABRIKAM**.</span></span>|  
    |<span data-ttu-id="2d9ab-113">**伙伴组织**</span><span class="sxs-lookup"><span data-stu-id="2d9ab-113">**Partner Organization**</span></span>|<span data-ttu-id="2d9ab-114">类型**CONTOSO**。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-114">Type **CONTOSO**.</span></span>|  
    |<span data-ttu-id="2d9ab-115">**Pip 代码**</span><span class="sxs-lookup"><span data-stu-id="2d9ab-115">**Pip Code**</span></span>|<span data-ttu-id="2d9ab-116">类型**0 C 2**。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-116">Type **0C2**.</span></span>|  
    |<span data-ttu-id="2d9ab-117">**Pip 版本**</span><span class="sxs-lookup"><span data-stu-id="2d9ab-117">**Pip Version**</span></span>|<span data-ttu-id="2d9ab-118">类型**R01.02**。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-118">Type **R01.02**.</span></span>|  
    |<span data-ttu-id="2d9ab-119">**Pip 实例 ID**</span><span class="sxs-lookup"><span data-stu-id="2d9ab-119">**Pip Instance ID**</span></span>|<span data-ttu-id="2d9ab-120">类型**0C2_Test**。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-120">Type **0C2_Test**.</span></span> <span data-ttu-id="2d9ab-121">**重要说明：**必须确保**PIP**对于提交以避免重复的消息 ID 错误每条消息是唯一的。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-121">**Important:**  You must make sure that the **PIP** is unique for each message that you submit to avoid duplicate message ID errors.</span></span> <span data-ttu-id="2d9ab-122">如果以后运行 0C2 测试，则必须更改本字段。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-122">If you run the 0C2 test in the future, you will have to change this field.</span></span>|  
    |<span data-ttu-id="2d9ab-123">**消息类别**</span><span class="sxs-lookup"><span data-stu-id="2d9ab-123">**Message Category**</span></span>|<span data-ttu-id="2d9ab-124">类型**操作**。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-124">Type **Action**.</span></span>|  
  
3.  <span data-ttu-id="2d9ab-125">使用记事本或其他文本编辑器中打开该 0C2_Request.xml 文件\<*驱动器*\>: files\microsoft BizTalk\<版本\>RosettaNet\SDK\ 快捷键LOBApplication\SampleInstances 文件夹，然后复制并粘贴到的内容**服务内容**LOBWebApplication 字段。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-125">Using Notepad or another text editor, open the 0C2_Request.xml file in the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances folder, and then copy and paste the contents into the **Service Content** field in LOBWebApplication.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2d9ab-126">若要删除提交邮件窗体服务内容字段中的现有文本，请将光标置于开头的文本，请按住**Shift**和**Ctrl**按钮，单击**结束**，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-126">To delete the existing text in the Service Content field of the Submit Message form, place the cursor at the beginning of the text, press and hold the **Shift** and **Ctrl** buttons, click **End**, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="2d9ab-127">单击**提交**提交 0 到 Contoso 计算机 C 2 请求。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-127">Click **Submit** to submit the 0C2 request to the Contoso computer.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a><span data-ttu-id="2d9ab-128">检验 Fabrikam 计算机上的通信是否成功</span><span class="sxs-lookup"><span data-stu-id="2d9ab-128">To verify successful communication on the Fabrikam computer</span></span>  
  
-   <span data-ttu-id="2d9ab-129">上**消息状态**LOBWebApplication 在页上，请验证是否接收两个传入消息。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-129">On the **Message Status** page in LOBWebApplication, verify that you receive two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2d9ab-130">首先应收到一条类别为 25 的消息，该消息为 Contoso 计算机的确认回执。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-130">You should first receive a category 25 message signifying a receipt acknowledgement from the Contoso computer.</span></span> <span data-ttu-id="2d9ab-131">然后，应收到一条类别为 50 的消息，该消息为 Contoso 计算机的响应消息。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-131">You should then receive a category 50 message that is the response message from the Contoso computer.</span></span> <span data-ttu-id="2d9ab-132">类别为 -99 的消息表示发生错误。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-132">A category -99 message signifies an error.</span></span> <span data-ttu-id="2d9ab-133">你可以使用**事件查看器**以确定实际错误消息。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-133">You can use **Event Viewer** to determine the actual error message.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a><span data-ttu-id="2d9ab-134">检验 Contoso 计算机上的通信是否成功</span><span class="sxs-lookup"><span data-stu-id="2d9ab-134">To verify successful communication on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="2d9ab-135">单击 **“开始”**，依次指向 **“所有程序”**和 **Microsoft SQL Server**，然后单击 **SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-135">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="2d9ab-136">在**连接到服务器**对话框中，在**SQL Server**框中，键入**localhost**，选择**Windows 身份验证**，然后单击**连接**。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-136">In the **Connect to Server** dialog box, in the **SQL Server** box, type **localhost**, select **Windows Authentication**, and then click **Connect**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2d9ab-137">如果未启动 SQL Server 代理，右键单击它，并依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-137">If the SQL Server Agent is not started, right-click it, and then click **Start**.</span></span>  
  
3.  <span data-ttu-id="2d9ab-138">在 Microsoft SQL Server Management Studio 中，单击**新查询**。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-138">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="2d9ab-139">在\<表\>文本对话框中，选择**BTARNDATA**从列表，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-139">In the \<table\> text dialog box, select **BTARNDATA** from the list, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="2d9ab-140">在“SQL”窗口中，键入以下 SQL 语句：</span><span class="sxs-lookup"><span data-stu-id="2d9ab-140">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  <span data-ttu-id="2d9ab-141">上**查询**菜单上，单击**执行**运行 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-141">On the **Query** menu, click **Execute** to run the SQL statement.</span></span>  
  
7.  <span data-ttu-id="2d9ab-142">在“查询”窗口的“结果”窗格中，检验你是否看到两条传入消息。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-142">In the Query window, in the Results pane, verify that you see two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2d9ab-143">首先应收到一条类别为 10 的消息，该消息代表 Fabrikam 计算机发送的原始请求。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-143">You should first receive a category 10 message that represents the original request sent by the Fabrikam computer.</span></span> <span data-ttu-id="2d9ab-144">然后，应收到一条类别为 25 的消息，该消息为确认消息回执。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-144">You should then receive a category 25 message signifying the receipt acknowledgement message.</span></span>  
  
8.  <span data-ttu-id="2d9ab-145">在“SQL”窗口中，键入以下 SQL 语句：</span><span class="sxs-lookup"><span data-stu-id="2d9ab-145">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. <span data-ttu-id="2d9ab-146">单击**执行**运行 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-146">Click **Execute** to run the SQL statement.</span></span>  
  
10. <span data-ttu-id="2d9ab-147">在“查询”窗口的“结果”窗格中，检验你是否看到一条传出消息。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-147">In the Query window, in the Results pane, verify that you see one outgoing message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2d9ab-148">应看到类别为 25 的消息，该消息代表从 Contoso 计算机发送到 Fabrikam 计算机的确认回执。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-148">You should see a category 25 message that represents the receipt acknowledgement sent from Contoso to the Fabrikam computer.</span></span> <span data-ttu-id="2d9ab-149">还应看到类别为 50 的消息，该消息代表从 Contoso 业务线 (LOB) 应用程序发送到 Fabrikam 计算机的响应。</span><span class="sxs-lookup"><span data-stu-id="2d9ab-149">You should also see a category 50 message that represents the response sent from the Contoso line-of-business (LOB) application to the Fabrikam computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d9ab-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d9ab-150">See Also</span></span>  
 <span data-ttu-id="2d9ab-151">[步骤 2： 提交 0 C 4 查询](../../adapters-and-accelerators/accelerator-rosettanet/step-2-submitting-a-0c4-query.md) </span><span class="sxs-lookup"><span data-stu-id="2d9ab-151">[Step 2: Submitting a 0C4 Query](../../adapters-and-accelerators/accelerator-rosettanet/step-2-submitting-a-0c4-query.md) </span></span>  
 [<span data-ttu-id="2d9ab-152">BTARN 中的消息流</span><span class="sxs-lookup"><span data-stu-id="2d9ab-152">Message Flow in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)