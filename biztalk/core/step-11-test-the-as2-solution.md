---
title: "步骤 11： 测试 AS2 解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 184ed8ee-6778-4bb9-b265-a94a1fed03cb
caps.latest.revision: "34"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 490833859717ec37e0cb53ae89497aa361adda6e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-11-test-the-as2-solution"></a><span data-ttu-id="fa87f-102">步骤 11： 测试 AS2 解决方案</span><span class="sxs-lookup"><span data-stu-id="fa87f-102">Step 11: Test the AS2 Solution</span></span>
<span data-ttu-id="fa87f-103">![步骤 11 11](../core/media/tut-step11-of-11.gif "Tut_Step11_of_11")</span><span class="sxs-lookup"><span data-stu-id="fa87f-103">![Step 11 of 11](../core/media/tut-step11-of-11.gif "Tut_Step11_of_11")</span></span>  
  
 <span data-ttu-id="fa87f-104">在此步骤中，你将验证此教程的结果。</span><span class="sxs-lookup"><span data-stu-id="fa87f-104">In this step you verify the results of this tutorial.</span></span>  
  
 <span data-ttu-id="fa87f-105">你需要生成 Sender.exe 文件，以用于将 EDI 消息发送到 Receive_AS2 接收位置（通过 Contoso 虚拟目录）。</span><span class="sxs-lookup"><span data-stu-id="fa87f-105">You need to build the Sender.exe file that you use to send an EDI message to the Receive_AS2 receive location (through the Contoso virtual directory).</span></span> <span data-ttu-id="fa87f-106">Sender.exe 返回一个异步 MDN 消息。</span><span class="sxs-lookup"><span data-stu-id="fa87f-106">Sender.exe returns an asynchronous MDN message.</span></span> <span data-ttu-id="fa87f-107">消息文件是位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] SDK\AS2 Tutorial 文件夹中的 X12_00401_864.edi。</span><span class="sxs-lookup"><span data-stu-id="fa87f-107">The message file is X12_00401_864.edi located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial folder.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fa87f-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="fa87f-108">Prerequisites</span></span>  
 <span data-ttu-id="fa87f-109">你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="fa87f-109">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-test-the-solution-with-an-asynchronous-edi-message"></a><span data-ttu-id="fa87f-110">使用异步 EDI 消息测试解决方案</span><span class="sxs-lookup"><span data-stu-id="fa87f-110">To test the solution with an asynchronous EDI message</span></span>  
  
1.  <span data-ttu-id="fa87f-111">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，打开 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender 文件夹中的 Sender.csproj 项目。</span><span class="sxs-lookup"><span data-stu-id="fa87f-111">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the Sender.csproj project in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender folder.</span></span> <span data-ttu-id="fa87f-112">右键单击 Sender 项目，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="fa87f-112">Right-click the Sender project, and then click **Properties**.</span></span> <span data-ttu-id="fa87f-113">单击**签名**在左侧的控制台。</span><span class="sxs-lookup"><span data-stu-id="fa87f-113">Click **Signing** in the left-hand console.</span></span> <span data-ttu-id="fa87f-114">确保**对程序集签名**是选择，并将强名称密钥文件设置为**Sender.snk**。</span><span class="sxs-lookup"><span data-stu-id="fa87f-114">Ensure that **Sign the assembly** is selected, and set the strong name key file to **Sender.snk**.</span></span> <span data-ttu-id="fa87f-115">请确保**仅延迟签名**处于未选中状态。</span><span class="sxs-lookup"><span data-stu-id="fa87f-115">Make sure that **Delay sign only** is cleared.</span></span>  
  
2.  <span data-ttu-id="fa87f-116">生成此项目。</span><span class="sxs-lookup"><span data-stu-id="fa87f-116">Build the project.</span></span>  
  
3.  <span data-ttu-id="fa87f-117">打开命令提示符，导航到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender\bin\debug。</span><span class="sxs-lookup"><span data-stu-id="fa87f-117">Open a command prompt and navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender\bin\debug.</span></span> <span data-ttu-id="fa87f-118">Enter `Sender.exe`，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="fa87f-118">Enter `Sender.exe`, and then press **Enter**.</span></span> <span data-ttu-id="fa87f-119">验证你已看到一条消息，指出 AS2 消息已成功发送，然后关闭命令提示符窗口。</span><span class="sxs-lookup"><span data-stu-id="fa87f-119">Verify that you see a message indicating that an AS2 message was successfully sent, and then close the command prompt.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fa87f-120">运行包含以下 AS2 消息的 Sender.exe 生成 EDI 测试交换： [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\X12_00401_864.edi。</span><span class="sxs-lookup"><span data-stu-id="fa87f-120">Running Sender.exe builds an AS2 message containing the following EDI test interchange: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\X12_00401_864.edi.</span></span> <span data-ttu-id="fa87f-121">生成 AS2 消息后，它将把该消息发布到 Contoso 虚拟目录，该虚拟目录使用 BTSHttpReceive.dll 将消息路由到接收位置。</span><span class="sxs-lookup"><span data-stu-id="fa87f-121">After building the AS2 message, it posts it to the Contoso virtual directory, which uses BTSHttpReceive.dll to route the message to the receive location.</span></span>  
  
4.  <span data-ttu-id="fa87f-122">导航到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 教程\\_MDNToFabrikam 文件夹。</span><span class="sxs-lookup"><span data-stu-id="fa87f-122">Navigate to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\\_MDNToFabrikam folder.</span></span> <span data-ttu-id="fa87f-123">验证是否有\<GUID > 文件夹中的消息文件。</span><span class="sxs-lookup"><span data-stu-id="fa87f-123">Verify that there is a \<GUID>.msg file in the folder.</span></span> <span data-ttu-id="fa87f-124">在记事本中打开该文件，验证消息是一个 MDN，且 AS2-From 设置为 Contoso，AS2-To 设置为 Fabrikam。</span><span class="sxs-lookup"><span data-stu-id="fa87f-124">Open the file in Notepad, and verify that the message is an MDN with AS2-From set to Contoso and AS2-To set to Fabrikam.</span></span>  
  
5.  <span data-ttu-id="fa87f-125">导航到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 教程\\_EDIXMLToContoso 文件夹。</span><span class="sxs-lookup"><span data-stu-id="fa87f-125">Navigate to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\\_EDIXMLToContoso folder.</span></span> <span data-ttu-id="fa87f-126">验证是否有\<GUID > 文件夹中的.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="fa87f-126">Verify that there is a \<GUID>.xml file in the folder.</span></span> <span data-ttu-id="fa87f-127">双击该文件，然后验证消息的 ST01 字段设置为 864。</span><span class="sxs-lookup"><span data-stu-id="fa87f-127">Double-click the file, and verify that the ST01 field of the message is set to 864.</span></span>  
  
6.  <span data-ttu-id="fa87f-128">导航到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 教程\\_997ToFabrikam 文件夹。</span><span class="sxs-lookup"><span data-stu-id="fa87f-128">Navigate to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\\_997ToFabrikam folder.</span></span> <span data-ttu-id="fa87f-129">验证是否有\<GUID > 文件夹中的消息文件。</span><span class="sxs-lookup"><span data-stu-id="fa87f-129">Verify that there is a \<GUID>.msg file in the folder.</span></span> <span data-ttu-id="fa87f-130">在记事本中打开该文件，验证消息是一个 997 消息（带有 997 的 ST1）且具有 EDI 负载上的 AS2 标头。</span><span class="sxs-lookup"><span data-stu-id="fa87f-130">Open the file in Notepad, and verify that the message is a 997 message (with an ST1 of 997) with AS2 headers over an EDI payload.</span></span> <span data-ttu-id="fa87f-131">验证 AS2-From 是 Contoso，AS2-To 是 Fabrikam。</span><span class="sxs-lookup"><span data-stu-id="fa87f-131">Verify that AS2-From is Contoso and AS2-To is Fabrikam.</span></span> <span data-ttu-id="fa87f-132">验证 ISA6（发送方标识符）设置为 1234567 (Contoso) 且 ISA8（接收方标识符）设置为 7654321 (Fabrikam)。</span><span class="sxs-lookup"><span data-stu-id="fa87f-132">Verify that ISA6 (Sender identifier) is set to 1234567 (Contoso) and ISA8 (Receiver identifier) is set to 7654321 (Fabrikam).</span></span>  
  
7.  <span data-ttu-id="fa87f-133">若要查看的 EDI 和 AS2 状态报告，请转到**组中心数据库**页在 BizTalk Server 管理控制台中，滚动到该页的底部，单击一个状态报表链接。</span><span class="sxs-lookup"><span data-stu-id="fa87f-133">To see the AS2 and EDI status reports, go to the **Group Hub** page in the BizTalk Server Administration Console, scroll to the bottom of the page, and click one of the status report links.</span></span> <span data-ttu-id="fa87f-134">有关详细信息，请参阅[EDI 和 AS2 状态报告](../core/edi-and-as2-status-reporting.md)。</span><span class="sxs-lookup"><span data-stu-id="fa87f-134">For more information, see [EDI and AS2 Status Reporting](../core/edi-and-as2-status-reporting.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="fa87f-135">后续步骤</span><span class="sxs-lookup"><span data-stu-id="fa87f-135">Next Steps</span></span>  
 <span data-ttu-id="fa87f-136">你已完成 AS2 教程。</span><span class="sxs-lookup"><span data-stu-id="fa87f-136">You have completed the AS2 Tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa87f-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fa87f-137">See Also</span></span>  
 <span data-ttu-id="fa87f-138">[教程 3: AS2 教程](../core/tutorial-3-as2-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="fa87f-138">[Tutorial 3: AS2 Tutorial](../core/tutorial-3-as2-tutorial.md) </span></span>  
 [<span data-ttu-id="fa87f-139">步骤 1： 准备 AS2 教程</span><span class="sxs-lookup"><span data-stu-id="fa87f-139">Step 1: Prepare for the AS2 Tutorial</span></span>](../core/step-1-prepare-for-the-as2-tutorial.md)