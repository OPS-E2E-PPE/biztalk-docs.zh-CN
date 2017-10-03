---
title: "安装所需的软件、 实用程序和示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: de0cb89d-08bd-48ec-a149-8929e2608df8
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 678037cd050ae8375b3c9ec465860d939d48cccc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="install-the-required-software-utilities-and-samples"></a><span data-ttu-id="421aa-102">安装所需的软件、 实用程序和示例</span><span class="sxs-lookup"><span data-stu-id="421aa-102">Install the Required Software, Utilities, and Samples</span></span>
<span data-ttu-id="421aa-103">本教程需要[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Windows Server 和自定义[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]包括 MLLP 测试工具的安装。</span><span class="sxs-lookup"><span data-stu-id="421aa-103">This tutorial requires [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Windows Server, and a custom [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] installation that includes the MLLP Test Tools.</span></span> <span data-ttu-id="421aa-104">此外，你应熟悉[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]中的开发[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)]和[了解 HL7 快捷键和提供的 BizTalk 工具](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md)。</span><span class="sxs-lookup"><span data-stu-id="421aa-104">Additionally, you should be familiar with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] development in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)] and [Learn the HL7 accelerator and the BizTalk tools available](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md).</span></span>
  
 <span data-ttu-id="421aa-105">你必须具有以下实用程序和在计算机上安装的示例：</span><span class="sxs-lookup"><span data-stu-id="421aa-105">You must have the following utilities and samples installed on your computer:</span></span>  
  
-   <span data-ttu-id="421aa-106">**MllpSend 工具**</span><span class="sxs-lookup"><span data-stu-id="421aa-106">**MllpSend Tool**</span></span>  
  
     <span data-ttu-id="421aa-107">此命令行实用工具将发送一条消息通过最少的较低层协议 (MLLP) 到 MLLP 协议接收位置。</span><span class="sxs-lookup"><span data-stu-id="421aa-107">This command-line utility sends a message over the Minimal Lower Layer Protocol (MLLP) protocol to an MLLP receive location.</span></span> <span data-ttu-id="421aa-108">用于测试你的教程结果。</span><span class="sxs-lookup"><span data-stu-id="421aa-108">You use it to test your tutorial results.</span></span> <span data-ttu-id="421aa-109">有关详细信息，请参阅[MllpSend 工具](../../adapters-and-accelerators/accelerator-hl7/mllpsend-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="421aa-109">For more information, see [MllpSend Tool](../../adapters-and-accelerators/accelerator-hl7/mllpsend-tool.md).</span></span>  
  
-   <span data-ttu-id="421aa-110">**MllpPReceive 工具**</span><span class="sxs-lookup"><span data-stu-id="421aa-110">**MllpPReceive Tool**</span></span>  
  
     <span data-ttu-id="421aa-111">此命令行实用工具通过 MLLP 协议，充当接收位置侦听器接收消息。</span><span class="sxs-lookup"><span data-stu-id="421aa-111">This command-line utility receives messages over the MLLP protocol, serving as a receive-location listener.</span></span> <span data-ttu-id="421aa-112">用于测试你的教程结果，显示消息和接收的确认。</span><span class="sxs-lookup"><span data-stu-id="421aa-112">You use it to test your tutorial results, displaying messages and acknowledgments received.</span></span> <span data-ttu-id="421aa-113">有关详细信息，请参阅[MllpReceive 工具](../../adapters-and-accelerators/accelerator-hl7/mllpreceive-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="421aa-113">For more information, see [MllpReceive Tool](../../adapters-and-accelerators/accelerator-hl7/mllpreceive-tool.md).</span></span>  
  
-   <span data-ttu-id="421aa-114">**示例应用程序接受 ACK.txt**</span><span class="sxs-lookup"><span data-stu-id="421aa-114">**Sample Application Accept ACK.txt**</span></span>  
  
     <span data-ttu-id="421aa-115">此示例文件包含文本的应用程序接受的确认消息。</span><span class="sxs-lookup"><span data-stu-id="421aa-115">This sample file contains the text of an application-accept acknowledgment message.</span></span> <span data-ttu-id="421aa-116">示例适用于 MllpReceive 工具，它接收并显示消息，然后将返回 acknowledgment(s) 发送示例文件中。</span><span class="sxs-lookup"><span data-stu-id="421aa-116">The sample works with the MllpReceive tool, which receives and displays messages, then sends back the acknowledgment(s) in the sample file.</span></span>  
  
 <span data-ttu-id="421aa-117">你需要使用 BTAHL7 自定义安装过程中安装两个工具和示例文件。</span><span class="sxs-lookup"><span data-stu-id="421aa-117">You need to install the two tools and the sample file by using the BTAHL7 Custom installation process.</span></span> <span data-ttu-id="421aa-118">典型的安装过程不会安装这些工具。</span><span class="sxs-lookup"><span data-stu-id="421aa-118">The Typical installation process does not install these tools.</span></span> <span data-ttu-id="421aa-119">若要安装这些工具，请在运行 BTAHL7 自定义安装，**自定义安装**屏幕上，选择**MLLP 测试工具**从**适配器**文件夹，并选择**测试实例**从**项目**文件夹。</span><span class="sxs-lookup"><span data-stu-id="421aa-119">To install these tools, run the BTAHL7 custom installation, at the **Custom Setup** screen, select **MLLP Test Tool** from the **Adapter** folder, and select **Test Instances** from the **Artifacts** folder.</span></span> <span data-ttu-id="421aa-120">有关详细信息，请参阅[HL7 安装 BizTalk 快捷键](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)。</span><span class="sxs-lookup"><span data-stu-id="421aa-120">For more information, see [Install BizTalk Accelerator for HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="421aa-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="421aa-121">See Also</span></span>  
 [<span data-ttu-id="421aa-122">准备使用批处理教程</span><span class="sxs-lookup"><span data-stu-id="421aa-122">Preparing to Use the Batching Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-batching-tutorial.md)