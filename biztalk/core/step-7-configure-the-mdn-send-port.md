---
title: "步骤 7： 配置 MDN 发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 983033ac-9d32-47c8-9bb8-b4161bcdf183
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d0f70df6846553e2d64711f33e8c5a0b0e4d2cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-7-configure-the-mdn-send-port"></a><span data-ttu-id="c7194-102">步骤 7： 配置 MDN 发送端口</span><span class="sxs-lookup"><span data-stu-id="c7194-102">Step 7: Configure the MDN Send Port</span></span>
<span data-ttu-id="c7194-103">![11 的第 7 步](../core/media/tut-step7-of-11.gif "Tut_Step7_of_11")</span><span class="sxs-lookup"><span data-stu-id="c7194-103">![Step 7 of 11](../core/media/tut-step7-of-11.gif "Tut_Step7_of_11")</span></span>  
  
 <span data-ttu-id="c7194-104">在此步骤中，你将设置动态发送端口发送异步 MDN 到\\_MDNToFabrikam 文件夹。</span><span class="sxs-lookup"><span data-stu-id="c7194-104">In this step, you set up a dynamic send port to send an asynchronous MDN to the \\_MDNToFabrikam folder.</span></span> <span data-ttu-id="c7194-105">此发送端口使用 AS2Send 发送管道生成传出 MDN 响应。</span><span class="sxs-lookup"><span data-stu-id="c7194-105">This send port uses the AS2Send send pipeline to generate the outgoing MDN response.</span></span> <span data-ttu-id="c7194-106">由于这是动态发送端口，它将使用地址的回执送达选项行中消息的标头来将消息路由到\\_MDNToFabrikam 文件夹。</span><span class="sxs-lookup"><span data-stu-id="c7194-106">Since this is a dynamic send port, it will use the address in the Receipt-Delivery-Option line in the header of the message to route the message to the \\_MDNToFabrikam folder.</span></span> <span data-ttu-id="c7194-107">此地址为 Fabrikam 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="c7194-107">That address is the Fabrikam virtual directory.</span></span> <span data-ttu-id="c7194-108">与此虚拟目录关联的 Default.aspx.cs 文件生成带扩展名 .msg 的 MDN，并将此文件发送到目标文件夹（也在 Receipt-Delivery-Option 中加以指定）。</span><span class="sxs-lookup"><span data-stu-id="c7194-108">The Default.aspx.cs file associated with that virtual directory builds the MDN with an .msg extension, and sends the file to the destination folder (which is also specified in Receipt-Delivery-Option).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7194-109">您还可以通过用协议设置覆盖消息设置，将协议配置为将 MDN 发送到其他地址。</span><span class="sxs-lookup"><span data-stu-id="c7194-109">You can also configure the agreement to send the MDN to another address, by overriding the message settings with the agreement settings.</span></span> <span data-ttu-id="c7194-110">有关详细信息，请参阅</span><span class="sxs-lookup"><span data-stu-id="c7194-110">For more information, see</span></span>  
  
 <span data-ttu-id="c7194-111">在此示例中，使用动态发送端口发送 MDN；但是您还可以使用静态发送端口将 MDN 发送到静态地址。</span><span class="sxs-lookup"><span data-stu-id="c7194-111">In this example the MDN is sent using a dynamic send port; however you can also use a static send port to send the MDN to a static address.</span></span> <span data-ttu-id="c7194-112">有关详细信息，请参阅[通过 AS2 异步 Mdn 的配置静态发送端口](../core/configuring-a-static-send-port-for-asynchronous-mdns-over-as2.md)和[通过 AS2 异步 Mdn 的配置动态发送端口](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md)。</span><span class="sxs-lookup"><span data-stu-id="c7194-112">For more information, see [Configuring a Static Send Port for Asynchronous MDNs over AS2](../core/configuring-a-static-send-port-for-asynchronous-mdns-over-as2.md) and [Configuring a Dynamic Send Port for Asynchronous MDNs over AS2](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c7194-113">先决条件</span><span class="sxs-lookup"><span data-stu-id="c7194-113">Prerequisites</span></span>  
 <span data-ttu-id="c7194-114">你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="c7194-114">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-create-the-sendasyncmdn-send-port"></a><span data-ttu-id="c7194-115">创建 Send_Async_MDN 发送端口</span><span class="sxs-lookup"><span data-stu-id="c7194-115">To create the Send_Async_MDN send port</span></span>  
  
1.  <span data-ttu-id="c7194-116">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，BizTalk 应用程序 1 节点下右键单击**发送端口**，指向**新建**，然后单击**动态单向发送端口**.</span><span class="sxs-lookup"><span data-stu-id="c7194-116">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the BizTalk Application 1 node, right-click **Send Ports**, point to **New**, and then click **Dynamic One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="c7194-117">在**发送端口属性**对话框中，名称发送端口作为**Send_Async_MDN**。</span><span class="sxs-lookup"><span data-stu-id="c7194-117">In the **Send Port Properties** dialog box, name the send port as **Send_Async_MDN**.</span></span>  
  
3.  <span data-ttu-id="c7194-118">选择**AS2Send**为**发送管道**。</span><span class="sxs-lookup"><span data-stu-id="c7194-118">Select **AS2Send** for **Send pipeline**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c7194-119">使用 AS2Send 管道是由于对于 MDN 而言不需要进行 EDI 处理。</span><span class="sxs-lookup"><span data-stu-id="c7194-119">The AS2Send pipeline is used because no EDI processing is required for the MDN.</span></span>  
  
4.  <span data-ttu-id="c7194-120">单击**筛选器**在控制台树中。</span><span class="sxs-lookup"><span data-stu-id="c7194-120">Click **Filters** in the console tree.</span></span> <span data-ttu-id="c7194-121">在筛选器窗格中，选择**EdiIntAS.IsAS2AsynchronousMdn**为**属性**，  **==** 为**运算符**，并输入**True**为**值**。</span><span class="sxs-lookup"><span data-stu-id="c7194-121">In the Filters pane, select **EdiIntAS.IsAS2AsynchronousMdn** for **Property**, **==** for **Operator**, and enter **True** for **Value**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c7194-122">此筛选器可确保动态发送端口只从 MessageBox 中提取异步 MDN。</span><span class="sxs-lookup"><span data-stu-id="c7194-122">This filter ensures that the dynamic send port only picks up asynchronous MDNs from the MessageBox.</span></span>  
  
5.  <span data-ttu-id="c7194-123">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="c7194-123">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="c7194-124">在**发送端口**窗格[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**Send_Async_MDN**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="c7194-124">In the **Send Ports** pane of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click **Send_Async_MDN**, and then click **Start**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c7194-125">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c7194-125">Next Steps</span></span>  
 <span data-ttu-id="c7194-126">配置发送端口 (**Send_Async_997**) 发送 997 确认重新为 Fabrikam 中, 所述[第 8 步： 配置 997 发送端口](../core/step-8-configure-the-997-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="c7194-126">You configure the send port (**Send_Async_997**) to send the 997 acknowledgement back to Fabrikam, as described in [Step 8: Configure the 997 Send Port](../core/step-8-configure-the-997-send-port.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7194-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7194-127">See Also</span></span>  
 <span data-ttu-id="c7194-128">[BizTalk Server 将 AS2 消息的发送](../core/how-biztalk-server-sends-as2-messages.md) </span><span class="sxs-lookup"><span data-stu-id="c7194-128">[How BizTalk Server Sends AS2 Messages](../core/how-biztalk-server-sends-as2-messages.md) </span></span>  
 <span data-ttu-id="c7194-129">[通过 AS2 异步 Mdn 的配置静态发送端口](../core/configuring-a-static-send-port-for-asynchronous-mdns-over-as2.md) </span><span class="sxs-lookup"><span data-stu-id="c7194-129">[Configuring a Static Send Port for Asynchronous MDNs over AS2](../core/configuring-a-static-send-port-for-asynchronous-mdns-over-as2.md) </span></span>  
 [<span data-ttu-id="c7194-130">通过 AS2 消息配置动态发送端口</span><span class="sxs-lookup"><span data-stu-id="c7194-130">Configuring a Dynamic Send Port for Messages over AS2</span></span>](../core/configuring-a-dynamic-send-port-for-messages-over-as2.md)