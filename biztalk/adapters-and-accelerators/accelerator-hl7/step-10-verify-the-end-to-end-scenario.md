---
title: "步骤 10： 验证端到端方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: end-to-end tutorial, verifying solution
ms.assetid: 24b74ba6-e303-4ab1-8a93-25a430e4894d
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d38f137625554bd689477964e3a969142eca0658
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="step-10-verify-the-end-to-end-scenario"></a><span data-ttu-id="3b872-102">步骤 10： 验证端到端方案</span><span class="sxs-lookup"><span data-stu-id="3b872-102">Step 10: Verify the End-to-End Scenario</span></span>
<span data-ttu-id="3b872-103">在此步骤中，你可以出于本教程验证端到端方案。</span><span class="sxs-lookup"><span data-stu-id="3b872-103">In this step, you verify the end-to-end scenario for this tutorial.</span></span>  
  
### <a name="to-verify-the-end-to-end-tutorial-scenario"></a><span data-ttu-id="3b872-104">若要验证的端到端教程方案</span><span class="sxs-lookup"><span data-stu-id="3b872-104">To verify the end-to-end tutorial scenario</span></span>  
  
1.  <span data-ttu-id="3b872-105">单击**启动**，指向**程序**，指向**附件**，然后单击**命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="3b872-105">Click **Start**, point to **Programs**, point to **Accessories**, and then click **Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="3b872-106">在命令提示符窗口中，将移到  **\<*驱动器*\>: files\microsoft BizTalk\<版本\>HL7\SDK\MLLP 快捷键实用工具 * *，，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="3b872-106">In the Command Prompt window, move to **\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\MLLP Utilities**, and then press **Enter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3b872-107">如果找不到 SDK 文件夹下的 MLLP Utilities 文件夹，可能未安装 MLLP 测试工具。</span><span class="sxs-lookup"><span data-stu-id="3b872-107">If you cannot find an MLLP Utilities folder under the SDK folder, the MLLP test tools may not be installed.</span></span> <span data-ttu-id="3b872-108">打开控制面板，然后打开**添加或删除程序**。</span><span class="sxs-lookup"><span data-stu-id="3b872-108">Open the Control Panel, and then open **Add or Remove Programs**.</span></span> <span data-ttu-id="3b872-109">选择**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后选择**更改**。</span><span class="sxs-lookup"><span data-stu-id="3b872-109">Select **Microsoft BizTalk \<version\> Accelerator for HL7**, and then select **Change**.</span></span> <span data-ttu-id="3b872-110">在 BTAHL7 安装向导中，选择**修改**。</span><span class="sxs-lookup"><span data-stu-id="3b872-110">In the BTAHL7 setup wizard, select **Modify**.</span></span> <span data-ttu-id="3b872-111">展开**适配器**文件夹以查看是否**MLLP 测试工具**已安装。</span><span class="sxs-lookup"><span data-stu-id="3b872-111">Expand the **Adapter** folder to see whether the **MLLP Test Tool** has been installed.</span></span> <span data-ttu-id="3b872-112">如果没有，请安装它。</span><span class="sxs-lookup"><span data-stu-id="3b872-112">If not, install it.</span></span>  
  
3.  <span data-ttu-id="3b872-113">在命令提示符窗口中，键入**mllpreceive/p 14000**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="3b872-113">In the Command Prompt window, type **mllpreceive /p 14000**, and then press **Enter**.</span></span> <span data-ttu-id="3b872-114">这运行 MLLP 侦听器应用程序侦听端口 14000 并指定 MLLP 消息中，默认 EB、 SB 和 CR 字符，并显示到屏幕接收任何消息。</span><span class="sxs-lookup"><span data-stu-id="3b872-114">This runs the MLLP listener application listening to port 14000 and specifying the default EB, SB, and CR characters of the MLLP message, and displays any messages received to the screen.</span></span>  
  
4.  <span data-ttu-id="3b872-115">通过单击启动其他的命令提示符**启动**，指向**程序**，指向**附件**，然后单击**命令提示符**.</span><span class="sxs-lookup"><span data-stu-id="3b872-115">Start an additional command prompt by clicking **Start**, point to **Programs**, point to **Accessories**, and then click **Command Prompt**.</span></span>  
  
5.  <span data-ttu-id="3b872-116">在第二个命令提示符窗口中，将移到  **\<*驱动器*\>: files\microsoft BizTalk\<版本\>HL7\SDK\ 快捷键MLLP 实用工具 * *，，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="3b872-116">In the second Command Prompt window, move to **\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\MLLP Utilities**, and then press **Enter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3b872-117">以下步骤将消息发送。</span><span class="sxs-lookup"><span data-stu-id="3b872-117">The following step sends the message.</span></span>  
  
6.  <span data-ttu-id="3b872-118">在命令提示符窗口中，键入 **mllpsend /SB 11 /EB 28 /CR 13 /f"\<*驱动器*\>: files\microsoft BizTalk\<版本\>Accelerator for HL7\SDK\End 端到端 Tutorial\ADT^A03.txt"**，其中\<*驱动器*\>是你安装驱动器号。</span><span class="sxs-lookup"><span data-stu-id="3b872-118">In the Command Prompt window, type **mllpsend /SB 11 /EB 28 /CR 13 /f "\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\ADT^A03.txt"**, where \<*drive*\> is your installation drive letter.</span></span> <span data-ttu-id="3b872-119">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="3b872-119">Press **Enter**.</span></span>  
  
7.  <span data-ttu-id="3b872-120">请验证您具有以下结果：</span><span class="sxs-lookup"><span data-stu-id="3b872-120">Verify that you have the following results:</span></span>  
  
    -   <span data-ttu-id="3b872-121">MLLP 侦听器应用程序应显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="3b872-121">The MLLP listener application should display a message.</span></span> <span data-ttu-id="3b872-122">消息的第一行应具有以下值：</span><span class="sxs-lookup"><span data-stu-id="3b872-122">The first line of the message should have the following values:</span></span>  
  
        ```  
        MSH|^~\&|BTAHL7^IE^UUID|MCM|HI^System^GUID||199601121005||ADT^A04|000001|P|2.4|||SU|NE  
        ```  
  
    -   <span data-ttu-id="3b872-123">消息将出现在\<*驱动器*\>: files\microsoft BizTalk\<版本\>HL7\SDK\End 端到端 Tutorial\Tutorial_sendMsg_RX 快捷键。</span><span class="sxs-lookup"><span data-stu-id="3b872-123">A message appears in \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_sendMsg_RX.</span></span> <span data-ttu-id="3b872-124">此消息应显示 MLLP 侦听器应用程序的消息相同。</span><span class="sxs-lookup"><span data-stu-id="3b872-124">This message should be the same as the message shown by the MLLP listener application.</span></span> <span data-ttu-id="3b872-125">验证消息的第一行，如下所示具有相同的消息值。</span><span class="sxs-lookup"><span data-stu-id="3b872-125">Verify that the first line of the message has the same message values as follows.</span></span> <span data-ttu-id="3b872-126">请注意 MSH3 和 MSH5 下面的代码中的值与你为 Tutorial_RXSystem 指定的值匹配：</span><span class="sxs-lookup"><span data-stu-id="3b872-126">Note that the values for MSH3 a nd MSH5 in the following code match the values you specified for the Tutorial_RXSystem:</span></span>  
  
        ```  
        MSH|^~\&|BTAHL7|MCM|Tutorial_RXSystem||199601121005||ADT^A03|000001|P|2.3.1  
        ```  
  
    -   <span data-ttu-id="3b872-127">两个消息将显示在\<*驱动器*\>: files\microsoft BizTalk\<版本\>HL7\SDK\End 端到端 Tutorial\Tutorial_sendAck_ADT 快捷键。</span><span class="sxs-lookup"><span data-stu-id="3b872-127">Two messages appear in \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_sendAck_ADT.</span></span> <span data-ttu-id="3b872-128">这些消息之一是应用程序确认;另一种是一个提交确认。</span><span class="sxs-lookup"><span data-stu-id="3b872-128">One of these messages is an application acknowledgment; the other is a commit acknowledgment.</span></span> <span data-ttu-id="3b872-129">该应用程序确认应具有以下内容：</span><span class="sxs-lookup"><span data-stu-id="3b872-129">The application acknowledgment should have the following content:</span></span>  
  
        ```  
        MSH|^~\&|BTAHL7InterfaceEngine||Tutorial_ADTSystem|MCM|<datetime>||ACK^A03^ACK|000001|P|2.3.1|||AL  
        MSA|AA|000001  
        ```  
  
    -   <span data-ttu-id="3b872-130">提交确认应具有以下内容：</span><span class="sxs-lookup"><span data-stu-id="3b872-130">The commit acknowledgment should have the following content:</span></span>  
  
        ```  
        MSH|^~\&|BTAHL7InterfaceEngine||Tutorial_ADTSystem|MCM|<datetime>||ACK^A03^ACK|100000|P|2.3.1  
        MSA|CA|000001  
        ```  
  
    > [!NOTE]
    >  <span data-ttu-id="3b872-131">如果未正确显示消息，使用运行状况和活动跟踪 (HAT) 工具解决此错误。</span><span class="sxs-lookup"><span data-stu-id="3b872-131">If the messages do not appear correctly, use the Health and Activity Tracking (HAT) tool to troubleshoot the error.</span></span>  
  
 <span data-ttu-id="3b872-132">恭喜！</span><span class="sxs-lookup"><span data-stu-id="3b872-132">Congratulations!</span></span> <span data-ttu-id="3b872-133">你已成功完成 BTAHL7 端到端教程。</span><span class="sxs-lookup"><span data-stu-id="3b872-133">You have successfully completed the BTAHL7 End-to-End Tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b872-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b872-134">See Also</span></span>  
 [<span data-ttu-id="3b872-135">端到端教程</span><span class="sxs-lookup"><span data-stu-id="3b872-135">End-to-End Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)