---
title: 第 2 步：提交 0c4 查询 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, submitting requests
ms.assetid: ce50b892-c87c-414a-94c5-b40947fec68f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd5ea963049d8d7a53c0098c1a53ae54784e0653
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281298"
---
# <a name="step-2-submitting-a-0c4-query"></a><span data-ttu-id="fd3e5-102">第 2 步：提交 4 查询</span><span class="sxs-lookup"><span data-stu-id="fd3e5-102">Step 2: Submitting a 0C4 Query</span></span>
<span data-ttu-id="fd3e5-103">在此步骤中，将准备和提交 0c4-同步测试查询的使用合作伙伴接口流程 (PIP) 的请求。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-103">In this step, you prepare and submit a request using the Partner Interface Process (PIP) for a 0C4 - Synchronous Test Query.</span></span> <span data-ttu-id="fd3e5-104">RosettaNet 定义此 PIP，以确保两个不同组织之间成功的同步通信通道正常工作。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-104">RosettaNet defines this PIP to make sure a successful synchronous communication channel is working correctly between two different organizations.</span></span> <span data-ttu-id="fd3e5-105">此 PIP 有一个同步通信模式，因为[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]不会发送确认回执。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-105">Because this PIP has a synchronous communication pattern, [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] does not send receipt acknowledgements.</span></span> <span data-ttu-id="fd3e5-106">此 PIP 遵循相同的模式与其他同步双操作 Pip，例如，PIP 2A9-查询技术产品信息。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-106">This PIP follows the same pattern as other synchronous double action PIPs, such as PIP 2A9 - Query Technical Product Information.</span></span>  
  
### <a name="to-submit-a-0c4---synchronous-test-query"></a><span data-ttu-id="fd3e5-107">若要提交 0c4-同步测试查询</span><span class="sxs-lookup"><span data-stu-id="fd3e5-107">To submit a 0C4 - Synchronous Test Query</span></span>  
  
1.  <span data-ttu-id="fd3e5-108">在 Fabrikam 计算机上，在 Internet Explorer 中，找到并打开 http://localhost/LOBWebApplication/default.aspx。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-108">On the Fabrikam computer, in Internet Explorer, locate and open http://localhost/LOBWebApplication/default.aspx.</span></span>  
  
2.  <span data-ttu-id="fd3e5-109">上**提交消息**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fd3e5-109">On the **Submit Message** page, do the following:</span></span>  
  
    |<span data-ttu-id="fd3e5-110">使用此选项</span><span class="sxs-lookup"><span data-stu-id="fd3e5-110">Use this</span></span>|<span data-ttu-id="fd3e5-111">执行的操作</span><span class="sxs-lookup"><span data-stu-id="fd3e5-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="fd3e5-112">**本组织**</span><span class="sxs-lookup"><span data-stu-id="fd3e5-112">**Home Organization**</span></span>|<span data-ttu-id="fd3e5-113">类型**FABRIKAM**。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-113">Type **FABRIKAM**.</span></span>|  
    |<span data-ttu-id="fd3e5-114">**合作伙伴组织**</span><span class="sxs-lookup"><span data-stu-id="fd3e5-114">**Partner Organization**</span></span>|<span data-ttu-id="fd3e5-115">类型**CONTOSO**。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-115">Type **CONTOSO**.</span></span>|  
    |<span data-ttu-id="fd3e5-116">**Pip 代码**</span><span class="sxs-lookup"><span data-stu-id="fd3e5-116">**Pip Code**</span></span>|<span data-ttu-id="fd3e5-117">类型**0c4**。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-117">Type **0C4**.</span></span>|  
    |<span data-ttu-id="fd3e5-118">**Pip 版本**</span><span class="sxs-lookup"><span data-stu-id="fd3e5-118">**Pip Version**</span></span>|<span data-ttu-id="fd3e5-119">类型**R01.02**。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-119">Type **R01.02**.</span></span>|  
    |<span data-ttu-id="fd3e5-120">**Pip 实例 ID**</span><span class="sxs-lookup"><span data-stu-id="fd3e5-120">**Pip Instance ID**</span></span>|<span data-ttu-id="fd3e5-121">类型**0C4_Test**。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-121">Type **0C4_Test**.</span></span> <span data-ttu-id="fd3e5-122">**重要提示：** 若要避免重复消息 ID 错误，您必须确保**PIP**是唯一的提交的每条消息。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-122">**Important:**  To avoid duplicate message ID errors, you must make sure that the **PIP** is unique for each message that you submit.</span></span> <span data-ttu-id="fd3e5-123">如果您运行 C 4 测试在将来，，必须更改本字段。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-123">If you run the 0C4 test in the future, you will have to change this field.</span></span>|  
    |<span data-ttu-id="fd3e5-124">**消息类别**</span><span class="sxs-lookup"><span data-stu-id="fd3e5-124">**Message Category**</span></span>|<span data-ttu-id="fd3e5-125">类型**操作**。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-125">Type **Action**.</span></span>|  
  
3.  <span data-ttu-id="fd3e5-126">使用记事本或其他文本编辑器打开中的文件 0C4_Request.xml *\<驱动器\>*: files\microsoft BizTalk 2009 Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances 文件夹然后复制并粘贴到**服务内容**LOBWebApplication 中的字段。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-126">Using Notepad or another text editor, open the 0C4_Request.xml file in the *\<drive\>*:\Program Files\Microsoft BizTalk 2009 Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances folder, and then copy and paste the contents into the **Service Content** field in LOBWebApplication.</span></span>  
  
4.  <span data-ttu-id="fd3e5-127">单击**提交**若要提交给 Contoso 计算机 C 4 查询。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-127">Click **Submit** to submit the 0C4 query to the Contoso computer.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a><span data-ttu-id="fd3e5-128">若要验证 Fabrikam 计算机上的成功通信</span><span class="sxs-lookup"><span data-stu-id="fd3e5-128">To verify successful communication on the Fabrikam computer</span></span>  
  
-   <span data-ttu-id="fd3e5-129">上**消息状态**LOBWebApplication 中的页上，确认已收到两条传入消息。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-129">On the **Message Status** page in LOBWebApplication, verify that you receive two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fd3e5-130">应收到一类别 50 条消息，是从 Contoso 计算机的响应消息。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-130">You should receive a category 50 message that is the response message from the Contoso computer.</span></span> <span data-ttu-id="fd3e5-131">类别-99 之间消息表示发生错误。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-131">A category -99 message signifies an error.</span></span> <span data-ttu-id="fd3e5-132">可以使用事件查看器来确定实际的错误消息。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-132">You can use the Event Viewer to determine the actual error message.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a><span data-ttu-id="fd3e5-133">若要验证 Contoso 计算机上的成功通信</span><span class="sxs-lookup"><span data-stu-id="fd3e5-133">To verify successful communication on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="fd3e5-134">单击 **“开始”**，依次指向 **“所有程序”** 和 **Microsoft SQL Server**，然后单击 **SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-134">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="fd3e5-135">在中**连接到服务器**对话框中**SQL Server**框中，键入**localhost**，选择**Windows 身份验证**，然后单击**连接**。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-135">In the **Connect to Server** dialog box, in the **SQL Server** box, type **localhost**, select **Windows Authentication**, and then click **Connect**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fd3e5-136">如果未启动 SQL Server 代理，右键单击它，然后依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-136">If the SQL Server Agent is not started, right-click it, and then click **Start**.</span></span>  
  
3.  <span data-ttu-id="fd3e5-137">在 Microsoft SQL Server Management Studio 中，单击**新查询**。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-137">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="fd3e5-138">在中\<表\>文本框中，选择**BTARNDATA**从列表中。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-138">In the \<table\> text box, select **BTARNDATA** from the list.</span></span>  
  
5.  <span data-ttu-id="fd3e5-139">在 SQL 窗口中，键入以下 SQL 语句：</span><span class="sxs-lookup"><span data-stu-id="fd3e5-139">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  <span data-ttu-id="fd3e5-140">单击**Execute**运行 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-140">Click **Execute** to run the SQL statement.</span></span>  
  
7.  <span data-ttu-id="fd3e5-141">在查询窗口中，在结果窗格中，验证看到一条传入消息。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-141">In the Query window, in the Results pane, verify that you see one incoming message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fd3e5-142">应看到类别为 10 表示消息的 Fabrikam 计算机发送的原始请求。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-142">You should see a category 10 message that represents the original request that the Fabrikam computer sent.</span></span>  
  
8.  <span data-ttu-id="fd3e5-143">在 SQL 窗口中，键入以下 SQL 语句：</span><span class="sxs-lookup"><span data-stu-id="fd3e5-143">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. <span data-ttu-id="fd3e5-144">单击**Execute**运行 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-144">Click **Execute** to run the SQL statement.</span></span>  
  
10. <span data-ttu-id="fd3e5-145">在查询窗口中，在结果窗格中，验证看到一条传出消息。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-145">In the Query window, in the Results pane, verify that you see one outgoing message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fd3e5-146">你应会看到类别为 50 消息表示的 Contoso 响应的针对 PIP 0c4 查询 Fabrikam 发送。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-146">You should see a category 50 message that represents the Contoso response to the PIP 0C4 query that Fabrikam sent.</span></span> <span data-ttu-id="fd3e5-147">在双操作同步方案中，响应方计算机不会发送到发起方计算机以响应初始查询消息的确认。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-147">In a double action synchronous scenario, the responder computer does not send an acknowledgement to the initiator computer in response to the initial query message.</span></span> <span data-ttu-id="fd3e5-148">响应消息作为确认。</span><span class="sxs-lookup"><span data-stu-id="fd3e5-148">The response message serves as the acknowledgement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd3e5-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd3e5-149">See Also</span></span>  
 <span data-ttu-id="fd3e5-150">[步骤 3：提交 3A2 请求](../../adapters-and-accelerators/accelerator-rosettanet/step-3-submitting-a-3a2-request.md) </span><span class="sxs-lookup"><span data-stu-id="fd3e5-150">[Step 3: Submitting a 3A2 Request](../../adapters-and-accelerators/accelerator-rosettanet/step-3-submitting-a-3a2-request.md) </span></span>  
 [<span data-ttu-id="fd3e5-151">BTARN 中的消息流</span><span class="sxs-lookup"><span data-stu-id="fd3e5-151">Message Flow in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)