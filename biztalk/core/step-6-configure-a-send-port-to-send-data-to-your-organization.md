---
title: 步骤 6： 配置发送端口将数据发送到你的组织 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 796570ca-8178-4679-9213-d67a2a189bf9
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b513725024aec755515ccac998745220ee5dfa7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277005"
---
# <a name="step-6-configure-a-send-port-to-send-data-to-your-organization"></a><span data-ttu-id="cd6e1-102">步骤 6： 配置发送端口将数据发送到你的组织</span><span class="sxs-lookup"><span data-stu-id="cd6e1-102">Step 6: Configure a Send Port to Send Data to Your Organization</span></span>
<span data-ttu-id="cd6e1-103">![步骤 6 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-6of9.gif "Step_6of9")</span><span class="sxs-lookup"><span data-stu-id="cd6e1-103">![Step 6 of 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-6of9.gif "Step_6of9")</span></span>  
  
 <span data-ttu-id="cd6e1-104">在该步骤中，会对发送端口进行配置，以将 850 消息从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 发送到代表您的组织的 OrderSystem 参与方。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-104">In this step you configure a send port to send the 850 message from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to the OrderSystem party that represents your organization.</span></span> <span data-ttu-id="cd6e1-105">此发送端口将应用**Inbound4010850_to_OrderFile**映射，转换到映射中指定的格式输入消息的格式输出消息。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-105">This send port applies the **Inbound4010850_to_OrderFile** map, transforming the output message from the format of the input message to the format specified in the map.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cd6e1-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="cd6e1-106">Prerequisites</span></span>  
 <span data-ttu-id="cd6e1-107">你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-a-send-port-for-the-850-message"></a><span data-ttu-id="cd6e1-108">为 850 消息配置发送端口</span><span class="sxs-lookup"><span data-stu-id="cd6e1-108">To configure a send port for the 850 message</span></span>  
  
1.  <span data-ttu-id="cd6e1-109">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**管道**，然后单击**刷新**。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click **Pipelines**, and then click **Refresh**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cd6e1-110">为了能够针对将要创建的发送端口选择 SendOrderFilePipeline，可能有必要刷新管道列表。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-110">Refreshing the pipelines list may be necessary to be able to select the SendOrderFilePipeline for the send port that you will create.</span></span>  
  
2.  <span data-ttu-id="cd6e1-111">右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-111">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
3.  <span data-ttu-id="cd6e1-112">在**发送端口属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cd6e1-112">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="cd6e1-113">使用此选项</span><span class="sxs-lookup"><span data-stu-id="cd6e1-113">Use this</span></span>|<span data-ttu-id="cd6e1-114">执行的操作</span><span class="sxs-lookup"><span data-stu-id="cd6e1-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="cd6e1-115">**名称**</span><span class="sxs-lookup"><span data-stu-id="cd6e1-115">**Name**</span></span>|<span data-ttu-id="cd6e1-116">输入`toOrderSystem`。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-116">Enter `toOrderSystem`.</span></span>|  
    |<span data-ttu-id="cd6e1-117">**类型**</span><span class="sxs-lookup"><span data-stu-id="cd6e1-117">**Type**</span></span>|<span data-ttu-id="cd6e1-118">选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-118">Select **FILE**.</span></span>|  
    |<span data-ttu-id="cd6e1-119">**配置**</span><span class="sxs-lookup"><span data-stu-id="cd6e1-119">**Configure**</span></span>|<span data-ttu-id="cd6e1-120">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-120">Click **Configure**.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="cd6e1-121">由于测试消息是要传送到文件夹中的平面文件，因此发送端口的传输类型为 FILE。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-121">The transport type of the send port is FILE because the test message is a flat file to be delivered into a folder.</span></span>  
  
4.  <span data-ttu-id="cd6e1-122">在**文件传输属性**对话框框中，执行以下操作，然后单击**确定**:</span><span class="sxs-lookup"><span data-stu-id="cd6e1-122">In the **FILE Transport Properties** dialog box, do the following and then click **OK**:</span></span>  
  
    |<span data-ttu-id="cd6e1-123">使用此选项</span><span class="sxs-lookup"><span data-stu-id="cd6e1-123">Use this</span></span>|<span data-ttu-id="cd6e1-124">执行的操作</span><span class="sxs-lookup"><span data-stu-id="cd6e1-124">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="cd6e1-125">**目标文件夹**</span><span class="sxs-lookup"><span data-stu-id="cd6e1-125">**Destination folder**</span></span>|<span data-ttu-id="cd6e1-126">单击**浏览**，然后在**浏览文件夹**对话框中，移动到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI 接口开发人员 Tutorial\ProcessEDI_TestLocations\ 方案 A\toOrderSystem</span><span class="sxs-lookup"><span data-stu-id="cd6e1-126">Click **Browse**, and in the **Browse for Folder** dialog box, move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\ Scenario A\toOrderSystem</span></span>|  
    |<span data-ttu-id="cd6e1-127">**文件名**</span><span class="sxs-lookup"><span data-stu-id="cd6e1-127">**File name**</span></span>|<span data-ttu-id="cd6e1-128">输入`%MessageID%.txt`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-128">Enter `%MessageID%.txt`, and then click **OK**.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="cd6e1-129">值设置为**文件名**属性可确保输出文件将具有.txt 扩展名。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-129">The value set for the **File name** property ensures that the output file will have a .txt extension.</span></span>  
  
5.  <span data-ttu-id="cd6e1-130">在**发送端口属性**对话框中，为**发送管道**，选择**SendOrderFilePipeline**。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-130">In the **Send Port Properties** dialog box, for **Send pipeline**, select **SendOrderFilePipeline**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cd6e1-131">**SendOrderFilePipeline**发送管道包括平面文件汇编组合.txt 输出文件中，使用从输入 850 消息映射的数据。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-131">The **SendOrderFilePipeline** send pipeline includes a flat-file assembler that assembles the .txt output file, using data mapped from the input 850 message.</span></span> <span data-ttu-id="cd6e1-132">由于输出文件是 .txt 文件，因此它将不显示在交换/ACK 状态报告中。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-132">Since the output file is a .txt file, it will not show up in the Interchange/ACK status report.</span></span>  
  
6.  <span data-ttu-id="cd6e1-133">在控制台树中，单击**筛选器**，然后执行以下：</span><span class="sxs-lookup"><span data-stu-id="cd6e1-133">In the console tree, click **Filters**, and then do the following:</span></span>  
  
    |<span data-ttu-id="cd6e1-134">使用此选项</span><span class="sxs-lookup"><span data-stu-id="cd6e1-134">Use this</span></span>|<span data-ttu-id="cd6e1-135">执行的操作</span><span class="sxs-lookup"><span data-stu-id="cd6e1-135">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="cd6e1-136">**属性**</span><span class="sxs-lookup"><span data-stu-id="cd6e1-136">**Property**</span></span>|<span data-ttu-id="cd6e1-137">选择**BTS。ReceivePortName**。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-137">Select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="cd6e1-138">**运算符**</span><span class="sxs-lookup"><span data-stu-id="cd6e1-138">**Operator**</span></span>|<span data-ttu-id="cd6e1-139">选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-139">Select **==**.</span></span>|  
    |<span data-ttu-id="cd6e1-140">**值**</span><span class="sxs-lookup"><span data-stu-id="cd6e1-140">**Value**</span></span>|<span data-ttu-id="cd6e1-141">输入`ReceiveEDI_fromTHEM_A`。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-141">Enter `ReceiveEDI_fromTHEM_A`.</span></span>|  
    |<span data-ttu-id="cd6e1-142">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="cd6e1-142">**Group by**</span></span>|<span data-ttu-id="cd6e1-143">选择**和**。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-143">Select **And**.</span></span>|  
    |<span data-ttu-id="cd6e1-144">**属性**</span><span class="sxs-lookup"><span data-stu-id="cd6e1-144">**Property**</span></span>|<span data-ttu-id="cd6e1-145">在下一行中，选择**BTS。MessageType**。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-145">On the next line, select **BTS.MessageType**.</span></span>|  
    |<span data-ttu-id="cd6e1-146">**运算符**</span><span class="sxs-lookup"><span data-stu-id="cd6e1-146">**Operator**</span></span>|<span data-ttu-id="cd6e1-147">选择 **！ =**。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-147">Select **!=**.</span></span>|  
    |<span data-ttu-id="cd6e1-148">**值**</span><span class="sxs-lookup"><span data-stu-id="cd6e1-148">**Value**</span></span>|<span data-ttu-id="cd6e1-149">输入`http://schemas.microsoft.com/Edi/X12#X12_997_Root`。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-149">Enter `http://schemas.microsoft.com/Edi/X12#X12_997_Root`.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="cd6e1-150">此筛选器可确保发送端口将提取由 Receive_EDI_fromTHEM_A 接收位置接收的消息，而且发送端口将不提取 997 确认，而只提取 850 消息。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-150">The filter ensures that the send port will pick up messages that were received by the Receive_EDI_fromTHEM_A receive location, and that the send port will not pick up 997 acknowledgments, but will pick only 850 messages.</span></span>  
  
7.  <span data-ttu-id="cd6e1-151">在控制台树中，单击**OutboundMaps**。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-151">In the console tree, click **OutboundMaps**.</span></span> <span data-ttu-id="cd6e1-152">在**出站映射**窗格中，请在**映射**列，请在第一行中，选择**Inbound4010850_to_OrderFile**。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-152">In the **Outbound Maps** pane, in the **Map** column, on the first row, select **Inbound4010850_to_OrderFile**.</span></span> <span data-ttu-id="cd6e1-153">(中的条目**源文档**列将为 X12_00401_850。)</span><span class="sxs-lookup"><span data-stu-id="cd6e1-153">(The entry in the **Source Document** column will be X12_00401_850.)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cd6e1-154">此步骤可确保对输出消息将包含仅的数据从输入消息根据映射**Inbound4010850_to_OrderFile**映射。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-154">This step ensures that the output message will consist only of the data mapped from the input message according to the **Inbound4010850_to_OrderFile** map.</span></span>  
  
8.  <span data-ttu-id="cd6e1-155">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-155">Click **OK**.</span></span>  
  
9. <span data-ttu-id="cd6e1-156">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-156">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click **Send Ports**.</span></span> <span data-ttu-id="cd6e1-157">右键单击**toOrderSystem**，然后单击**启动**登记和启动端口。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-157">Right-click **toOrderSystem**, and then click **Start** to enlist and start the port.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="cd6e1-158">后续步骤</span><span class="sxs-lookup"><span data-stu-id="cd6e1-158">Next Steps</span></span>  
 <span data-ttu-id="cd6e1-159">配置发送端口 (**toTHEM_997**) 发送 997 确认重新为 Fabrikam 中, 所述[步骤 7： 配置发送端口将确认发送到你的贸易合作伙伴](../core/step-7-configure-a-send-port-to-send-the-acknowledgment-to-trading-partner.md)。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-159">You configure the send port (**toTHEM_997**) to send the 997 acknowledgment back to Fabrikam, as described in [Step 7: Configure a Send Port to Send the Acknowledgment to Your Trading Partner](../core/step-7-configure-a-send-port-to-send-the-acknowledgment-to-trading-partner.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd6e1-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd6e1-160">See Also</span></span>  
 [<span data-ttu-id="cd6e1-161">配置静态发送端口发送 EDI 交换和确认</span><span class="sxs-lookup"><span data-stu-id="cd6e1-161">Configuring a Static Send Port to Send EDI Interchanges and Acknowledgments</span></span>](../core/configuring-a-static-send-port-to-send-edi-interchanges-and-acknowledgments.md)