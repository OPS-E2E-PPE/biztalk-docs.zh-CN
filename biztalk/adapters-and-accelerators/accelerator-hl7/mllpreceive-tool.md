---
title: MllpReceive 工具 |Microsoft Docs
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
ms.openlocfilehash: 4e2684ef0d2ae7ee678e11f7b03541499b5f4c7d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65290298"
---
# <a name="mllpreceive-tool"></a><span data-ttu-id="78b17-102">MllpReceive 工具</span><span class="sxs-lookup"><span data-stu-id="78b17-102">MllpReceive Tool</span></span>
<span data-ttu-id="78b17-103">MllpReceive 工具可用于从 MLLP 发送端口接收数据。</span><span class="sxs-lookup"><span data-stu-id="78b17-103">You can use the MllpReceive tool to receive data from an MLLP send port.</span></span>  
  
 <span data-ttu-id="78b17-104">安装此工具通过[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]自定义安装过程。</span><span class="sxs-lookup"><span data-stu-id="78b17-104">You install this tool through the [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Custom installation procedure.</span></span> <span data-ttu-id="78b17-105">如果您执行典型安装中安装 BTAHL7，然后必须运行自定义安装，并按本教程中正常工作的顺序安装测试工具。</span><span class="sxs-lookup"><span data-stu-id="78b17-105">If you performed a Typical installation to install BTAHL7, then you must run a Custom installation and install the test tools in order for this tutorial to work correctly.</span></span> <span data-ttu-id="78b17-106">在自定义设置屏幕中，选择**MLLP 测试工具**从**适配器**文件夹，然后选择**测试实例**从**项目**文件夹。</span><span class="sxs-lookup"><span data-stu-id="78b17-106">At the Custom Setup screen, select **MLLP Test Tool** from the **Adapter** folder, and select **Test Instances** from the **Artifacts** folder.</span></span> <span data-ttu-id="78b17-107">有关详细信息，请参阅[执行自定义安装](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692)。</span><span class="sxs-lookup"><span data-stu-id="78b17-107">For more information, see [Performing a Custom Installation](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692).</span></span>  
  
 <span data-ttu-id="78b17-108">BTAHL7 安装程序将安装在此工具*\<驱动器\>*: \Program Files\Microsoft BizTalk\<版本\>Accelerator for HL7\SDK\MLLP 实用程序。</span><span class="sxs-lookup"><span data-stu-id="78b17-108">BTAHL7 setup installs this tool in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\MLLP Utilities.</span></span>  
  
 <span data-ttu-id="78b17-109">使用此工具中的[端到端教程](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)，则[询问教程](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)，则[批处理教程](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)，和[消息充实教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="78b17-109">You use this tool in the [End-to-End Tutorial](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md), the [Interrogative Tutorial](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md), the [Batching Tutorial](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md), and the [Message Enrichment Tutorial](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md).</span></span> <span data-ttu-id="78b17-110">如果您安装了[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]通过默认安装中，且尚未安装和使用的 MLLPTest 工具 （包括 MllpReceive MllpSend），您将不能测试您的教程结果。</span><span class="sxs-lookup"><span data-stu-id="78b17-110">If you installed [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] through the default installation, and have not installed the MLLPTest tool (including MllpReceive and MllpSend), you will not be able to test your tutorial results.</span></span>  
  
## <a name="tool-usage"></a><span data-ttu-id="78b17-111">工具使用情况</span><span class="sxs-lookup"><span data-stu-id="78b17-111">Tool Usage</span></span>  
 <span data-ttu-id="78b17-112">下面显示了用于调用此命令行工具的语法：</span><span class="sxs-lookup"><span data-stu-id="78b17-112">The following shows the syntax you use to invoke this command-line tool:</span></span>  
  
```  
mllpreceive.exe [/?] [/I <IP>] [/P <PORT>] [/SPLIT] [/D <DIRECTORY>] [/STATICACK "ACKTEXT" | /HL7ACK <FILENAME>] /SB nn /EB nn /CR nn  
```  
  
 <span data-ttu-id="78b17-113">下表描述 MllpReceive 工具使用的语法的各个部分。</span><span class="sxs-lookup"><span data-stu-id="78b17-113">The following table describes each part of the syntax the MllpReceive tool uses.</span></span>  
  
|<span data-ttu-id="78b17-114">语法</span><span class="sxs-lookup"><span data-stu-id="78b17-114">Syntax</span></span>|<span data-ttu-id="78b17-115">含义</span><span class="sxs-lookup"><span data-stu-id="78b17-115">Meaning</span></span>|  
|------------|-------------|  
|<span data-ttu-id="78b17-116">/?</span><span class="sxs-lookup"><span data-stu-id="78b17-116">/?</span></span>|<span data-ttu-id="78b17-117">显示此帮助。</span><span class="sxs-lookup"><span data-stu-id="78b17-117">Displays this help.</span></span>|  
|<span data-ttu-id="78b17-118">/I \<IP\></span><span class="sxs-lookup"><span data-stu-id="78b17-118">/I \<IP\></span></span>|<span data-ttu-id="78b17-119">表示要侦听的地址。</span><span class="sxs-lookup"><span data-stu-id="78b17-119">Denotes the address to listen to.</span></span> <span data-ttu-id="78b17-120">默认值为所有可用的 Ip。</span><span class="sxs-lookup"><span data-stu-id="78b17-120">The default is all available IPs.</span></span>|  
|<span data-ttu-id="78b17-121">/P\<端口\></span><span class="sxs-lookup"><span data-stu-id="78b17-121">/P \<PORT\></span></span>|<span data-ttu-id="78b17-122">表示要侦听的端口号。</span><span class="sxs-lookup"><span data-stu-id="78b17-122">Denotes the port number to listen to.</span></span> <span data-ttu-id="78b17-123">默认值为 12000。</span><span class="sxs-lookup"><span data-stu-id="78b17-123">The default value is 12000.</span></span>|  
|<span data-ttu-id="78b17-124">/D\<目录\></span><span class="sxs-lookup"><span data-stu-id="78b17-124">/D \<DIRECTORY\></span></span>|<span data-ttu-id="78b17-125">存储中的目录中的所有已接收的消息\<DIRECTORY\>。</span><span class="sxs-lookup"><span data-stu-id="78b17-125">Stores all received message(s) in the directory in \<DIRECTORY\>.</span></span> <span data-ttu-id="78b17-126">如果未指定\<DIRECTORY\>，默认目录为 %TEMP%。</span><span class="sxs-lookup"><span data-stu-id="78b17-126">If you do not specify \<DIRECTORY\>, the default directory is %TEMP%.</span></span>|  
|<span data-ttu-id="78b17-127">/SPLIT</span><span class="sxs-lookup"><span data-stu-id="78b17-127">/SPLIT</span></span>|<span data-ttu-id="78b17-128">将接收到的数据拆分为单独的消息根据分隔符。</span><span class="sxs-lookup"><span data-stu-id="78b17-128">Splits the received data into separate messages based on the delimiters.</span></span> <span data-ttu-id="78b17-129">SB 和 EB 是必需的。</span><span class="sxs-lookup"><span data-stu-id="78b17-129">SB and EB are required.</span></span> <span data-ttu-id="78b17-130">CR 是可选的。</span><span class="sxs-lookup"><span data-stu-id="78b17-130">CR is optional.</span></span>|  
|<span data-ttu-id="78b17-131">/ STATICACK</span><span class="sxs-lookup"><span data-stu-id="78b17-131">/STATICACK</span></span>|<span data-ttu-id="78b17-132">静态确认返回给发件人。</span><span class="sxs-lookup"><span data-stu-id="78b17-132">The static acknowledgment returned to the sender.</span></span> <span data-ttu-id="78b17-133">将强制执行拆分模式。</span><span class="sxs-lookup"><span data-stu-id="78b17-133">Will enforce SPLIT mode.</span></span>|  
|<span data-ttu-id="78b17-134">/ HL7ACK</span><span class="sxs-lookup"><span data-stu-id="78b17-134">/HL7ACK</span></span>|<span data-ttu-id="78b17-135">HL7 确认返回给发件人。</span><span class="sxs-lookup"><span data-stu-id="78b17-135">The HL7 acknowledgment returned to the sender.</span></span> <span data-ttu-id="78b17-136">文件名指示包含 HL7 确认的文件的名称</span><span class="sxs-lookup"><span data-stu-id="78b17-136">FILENAME denotes the name of the file containing the HL7 ACK.</span></span> <span data-ttu-id="78b17-137">将强制执行拆分模式。</span><span class="sxs-lookup"><span data-stu-id="78b17-137">Will enforce SPLIT mode.</span></span>|  
|<span data-ttu-id="78b17-138">/SB</span><span class="sxs-lookup"><span data-stu-id="78b17-138">/SB</span></span>|<span data-ttu-id="78b17-139">设置开始块分隔符字节的 ASCII 值。</span><span class="sxs-lookup"><span data-stu-id="78b17-139">Sets the ASCII value of Start Block Delimiter Byte.</span></span> <span data-ttu-id="78b17-140">默认值为 none。</span><span class="sxs-lookup"><span data-stu-id="78b17-140">The default is none.</span></span>|  
|<span data-ttu-id="78b17-141">/EB</span><span class="sxs-lookup"><span data-stu-id="78b17-141">/EB</span></span>|<span data-ttu-id="78b17-142">设置结束块分隔符字节的 ASCII 值。</span><span class="sxs-lookup"><span data-stu-id="78b17-142">Sets the ASCII value of End Block Delimiter Byte.</span></span> <span data-ttu-id="78b17-143">默认值为 none。</span><span class="sxs-lookup"><span data-stu-id="78b17-143">The default is none.</span></span>|  
|<span data-ttu-id="78b17-144">/CR</span><span class="sxs-lookup"><span data-stu-id="78b17-144">/CR</span></span>|<span data-ttu-id="78b17-145">设置回车符返回分隔符字节的 ASCII 值。</span><span class="sxs-lookup"><span data-stu-id="78b17-145">Sets the ASCII value of Carriage Return Delimiter Byte.</span></span> <span data-ttu-id="78b17-146">默认值为 none。</span><span class="sxs-lookup"><span data-stu-id="78b17-146">The default is none.</span></span>|  
  
## <a name="example-of-tool-use"></a><span data-ttu-id="78b17-147">工具使用的示例</span><span class="sxs-lookup"><span data-stu-id="78b17-147">Example of Tool Use</span></span>  
 <span data-ttu-id="78b17-148">可以使用以下命令来侦听端口 10000 上 localhost，并保存消息以便分离 C:\TEMP 上的文件：</span><span class="sxs-lookup"><span data-stu-id="78b17-148">You can use the following command to listen to port 10000 on localhost, and save messages to separate files on C:\TEMP:</span></span>  
  
```  
mllpreceive.exe /P 10000 /SPLIT /SB 11 /EB 28 /CR 13 /D C:\TEMP  
```  
  
## <a name="see-also"></a><span data-ttu-id="78b17-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="78b17-149">See Also</span></span>  
 [<span data-ttu-id="78b17-150">实用工具</span><span class="sxs-lookup"><span data-stu-id="78b17-150">Utilities</span></span>](../../adapters-and-accelerators/accelerator-hl7/utilities2.md)