---
title: 步骤 3：提交 3A2 请求 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, submitting requests
ms.assetid: 09f22be8-6d7d-48bf-862b-73248bae0506
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4feb98c9258c870fc43eb9cf5b9583e932933092
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281047"
---
# <a name="step-3-submitting-a-3a2-request"></a><span data-ttu-id="95973-102">步骤 3：提交 3A2 请求</span><span class="sxs-lookup"><span data-stu-id="95973-102">Step 3: Submitting a 3A2 Request</span></span>
<span data-ttu-id="95973-103">在此步骤中，将准备和提交使用 3a2-请求价格与可用性合作伙伴接口流程 (PIP) 的请求。</span><span class="sxs-lookup"><span data-stu-id="95973-103">In this step, you prepare and submit a request using the Partner Interface Process (PIP) for a 3A2 - Request Price and Availability.</span></span> <span data-ttu-id="95973-104">此 PIP，买方组织以获取有关特定产品，如价格和可用单位数的信息。</span><span class="sxs-lookup"><span data-stu-id="95973-104">This PIP enables a buyer organization to obtain information about a certain product, such as price and number of available units.</span></span> <span data-ttu-id="95973-105">买方就可以处理该信息通过业务规则以确定是否从供应商购买产品。</span><span class="sxs-lookup"><span data-stu-id="95973-105">The buyer can then process that information through business rules to determine whether to purchase the product from the supplier.</span></span>  
  
### <a name="to-submit-a-3a2---request-price-and-availability"></a><span data-ttu-id="95973-106">若要提交 3A2-请求价格与可用性</span><span class="sxs-lookup"><span data-stu-id="95973-106">To submit a 3A2 - Request Price and Availability</span></span>  
  
1.  <span data-ttu-id="95973-107">在 Fabrikam 计算机上，在 Internet Explorer 中，找到并打开 http://localhost/LOBWebApplication/default.aspx。</span><span class="sxs-lookup"><span data-stu-id="95973-107">On the Fabrikam computer, in Internet Explorer, locate and open http://localhost/LOBWebApplication/default.aspx.</span></span>  
  
2.  <span data-ttu-id="95973-108">上**提交消息**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="95973-108">On the **Submit Message** page, do the following:</span></span>  
  
    |<span data-ttu-id="95973-109">使用此选项</span><span class="sxs-lookup"><span data-stu-id="95973-109">Use this</span></span>|<span data-ttu-id="95973-110">执行的操作</span><span class="sxs-lookup"><span data-stu-id="95973-110">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="95973-111">**本组织**</span><span class="sxs-lookup"><span data-stu-id="95973-111">**Home Organization**</span></span>|<span data-ttu-id="95973-112">类型**FABRIKAM**。</span><span class="sxs-lookup"><span data-stu-id="95973-112">Type **FABRIKAM**.</span></span>|  
    |<span data-ttu-id="95973-113">**合作伙伴组织**</span><span class="sxs-lookup"><span data-stu-id="95973-113">**Partner Organization**</span></span>|<span data-ttu-id="95973-114">类型**Contoso**。</span><span class="sxs-lookup"><span data-stu-id="95973-114">Type **Contoso**.</span></span>|  
    |<span data-ttu-id="95973-115">**Pip 代码**</span><span class="sxs-lookup"><span data-stu-id="95973-115">**Pip Code**</span></span>|<span data-ttu-id="95973-116">类型**3A2**。</span><span class="sxs-lookup"><span data-stu-id="95973-116">Type **3A2**.</span></span> <span data-ttu-id="95973-117">**重要提示：** 若要避免重复消息 ID 错误，您必须确保**Pip**是唯一的提交的每条消息。</span><span class="sxs-lookup"><span data-stu-id="95973-117">**Important:**  To avoid duplicate message ID errors, you must make sure that the **Pip** is unique for each message that you submit.</span></span> <span data-ttu-id="95973-118">如果在以后运行 3A2 测试，您必须更改本字段。</span><span class="sxs-lookup"><span data-stu-id="95973-118">If you run the 3A2 test in the future, you have to change this field.</span></span>|  
    |<span data-ttu-id="95973-119">**Pip 版本**</span><span class="sxs-lookup"><span data-stu-id="95973-119">**Pip Version**</span></span>|<span data-ttu-id="95973-120">类型**R02.00.00A**。</span><span class="sxs-lookup"><span data-stu-id="95973-120">Type **R02.00.00A**.</span></span>|  
    |<span data-ttu-id="95973-121">**Pip 实例 ID**</span><span class="sxs-lookup"><span data-stu-id="95973-121">**Pip Instance ID**</span></span>|<span data-ttu-id="95973-122">类型**3A2_Test**。</span><span class="sxs-lookup"><span data-stu-id="95973-122">Type **3A2_Test**.</span></span>|  
    |<span data-ttu-id="95973-123">**消息类别**</span><span class="sxs-lookup"><span data-stu-id="95973-123">**Message Category**</span></span>|<span data-ttu-id="95973-124">类型**操作**。</span><span class="sxs-lookup"><span data-stu-id="95973-124">Type **Action**.</span></span>|  
  
3.  <span data-ttu-id="95973-125">使用记事本或其他文本编辑器，打开在文件 3A2_Request.xml *\<驱动器\>*: \程序 Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances 文件夹，然后复制并粘贴到**服务内容**字段中LOBWebApplication。</span><span class="sxs-lookup"><span data-stu-id="95973-125">Using Notepad or another text editor, open the file 3A2_Request.xml in the *\<drive\>*:\ Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances folder, and then copy and paste the contents into the **Service Content** field in LOBWebApplication.</span></span>  
  
4.  <span data-ttu-id="95973-126">单击**提交**3A2 请求提交给 Contoso 计算机。</span><span class="sxs-lookup"><span data-stu-id="95973-126">Click **Submit** to submit the 3A2 request to the Contoso computer.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a><span data-ttu-id="95973-127">若要验证 Fabrikam 计算机上的成功通信</span><span class="sxs-lookup"><span data-stu-id="95973-127">To verify successful communication on the Fabrikam computer</span></span>  
  
-   <span data-ttu-id="95973-128">上**消息状态**LOBWebApplication 中的页上，确认已收到两条传入消息。</span><span class="sxs-lookup"><span data-stu-id="95973-128">On the **Message Status** page in LOBWebApplication, verify that you receive two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="95973-129">首先应收到类别 25 消息表明 Contoso 计算机的确认回执。</span><span class="sxs-lookup"><span data-stu-id="95973-129">You should first receive a category 25 message signifying a receipt acknowledgement from the Contoso computer.</span></span> <span data-ttu-id="95973-130">然后，应收到一类别 50 条消息，是从 Contoso 计算机的响应消息。</span><span class="sxs-lookup"><span data-stu-id="95973-130">You should then receive a category 50 message that is the response message from the Contoso computer.</span></span> <span data-ttu-id="95973-131">类别-99 之间消息表示发生错误。</span><span class="sxs-lookup"><span data-stu-id="95973-131">A category -99 message signifies an error.</span></span> <span data-ttu-id="95973-132">可以使用**事件查看器**来确定实际的错误消息。</span><span class="sxs-lookup"><span data-stu-id="95973-132">You can use **Event Viewer** to determine the actual error message.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a><span data-ttu-id="95973-133">若要验证 Contoso 计算机上的成功通信</span><span class="sxs-lookup"><span data-stu-id="95973-133">To verify successful communication on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="95973-134">单击**启动**，依次指向**所有程序**，指向**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="95973-134">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="95973-135">在中**连接到服务器**对话框中**SQL Server**框中，键入**localhost**，选择**Windows 身份验证**，然后单击**连接**。</span><span class="sxs-lookup"><span data-stu-id="95973-135">In the **Connect to Server** dialog box, in the **SQL Server** box, type **localhost**, select **Windows Authentication**, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="95973-136">在 Microsoft SQL Server Management Studio 中，单击**新查询**。</span><span class="sxs-lookup"><span data-stu-id="95973-136">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="95973-137">在中\<表\>文本框中，选择**BTARNDATA**从列表中。</span><span class="sxs-lookup"><span data-stu-id="95973-137">In the \<table\> text box, select **BTARNDATA** from the list.</span></span>  
  
5.  <span data-ttu-id="95973-138">在 SQL 窗口中，键入以下 SQL 语句：</span><span class="sxs-lookup"><span data-stu-id="95973-138">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  <span data-ttu-id="95973-139">单击**Execute**运行 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="95973-139">Click **Execute** to run the SQL statement.</span></span>  
  
7.  <span data-ttu-id="95973-140">在查询窗口中，在结果窗格中，验证看到两条传入消息。</span><span class="sxs-lookup"><span data-stu-id="95973-140">In the Query window, in the Results pane, verify that you see two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="95973-141">首先应收到一类别为 10 条消息，代表 Fabrikam 计算机发送的原始请求。</span><span class="sxs-lookup"><span data-stu-id="95973-141">You should first receive a category 10 message that represents the original request sent by the Fabrikam computer.</span></span> <span data-ttu-id="95973-142">然后，应收到条确认消息回执一类别 25 条消息。</span><span class="sxs-lookup"><span data-stu-id="95973-142">You should then receive a category 25 message signifying the receipt acknowledgement message.</span></span>  
  
8.  <span data-ttu-id="95973-143">在 SQL 窗口中，键入以下 SQL 语句：</span><span class="sxs-lookup"><span data-stu-id="95973-143">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. <span data-ttu-id="95973-144">单击**Execute**运行 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="95973-144">Click **Execute** to run the SQL statement.</span></span>  
  
10. <span data-ttu-id="95973-145">在查询窗口中，在结果窗格中，验证看到一条传出消息。</span><span class="sxs-lookup"><span data-stu-id="95973-145">In the Query window, in the Results pane, verify that you see one outgoing message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="95973-146">应看到类别 25 消息，表示从 Contoso 发送到 Fabrikam 计算机的确认回执消息。</span><span class="sxs-lookup"><span data-stu-id="95973-146">You should see a category 25 message that represents the receipt acknowledgement sent from Contoso to the Fabrikam computer.</span></span> <span data-ttu-id="95973-147">您应看到类别为 50 的消息，表示从 Contoso 业务线 (LOB) 应用程序到 Fabrikam 计算机发送的响应。</span><span class="sxs-lookup"><span data-stu-id="95973-147">You should also see a category 50 message that represents the response sent from the Contoso line-of-business (LOB) application to the Fabrikam computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95973-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="95973-148">See Also</span></span>  
 <span data-ttu-id="95973-149">[步骤 4：提交 3A4 请求](../../adapters-and-accelerators/accelerator-rosettanet/step-4-submitting-a-3a4-request.md) </span><span class="sxs-lookup"><span data-stu-id="95973-149">[Step 4: Submitting a 3A4 Request](../../adapters-and-accelerators/accelerator-rosettanet/step-4-submitting-a-3a4-request.md) </span></span>  
 [<span data-ttu-id="95973-150">BTARN 中的消息流</span><span class="sxs-lookup"><span data-stu-id="95973-150">Message Flow in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)