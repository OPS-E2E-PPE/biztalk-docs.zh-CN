---
title: 安装所需的软件、 实用工具和示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de0cb89d-08bd-48ec-a149-8929e2608df8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45f92f4cc994b4139c1c33423cc7a94c9072e226
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36965902"
---
# <a name="install-the-required-software-utilities-and-samples"></a><span data-ttu-id="4aea8-102">安装所需的软件、 实用工具和示例</span><span class="sxs-lookup"><span data-stu-id="4aea8-102">Install the Required Software, Utilities, and Samples</span></span>
<span data-ttu-id="4aea8-103">本教程需要安装 Microsoft Windows Server 和自定义 Microsoft[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]包括 MLLP 测试工具的安装。</span><span class="sxs-lookup"><span data-stu-id="4aea8-103">This tutorial requires Microsoft Windows Server, and a custom Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] installation that includes the MLLP Test Tools.</span></span> <span data-ttu-id="4aea8-104">此外，您应熟悉[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]在 Microsoft 中的进行开发[!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)]并[了解 HL7 加速器及可用的 BizTalk 工具](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md)。</span><span class="sxs-lookup"><span data-stu-id="4aea8-104">Additionally, you should be familiar with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] development in Microsoft [!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)] and [Learn the HL7 accelerator and the BizTalk tools available](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md).</span></span>
  
 <span data-ttu-id="4aea8-105">您必须具有以下实用程序和在计算机上安装的示例：</span><span class="sxs-lookup"><span data-stu-id="4aea8-105">You must have the following utilities and samples installed on your computer:</span></span>  
  
- <span data-ttu-id="4aea8-106">**MllpSend 工具**</span><span class="sxs-lookup"><span data-stu-id="4aea8-106">**MllpSend Tool**</span></span>  
  
   <span data-ttu-id="4aea8-107">此命令行实用程序将发送一条消息通过最少的较低层协议 (MLLP) 协议向 MLLP 接收位置。</span><span class="sxs-lookup"><span data-stu-id="4aea8-107">This command-line utility sends a message over the Minimal Lower Layer Protocol (MLLP) protocol to an MLLP receive location.</span></span> <span data-ttu-id="4aea8-108">用于测试您的教程结果。</span><span class="sxs-lookup"><span data-stu-id="4aea8-108">You use it to test your tutorial results.</span></span> <span data-ttu-id="4aea8-109">有关详细信息，请参阅[MllpSend 工具](../../adapters-and-accelerators/accelerator-hl7/mllpsend-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="4aea8-109">For more information, see [MllpSend Tool](../../adapters-and-accelerators/accelerator-hl7/mllpsend-tool.md).</span></span>  
  
- <span data-ttu-id="4aea8-110">**MllpPReceive 工具**</span><span class="sxs-lookup"><span data-stu-id="4aea8-110">**MllpPReceive Tool**</span></span>  
  
   <span data-ttu-id="4aea8-111">此命令行实用程序通过 MLLP 协议，充当接收位置侦听程序接收消息。</span><span class="sxs-lookup"><span data-stu-id="4aea8-111">This command-line utility receives messages over the MLLP protocol, serving as a receive-location listener.</span></span> <span data-ttu-id="4aea8-112">用于测试您的教程结果，显示消息和接收的确认。</span><span class="sxs-lookup"><span data-stu-id="4aea8-112">You use it to test your tutorial results, displaying messages and acknowledgments received.</span></span> <span data-ttu-id="4aea8-113">有关详细信息，请参阅[MllpReceive 工具](../../adapters-and-accelerators/accelerator-hl7/mllpreceive-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="4aea8-113">For more information, see [MllpReceive Tool](../../adapters-and-accelerators/accelerator-hl7/mllpreceive-tool.md).</span></span>  
  
- <span data-ttu-id="4aea8-114">**示例应用程序接受 ACK.txt**</span><span class="sxs-lookup"><span data-stu-id="4aea8-114">**Sample Application Accept ACK.txt**</span></span>  
  
   <span data-ttu-id="4aea8-115">此示例文件包含文本的应用程序接受确认消息。</span><span class="sxs-lookup"><span data-stu-id="4aea8-115">This sample file contains the text of an application-accept acknowledgment message.</span></span> <span data-ttu-id="4aea8-116">此示例适用 MllpReceive 工具，它接收并显示消息，然后在示例文件中发送回确认。</span><span class="sxs-lookup"><span data-stu-id="4aea8-116">The sample works with the MllpReceive tool, which receives and displays messages, then sends back the acknowledgment(s) in the sample file.</span></span>  
  
  <span data-ttu-id="4aea8-117">您需要通过 BTAHL7 自定义安装过程中安装的两个工具和示例文件。</span><span class="sxs-lookup"><span data-stu-id="4aea8-117">You need to install the two tools and the sample file by using the BTAHL7 Custom installation process.</span></span> <span data-ttu-id="4aea8-118">典型安装过程不会安装这些工具。</span><span class="sxs-lookup"><span data-stu-id="4aea8-118">The Typical installation process does not install these tools.</span></span> <span data-ttu-id="4aea8-119">若要安装这些工具，请在运行 BTAHL7 自定义安装，**自定义安装**屏幕上，选择**MLLP 测试工具**从**适配器**文件夹，然后选择**测试实例**从**项目**文件夹。</span><span class="sxs-lookup"><span data-stu-id="4aea8-119">To install these tools, run the BTAHL7 custom installation, at the **Custom Setup** screen, select **MLLP Test Tool** from the **Adapter** folder, and select **Test Instances** from the **Artifacts** folder.</span></span> <span data-ttu-id="4aea8-120">有关详细信息，请参阅[安装 BizTalk Accelerator for HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)。</span><span class="sxs-lookup"><span data-stu-id="4aea8-120">For more information, see [Install BizTalk Accelerator for HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4aea8-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="4aea8-121">See Also</span></span>  
 [<span data-ttu-id="4aea8-122">为使用批处理教程做准备</span><span class="sxs-lookup"><span data-stu-id="4aea8-122">Preparing to Use the Batching Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-batching-tutorial.md)