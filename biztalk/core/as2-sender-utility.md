---
title: "AS2 发送方实用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e2a88fc-67fd-4801-a6f8-1e7c92098eaf
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e69f70e2a404c92393fb02b301b58abf2d97da2f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="as2-sender-utility"></a><span data-ttu-id="28153-102">AS2 发送方实用工具</span><span class="sxs-lookup"><span data-stu-id="28153-102">AS2 Sender Utility</span></span>
<span data-ttu-id="28153-103">AS2 发送方实用工具与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 一起提供，允许您向某一计算机上的网站发送 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="28153-103">The AS2 Sender utility shipped with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] enables you to send an AS2 message to a Web site on a single computer.</span></span> <span data-ttu-id="28153-104">此实用工具可模拟从单独的计算机发送 AS2 消息的过程。</span><span class="sxs-lookup"><span data-stu-id="28153-104">This utility simulates the sending of an AS2 message from a separate computer.</span></span>  
  
 <span data-ttu-id="28153-105">AS2 发送方实用工具文件位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender 中。</span><span class="sxs-lookup"><span data-stu-id="28153-105">The AS2 Sender utility files are located in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="28153-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="28153-106">Prerequisites</span></span>  
 <span data-ttu-id="28153-107">你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="28153-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
## <a name="what-this-utility-does"></a><span data-ttu-id="28153-108">此实用程序的用途</span><span class="sxs-lookup"><span data-stu-id="28153-108">What This Utility Does</span></span>  
 <span data-ttu-id="28153-109">AS2 发送方实用工具生成一个带有 EDI 负载的 AS2 消息，并将该消息发送到使用 BTSHTTPReceive ISAPI 筛选器的网站。</span><span class="sxs-lookup"><span data-stu-id="28153-109">The AS2 Sender utility builds an AS2 message with an EDI payload, and sends that message to a Web site that uses the BTSHTTPReceive ISAPI filter.</span></span> <span data-ttu-id="28153-110">默认情况下，此教程将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="28153-110">By default the tutorial does the following:</span></span>  
  
-   <span data-ttu-id="28153-111">发送一个带有 864 X12 编码的负载的名为 X12_00401_864.edi 的 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="28153-111">Sends an AS2 message named X12_00401_864.edi with an 864 X12-encoded payload.</span></span> <span data-ttu-id="28153-112">此消息位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="28153-112">This message is located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial folder.</span></span>  
  
-   <span data-ttu-id="28153-113">提示一个异步 MDN 以响应该 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="28153-113">Prompts an asynchronous MDN in response to the AS2 message.</span></span> <span data-ttu-id="28153-114">这是由发送的消息确定的，可进行更改。</span><span class="sxs-lookup"><span data-stu-id="28153-114">This is determined by the message sent, and can be changed.</span></span>  
  
-   <span data-ttu-id="28153-115">将该 AS2 消息通过 Contoso 虚拟目录发送到一个接收位置。</span><span class="sxs-lookup"><span data-stu-id="28153-115">Sends the AS2 message to a receive location through the Contoso virtual directory.</span></span>  
  
 <span data-ttu-id="28153-116">可修改该实用工具以更改此特定行为。</span><span class="sxs-lookup"><span data-stu-id="28153-116">The utility can be modified to change this specific behavior.</span></span> <span data-ttu-id="28153-117">请参阅[如何自定义的 AS2 发件人实用程序](../core/as2-sender-utility.md#BKMK_Custom)下面一节。</span><span class="sxs-lookup"><span data-stu-id="28153-117">See the [How to Customize the AS2 Sender Utility](../core/as2-sender-utility.md#BKMK_Custom) section below.</span></span>  
  
## <a name="how-to-set-up-a-solution-using-the-as2-sender-utility"></a><span data-ttu-id="28153-118">如何使用 AS2 发送方实用工具设置解决方案</span><span class="sxs-lookup"><span data-stu-id="28153-118">How to Set Up a Solution Using the AS2 Sender Utility</span></span>  
 <span data-ttu-id="28153-119">若要设置一个解决方案以使用 AS2 发送方实用工具，需要执行下列操作。</span><span class="sxs-lookup"><span data-stu-id="28153-119">To set up a solution to use the AS2 Sender utility, you need to do the following.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="28153-120">这些步骤在 AS2 教程和两个 AS2 发送方演练中进行演示。</span><span class="sxs-lookup"><span data-stu-id="28153-120">These steps are demonstrated in the AS2 Tutorial and two AS2 send-side walkthroughs.</span></span> <span data-ttu-id="28153-121">有关详细信息，请参阅[教程 3: AS2 教程](../core/tutorial-3-as2-tutorial.md)，[演练 (AS2): 通过使用同步 MDN 的 AS2 发送 EDI](../core/walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn.md)，和[演练 (AS2): 通过使用异步的 AS2 发送 EDIMDN](../core/walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn.md)。</span><span class="sxs-lookup"><span data-stu-id="28153-121">For more information, see [Tutorial 3: AS2 Tutorial](../core/tutorial-3-as2-tutorial.md), [Walkthrough (AS2): Sending EDI over AS2 with a Synchronous MDN](../core/walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn.md), and [Walkthrough (AS2): Sending EDI over AS2 with an Asynchronous MDN](../core/walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn.md).</span></span>  
  
-   <span data-ttu-id="28153-122">启用 BTSHTTPReceive ISAPI 筛选器。</span><span class="sxs-lookup"><span data-stu-id="28153-122">Enable the BTSHTTPReceive ISAPI filter.</span></span>  
  
-   <span data-ttu-id="28153-123">配置网页和接收位置以接收 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="28153-123">Configure a Web page and a receive location to receive the AS2 message.</span></span> <span data-ttu-id="28153-124">在默认的 AS2 发送方实用工具中，该网页是 Contoso 网页。</span><span class="sxs-lookup"><span data-stu-id="28153-124">In the default AS2 Sender utility, the Web page is the Contoso Web page.</span></span>  
  
-   <span data-ttu-id="28153-125">部署您将作为 AS2 消息的负载进行发送的 EDI 交换的架构。</span><span class="sxs-lookup"><span data-stu-id="28153-125">Deploy the schema for the EDI interchange that you will send as a payload of the AS2 message.</span></span>  
  
-   <span data-ttu-id="28153-126">设置相应的 AS2 和 EDI 参与方属性。</span><span class="sxs-lookup"><span data-stu-id="28153-126">Set the appropriate AS2 and EDI party properties.</span></span>  
  
##  <span data-ttu-id="28153-127"><a name="BKMK_Custom"></a>如何自定义的 AS2 发件人实用程序</span><span class="sxs-lookup"><span data-stu-id="28153-127"><a name="BKMK_Custom"></a> How to Customize the AS2 Sender Utility</span></span>  
 <span data-ttu-id="28153-128">默认的 AS2 发送方实用工具通过 AS2 将一个测试 864 EDI 交换发送到一个使用 BTSHTTPReceive ISAPI 筛选器的 Contoso 网页。</span><span class="sxs-lookup"><span data-stu-id="28153-128">The default AS2 Sender utility sends a test 864 EDI interchange over AS2 to a Contoso Web page using the BTSHTTPReceive ISAPI filter.</span></span> <span data-ttu-id="28153-129">名为 X12_00401_864.edi 的 AS2 消息将提示一个异步 MDN。</span><span class="sxs-lookup"><span data-stu-id="28153-129">The AS2 message, named X12_00401_864.edi, prompts an asynchronous MDN.</span></span> <span data-ttu-id="28153-130">AS2 发送方实用工具代码位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] AS2 Tutorial\Sender 文件夹中的 HttpSender.cs 中。</span><span class="sxs-lookup"><span data-stu-id="28153-130">The AS2 Sender utility code is located in HttpSender.cs in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]AS2 Tutorial\Sender folder.</span></span> <span data-ttu-id="28153-131">HttpSender.cs 中的以下代码行用于发送默认 864 测试文件：</span><span class="sxs-lookup"><span data-stu-id="28153-131">The following line of code in HttpSender.cs sends the default 864 test file:</span></span>  
  
```  
Stream sr = new FileStream(getBizTalkInstallPath() + @"SDK\AS2 Tutorial\X12_00401_864.edi", FileMode.Open, FileAccess.Read);  
```  
  
> [!NOTE]
>  <span data-ttu-id="28153-132">您可使用其他文件名和其他路径来修改此行。</span><span class="sxs-lookup"><span data-stu-id="28153-132">You can modify this line with a different file name and different path.</span></span>  
  
 <span data-ttu-id="28153-133">HttpSender.cs 中的以下行发送名为 X12_00401_864 Sync.edi AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="28153-133">The following line in HttpSender.cs sends an AS2 message named X12_00401_864-Sync.edi.</span></span> <span data-ttu-id="28153-134">此消息将提示一个异步 MDN。</span><span class="sxs-lookup"><span data-stu-id="28153-134">This message prompts a synchronous MDN.</span></span> <span data-ttu-id="28153-135">默认情况下，HttpSender.cs 中的此代码行是被注释掉的，以利于执行用于发送 X12_00401_864.edi 的代码行。</span><span class="sxs-lookup"><span data-stu-id="28153-135">By default, this line of code in HttpSender.cs is commented out in favor of the line that sends X12_00401_864.edi.</span></span> <span data-ttu-id="28153-136">若要发送 X12_00401_864-Sync.edi，取消 X12_00401_864-Sync.edi 行的注释并注释掉 X12_00401_864.edi 行。</span><span class="sxs-lookup"><span data-stu-id="28153-136">To send X12_00401_864-Sync.edi, uncomment the X12_00401_864-Sync.edi line and comment out the X12_00401_864.edi line.</span></span>  
  
```  
Stream sr = new FileStream(getBizTalkInstallPath() + @"SDK\AS2 Tutorial\X12_00401_864-Sync.edi", FileMode.Open, FileAccess.Read);  
```  
  
 <span data-ttu-id="28153-137">HttpSender.cs 中的以下代码行用于将消息发送到 Contoso 网页：</span><span class="sxs-lookup"><span data-stu-id="28153-137">The following line of code in HttpSender.cs sends the message to the Contoso Web page:</span></span>  
  
```  
HttpSender TestSender = new HttpSender("http://localhost/Contoso/BTSHttpReceive.dll");  
```  
  
> [!NOTE]
>  <span data-ttu-id="28153-138">您可使用其他虚拟目录和 ISAPI 筛选器来修改此行。</span><span class="sxs-lookup"><span data-stu-id="28153-138">You can modify this line with a different virtual directory and ISAPI filter.</span></span>  
  
### <a name="to-build-the-as2-sender-sample"></a><span data-ttu-id="28153-139">生成 AS2 发送方示例</span><span class="sxs-lookup"><span data-stu-id="28153-139">To build the AS2 Sender sample</span></span>  
  
1.  <span data-ttu-id="28153-140">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，打开 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender 文件夹中的 Sender.csproj 项目。</span><span class="sxs-lookup"><span data-stu-id="28153-140">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the Sender.csproj project in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender folder.</span></span>  
  
2.  <span data-ttu-id="28153-141">打开发送方项目中的 HttpSender.cs，使用适当的接收网页和 EDI 文件名和路径自定义发送方代码。</span><span class="sxs-lookup"><span data-stu-id="28153-141">Open HttpSender.cs in the Sender project, and customize the Sender code with the appropriate receiving Web page and the appropriate EDI filename and path.</span></span>  
  
3.  <span data-ttu-id="28153-142">右键单击 Sender 项目，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="28153-142">Right-click the Sender project, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="28153-143">单击**签名**在左侧的控制台。</span><span class="sxs-lookup"><span data-stu-id="28153-143">Click **Signing** in the left-hand console.</span></span> <span data-ttu-id="28153-144">确保**对程序集签名**选择时，和强名称密钥文件设置为**Sender.snk**。</span><span class="sxs-lookup"><span data-stu-id="28153-144">Ensure that **Sign the assembly** is selected, and the strong name key file is set to **Sender.snk**.</span></span> <span data-ttu-id="28153-145">请确保**仅延迟签名**处于未选中状态。</span><span class="sxs-lookup"><span data-stu-id="28153-145">Make sure that **Delay sign only** is cleared.</span></span>  
  
5.  <span data-ttu-id="28153-146">生成此项目。</span><span class="sxs-lookup"><span data-stu-id="28153-146">Build the project.</span></span>  
  
### <a name="to-run-the-as2-sender-sample"></a><span data-ttu-id="28153-147">运行 AS2 发送方示例</span><span class="sxs-lookup"><span data-stu-id="28153-147">To run the AS2 Sender sample</span></span>  
  
1.  <span data-ttu-id="28153-148">打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="28153-148">Open a command prompt.</span></span> <span data-ttu-id="28153-149">移动到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender\bin\debug。</span><span class="sxs-lookup"><span data-stu-id="28153-149">Move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender\bin\debug.</span></span>  
  
2.  <span data-ttu-id="28153-150">Enter **Sender.exe**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="28153-150">Enter **Sender.exe**, and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="28153-151">验证你已看到一条消息，指出 AS2 消息已成功发送，然后关闭命令提示符窗口。</span><span class="sxs-lookup"><span data-stu-id="28153-151">Verify that you see a message indicating that an AS2 message was successfully sent, and then close the command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28153-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28153-152">See Also</span></span>  
 <span data-ttu-id="28153-153">[教程 3: AS2 教程](../core/tutorial-3-as2-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="28153-153">[Tutorial 3: AS2 Tutorial](../core/tutorial-3-as2-tutorial.md) </span></span>  
 <span data-ttu-id="28153-154">[演练 (AS2): 通过使用同步 MDN 的 AS2 发送 EDI](../core/walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn.md) </span><span class="sxs-lookup"><span data-stu-id="28153-154">[Walkthrough (AS2): Sending EDI over AS2 with a Synchronous MDN](../core/walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn.md) </span></span>  
 [<span data-ttu-id="28153-155">演练 (AS2): 通过使用异步 MDN 的 AS2 发送 EDI</span><span class="sxs-lookup"><span data-stu-id="28153-155">Walkthrough (AS2): Sending EDI over AS2 with an Asynchronous MDN</span></span>](../core/walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn.md)