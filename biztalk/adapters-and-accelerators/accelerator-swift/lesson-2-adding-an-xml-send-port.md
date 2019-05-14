---
title: 第 2 课：添加 XML 发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, XML ports
- XML ports
ms.assetid: 03b2ee43-7874-4ef9-b716-8e16e96d8382
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac2a76fc7c614fbaed34845ae8c9f8f8bec69b4e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377404"
---
# <a name="lesson-2-adding-an-xml-send-port"></a><span data-ttu-id="4c890-102">第 2 课：添加 XML 发送端口</span><span class="sxs-lookup"><span data-stu-id="4c890-102">Lesson 2: Adding an XML Send Port</span></span>
<span data-ttu-id="4c890-103">使用发送端口以定义要发送的消息的方式。</span><span class="sxs-lookup"><span data-stu-id="4c890-103">You use a send port to define how you want the messages sent.</span></span> <span data-ttu-id="4c890-104">在本课程中，您可以创建用于定义应如何发送 XML 消息的发送端口。</span><span class="sxs-lookup"><span data-stu-id="4c890-104">In this lesson, you create a send port to define how XML messages should be sent.</span></span>  

### <a name="to-add-an-xml-send-port"></a><span data-ttu-id="4c890-105">若要添加 XML 发送端口</span><span class="sxs-lookup"><span data-stu-id="4c890-105">To add an XML send port</span></span>  

1. <span data-ttu-id="4c890-106">在 BizTalk Server 管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="4c890-106">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  

2. <span data-ttu-id="4c890-107">在发送端口属性对话框中，在**名称**框中，键入**MT103_XML_SendPort**。</span><span class="sxs-lookup"><span data-stu-id="4c890-107">In the Send Port Properties dialog box, in the **Name** box, type **MT103_XML_SendPort**.</span></span>  

3. <span data-ttu-id="4c890-108">在中**传输**部分中，对于**类型**框中，单击下拉列表中，并选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="4c890-108">In the **Transport** section, for the **Type** box, click the drop-down list, and then select **FILE**.</span></span>  

4. <span data-ttu-id="4c890-109">单击**配置**类型下拉列表右侧的按钮。</span><span class="sxs-lookup"><span data-stu-id="4c890-109">Click the **Configure** button to the right of the Type drop-down list.</span></span>  

5. <span data-ttu-id="4c890-110">在 FILE 传输属性对话框中，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="4c890-110">In the FILE Transport Properties dialog box, click **Browse**.</span></span>  

6. <span data-ttu-id="4c890-111">在浏览文件夹对话框中，转至**\<驱动器\>: \Labs\Outbound**文件夹，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="4c890-111">In the Browse For Folder dialog box, move to the **\<drive\>:\Labs\Outbound** folder, and then click **OK**.</span></span>  

7. <span data-ttu-id="4c890-112">在 FILE 传输属性对话框中，确保 **%MessageID%.xml**中输入**文件名**框中，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="4c890-112">In the FILE Transport Properties dialog box, ensure that **%MessageID%.xml** is entered in the **File Name** box, and then click **OK**.</span></span>  

8. <span data-ttu-id="4c890-113">在发送端口属性对话框中，确保**BizTalkServerApplication**选择了**发送处理程序**中，并确保**PassThruTransmit**为选择**发送管道**框。</span><span class="sxs-lookup"><span data-stu-id="4c890-113">In the Send Port Properties dialog box, ensure that **BizTalkServerApplication** is selected for the **Send handler** box, and that **PassThruTransmit** is selected for the **Send pipeline** box.</span></span>  

9. <span data-ttu-id="4c890-114">在左窗格中，单击**筛选器**，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4c890-114">In the left pane, click **Filters**, and then do the following:</span></span>  


   |   <span data-ttu-id="4c890-115">使用此选项</span><span class="sxs-lookup"><span data-stu-id="4c890-115">Use this</span></span>   |              <span data-ttu-id="4c890-116">执行的操作</span><span class="sxs-lookup"><span data-stu-id="4c890-116">To do this</span></span>              |
   |--------------|--------------------------------------|
   | <span data-ttu-id="4c890-117">**属性**</span><span class="sxs-lookup"><span data-stu-id="4c890-117">**Property**</span></span> |   <span data-ttu-id="4c890-118">选择**BTS。ReceivePortName**。</span><span class="sxs-lookup"><span data-stu-id="4c890-118">Select **BTS.ReceivePortName**.</span></span>    |
   | <span data-ttu-id="4c890-119">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="4c890-119">**Operator**</span></span> |            <span data-ttu-id="4c890-120">选择 ==。</span><span class="sxs-lookup"><span data-stu-id="4c890-120">Select **==**.</span></span>            |
   |  <span data-ttu-id="4c890-121">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="4c890-121">**Value**</span></span>   | <span data-ttu-id="4c890-122">类型**MT103_FlatFile_ReceivePort**。</span><span class="sxs-lookup"><span data-stu-id="4c890-122">Type **MT103_FlatFile_ReceivePort**.</span></span> |
   |  <span data-ttu-id="4c890-123">**分组**</span><span class="sxs-lookup"><span data-stu-id="4c890-123">**Group**</span></span>   |           <span data-ttu-id="4c890-124">选择**和**。</span><span class="sxs-lookup"><span data-stu-id="4c890-124">Select **And**.</span></span>            |


10. <span data-ttu-id="4c890-125">在下一步的属性行中单击，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4c890-125">Click inside the next property line and do the following:</span></span>  

    |<span data-ttu-id="4c890-126">使用此选项</span><span class="sxs-lookup"><span data-stu-id="4c890-126">Use this</span></span>|<span data-ttu-id="4c890-127">执行的操作</span><span class="sxs-lookup"><span data-stu-id="4c890-127">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="4c890-128">**属性**</span><span class="sxs-lookup"><span data-stu-id="4c890-128">**Property**</span></span>|<span data-ttu-id="4c890-129">选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**</span><span class="sxs-lookup"><span data-stu-id="4c890-129">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**</span></span>|  
    |<span data-ttu-id="4c890-130">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="4c890-130">**Operator**</span></span>|<span data-ttu-id="4c890-131">选择 ==。</span><span class="sxs-lookup"><span data-stu-id="4c890-131">Select **==**.</span></span>|  
    |<span data-ttu-id="4c890-132">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="4c890-132">**Value**</span></span>|<span data-ttu-id="4c890-133">类型**False**为有效的消息。</span><span class="sxs-lookup"><span data-stu-id="4c890-133">Type **False** for valid messages.</span></span>|  

    > [!NOTE]
    >  <span data-ttu-id="4c890-134">您将添加 **"Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed = = False"** 筛选器表达式子句，以便发送端口将发送仅成功分析和验证消息。</span><span class="sxs-lookup"><span data-stu-id="4c890-134">You add the **"Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed == False"** filter expression clause so that the send port sends only successfully parsed and validated messages.</span></span> <span data-ttu-id="4c890-135">与不同的接收管道使用本机[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]拆装器，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]拆装器不会挂起失败 （错误） 消息，但改为将其发布到 MessageBox 和标记为失败，使用升级的属性。</span><span class="sxs-lookup"><span data-stu-id="4c890-135">Unlike a receive pipeline using native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] disassemblers, the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] disassembler will not suspend a failed (erroneous) message, but instead publishes it to the MessageBox and marks it as failed, using promoted properties.</span></span> <span data-ttu-id="4c890-136">A4SWIFT 将附加的 XML 表示形式将其发布到 MessageBox 之前收集到失败消息的错误。</span><span class="sxs-lookup"><span data-stu-id="4c890-136">A4SWIFT attaches an XML representation of the errors that were collected to the failed message before publishing it to the MessageBox.</span></span>  
    > <span data-ttu-id="4c890-137">不包含"Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed = = False"筛选表达式子句中，您的发送端口将发送所有消息： 通过或失败。</span><span class="sxs-lookup"><span data-stu-id="4c890-137">Without including the "Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed == False" filter expression clause, your send port will send all messages: passed or failed.</span></span> <span data-ttu-id="4c890-138">有关失败的消息订阅的详细信息，请参阅[使用失败消息订阅](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="4c890-138">For more information about failed message subscriptions, see [Working with Failed Message Subscriptions](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md).</span></span>  

11. <span data-ttu-id="4c890-139">单击**Apply**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="4c890-139">Click **Apply**, and then click **OK**.</span></span>  

12. <span data-ttu-id="4c890-140">在 BizTalk Server 管理控制台中，在**发送端口**，右键单击**MT103_XML_SendPort**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="4c890-140">In the BizTalk Server Administration Console, in **Send Ports**, right-click **MT103_XML_SendPort**, and then click **Start**.</span></span>  

    <span data-ttu-id="4c890-141">请继续执行[模块 6:部署业务规则](../../adapters-and-accelerators/accelerator-swift/module-6-deploying-the-business-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="4c890-141">Proceed to [Module 6: Deploying the Business Rules](../../adapters-and-accelerators/accelerator-swift/module-6-deploying-the-business-rules.md).</span></span>