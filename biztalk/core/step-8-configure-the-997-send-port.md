---
title: 步骤 8： 配置 997 发送端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4780c491-9f1a-4f13-b346-6a2e1801ec09
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec3c022ec1236d760c69250a2faecc7cacdb543c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277213"
---
# <a name="step-8-configure-the-997-send-port"></a><span data-ttu-id="9fe77-102">步骤 8： 配置 997 发送端口</span><span class="sxs-lookup"><span data-stu-id="9fe77-102">Step 8: Configure the 997 Send Port</span></span>
<span data-ttu-id="9fe77-103">![步骤 8 11](../core/media/tut-step8-of-11.gif "Tut_Step8_of_11")</span><span class="sxs-lookup"><span data-stu-id="9fe77-103">![Step 8 of 11](../core/media/tut-step8-of-11.gif "Tut_Step8_of_11")</span></span>  
  
 <span data-ttu-id="9fe77-104">在此步骤中，您将设置发送端口以将 997 消息发送给合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="9fe77-104">In this step, you set up a send port to send the 997 message to the partner.</span></span> <span data-ttu-id="9fe77-105">该发送端口使用 AS2EdiSend 发送管道将 EDIINT/AS2 编码的 997 确认传输到 _997ToFabrikam 文件夹。</span><span class="sxs-lookup"><span data-stu-id="9fe77-105">This send port uses the AS2EdiSend send pipeline to transport an EDIINT/AS2-encoded 997 acknowledgment to the _997ToFabrikam folder.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9fe77-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="9fe77-106">Prerequisites</span></span>  
 <span data-ttu-id="9fe77-107">你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="9fe77-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-create-the-sendasync997-send-port"></a><span data-ttu-id="9fe77-108">创建 Send_Async_997 发送端口</span><span class="sxs-lookup"><span data-stu-id="9fe77-108">To create the Send_Async_997 send port</span></span>  
  
1.  <span data-ttu-id="9fe77-109">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，BizTalk 应用程序 1 节点下右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**.</span><span class="sxs-lookup"><span data-stu-id="9fe77-109">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the BizTalk Application 1 node, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9fe77-110">您将使用静态单向发送端口，这是因为没有为作为 AS2 消息接收方的 Fabrikam 参与方设置任何 MDN。</span><span class="sxs-lookup"><span data-stu-id="9fe77-110">You will use a static one-way send port because no MDN has been set up for the Fabrikam party as an AS2 message receiver.</span></span>  
  
2.  <span data-ttu-id="9fe77-111">在**发送端口属性**对话框框中，将发送端口**Send_Async_997**。</span><span class="sxs-lookup"><span data-stu-id="9fe77-111">In the **Send Port Properties** dialog box, name your send port **Send_Async_997**.</span></span> <span data-ttu-id="9fe77-112">选择**HTTP**为**类型**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="9fe77-112">Select **HTTP** for **Type**, and then click **Configure**.</span></span>  
  
3.  <span data-ttu-id="9fe77-113">在**HTTP 传输属性**对话框中，为**目标 URL**，输入`http://localhost/Fabrikam/Default.aspx?Destination=_997ToFabrikam`。</span><span class="sxs-lookup"><span data-stu-id="9fe77-113">In the **HTTP Transport Properties** dialog box, for **Destination URL**, enter `http://localhost/Fabrikam/Default.aspx?Destination=_997ToFabrikam`.</span></span> <span data-ttu-id="9fe77-114">清除**启用 chunked 编码**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9fe77-114">Clear **Enable chunked encoding** and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9fe77-115">**目标 URL**设置可以确保发送端口将将 997 消息发送到 Fabrikam 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="9fe77-115">The **Destination URL** setting ensures that the send port will send the 997 message to the Fabrikam virtual directory.</span></span> <span data-ttu-id="9fe77-116">与该虚拟目录关联的 Default.aspx.cs 文件可生成具有 .msg 扩展名的 997，并将其发送到目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="9fe77-116">The Default.aspx.cs file associated with that virtual directory builds the 997 with an .msg extension, and sends it to the destination folder.</span></span>  
  
4.  <span data-ttu-id="9fe77-117">在**发送端口属性**对话框中，选择**AS2EdiSend**为**发送管道**。</span><span class="sxs-lookup"><span data-stu-id="9fe77-117">In the **Send Port Properties** dialog box, select **AS2EdiSend** for **Send Pipeline**.</span></span>  
  
5.  <span data-ttu-id="9fe77-118">单击**筛选器**在控制台树中。</span><span class="sxs-lookup"><span data-stu-id="9fe77-118">Click **Filters** in the console tree.</span></span> <span data-ttu-id="9fe77-119">有关**属性**，选择**BTS。MessageType**。</span><span class="sxs-lookup"><span data-stu-id="9fe77-119">For **Property**, select **BTS.MessageType**.</span></span> <span data-ttu-id="9fe77-120">有关**运算符**，选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="9fe77-120">For **Operator**, select **==**.</span></span> <span data-ttu-id="9fe77-121">有关**值**，输入`http://schemas.microsoft.com/Edi/X12#X12_997_Root`。</span><span class="sxs-lookup"><span data-stu-id="9fe77-121">For **Value**, enter `http://schemas.microsoft.com/Edi/X12#X12_997_Root`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9fe77-122">该筛选器可确保发送端口只从 MessageBox 中提取 997 确认。</span><span class="sxs-lookup"><span data-stu-id="9fe77-122">This filter ensures that the send port will only pick up 997 acknowledgments from the MessageBox.</span></span>  
  
6.  <span data-ttu-id="9fe77-123">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="9fe77-123">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="9fe77-124">在**发送端口**窗格[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**Send_Async_997**发送端口，并依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="9fe77-124">In the **Send Ports** pane of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Send_Async_997** send port, and then click **Start**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9fe77-125">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9fe77-125">Next Steps</span></span>  
 <span data-ttu-id="9fe77-126">配置发送端口 (**Send_Payload_EdiXml**) 向 Contoso 发送 EDI 负载，如中所述[步骤 9： 配置 EDI 负载发送端口](../core/step-9-configure-the-edi-payload-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="9fe77-126">You configure the send port (**Send_Payload_EdiXml**) to send the EDI payload to Contoso, as described in [Step 9: Configure the EDI Payload Send Port](../core/step-9-configure-the-edi-payload-send-port.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fe77-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9fe77-127">See Also</span></span>  
 <span data-ttu-id="9fe77-128">[BizTalk Server 将 AS2 消息的发送](../core/how-biztalk-server-sends-as2-messages.md) </span><span class="sxs-lookup"><span data-stu-id="9fe77-128">[How BizTalk Server Sends AS2 Messages](../core/how-biztalk-server-sends-as2-messages.md) </span></span>  
 [<span data-ttu-id="9fe77-129">通过 AS2 消息配置静态发送端口</span><span class="sxs-lookup"><span data-stu-id="9fe77-129">Configuring a Static Send Port for Messages over AS2</span></span>](../core/configuring-a-static-send-port-for-messages-over-as2.md)