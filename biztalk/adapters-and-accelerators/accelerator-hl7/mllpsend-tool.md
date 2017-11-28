---
title: "MllpSend 工具 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MllpSend tool
- MLLP-encoded messages, receive adapters
- MLLP-encoded messages, MllpSend tool
ms.assetid: b1723d52-4909-4543-8215-4f73802b6c4f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a15da306f61cb4297d9ba8cdc036035310474d8e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="mllpsend-tool"></a><span data-ttu-id="074b4-102">MllpSend 工具</span><span class="sxs-lookup"><span data-stu-id="074b4-102">MllpSend Tool</span></span>
<span data-ttu-id="074b4-103">MllpSend 工具可用于发送数据到 MLLP 接收位置。</span><span class="sxs-lookup"><span data-stu-id="074b4-103">You can use the MllpSend tool to send data to an MLLP receive location.</span></span>  
  
 <span data-ttu-id="074b4-104">在安装此工具通过[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]自定义安装过程。</span><span class="sxs-lookup"><span data-stu-id="074b4-104">You install this tool through the [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Custom installation procedure.</span></span> <span data-ttu-id="074b4-105">如果执行典型的安装，以安装 BTAHL7，然后必须运行自定义安装，并按本教程中正常工作的顺序安装的测试工具。</span><span class="sxs-lookup"><span data-stu-id="074b4-105">If you performed a Typical installation to install BTAHL7, then you must run a Custom installation and install the test tools in order for this tutorial to work correctly.</span></span> <span data-ttu-id="074b4-106">在自定义安装屏幕中，选择**MLLP 测试工具**从**适配器**文件夹，并选择**测试实例**从**项目**文件夹。</span><span class="sxs-lookup"><span data-stu-id="074b4-106">At the Custom Setup screen, select **MLLP Test Tool** from the **Adapter** folder, and select **Test Instances** from the **Artifacts** folder.</span></span> <span data-ttu-id="074b4-107">有关详细信息，请参阅[执行自定义安装](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692)。</span><span class="sxs-lookup"><span data-stu-id="074b4-107">For more information, see [Performing a Custom Installation](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692).</span></span>  
  
 <span data-ttu-id="074b4-108">BTAHL7 安装程序将安装在此工具*\<驱动器 >*: files\microsoft BizTalk\<版本 > Accelerator for HL7\SDK\MLLP 实用程序。</span><span class="sxs-lookup"><span data-stu-id="074b4-108">BTAHL7 setup installs this tool in *\<drive>*:\Program Files\Microsoft BizTalk \<version> Accelerator for HL7\SDK\MLLP Utilities.</span></span>  
  
 <span data-ttu-id="074b4-109">使用此工具中的[端到端教程](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)、 [Interrogative 教程](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)、[批处理教程](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)，和[消息扩充教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="074b4-109">You use this tool in the [End-to-End Tutorial](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md), the [Interrogative Tutorial](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md), the [Batching Tutorial](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md), and the [Message Enrichment Tutorial](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md).</span></span> <span data-ttu-id="074b4-110">如果你安装[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]通过默认安装中，且不安装你将不能测试您的教程结果 MLLP Testtools （包括 MllpSend 和 MllpReceive）。</span><span class="sxs-lookup"><span data-stu-id="074b4-110">If you installed [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] through the default installation, and have not installed the MLLP Testtools (including MllpSend and MllpReceive), you will not be able to test your tutorial results.</span></span>  
  
## <a name="tool-usage"></a><span data-ttu-id="074b4-111">工具使用情况</span><span class="sxs-lookup"><span data-stu-id="074b4-111">Tool Usage</span></span>  
 <span data-ttu-id="074b4-112">下面演示使用来调用此命令行工具的语法：</span><span class="sxs-lookup"><span data-stu-id="074b4-112">The following shows the syntax you use to invoke this command-line tool:</span></span>  
  
```  
mllpsend.exe [/?] [/I <IP>] [/P <PORT>] [/TWOWAY] [/REPEAT <n>] [/F <FILENAME> | "TEXT"] /SB nn /EB nn /CR nn  
```  
  
 <span data-ttu-id="074b4-113">下表介绍每个部分的 MllpSend 工具使用的语法。</span><span class="sxs-lookup"><span data-stu-id="074b4-113">The following table describes each part of the syntax the MllpSend tool uses.</span></span>  
  
|<span data-ttu-id="074b4-114">语法</span><span class="sxs-lookup"><span data-stu-id="074b4-114">Syntax</span></span>|<span data-ttu-id="074b4-115">Description</span><span class="sxs-lookup"><span data-stu-id="074b4-115">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="074b4-116">**/?**</span><span class="sxs-lookup"><span data-stu-id="074b4-116">**/?**</span></span>|<span data-ttu-id="074b4-117">在命令提示符窗口中显示帮助。</span><span class="sxs-lookup"><span data-stu-id="074b4-117">Displays Help in the Command Prompt window.</span></span>|  
|<span data-ttu-id="074b4-118">**/I \<IP >**</span><span class="sxs-lookup"><span data-stu-id="074b4-118">**/I \<IP>**</span></span>|<span data-ttu-id="074b4-119">表示要将发送到的地址。</span><span class="sxs-lookup"><span data-stu-id="074b4-119">Denotes the address to send to.</span></span> <span data-ttu-id="074b4-120">默认值为 localhost。</span><span class="sxs-lookup"><span data-stu-id="074b4-120">The default value is localhost.</span></span>|  
|<span data-ttu-id="074b4-121">**/ P\<端口 >**</span><span class="sxs-lookup"><span data-stu-id="074b4-121">**/P \<PORT>**</span></span>|<span data-ttu-id="074b4-122">表示要将发送到的端口号。</span><span class="sxs-lookup"><span data-stu-id="074b4-122">Denotes the port number to send to.</span></span> <span data-ttu-id="074b4-123">默认值是**11000**。</span><span class="sxs-lookup"><span data-stu-id="074b4-123">The default value is **11000**.</span></span>|  
|<span data-ttu-id="074b4-124">**/F**</span><span class="sxs-lookup"><span data-stu-id="074b4-124">**/F**</span></span>|<span data-ttu-id="074b4-125">将发送文件 FILENAME 的内容。</span><span class="sxs-lookup"><span data-stu-id="074b4-125">Sends content of the file FILENAME.</span></span>|  
|<span data-ttu-id="074b4-126">**/ 重复\<n>**</span><span class="sxs-lookup"><span data-stu-id="074b4-126">**/REPEAT \<n>**</span></span>|<span data-ttu-id="074b4-127">将发送同一消息 *n* 时间。</span><span class="sxs-lookup"><span data-stu-id="074b4-127">Sends the same message *n* times.</span></span> <span data-ttu-id="074b4-128">包装字符将应用到每条消息。</span><span class="sxs-lookup"><span data-stu-id="074b4-128">The wrapper characters will be applied to each message.</span></span>|  
|<span data-ttu-id="074b4-129">**/ 双向**</span><span class="sxs-lookup"><span data-stu-id="074b4-129">**/TWOWAY**</span></span>|<span data-ttu-id="074b4-130">发件人将等待来自接收方的响应。</span><span class="sxs-lookup"><span data-stu-id="074b4-130">The sender will wait for a response from the receiver.</span></span> <span data-ttu-id="074b4-131">SB 和 EB 需要指定。</span><span class="sxs-lookup"><span data-stu-id="074b4-131">SB and EB need to be specified.</span></span> <span data-ttu-id="074b4-132">CR 是可选的。</span><span class="sxs-lookup"><span data-stu-id="074b4-132">CR is optional.</span></span> <span data-ttu-id="074b4-133">在文件模式下，响应存储在文件的文件。响应。</span><span class="sxs-lookup"><span data-stu-id="074b4-133">In File mode, the response is stored in the file FILE.RESPONSE.</span></span>|  
|<span data-ttu-id="074b4-134">**/SB**</span><span class="sxs-lookup"><span data-stu-id="074b4-134">**/SB**</span></span>|<span data-ttu-id="074b4-135">设置启动块分隔符字节的 ASCII 值。</span><span class="sxs-lookup"><span data-stu-id="074b4-135">Sets the ASCII value of the Start Block Delimiter Byte.</span></span> <span data-ttu-id="074b4-136">默认值为 none。</span><span class="sxs-lookup"><span data-stu-id="074b4-136">The default is none.</span></span>|  
|<span data-ttu-id="074b4-137">**/EB**</span><span class="sxs-lookup"><span data-stu-id="074b4-137">**/EB**</span></span>|<span data-ttu-id="074b4-138">设置结束块分隔符字节的 ASCII 值。</span><span class="sxs-lookup"><span data-stu-id="074b4-138">Sets the ASCII value of the End Block Delimiter Byte.</span></span> <span data-ttu-id="074b4-139">默认值为 none。</span><span class="sxs-lookup"><span data-stu-id="074b4-139">The default is none.</span></span>|  
|<span data-ttu-id="074b4-140">**/CR**</span><span class="sxs-lookup"><span data-stu-id="074b4-140">**/CR**</span></span>|<span data-ttu-id="074b4-141">设置回车符返回分隔符字节的 ASCII 值。</span><span class="sxs-lookup"><span data-stu-id="074b4-141">Sets the ASCII value of the Carriage Return Delimiter Byte.</span></span> <span data-ttu-id="074b4-142">默认值为 none。</span><span class="sxs-lookup"><span data-stu-id="074b4-142">The default is none.</span></span>|  
  
## <a name="examples-of-tool-use"></a><span data-ttu-id="074b4-143">工具使用的示例</span><span class="sxs-lookup"><span data-stu-id="074b4-143">Examples of Tool Use</span></span>  
 <span data-ttu-id="074b4-144">下面的示例演示如何使用 MllpSend 工具。</span><span class="sxs-lookup"><span data-stu-id="074b4-144">The following examples demonstrate how you can use the MllpSend tool.</span></span>  
  
 <span data-ttu-id="074b4-145">**示例 1。**</span><span class="sxs-lookup"><span data-stu-id="074b4-145">**Example 1.**</span></span> <span data-ttu-id="074b4-146">以下命令可用于将消息发送到单向适配器侦听端口 13000 服务器"myserver"上。</span><span class="sxs-lookup"><span data-stu-id="074b4-146">You can use the following command to send a message to a one-way adapter listening on port 13000 on server "myserver".</span></span> <span data-ttu-id="074b4-147">包装字符的 ASCII 值是 SB 11、 EB 28 和 CR 13。</span><span class="sxs-lookup"><span data-stu-id="074b4-147">The ASCII values of the wrapper characters are SB 11, EB 28, and CR 13.</span></span>  
  
```  
mllpsend.exe /I myserver /P 13000 /SB 11 /EB 28 /CR 13 "A short message"  
```  
  
 <span data-ttu-id="074b4-148">**示例 2。**</span><span class="sxs-lookup"><span data-stu-id="074b4-148">**Example 2.**</span></span> <span data-ttu-id="074b4-149">可以使用以下命令以向侦听端口 11000 服务器"localhost"上的双向适配器 100 次发送消息。</span><span class="sxs-lookup"><span data-stu-id="074b4-149">You can use the following command to send a message 100 times to a two-way adapter listening on port 11000 on server "localhost".</span></span> <span data-ttu-id="074b4-150">包装字符的 ASCII 值是 SB 11、 EB 28 和 CR 13。</span><span class="sxs-lookup"><span data-stu-id="074b4-150">The ASCII values of the wrapper characters are SB 11, EB 28, and CR 13.</span></span>  
  
```  
mllpsend.exe /SB 11 /EB 28 /CR 13 /TWOWAY /REPEAT 100 "A short message"  
```  
  
## <a name="see-also"></a><span data-ttu-id="074b4-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="074b4-151">See Also</span></span>  
 [<span data-ttu-id="074b4-152">实用程序</span><span class="sxs-lookup"><span data-stu-id="074b4-152">Utilities</span></span>](../../adapters-and-accelerators/accelerator-hl7/utilities2.md)