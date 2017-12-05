---
title: "步骤 6： 创建发送端口，以提供 ADT ^ 到 RX 系统使用了文件适配器 A03 消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, send ports
- creating, send ports
- send ports, creating
ms.assetid: 66c4b524-c8ff-43b5-9c44-6d7bc759ae2c
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62581310d4260ecb5b1162df1f52b0170d791d57
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="step-6-create-a-send-port-to-deliver-the-adta03-message-to-the-rx-system-using-the-file-adapter"></a><span data-ttu-id="ba1a2-102">步骤 6： 创建发送端口，以提供 ADT ^ 到 RX 系统使用了文件适配器 A03 消息</span><span class="sxs-lookup"><span data-stu-id="ba1a2-102">Step 6: Create a Send Port to Deliver the ADT^A03 Message to the RX System Using the File Adapter</span></span>
<span data-ttu-id="ba1a2-103">在此步骤中，你创建发送端口文件适配器时为药房系统 (RX)。</span><span class="sxs-lookup"><span data-stu-id="ba1a2-103">In this step, you create the send port for the Pharmacy System (RX) using the File adapter.</span></span>  
  
### <a name="to-create-the-tutorialsendmsgrx-send-port"></a><span data-ttu-id="ba1a2-104">若要创建 Tutorial_sendMsg_RX 发送端口</span><span class="sxs-lookup"><span data-stu-id="ba1a2-104">To create the Tutorial_sendMsg_RX send port</span></span>  
  
1.  <span data-ttu-id="ba1a2-105">在 BizTalk Server 管理控制台中，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="ba1a2-105">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="ba1a2-106">在**发送端口属性**对话框框中，执行以下操作，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ba1a2-106">In the **Send Port Properties** dialog box, do the following actions and then click **OK**.</span></span>  
  
    |<span data-ttu-id="ba1a2-107">使用此选项</span><span class="sxs-lookup"><span data-stu-id="ba1a2-107">Use this</span></span>|<span data-ttu-id="ba1a2-108">执行的操作</span><span class="sxs-lookup"><span data-stu-id="ba1a2-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="ba1a2-109">**名称**</span><span class="sxs-lookup"><span data-stu-id="ba1a2-109">**Name**</span></span>|<span data-ttu-id="ba1a2-110">类型**Tutorial_sendMsg_RX**。</span><span class="sxs-lookup"><span data-stu-id="ba1a2-110">Type **Tutorial_sendMsg_RX**.</span></span>|  
    |<span data-ttu-id="ba1a2-111">**传输类型**</span><span class="sxs-lookup"><span data-stu-id="ba1a2-111">**Transport type**</span></span>|<span data-ttu-id="ba1a2-112">选择**文件**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="ba1a2-112">Select **FILE** from the drop-down list.</span></span>|  
    |<span data-ttu-id="ba1a2-113">**配置**</span><span class="sxs-lookup"><span data-stu-id="ba1a2-113">**Configure**</span></span>|<span data-ttu-id="ba1a2-114">单击**配置**以打开**文件传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="ba1a2-114">Click **Configure** to open the **File Transport Properties** dialog box.</span></span>|  
  
3.  <span data-ttu-id="ba1a2-115">在文件传输属性对话框中，执行以下操作，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ba1a2-115">In the FILE Transport Properties dialog box, do the following actions and then click **OK**.</span></span>  
  
    |<span data-ttu-id="ba1a2-116">使用此选项</span><span class="sxs-lookup"><span data-stu-id="ba1a2-116">Use this</span></span>|<span data-ttu-id="ba1a2-117">执行的操作</span><span class="sxs-lookup"><span data-stu-id="ba1a2-117">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="ba1a2-118">**目标文件夹**</span><span class="sxs-lookup"><span data-stu-id="ba1a2-118">**Destination folder**</span></span>|<span data-ttu-id="ba1a2-119">浏览到 **\<** *驱动器***:\>files\microsoft BizTalk\<版本\>HL7\SDK\End 端到端的快捷键Tutorial\Tutorial_sendMsg_RX**。</span><span class="sxs-lookup"><span data-stu-id="ba1a2-119">Browse to **\<***drive***:\>\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_sendMsg_RX**.</span></span>|  
    |<span data-ttu-id="ba1a2-120">**文件名**</span><span class="sxs-lookup"><span data-stu-id="ba1a2-120">**File name**</span></span>|<span data-ttu-id="ba1a2-121">类型**%MessageID%.txt** （替换为.xml 扩展名.txt 扩展名）。</span><span class="sxs-lookup"><span data-stu-id="ba1a2-121">Type **%MessageID%.txt** (replace the .xml extension with the .txt extension).</span></span>|  
  
4.  <span data-ttu-id="ba1a2-122">在**发送端口属性**对话框中，为**发送管道**，选择**BTAHL72XPipelines.BTAHL72XSendPipeline**。</span><span class="sxs-lookup"><span data-stu-id="ba1a2-122">In the **Send Port Properties** dialog box, for **Send Pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  
  
5.  <span data-ttu-id="ba1a2-123">在左窗格中，选择**筛选器**，然后执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="ba1a2-123">In the left pane, select **Filters**, and then do the following actions.</span></span> <span data-ttu-id="ba1a2-124">单击 **“确定”** 继续。</span><span class="sxs-lookup"><span data-stu-id="ba1a2-124">Click **OK** to continue.</span></span>  
  
    |<span data-ttu-id="ba1a2-125">使用此选项</span><span class="sxs-lookup"><span data-stu-id="ba1a2-125">Use this</span></span>|<span data-ttu-id="ba1a2-126">执行的操作</span><span class="sxs-lookup"><span data-stu-id="ba1a2-126">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="ba1a2-127">**属性**（首行）</span><span class="sxs-lookup"><span data-stu-id="ba1a2-127">**Property** (first line)</span></span>|<span data-ttu-id="ba1a2-128">选择**BTS。MessageType**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="ba1a2-128">Select **BTS.MessageType** from the drop-down list.</span></span>|  
    |<span data-ttu-id="ba1a2-129">**运算符**</span><span class="sxs-lookup"><span data-stu-id="ba1a2-129">**Operator**</span></span>|<span data-ttu-id="ba1a2-130">选择**！ =**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="ba1a2-130">Select **!=** from the drop-down list.</span></span>|  
    |<span data-ttu-id="ba1a2-131">**值**</span><span class="sxs-lookup"><span data-stu-id="ba1a2-131">**Value**</span></span>|<span data-ttu-id="ba1a2-132">类型**http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF**。</span><span class="sxs-lookup"><span data-stu-id="ba1a2-132">Type **http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF**.</span></span>|  
    |<span data-ttu-id="ba1a2-133">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="ba1a2-133">**Group By**</span></span>|<span data-ttu-id="ba1a2-134">选择**或**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="ba1a2-134">Select **OR** from the drop-down list.</span></span>|  
    |<span data-ttu-id="ba1a2-135">**属性**（第二个行）</span><span class="sxs-lookup"><span data-stu-id="ba1a2-135">**Property** (second line)</span></span>|<span data-ttu-id="ba1a2-136">单击下的字段**属性**，然后选择**BTS。MessageType**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="ba1a2-136">Click the field under **Property**, and then select **BTS.MessageType** from the drop-down list.</span></span>|  
    |<span data-ttu-id="ba1a2-137">**运算符**</span><span class="sxs-lookup"><span data-stu-id="ba1a2-137">**Operator**</span></span>|<span data-ttu-id="ba1a2-138">选择**！ =**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="ba1a2-138">Select **!=** from the drop-down list.</span></span>|  
    |<span data-ttu-id="ba1a2-139">**值**</span><span class="sxs-lookup"><span data-stu-id="ba1a2-139">**Value**</span></span>|<span data-ttu-id="ba1a2-140">类型**http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF。**</span><span class="sxs-lookup"><span data-stu-id="ba1a2-140">Type **http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF.**</span></span>|  
    |<span data-ttu-id="ba1a2-141">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="ba1a2-141">**Group By**</span></span>|<span data-ttu-id="ba1a2-142">选择**AND**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="ba1a2-142">Select **AND** from the drop-down list.</span></span>|  
    |<span data-ttu-id="ba1a2-143">**属性**（第三个行）</span><span class="sxs-lookup"><span data-stu-id="ba1a2-143">**Property** (third line)</span></span>|<span data-ttu-id="ba1a2-144">选择**BTAHL7Schemas.MSH3_1**。</span><span class="sxs-lookup"><span data-stu-id="ba1a2-144">Select **BTAHL7Schemas.MSH3_1**.</span></span>|  
    |<span data-ttu-id="ba1a2-145">**运算符**</span><span class="sxs-lookup"><span data-stu-id="ba1a2-145">**Operator**</span></span>|<span data-ttu-id="ba1a2-146">选择 **==** 从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="ba1a2-146">Select **==** from the drop-down list.</span></span>|  
    |<span data-ttu-id="ba1a2-147">**值**</span><span class="sxs-lookup"><span data-stu-id="ba1a2-147">**Value**</span></span>|<span data-ttu-id="ba1a2-148">类型**Tutorial_ADTSystem**。</span><span class="sxs-lookup"><span data-stu-id="ba1a2-148">Type **Tutorial_ADTSystem**.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="ba1a2-149">第一个筛选器意味着医院信息系统 (HIS) 璹一条消息，不确认。</span><span class="sxs-lookup"><span data-stu-id="ba1a2-149">The first filter means that the Hospital Information System (HIS) is subscribing to a message, not an acknowledgment.</span></span> <span data-ttu-id="ba1a2-150">第二个筛选器意味着他订阅其源是许可释放和传输 (ADT) 系统的消息。</span><span class="sxs-lookup"><span data-stu-id="ba1a2-150">The second filter means that HIS is subscribing to messages whose source is the Admissions Discharge and Transfer (ADT) System.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ba1a2-151">BTAHL7 在文件放置位置将删除该消息\<*驱动器*\>： 程序 FilesMicrosoft BizTalk <version> HL7SDKEnd 端到端 TutorialTutorial_sendMsg_RX 快捷键。</span><span class="sxs-lookup"><span data-stu-id="ba1a2-151">BTAHL7 drops the message at the file drop location \<*drive*\>:Program FilesMicrosoft BizTalk <version> Accelerator for HL7SDKEnd-to-End TutorialTutorial_sendMsg_RX.</span></span>  
  
6.  <span data-ttu-id="ba1a2-152">单击**应用**，然后单击**确定。**</span><span class="sxs-lookup"><span data-stu-id="ba1a2-152">Click **Apply**, and then click **OK.**</span></span>  
  
7.  <span data-ttu-id="ba1a2-153">在管理控制台中，单击**发送端口**，右键单击**Tutorial_sendMsg_RX**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="ba1a2-153">In the Administration Console, click **Send Ports**, right-click **Tutorial_sendMsg_RX**, and then click **Start**.</span></span>  
  
 <span data-ttu-id="ba1a2-154">继续执行[步骤 7： 创建发送端口，以提供 ADT ^ A03 消息到他使用 MLLP 适配器](../../adapters-and-accelerators/accelerator-hl7/step-7-create-send-port-to-deliver-adt^a03-message-to-his-using-mllp-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="ba1a2-154">Proceed to [Step 7: Create a Send Port to Deliver the ADT^A03 Message to HIS Using the MLLP Adapter](../../adapters-and-accelerators/accelerator-hl7/step-7-create-send-port-to-deliver-adt^a03-message-to-his-using-mllp-adapter.md).</span></span>