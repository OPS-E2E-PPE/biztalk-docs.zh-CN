---
title: "步骤 7： 配置发送端口将确认发送到贸易合作伙伴 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3a082870-894c-4f64-a575-3681d8a5c4ea
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59d36aaaf33673095c664363da5b3417bbd1cde4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-7-configure-a-send-port-to-send-the-acknowledgment-to-your-trading-partner"></a><span data-ttu-id="27982-102">步骤 7： 配置发送端口将确认发送到贸易合作伙伴</span><span class="sxs-lookup"><span data-stu-id="27982-102">Step 7: Configure a Send Port to Send the Acknowledgment to Your Trading Partner</span></span>
<span data-ttu-id="27982-103">![9 的第 7 步](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-7of9.gif "Step_7of9")</span><span class="sxs-lookup"><span data-stu-id="27982-103">![Step 7 of 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-7of9.gif "Step_7of9")</span></span>  
  
 <span data-ttu-id="27982-104">在此步骤中配置要发送由生成的 997 确认消息的发送端口[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到 Fabrikam **toTHEM_997**文件夹。</span><span class="sxs-lookup"><span data-stu-id="27982-104">In this step you configure a send port to send the 997 acknowledgment message that is generated by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to the Fabrikam **toTHEM_997** folder.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="27982-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="27982-105">Prerequisites</span></span>  
 <span data-ttu-id="27982-106">你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="27982-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-a-send-port-that-subscribes-to-the-997-acknowledgment"></a><span data-ttu-id="27982-107">配置订阅 997 确认的发送端口</span><span class="sxs-lookup"><span data-stu-id="27982-107">To configure a send port that subscribes to the 997 acknowledgment</span></span>  
  
1.  <span data-ttu-id="27982-108">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="27982-108">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="27982-109">在**发送端口属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="27982-109">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="27982-110">使用此选项</span><span class="sxs-lookup"><span data-stu-id="27982-110">Use this</span></span>|<span data-ttu-id="27982-111">执行的操作</span><span class="sxs-lookup"><span data-stu-id="27982-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="27982-112">**名称**</span><span class="sxs-lookup"><span data-stu-id="27982-112">**Name**</span></span>|<span data-ttu-id="27982-113">输入`toTHEM_997`。</span><span class="sxs-lookup"><span data-stu-id="27982-113">Enter `toTHEM_997`.</span></span>|  
    |<span data-ttu-id="27982-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="27982-114">**Type**</span></span>|<span data-ttu-id="27982-115">选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="27982-115">Select **FILE**.</span></span>|  
    |<span data-ttu-id="27982-116">**配置**</span><span class="sxs-lookup"><span data-stu-id="27982-116">**Configure**</span></span>|<span data-ttu-id="27982-117">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="27982-117">Click **Configure**.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="27982-118">由于 997 是要传送到文件夹中的平面文件，因而发送端口的传输类型为 FILE。</span><span class="sxs-lookup"><span data-stu-id="27982-118">The transport type of the send port is FILE because the 997 is a flat file to be delivered into a folder.</span></span>  
  
3.  <span data-ttu-id="27982-119">在**文件传输属性**对话框框中，执行以下操作，然后单击**确定**:</span><span class="sxs-lookup"><span data-stu-id="27982-119">In the **FILE Transport Properties** dialog box, do the following and then click **OK**:</span></span>  
  
    |<span data-ttu-id="27982-120">使用此选项</span><span class="sxs-lookup"><span data-stu-id="27982-120">Use this</span></span>|<span data-ttu-id="27982-121">执行的操作</span><span class="sxs-lookup"><span data-stu-id="27982-121">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="27982-122">**目标文件夹**</span><span class="sxs-lookup"><span data-stu-id="27982-122">**Destination folder**</span></span>|<span data-ttu-id="27982-123">单击**浏览**，然后在**浏览文件夹**对话框中，移动到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI 接口开发人员 Tutorial\ProcessEDI_TestLocations\ 方案 A\toTHEM_997。</span><span class="sxs-lookup"><span data-stu-id="27982-123">Click **Browse**, and in the **Browse For Folder** dialog box, move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\ Scenario A\toTHEM_997.</span></span>|  
    |<span data-ttu-id="27982-124">**文件名**</span><span class="sxs-lookup"><span data-stu-id="27982-124">**File name**</span></span>|<span data-ttu-id="27982-125">输入`%MessageID%.txt`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="27982-125">Enter `%MessageID%.txt`, and then click **OK**.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="27982-126">值设置为**文件名**属性可确保输出文件将具有.txt 扩展名。</span><span class="sxs-lookup"><span data-stu-id="27982-126">The value set for the **File name** property ensures that the output file will have a .txt extension.</span></span>  
  
4.  <span data-ttu-id="27982-127">在**发送端口属性**对话框中，为**发送管道**，选择**EdiSend**。</span><span class="sxs-lookup"><span data-stu-id="27982-127">In the **Send Port Properties** dialog box, for **Send Pipeline**, select **EdiSend**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="27982-128">用于发送 EDI 交换的发送管道除通过 AS2 传输传递的之外其他均为 EdiSend 管道。</span><span class="sxs-lookup"><span data-stu-id="27982-128">The send pipeline used to send EDI interchanges, except for those delivered over the AS2 transport, is the EdiSend pipeline.</span></span> <span data-ttu-id="27982-129">（AS2EdiSend 发送管道用于通过 AS2 传输发送 EDI 交换。）</span><span class="sxs-lookup"><span data-stu-id="27982-129">(The AS2EdiSend send pipeline is used to send EDI interchanges delivered over the AS2 transport.)</span></span>  
  
5.  <span data-ttu-id="27982-130">在控制台树中，单击**筛选器**，然后执行以下：</span><span class="sxs-lookup"><span data-stu-id="27982-130">In the console tree, click **Filters**, and then do the following:</span></span>  
  
    |<span data-ttu-id="27982-131">使用此选项</span><span class="sxs-lookup"><span data-stu-id="27982-131">Use this</span></span>|<span data-ttu-id="27982-132">执行的操作</span><span class="sxs-lookup"><span data-stu-id="27982-132">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="27982-133">**属性**</span><span class="sxs-lookup"><span data-stu-id="27982-133">**Property**</span></span>|<span data-ttu-id="27982-134">选择**BTS。MessageType**。</span><span class="sxs-lookup"><span data-stu-id="27982-134">Select **BTS.MessageType**.</span></span>|  
    |<span data-ttu-id="27982-135">**运算符**</span><span class="sxs-lookup"><span data-stu-id="27982-135">**Operator**</span></span>|<span data-ttu-id="27982-136">选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="27982-136">Select **==**.</span></span>|  
    |<span data-ttu-id="27982-137">**值**</span><span class="sxs-lookup"><span data-stu-id="27982-137">**Value**</span></span>|<span data-ttu-id="27982-138">输入**http://schemas.microsoft.com/Edi/X12#X12_997_Root**。</span><span class="sxs-lookup"><span data-stu-id="27982-138">Enter **http://schemas.microsoft.com/Edi/X12#X12_997_Root**.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="27982-139">本筛选器可确保发送端口将提取 997 消息类型的消息。</span><span class="sxs-lookup"><span data-stu-id="27982-139">The filter ensures that the send port will pick up messages with the 997 message type.</span></span>  
  
6.  <span data-ttu-id="27982-140">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="27982-140">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="27982-141">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="27982-141">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click **Send Ports**.</span></span> <span data-ttu-id="27982-142">右键单击**toTHEM_997**，然后单击**启动**登记和启动端口。</span><span class="sxs-lookup"><span data-stu-id="27982-142">Right-click **toTHEM_997**, and then click **Start** to enlist and start the port.</span></span>  
  
8.  <span data-ttu-id="27982-143">在 BizTalk Server 管理控制台中，在控制台树中，单击**平台设置**，然后单击**主机实例**。</span><span class="sxs-lookup"><span data-stu-id="27982-143">In the BizTalk Server Administration Console, in the console tree, click **Platform Settings**, and then click **Host Instances**.</span></span> <span data-ttu-id="27982-144">在主机实例窗格中，单击**BizTalkServerApplication**，然后单击**重新启动**。</span><span class="sxs-lookup"><span data-stu-id="27982-144">In the Host Instances pane, click **BizTalkServerApplication**, and then click **Restart**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="27982-145">后续步骤</span><span class="sxs-lookup"><span data-stu-id="27982-145">Next Steps</span></span>  
 <span data-ttu-id="27982-146">中所述创建两个贸易合作伙伴之间的协议[第 8 步： 配置参与方之间贸易合作伙伴协议](../core/step-8-configure-the-trading-partner-agreement-between-the-parties.md)。</span><span class="sxs-lookup"><span data-stu-id="27982-146">You create an agreement between the two trading partners, as described in [Step 8: Configure the Trading Partner Agreement between the Parties](../core/step-8-configure-the-trading-partner-agreement-between-the-parties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27982-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27982-147">See Also</span></span>  
 [<span data-ttu-id="27982-148">配置静态发送端口发送 EDI 交换和确认</span><span class="sxs-lookup"><span data-stu-id="27982-148">Configuring a Static Send Port to Send EDI Interchanges and Acknowledgments</span></span>](../core/configuring-a-static-send-port-to-send-edi-interchanges-and-acknowledgments.md)