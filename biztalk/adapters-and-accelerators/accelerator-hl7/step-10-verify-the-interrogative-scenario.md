---
title: "步骤 10： 验证 Interrogative 方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: interrogative tutorial, verifying solution
ms.assetid: 1f28800b-4a1d-4f29-8123-5cdea4b4a365
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b932ab2f179faab1381609c007dcdd148f200f7e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="step-10-verify-the-interrogative-scenario"></a><span data-ttu-id="047cb-102">步骤 10： 验证 Interrogative 方案</span><span class="sxs-lookup"><span data-stu-id="047cb-102">Step 10: Verify the Interrogative Scenario</span></span>
<span data-ttu-id="047cb-103">在此步骤中，你可以出于本教程验证端到端方案。</span><span class="sxs-lookup"><span data-stu-id="047cb-103">In this step, you verify the end-to-end scenario for this tutorial.</span></span>  
  
### <a name="to-send-the-query-message"></a><span data-ttu-id="047cb-104">若要发送查询邮件</span><span class="sxs-lookup"><span data-stu-id="047cb-104">To send the query message</span></span>  
  
1.  <span data-ttu-id="047cb-105">打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="047cb-105">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="047cb-106">在命令提示符下，将移到  **\<*驱动器*\>: files\microsoft BizTalk\<版本\>快捷键的 HL7\SDK\MLLP 实用程序 **.</span><span class="sxs-lookup"><span data-stu-id="047cb-106">In the command prompt, move to **\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\MLLP Utilities**.</span></span>  
  
3.  <span data-ttu-id="047cb-107">在命令提示符下键入**MllpReceive/P 24000**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="047cb-107">In the command prompt, type **MllpReceive /P 24000**, and then press **Enter**.</span></span> <span data-ttu-id="047cb-108">这运行侦听端口 24000 MLLP 侦听器应用程序，并显示到屏幕接收任何消息。</span><span class="sxs-lookup"><span data-stu-id="047cb-108">This runs the MLLP listener application listening to port 24000 and displays any messages received to the screen.</span></span> <span data-ttu-id="047cb-109">此应用程序模拟医院信息系统。</span><span class="sxs-lookup"><span data-stu-id="047cb-109">This application is simulating the Hospital Information System.</span></span>  
  
4.  <span data-ttu-id="047cb-110">打开其他的命令提示符。</span><span class="sxs-lookup"><span data-stu-id="047cb-110">Open an additional command prompt.</span></span>  
  
5.  <span data-ttu-id="047cb-111">在第二个命令提示符窗口中，将移到  **\<*驱动器*\>: files\microsoft BizTalk\<版本\>HL7\SDK\ 快捷键MLLP 实用工具 * *。</span><span class="sxs-lookup"><span data-stu-id="047cb-111">In the second Command Prompt window, move to **\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\MLLP Utilities**.</span></span>  
  
6.  <span data-ttu-id="047cb-112">在第二个命令提示符处，键入 **MllpSend /SB 11 /EB 28 /CR 13/双向/P 22000 /F"\<*驱动器*\>: files\microsoft BizTalk\<版本\>快捷键 HL7\SDK\Interrogative Tutorial\QRY^Q01.txt**，然后按**enter 键。**</span><span class="sxs-lookup"><span data-stu-id="047cb-112">In the second command prompt, type **MllpSend /SB 11 /EB 28 /CR 13 /TWOWAY /P 22000 /F "\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\Interrogative Tutorial\QRY^Q01.txt**, and then press **Enter.**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="047cb-113">此命令将发送到 MLLP 端口 22000 并等待响应 （确认） 本教程开头创建查询电子邮件。</span><span class="sxs-lookup"><span data-stu-id="047cb-113">This command sends the query message you created at the beginning of this tutorial to MLLP port 22000 and waits for a response (acknowledgment).</span></span> <span data-ttu-id="047cb-114">ADT 接收端口选取此消息并处理它。</span><span class="sxs-lookup"><span data-stu-id="047cb-114">The ADT receive port picks up this message and processes it.</span></span>  
  
7.  <span data-ttu-id="047cb-115">请验证您具有以下结果：</span><span class="sxs-lookup"><span data-stu-id="047cb-115">Verify that you have the following results:</span></span>  
  
    -   <span data-ttu-id="047cb-116">MLLP 侦听器应用程序应显示一条消息具有以下值：</span><span class="sxs-lookup"><span data-stu-id="047cb-116">The MLLP listener application should display a message with the following values:</span></span>  
  
        ```  
        MSH|^~\&|ADT||HIS||19990303||QRY^Q01|MSG00001|P|2.4  
        QRD|200307231012|D|I|4387|||20^LI|12233|RES|ALL  
        ```  
  
    -   <span data-ttu-id="047cb-117">此外，MllpSend 实用工具可用于创建中的确认文件\<*驱动器*\>: files\microsoft BizTalk\<版本\>HL7\SDK\ 快捷键名为 QRY^Q01.txt.RESPONSE interrogative 教程文件夹。</span><span class="sxs-lookup"><span data-stu-id="047cb-117">In addition, the MllpSend utility creates an acknowledgment file in the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\Interrogative Tutorial folder named QRY^Q01.txt.RESPONSE.</span></span> <span data-ttu-id="047cb-118">此文件包含以下信息作为该确认：</span><span class="sxs-lookup"><span data-stu-id="047cb-118">This file contains the following information as the acknowledgment:</span></span>  
  
        ```  
        MSH|^~\&|HIS||ADT||20040331154031.2222-0800||ACK^Q01^ACK|10000GSM|P|2.4  
        MSA|CA|MSG00001  
        ****END ACK****  
        ```  
  
### <a name="to-send-the-response-message"></a><span data-ttu-id="047cb-119">若要发送响应消息</span><span class="sxs-lookup"><span data-stu-id="047cb-119">To send the response message</span></span>  
  
1.  <span data-ttu-id="047cb-120">在命令提示符下运行 MllpReceive 应用程序后，按**CTRL-C**取消以前的操作。</span><span class="sxs-lookup"><span data-stu-id="047cb-120">In the command prompt running the MllpReceive application, press **Ctrl-C** to cancel the previous operation.</span></span>  
  
2.  <span data-ttu-id="047cb-121">在命令提示符处，键入**MllpReceive/P 25000**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="047cb-121">At the command prompt, type **MllpReceive /P 25000**, and then press **Enter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="047cb-122">步骤 2 运行侦听端口 25000 MLLP 侦听器应用程序，并显示到屏幕收到任何消息。</span><span class="sxs-lookup"><span data-stu-id="047cb-122">Step 2 runs the MLLP listener application listening to port 25000 and displays any messages received to the screen.</span></span> <span data-ttu-id="047cb-123">此应用程序模拟 ADT 系统。</span><span class="sxs-lookup"><span data-stu-id="047cb-123">This application is simulating the ADT system.</span></span>  
  
3.  <span data-ttu-id="047cb-124">在第二个命令提示符处，键入 **MllpSend /SB 11 /EB 28 /CR 13/P 23000 /F"\<*驱动器*\>: files\microsoft BizTalk\<版本\>Accelerator for HL7\SDK\Interrogative Tutorial\DSR.txt"**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="047cb-124">In the second command prompt, type **MllpSend /SB 11 /EB 28 /CR 13 /P 23000 /F "\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\Interrogative Tutorial\DSR.txt"**, then press **Enter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="047cb-125">步骤 3 将发送到 MLLP 端口 23000 本教程开头创建响应消息。</span><span class="sxs-lookup"><span data-stu-id="047cb-125">Step 3 sends the response message you created at the beginning of this tutorial to MLLP port 23000.</span></span> <span data-ttu-id="047cb-126">HIS 接收端口选取此消息并处理它。</span><span class="sxs-lookup"><span data-stu-id="047cb-126">The HIS receive port picks up this message and processes it.</span></span>  
  
4.  <span data-ttu-id="047cb-127">请验证您具有以下结果：</span><span class="sxs-lookup"><span data-stu-id="047cb-127">Verify that you have the following results:</span></span>  
  
    -   <span data-ttu-id="047cb-128">MLLP 侦听器应用程序应显示一条消息具有以下值：</span><span class="sxs-lookup"><span data-stu-id="047cb-128">The MLLP listener application should display a message with the following values:</span></span>  
  
        ```  
        MSH|^~\&|HIS||ADT||19990505||DSR^Q01|ZXT23469|P|2.4  
        MSA|AA|MSG00003  
        QRD|200307231012|D|I|4387|||20^LI|12233|RES|ALL  
        DSP|||RESULTS FOR PATIENT#12233 SMITH, JOHN H. 07/23/03  
        DSP|||SPECIMEN#H85 COLLECTED 07/22/03 /07/0/0  
        DSP|||ELECTROLYTES  
        DSP||| SODIUM 136 [135-148] MEQ/L STAT  
        DSP||| POTASSIUM 4.2 [3.5-5.0] MEQ/L STAT  
        DSP||| CHLORIDE 91 [95-111] MEQ/L STAT  
        DSP||| CO2 25 [20-30] MEQ/L STAT  
        DSP|||CO2 25 [20-30] MEQ/L STAT|LB  
        ```  
  
    > [!NOTE]
    >  <span data-ttu-id="047cb-129">如果未正确出现上述消息，使用运行状况和活动跟踪 (HAT) 工具解决此错误。</span><span class="sxs-lookup"><span data-stu-id="047cb-129">If the messages above do not appear correctly, use the Health and Activity Tracking (HAT) tool to troubleshoot the error.</span></span>  
  
 <span data-ttu-id="047cb-130">恭喜！</span><span class="sxs-lookup"><span data-stu-id="047cb-130">Congratulations!</span></span> <span data-ttu-id="047cb-131">你已成功完成 BTAHL7 Interrogative 教程。</span><span class="sxs-lookup"><span data-stu-id="047cb-131">You have successfully completed the BTAHL7 Interrogative Tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="047cb-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="047cb-132">See Also</span></span>  
 <span data-ttu-id="047cb-133">[批处理教程](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="047cb-133">[Batching Tutorial](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md) </span></span>  
 <span data-ttu-id="047cb-134">[端到端教程](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md) </span><span class="sxs-lookup"><span data-stu-id="047cb-134">[End-to-End Tutorial](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md) </span></span>  
 [<span data-ttu-id="047cb-135">消息充实教程</span><span class="sxs-lookup"><span data-stu-id="047cb-135">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)