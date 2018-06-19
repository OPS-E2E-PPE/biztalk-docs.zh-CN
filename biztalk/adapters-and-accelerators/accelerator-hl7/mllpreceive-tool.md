---
title: MllpReceive 工具 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MLLP-encoded messages, send adapters
- MllpReceive tool
- MLLP-encoded messages, MllpReceive tool
ms.assetid: 7069444b-1412-40bf-b567-fa86f76cd007
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e990c49a221653289619a33c30100accc3c68d6e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961507"
---
# <a name="mllpreceive-tool"></a><span data-ttu-id="61da1-102">MllpReceive 工具</span><span class="sxs-lookup"><span data-stu-id="61da1-102">MllpReceive Tool</span></span>
<span data-ttu-id="61da1-103">MllpReceive 工具可用于从 MLLP 发送端口接收数据。</span><span class="sxs-lookup"><span data-stu-id="61da1-103">You can use the MllpReceive tool to receive data from an MLLP send port.</span></span>  
  
 <span data-ttu-id="61da1-104">在安装此工具通过[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]自定义安装过程。</span><span class="sxs-lookup"><span data-stu-id="61da1-104">You install this tool through the [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Custom installation procedure.</span></span> <span data-ttu-id="61da1-105">如果执行典型的安装，以安装 BTAHL7，然后必须运行自定义安装，并按本教程中正常工作的顺序安装的测试工具。</span><span class="sxs-lookup"><span data-stu-id="61da1-105">If you performed a Typical installation to install BTAHL7, then you must run a Custom installation and install the test tools in order for this tutorial to work correctly.</span></span> <span data-ttu-id="61da1-106">在自定义安装屏幕中，选择**MLLP 测试工具**从**适配器**文件夹，并选择**测试实例**从**项目**文件夹。</span><span class="sxs-lookup"><span data-stu-id="61da1-106">At the Custom Setup screen, select **MLLP Test Tool** from the **Adapter** folder, and select **Test Instances** from the **Artifacts** folder.</span></span> <span data-ttu-id="61da1-107">有关详细信息，请参阅[执行自定义安装](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692)。</span><span class="sxs-lookup"><span data-stu-id="61da1-107">For more information, see [Performing a Custom Installation](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692).</span></span>  
  
 <span data-ttu-id="61da1-108">BTAHL7 安装程序将安装在此工具*\<驱动器\>*: files\microsoft BizTalk\<版本\>Accelerator for HL7\SDK\MLLP 实用程序。</span><span class="sxs-lookup"><span data-stu-id="61da1-108">BTAHL7 setup installs this tool in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\MLLP Utilities.</span></span>  
  
 <span data-ttu-id="61da1-109">使用此工具中的[端到端教程](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)、 [Interrogative 教程](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)、[批处理教程](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)，和[消息扩充教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="61da1-109">You use this tool in the [End-to-End Tutorial](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md), the [Interrogative Tutorial](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md), the [Batching Tutorial](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md), and the [Message Enrichment Tutorial](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md).</span></span> <span data-ttu-id="61da1-110">如果你安装[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]通过默认安装中，并且不安装和使用的 MLLPTest 工具 （包括 MllpReceive MllpSend），你将不能测试您的教程结果。</span><span class="sxs-lookup"><span data-stu-id="61da1-110">If you installed [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] through the default installation, and have not installed the MLLPTest tool (including MllpReceive and MllpSend), you will not be able to test your tutorial results.</span></span>  
  
## <a name="tool-usage"></a><span data-ttu-id="61da1-111">工具使用情况</span><span class="sxs-lookup"><span data-stu-id="61da1-111">Tool Usage</span></span>  
 <span data-ttu-id="61da1-112">下面演示使用来调用此命令行工具的语法：</span><span class="sxs-lookup"><span data-stu-id="61da1-112">The following shows the syntax you use to invoke this command-line tool:</span></span>  
  
```  
mllpreceive.exe [/?] [/I <IP>] [/P <PORT>] [/SPLIT] [/D <DIRECTORY>] [/STATICACK "ACKTEXT" | /HL7ACK <FILENAME>] /SB nn /EB nn /CR nn  
```  
  
 <span data-ttu-id="61da1-113">下表介绍每个部分的 MllpReceive 工具使用的语法。</span><span class="sxs-lookup"><span data-stu-id="61da1-113">The following table describes each part of the syntax the MllpReceive tool uses.</span></span>  
  
|<span data-ttu-id="61da1-114">语法</span><span class="sxs-lookup"><span data-stu-id="61da1-114">Syntax</span></span>|<span data-ttu-id="61da1-115">含义</span><span class="sxs-lookup"><span data-stu-id="61da1-115">Meaning</span></span>|  
|------------|-------------|  
|<span data-ttu-id="61da1-116">/?</span><span class="sxs-lookup"><span data-stu-id="61da1-116">/?</span></span>|<span data-ttu-id="61da1-117">显示此帮助。</span><span class="sxs-lookup"><span data-stu-id="61da1-117">Displays this help.</span></span>|  
|<span data-ttu-id="61da1-118">/I \<IP\></span><span class="sxs-lookup"><span data-stu-id="61da1-118">/I \<IP\></span></span>|<span data-ttu-id="61da1-119">表示要侦听的地址。</span><span class="sxs-lookup"><span data-stu-id="61da1-119">Denotes the address to listen to.</span></span> <span data-ttu-id="61da1-120">默认值为所有可用的 Ip。</span><span class="sxs-lookup"><span data-stu-id="61da1-120">The default is all available IPs.</span></span>|  
|<span data-ttu-id="61da1-121">/ P\<端口\></span><span class="sxs-lookup"><span data-stu-id="61da1-121">/P \<PORT\></span></span>|<span data-ttu-id="61da1-122">表示要侦听的端口号。</span><span class="sxs-lookup"><span data-stu-id="61da1-122">Denotes the port number to listen to.</span></span> <span data-ttu-id="61da1-123">默认值为 12000。</span><span class="sxs-lookup"><span data-stu-id="61da1-123">The default value is 12000.</span></span>|  
|<span data-ttu-id="61da1-124">/D\<目录\></span><span class="sxs-lookup"><span data-stu-id="61da1-124">/D \<DIRECTORY\></span></span>|<span data-ttu-id="61da1-125">将所有已收到的消息存储目录中\<目录\>。</span><span class="sxs-lookup"><span data-stu-id="61da1-125">Stores all received message(s) in the directory in \<DIRECTORY\>.</span></span> <span data-ttu-id="61da1-126">如果不指定\<目录\>，默认目录为 %TEMP%。</span><span class="sxs-lookup"><span data-stu-id="61da1-126">If you do not specify \<DIRECTORY\>, the default directory is %TEMP%.</span></span>|  
|<span data-ttu-id="61da1-127">/ 拆分</span><span class="sxs-lookup"><span data-stu-id="61da1-127">/SPLIT</span></span>|<span data-ttu-id="61da1-128">将接收到的数据拆分为单独的消息基于分隔符。</span><span class="sxs-lookup"><span data-stu-id="61da1-128">Splits the received data into separate messages based on the delimiters.</span></span> <span data-ttu-id="61da1-129">SB 和 EB 是必需的。</span><span class="sxs-lookup"><span data-stu-id="61da1-129">SB and EB are required.</span></span> <span data-ttu-id="61da1-130">CR 是可选的。</span><span class="sxs-lookup"><span data-stu-id="61da1-130">CR is optional.</span></span>|  
|<span data-ttu-id="61da1-131">/ STATICACK</span><span class="sxs-lookup"><span data-stu-id="61da1-131">/STATICACK</span></span>|<span data-ttu-id="61da1-132">静态确认返回到发件人。</span><span class="sxs-lookup"><span data-stu-id="61da1-132">The static acknowledgment returned to the sender.</span></span> <span data-ttu-id="61da1-133">将强制执行拆分模式。</span><span class="sxs-lookup"><span data-stu-id="61da1-133">Will enforce SPLIT mode.</span></span>|  
|<span data-ttu-id="61da1-134">/ HL7ACK</span><span class="sxs-lookup"><span data-stu-id="61da1-134">/HL7ACK</span></span>|<span data-ttu-id="61da1-135">HL7 确认返回到发件人。</span><span class="sxs-lookup"><span data-stu-id="61da1-135">The HL7 acknowledgment returned to the sender.</span></span> <span data-ttu-id="61da1-136">FILENAME 表示包含 HL7 确认的文件的名称</span><span class="sxs-lookup"><span data-stu-id="61da1-136">FILENAME denotes the name of the file containing the HL7 ACK.</span></span> <span data-ttu-id="61da1-137">将强制执行拆分模式。</span><span class="sxs-lookup"><span data-stu-id="61da1-137">Will enforce SPLIT mode.</span></span>|  
|<span data-ttu-id="61da1-138">/SB</span><span class="sxs-lookup"><span data-stu-id="61da1-138">/SB</span></span>|<span data-ttu-id="61da1-139">设置启动块分隔符字节的 ASCII 值。</span><span class="sxs-lookup"><span data-stu-id="61da1-139">Sets the ASCII value of Start Block Delimiter Byte.</span></span> <span data-ttu-id="61da1-140">默认值为 none。</span><span class="sxs-lookup"><span data-stu-id="61da1-140">The default is none.</span></span>|  
|<span data-ttu-id="61da1-141">/EB</span><span class="sxs-lookup"><span data-stu-id="61da1-141">/EB</span></span>|<span data-ttu-id="61da1-142">设置结束块分隔符字节的 ASCII 值。</span><span class="sxs-lookup"><span data-stu-id="61da1-142">Sets the ASCII value of End Block Delimiter Byte.</span></span> <span data-ttu-id="61da1-143">默认值为 none。</span><span class="sxs-lookup"><span data-stu-id="61da1-143">The default is none.</span></span>|  
|<span data-ttu-id="61da1-144">/CR</span><span class="sxs-lookup"><span data-stu-id="61da1-144">/CR</span></span>|<span data-ttu-id="61da1-145">设置回车符返回分隔符字节的 ASCII 值。</span><span class="sxs-lookup"><span data-stu-id="61da1-145">Sets the ASCII value of Carriage Return Delimiter Byte.</span></span> <span data-ttu-id="61da1-146">默认值为 none。</span><span class="sxs-lookup"><span data-stu-id="61da1-146">The default is none.</span></span>|  
  
## <a name="example-of-tool-use"></a><span data-ttu-id="61da1-147">工具使用的示例</span><span class="sxs-lookup"><span data-stu-id="61da1-147">Example of Tool Use</span></span>  
 <span data-ttu-id="61da1-148">你可以使用以下命令来侦听端口 10000 上 localhost，并将保存消息以便分离 C:\TEMP 上的文件：</span><span class="sxs-lookup"><span data-stu-id="61da1-148">You can use the following command to listen to port 10000 on localhost, and save messages to separate files on C:\TEMP:</span></span>  
  
```  
mllpreceive.exe /P 10000 /SPLIT /SB 11 /EB 28 /CR 13 /D C:\TEMP  
```  
  
## <a name="see-also"></a><span data-ttu-id="61da1-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61da1-149">See Also</span></span>  
 [<span data-ttu-id="61da1-150">实用工具</span><span class="sxs-lookup"><span data-stu-id="61da1-150">Utilities</span></span>](../../adapters-and-accelerators/accelerator-hl7/utilities2.md)