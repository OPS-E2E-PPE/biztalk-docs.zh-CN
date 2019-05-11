---
title: 第 1 步：提交 0c2 请求 |Microsoft Docs
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
ms.openlocfilehash: 8bc9102198305d6f9ea92ca4d1462d1839c4f5aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281419"
---
# <a name="step-1-submitting-a-0c2-request"></a><span data-ttu-id="cdb24-102">第 1 步：提交请求 2</span><span class="sxs-lookup"><span data-stu-id="cdb24-102">Step 1: Submitting a 0C2 Request</span></span>
<span data-ttu-id="cdb24-103">在此步骤中，将准备和提交 0c2-异步测试请求的使用合作伙伴接口流程 (PIP) 的请求。</span><span class="sxs-lookup"><span data-stu-id="cdb24-103">In this step, you prepare and submit a request using the Partner Interface Process (PIP) for an 0C2 - Asynchronous Test Request.</span></span> <span data-ttu-id="cdb24-104">此 PIP 可确保两个不同组织之间正常工作一个异步通信通道。</span><span class="sxs-lookup"><span data-stu-id="cdb24-104">This PIP ensures that an asynchronous communication channel is working correctly between two different organizations.</span></span> <span data-ttu-id="cdb24-105">此 PIP 遵循相同的模式与其他异步双操作 Pip，例如 3A4-请求采购订单 PIP。</span><span class="sxs-lookup"><span data-stu-id="cdb24-105">This PIP follows the same pattern as other asynchronous double action PIPs, such as the 3A4 - Request Purchase Order PIP.</span></span>  
  
### <a name="to-submit-a-0c2---asynchronous-test-request"></a><span data-ttu-id="cdb24-106">提交 0c2-异步测试请求</span><span class="sxs-lookup"><span data-stu-id="cdb24-106">To submit a 0C2 - Asynchronous Test Request</span></span>  
  
1.  <span data-ttu-id="cdb24-107">在 Fabrikam 计算机上，在 Internet Explorer 中，找到并打开 http://localhost/LOBWebApplication/default.aspx。</span><span class="sxs-lookup"><span data-stu-id="cdb24-107">On the Fabrikam computer, in Internet Explorer, locate and open http://localhost/LOBWebApplication/default.aspx.</span></span>  
  
2.  <span data-ttu-id="cdb24-108">上**提交消息**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cdb24-108">On the **Submit Message** page, do the following:</span></span>  
  
    |<span data-ttu-id="cdb24-109">使用此选项</span><span class="sxs-lookup"><span data-stu-id="cdb24-109">Use this</span></span>|<span data-ttu-id="cdb24-110">执行的操作</span><span class="sxs-lookup"><span data-stu-id="cdb24-110">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="cdb24-111">**本组织**</span><span class="sxs-lookup"><span data-stu-id="cdb24-111">**Home Organization**</span></span>|<span data-ttu-id="cdb24-112">类型**FABRIKAM**。</span><span class="sxs-lookup"><span data-stu-id="cdb24-112">Type **FABRIKAM**.</span></span>|  
    |<span data-ttu-id="cdb24-113">**合作伙伴组织**</span><span class="sxs-lookup"><span data-stu-id="cdb24-113">**Partner Organization**</span></span>|<span data-ttu-id="cdb24-114">类型**CONTOSO**。</span><span class="sxs-lookup"><span data-stu-id="cdb24-114">Type **CONTOSO**.</span></span>|  
    |<span data-ttu-id="cdb24-115">**Pip 代码**</span><span class="sxs-lookup"><span data-stu-id="cdb24-115">**Pip Code**</span></span>|<span data-ttu-id="cdb24-116">类型**0c2**。</span><span class="sxs-lookup"><span data-stu-id="cdb24-116">Type **0C2**.</span></span>|  
    |<span data-ttu-id="cdb24-117">**Pip 版本**</span><span class="sxs-lookup"><span data-stu-id="cdb24-117">**Pip Version**</span></span>|<span data-ttu-id="cdb24-118">类型**R01.02**。</span><span class="sxs-lookup"><span data-stu-id="cdb24-118">Type **R01.02**.</span></span>|  
    |<span data-ttu-id="cdb24-119">**Pip 实例 ID**</span><span class="sxs-lookup"><span data-stu-id="cdb24-119">**Pip Instance ID**</span></span>|<span data-ttu-id="cdb24-120">类型**0C2_Test**。</span><span class="sxs-lookup"><span data-stu-id="cdb24-120">Type **0C2_Test**.</span></span> <span data-ttu-id="cdb24-121">**重要提示：** 必须确保**PIP**是唯一的提交以避免重复消息 ID 错误每条消息。</span><span class="sxs-lookup"><span data-stu-id="cdb24-121">**Important:**  You must make sure that the **PIP** is unique for each message that you submit to avoid duplicate message ID errors.</span></span> <span data-ttu-id="cdb24-122">如果您运行 C 2 测试在将来，，必须更改本字段。</span><span class="sxs-lookup"><span data-stu-id="cdb24-122">If you run the 0C2 test in the future, you will have to change this field.</span></span>|  
    |<span data-ttu-id="cdb24-123">**消息类别**</span><span class="sxs-lookup"><span data-stu-id="cdb24-123">**Message Category**</span></span>|<span data-ttu-id="cdb24-124">类型**操作**。</span><span class="sxs-lookup"><span data-stu-id="cdb24-124">Type **Action**.</span></span>|  
  
3.  <span data-ttu-id="cdb24-125">使用记事本或其他文本编辑器打开中的 0C2_Request.xml 文件\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances 文件夹，然后复制并粘贴到**服务内容**LOBWebApplication 中的字段。</span><span class="sxs-lookup"><span data-stu-id="cdb24-125">Using Notepad or another text editor, open the 0C2_Request.xml file in the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances folder, and then copy and paste the contents into the **Service Content** field in LOBWebApplication.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cdb24-126">若要删除服务内容提交消息窗体的字段中的现有文本，请将光标放在开头的文本，请按住**Shift**并**Ctrl**按钮，单击**结束**，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="cdb24-126">To delete the existing text in the Service Content field of the Submit Message form, place the cursor at the beginning of the text, press and hold the **Shift** and **Ctrl** buttons, click **End**, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="cdb24-127">单击**提交**若要提交给 Contoso 计算机 C 2 请求。</span><span class="sxs-lookup"><span data-stu-id="cdb24-127">Click **Submit** to submit the 0C2 request to the Contoso computer.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a><span data-ttu-id="cdb24-128">若要验证 Fabrikam 计算机上的成功通信</span><span class="sxs-lookup"><span data-stu-id="cdb24-128">To verify successful communication on the Fabrikam computer</span></span>  
  
-   <span data-ttu-id="cdb24-129">上**消息状态**LOBWebApplication 中的页上，确认已收到两条传入消息。</span><span class="sxs-lookup"><span data-stu-id="cdb24-129">On the **Message Status** page in LOBWebApplication, verify that you receive two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cdb24-130">首先应收到类别 25 消息表明 Contoso 计算机的确认回执。</span><span class="sxs-lookup"><span data-stu-id="cdb24-130">You should first receive a category 25 message signifying a receipt acknowledgement from the Contoso computer.</span></span> <span data-ttu-id="cdb24-131">然后，应收到一类别 50 条消息，是从 Contoso 计算机的响应消息。</span><span class="sxs-lookup"><span data-stu-id="cdb24-131">You should then receive a category 50 message that is the response message from the Contoso computer.</span></span> <span data-ttu-id="cdb24-132">类别-99 之间消息表示发生错误。</span><span class="sxs-lookup"><span data-stu-id="cdb24-132">A category -99 message signifies an error.</span></span> <span data-ttu-id="cdb24-133">可以使用**事件查看器**来确定实际的错误消息。</span><span class="sxs-lookup"><span data-stu-id="cdb24-133">You can use **Event Viewer** to determine the actual error message.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a><span data-ttu-id="cdb24-134">若要验证 Contoso 计算机上的成功通信</span><span class="sxs-lookup"><span data-stu-id="cdb24-134">To verify successful communication on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="cdb24-135">单击 **“开始”**，依次指向 **“所有程序”** 和 **Microsoft SQL Server**，然后单击 **SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="cdb24-135">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="cdb24-136">在中**连接到服务器**对话框中**SQL Server**框中，键入**localhost**，选择**Windows 身份验证**，然后单击**连接**。</span><span class="sxs-lookup"><span data-stu-id="cdb24-136">In the **Connect to Server** dialog box, in the **SQL Server** box, type **localhost**, select **Windows Authentication**, and then click **Connect**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cdb24-137">如果未启动 SQL Server 代理，右键单击它，然后依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="cdb24-137">If the SQL Server Agent is not started, right-click it, and then click **Start**.</span></span>  
  
3.  <span data-ttu-id="cdb24-138">在 Microsoft SQL Server Management Studio 中，单击**新查询**。</span><span class="sxs-lookup"><span data-stu-id="cdb24-138">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="cdb24-139">在中\<表\>文本对话框中，选择**BTARNDATA**从列表中，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cdb24-139">In the \<table\> text dialog box, select **BTARNDATA** from the list, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="cdb24-140">在 SQL 窗口中，键入以下 SQL 语句：</span><span class="sxs-lookup"><span data-stu-id="cdb24-140">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  <span data-ttu-id="cdb24-141">上**查询**菜单上，单击**Execute**运行 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="cdb24-141">On the **Query** menu, click **Execute** to run the SQL statement.</span></span>  
  
7.  <span data-ttu-id="cdb24-142">在查询窗口中，在结果窗格中，验证看到两条传入消息。</span><span class="sxs-lookup"><span data-stu-id="cdb24-142">In the Query window, in the Results pane, verify that you see two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cdb24-143">首先应收到一类别为 10 条消息，代表 Fabrikam 计算机发送的原始请求。</span><span class="sxs-lookup"><span data-stu-id="cdb24-143">You should first receive a category 10 message that represents the original request sent by the Fabrikam computer.</span></span> <span data-ttu-id="cdb24-144">然后，应收到条确认消息回执一类别 25 条消息。</span><span class="sxs-lookup"><span data-stu-id="cdb24-144">You should then receive a category 25 message signifying the receipt acknowledgement message.</span></span>  
  
8.  <span data-ttu-id="cdb24-145">在 SQL 窗口中，键入以下 SQL 语句：</span><span class="sxs-lookup"><span data-stu-id="cdb24-145">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. <span data-ttu-id="cdb24-146">单击**Execute**运行 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="cdb24-146">Click **Execute** to run the SQL statement.</span></span>  
  
10. <span data-ttu-id="cdb24-147">在查询窗口中，在结果窗格中，验证看到一条传出消息。</span><span class="sxs-lookup"><span data-stu-id="cdb24-147">In the Query window, in the Results pane, verify that you see one outgoing message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cdb24-148">应看到类别 25 消息，表示从 Contoso 发送到 Fabrikam 计算机的确认回执消息。</span><span class="sxs-lookup"><span data-stu-id="cdb24-148">You should see a category 25 message that represents the receipt acknowledgement sent from Contoso to the Fabrikam computer.</span></span> <span data-ttu-id="cdb24-149">您应看到类别为 50 的消息，表示从 Contoso 业务线 (LOB) 应用程序到 Fabrikam 计算机发送的响应。</span><span class="sxs-lookup"><span data-stu-id="cdb24-149">You should also see a category 50 message that represents the response sent from the Contoso line-of-business (LOB) application to the Fabrikam computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdb24-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="cdb24-150">See Also</span></span>  
 <span data-ttu-id="cdb24-151">[步骤 2：提交 4 查询](../../adapters-and-accelerators/accelerator-rosettanet/step-2-submitting-a-0c4-query.md) </span><span class="sxs-lookup"><span data-stu-id="cdb24-151">[Step 2: Submitting a 0C4 Query](../../adapters-and-accelerators/accelerator-rosettanet/step-2-submitting-a-0c4-query.md) </span></span>  
 [<span data-ttu-id="cdb24-152">BTARN 中的消息流</span><span class="sxs-lookup"><span data-stu-id="cdb24-152">Message Flow in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)