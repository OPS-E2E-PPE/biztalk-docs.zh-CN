---
title: 步骤 18:测试新消息充实解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, testing solution
ms.assetid: 233fbf79-0ab1-4064-b828-6bbbb56cbec2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8f57aeb039d2ff4e33f2bfcf14a2d4cf2257f27
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288740"
---
# <a name="step-18-test-your-new-message-enrichment-solution"></a><span data-ttu-id="eeaa4-102">步骤 18:测试新消息充实解决方案</span><span class="sxs-lookup"><span data-stu-id="eeaa4-102">Step 18: Test Your New Message Enrichment Solution</span></span>
<span data-ttu-id="eeaa4-103">通过使用 WSClient 应用程序将消息发送到在此步骤中，测试您的解决方案[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]并查看按预期方式 MLLPReceive 应用程序是否接收 HL7 格式的消息。</span><span class="sxs-lookup"><span data-stu-id="eeaa4-103">In this step, you test your solution by using the WSClient application to send a message to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and seeing if the MLLPReceive application receives an HL7-formatted message as expected.</span></span>  
  
### <a name="to-test-your-solution"></a><span data-ttu-id="eeaa4-104">若要测试你的解决方案</span><span class="sxs-lookup"><span data-stu-id="eeaa4-104">To test your solution</span></span>  
  
1.  <span data-ttu-id="eeaa4-105">打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="eeaa4-105">Open a command prompt.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eeaa4-106">步骤 2 要求您已安装 MLLP 测试工具使用的自定义安装过程。</span><span class="sxs-lookup"><span data-stu-id="eeaa4-106">Step 2 requires that you have installed the MLLP Test tool using the custom installation procedure.</span></span> <span data-ttu-id="eeaa4-107">如果您的计算机不存在目录包含 MllpReceive.exe 和 MllpSend.exe \MLLP 实用程序通过执行自定义安装中安装。</span><span class="sxs-lookup"><span data-stu-id="eeaa4-107">If the \MLLP Utilities directory containing MllpReceive.exe and MllpSend.exe does not exist on your computer, install them by performing a custom installation.</span></span> <span data-ttu-id="eeaa4-108">有关信息，请参阅[执行自定义安装](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692)。</span><span class="sxs-lookup"><span data-stu-id="eeaa4-108">For information, see [Performing a Custom Installation](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692).</span></span>  
  
2.  <span data-ttu-id="eeaa4-109">在命令提示符处，键入**cd \<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>HL7\SDK\MLLP 实用工具 Accelerator** (其中\<*驱动器*\>是你安装的驱动器号)，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="eeaa4-109">At the command prompt, type **cd \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\MLLP Utilities** (where \<*drive*\> is your installation drive letter), and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="eeaa4-110">在命令提示符处，键入**mllpreceive/p 11000 /eb 11 /sb 28 /cr 13**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="eeaa4-110">At the command prompt, type **mllpreceive /p 11000 /eb 11 /sb 28 /cr 13**, and then press **Enter**.</span></span> <span data-ttu-id="eeaa4-111">此运行 MLLP 侦听器应用程序侦听端口 11000 并指定默认 EB、 SB 和 CR 字符的 MLLP 消息，并显示在屏幕上收到任何消息。</span><span class="sxs-lookup"><span data-stu-id="eeaa4-111">This runs the MLLP listener application listening to port 11000 and specifying the default EB, SB, and CR characters of the MLLP message, and displays any messages received to the screen.</span></span>  
  
4.  <span data-ttu-id="eeaa4-112">打开第二个命令提示符。</span><span class="sxs-lookup"><span data-stu-id="eeaa4-112">Open a second command prompt.</span></span>  
  
5.  <span data-ttu-id="eeaa4-113">在命令提示符处，键入**cd \<*驱动器*\>: \Tutorial\WSClient\bin\Debug**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="eeaa4-113">At the command prompt, type **cd \<*drive*\>:\Tutorial\WSClient\bin\Debug**, and then press **Enter**.</span></span>  
  
6.  <span data-ttu-id="eeaa4-114">在命令提示符处，键入**wsclient john henry smith 123456789**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="eeaa4-114">At the command prompt, type **wsclient john henry smith 123456789**, and then press **Enter**.</span></span> <span data-ttu-id="eeaa4-115">这将一条消息发送到包含示例社会安全号码的 123456789 和 John Henry Smith 患者名称的示例消息的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="eeaa4-115">This sends a message to the Web service that contains a sample message with a patient name of John Henry Smith and a sample social security number of 123456789.</span></span>  
  
7.  <span data-ttu-id="eeaa4-116">片刻时间 MLLPReceive 应用程序显示传入 MLLP 消息。</span><span class="sxs-lookup"><span data-stu-id="eeaa4-116">After a short pause, the MLLPReceive application displays the incoming MLLP message.</span></span> <span data-ttu-id="eeaa4-117">该消息应类似于下面所示：</span><span class="sxs-lookup"><span data-stu-id="eeaa4-117">The message should look similar to the following:</span></span>  
  
    ```  
    MSH|^~\&|TestTrailing^Delimiters|srcFac^srcFacUid|dstApp^dstAppUid|dstFac^dstFacUid|200307092343|sec|ADT^A04|msgid2134|P|2.2PID|||123456789||smith^john  
    ```  
  
     <span data-ttu-id="eeaa4-118">如果在几分钟后未收到响应，应检查应用程序事件日志的任何错误，并开始进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="eeaa4-118">If you do not receive a response after a few minutes, you should check the Application event log for any errors and begin troubleshooting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeaa4-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="eeaa4-119">See Also</span></span>  
 [<span data-ttu-id="eeaa4-120">消息充实教程</span><span class="sxs-lookup"><span data-stu-id="eeaa4-120">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)