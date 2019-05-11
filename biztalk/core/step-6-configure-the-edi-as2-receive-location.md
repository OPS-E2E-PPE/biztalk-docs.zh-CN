---
title: 步骤 6：配置 EDI-AS2 接收位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 167f8ba2-d38b-4088-863b-2bd90c2a12a2
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d72735d128a2afbad003eacb0662dba3c98fde0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244311"
---
# <a name="step-6-configure-the-edi-as2-receive-location"></a><span data-ttu-id="c4a84-102">步骤 6：配置 EDI-AS2 接收位置</span><span class="sxs-lookup"><span data-stu-id="c4a84-102">Step 6: Configure the EDI-AS2 Receive Location</span></span>
<span data-ttu-id="c4a84-103">![步骤 6 11](../core/media/tut-step6-of-11.gif "Tut_Step6_of_11")</span><span class="sxs-lookup"><span data-stu-id="c4a84-103">![Step 6 of 11](../core/media/tut-step6-of-11.gif "Tut_Step6_of_11")</span></span>  
  
 <span data-ttu-id="c4a84-104">在此步骤中，您将设置一个单向接收位置用于从 Fabrikam 参与方接收 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="c4a84-104">In this step, you set up a one-way receive location that receives the EDI message from the Fabrikam party.</span></span> <span data-ttu-id="c4a84-105">此接收位置使用 AS2EdiReceive 接收管道处理传入的 EDI/AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="c4a84-105">This receive location uses the AS2EdiReceive receive pipeline to process the incoming EDI/AS2 message.</span></span> <span data-ttu-id="c4a84-106">由 sender.exe 应用程序通过 Contoso 虚拟目录使用 BTSHTTPReceive.dll ISAPI 扩展，该消息将发送到接收位置。</span><span class="sxs-lookup"><span data-stu-id="c4a84-106">The message will be sent to the receive location by the sender.exe application through the Contoso virtual directory using the BTSHTTPReceive.dll ISAPI extension.</span></span>  
  
 <span data-ttu-id="c4a84-107">在本教程中，您将设置动态发送端口将以异步方式发送 MDN 响应。</span><span class="sxs-lookup"><span data-stu-id="c4a84-107">In this tutorial, you will set up a dynamic send port to send the MDN response asynchronously.</span></span> <span data-ttu-id="c4a84-108">在此方案中，只有一个单向接收端口是必需的。</span><span class="sxs-lookup"><span data-stu-id="c4a84-108">In this scenario, only a one-way receive port is required.</span></span> <span data-ttu-id="c4a84-109">但是，您也可以更改 Sender.exe 以发送 AS2 消息指定同步 MDN。</span><span class="sxs-lookup"><span data-stu-id="c4a84-109">However, you could also change Sender.exe to send an AS2 message specifying a synchronous MDN.</span></span> <span data-ttu-id="c4a84-110">然后必须创建一个双向请求响应接收端口以返回 MDN。</span><span class="sxs-lookup"><span data-stu-id="c4a84-110">You would then have to create a two-way request response receive port to return the MDN.</span></span> <span data-ttu-id="c4a84-111">有关详细信息，请参阅"测试解决方案"部分的[演练 (AS2):使用同步 MDN 通过 AS2 接收 EDI](../core/walkthrough-as2-receiving-edi-over-as2-with-a-synchronous-mdn.md)。</span><span class="sxs-lookup"><span data-stu-id="c4a84-111">For more information, see the "To test the solution" section of [Walkthrough (AS2): Receiving EDI over AS2 with a Synchronous MDN](../core/walkthrough-as2-receiving-edi-over-as2-with-a-synchronous-mdn.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c4a84-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="c4a84-112">Prerequisites</span></span>  
 <span data-ttu-id="c4a84-113">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="c4a84-113">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-create-the-biztalk-http-receive-location"></a><span data-ttu-id="c4a84-114">若要创建 BizTalk HTTP 接收位置</span><span class="sxs-lookup"><span data-stu-id="c4a84-114">To create the BizTalk HTTP receive location</span></span>  
  
1. <span data-ttu-id="c4a84-115">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，在 BizTalk Application 1 节点中，右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**.</span><span class="sxs-lookup"><span data-stu-id="c4a84-115">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the BizTalk Application 1 node, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
2. <span data-ttu-id="c4a84-116">为接收端口的名称**Receive_AS2**。</span><span class="sxs-lookup"><span data-stu-id="c4a84-116">Name the receive port as **Receive_AS2**.</span></span>  
  
3. <span data-ttu-id="c4a84-117">单击**接收位置**在控制台树中，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="c4a84-117">Click **Receive Locations** in the console tree, and then click **New**.</span></span>  
  
4. <span data-ttu-id="c4a84-118">在中**接收位置属性**对话框中，名称在接收位置**Receive_AS2**，选择**HTTP**有关**类型**，，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="c4a84-118">In the **Receive Location Properties** dialog box, name your receive location **Receive_AS2**, select **HTTP** for **Type**, and then click **Configure**.</span></span>  
  
5. <span data-ttu-id="c4a84-119">在中**HTTP 传输属性**对话框框中，输入 **/Contoso/BTSHTTPReceive.dll**有关**虚拟目录和 ISAPI 扩展**。</span><span class="sxs-lookup"><span data-stu-id="c4a84-119">In the **HTTP Transport Properties** dialog box, enter **/Contoso/BTSHTTPReceive.dll** for **Virtual directory plus ISAPI extension**.</span></span> <span data-ttu-id="c4a84-120">清除**成功后的返回相关句柄**，然后选择**挂起失败的请求**。</span><span class="sxs-lookup"><span data-stu-id="c4a84-120">Clear **Return correlation handle on success** and select **Suspend failed requests**.</span></span> <span data-ttu-id="c4a84-121">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="c4a84-121">Click **OK**.</span></span>  
  
6. <span data-ttu-id="c4a84-122">选择**AS2EdiReceive**有关**接收管道**。</span><span class="sxs-lookup"><span data-stu-id="c4a84-122">Select **AS2EdiReceive** for the **Receive Pipeline**.</span></span> <span data-ttu-id="c4a84-123">单击**确定**，然后单击**确定**试。</span><span class="sxs-lookup"><span data-stu-id="c4a84-123">Click **OK**, and then click **OK** again.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="c4a84-124">AS2EdiReceive 接收管道执行 AS2 解码和 EDI 拆装。</span><span class="sxs-lookup"><span data-stu-id="c4a84-124">The AS2EdiReceive receive pipeline performs AS2 decoding and EDI disassembly.</span></span>  
  
7. <span data-ttu-id="c4a84-125">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**接收位置**下的 BizTalk Application 1 节点中，右键单击**Receive_AS2**，然后单击**启用**.</span><span class="sxs-lookup"><span data-stu-id="c4a84-125">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click **Receive Locations** under the BizTalk Application 1 node, right-click **Receive_AS2**, and then click **Enable**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c4a84-126">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c4a84-126">Next Steps</span></span>  
 <span data-ttu-id="c4a84-127">配置发送端口 (**Send_Asynch_MDN**) 发送端口以将异步 MDN 发送回 Fabrikam，如中所述[步骤 7:配置 MDN 发送端口](../core/step-7-configure-the-mdn-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="c4a84-127">You configure the send port (**Send_Asynch_MDN**) send port to send the asynchronous MDN back to Fabrikam, as described in [Step 7: Configure the MDN Send Port](../core/step-7-configure-the-mdn-send-port.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4a84-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4a84-128">See Also</span></span>  
 <span data-ttu-id="c4a84-129">[BizTalk Server 如何接收 AS2 消息](../core/how-biztalk-server-receives-as2-messages.md) </span><span class="sxs-lookup"><span data-stu-id="c4a84-129">[How BizTalk Server Receives AS2 Messages](../core/how-biztalk-server-receives-as2-messages.md) </span></span>  
 [<span data-ttu-id="c4a84-130">配置 AS2 消息的接收端口</span><span class="sxs-lookup"><span data-stu-id="c4a84-130">Configuring a Receive Port for Messages over AS2</span></span>](../core/configuring-a-receive-port-for-messages-over-as2.md)