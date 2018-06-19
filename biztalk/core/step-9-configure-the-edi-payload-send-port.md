---
title: 步骤 9： 配置 EDI 负载发送端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71a8a4a7-7c3e-4e33-a9c0-a6445a3cc236
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9de1dff24af11cd03cda2550dcab921aec25d585
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277045"
---
# <a name="step-9-configure-the-edi-payload-send-port"></a><span data-ttu-id="275c5-102">步骤 9： 配置 EDI 负载发送端口</span><span class="sxs-lookup"><span data-stu-id="275c5-102">Step 9: Configure the EDI Payload Send Port</span></span>
<span data-ttu-id="275c5-103">![步骤 9 11](../core/media/tut-step9-of-11.gif "Tut_Step9_of_11")</span><span class="sxs-lookup"><span data-stu-id="275c5-103">![Step 9 of 11](../core/media/tut-step9-of-11.gif "Tut_Step9_of_11")</span></span>  
  
 <span data-ttu-id="275c5-104">在此步骤中，你将发送端口设置为发送到后端 Contoso 应用程序，从 EDI 负载生成的 XML 表示\\_EDIXMLToContoso 文件夹。</span><span class="sxs-lookup"><span data-stu-id="275c5-104">In this step, you set up a send port to send the XML generated from the EDI payload to the back-end Contoso application, represented by the \\_EDIXMLToContoso folder.</span></span> <span data-ttu-id="275c5-105">此发送端口使用 PassThruTransmit 发送管道。</span><span class="sxs-lookup"><span data-stu-id="275c5-105">This send port uses a PassThruTransmit send pipeline.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="275c5-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="275c5-106">Prerequisites</span></span>  
 <span data-ttu-id="275c5-107">你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="275c5-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-create-the-sendpayloadedixml-send-port"></a><span data-ttu-id="275c5-108">创建 Send_Payload_EdiXml 发送端口</span><span class="sxs-lookup"><span data-stu-id="275c5-108">To create the Send_Payload_EdiXml send port</span></span>  
  
1.  <span data-ttu-id="275c5-109">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="275c5-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-Way Send Port**.</span></span>  
  
2.  <span data-ttu-id="275c5-110">在**发送端口属性**对话框中，你发送端口作为名称**Send_Payload_EdiXml**。</span><span class="sxs-lookup"><span data-stu-id="275c5-110">In the **Send Port Properties** dialog box, name your send port as **Send_Payload_EdiXml**.</span></span> <span data-ttu-id="275c5-111">选择**文件**为**类型**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="275c5-111">Select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="275c5-112">之所以指定 FILE 类型是因为该发送管道将不对负载文件执行 AS2 处理。</span><span class="sxs-lookup"><span data-stu-id="275c5-112">The FILE type is specified because the send pipeline is not performing AS2 processing on the payload file.</span></span> <span data-ttu-id="275c5-113">它只是将负载文件路由到某个本地文件夹，以便您可以看到 EDI 事务集。</span><span class="sxs-lookup"><span data-stu-id="275c5-113">It is just routing the payload file to a local folder so you can see the EDI transaction set.</span></span>  
  
3.  <span data-ttu-id="275c5-114">在**文件传输属性**对话框中，为**目标文件夹**，浏览到并选择[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 教程\\_EDIXMLToContoso。</span><span class="sxs-lookup"><span data-stu-id="275c5-114">In the **FILE Transport Properties** dialog box, for **Destination folder**, browse to and select [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\\_EDIXMLToContoso.</span></span> <span data-ttu-id="275c5-115">保留**文件名**作为 **%MessageID%.xml**。</span><span class="sxs-lookup"><span data-stu-id="275c5-115">Leave **File name** as **%MessageID%.xml**.</span></span> <span data-ttu-id="275c5-116">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="275c5-116">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="275c5-117">接受默认的**PassThruTransmit**为**发送管道**。</span><span class="sxs-lookup"><span data-stu-id="275c5-117">Accept the default of **PassThruTransmit** for **Send Pipeline**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="275c5-118">由于使用 PassThruTransmit 发送管道，该管道将不对负载消息执行任何 EDI 处理，而是将消息以 AS2EdiReceive 接收管道生成的 XML 格式发送到本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="275c5-118">Because the PassThruTransmit send pipeline is used, the pipeline will not perform any EDI processing on the payload message, but will be sent to the local folder in the XML format produced by the AS2EdiReceive receive pipeline.</span></span>  
  
5.  <span data-ttu-id="275c5-119">单击**筛选器**在控制台树中。</span><span class="sxs-lookup"><span data-stu-id="275c5-119">Click **Filters** in the console tree.</span></span> <span data-ttu-id="275c5-120">有关**属性**，输入**BTS。MessageType**。</span><span class="sxs-lookup"><span data-stu-id="275c5-120">For **Property**, enter **BTS.MessageType**.</span></span> <span data-ttu-id="275c5-121">有关**运算符**，输入 **==** 。</span><span class="sxs-lookup"><span data-stu-id="275c5-121">For **Operator**, enter **==**.</span></span> <span data-ttu-id="275c5-122">有关**值**，输入`http://schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_864`。</span><span class="sxs-lookup"><span data-stu-id="275c5-122">For **Value**, enter `http://schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_864`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="275c5-123">该筛选器可确保此发送端口只从 MessageBox 中提取 X12 864 负载消息。</span><span class="sxs-lookup"><span data-stu-id="275c5-123">This filter ensures that this send port will only pick up X12 864 payload messages from the MessageBox.</span></span>  
  
6.  <span data-ttu-id="275c5-124">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="275c5-124">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="275c5-125">在**发送端口**窗格[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**Send_Payload_EdiXml**发送端口，并依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="275c5-125">In the **Send Ports** pane of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Send_Payload_EdiXml** send port, and then click **Start**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="275c5-126">后续步骤</span><span class="sxs-lookup"><span data-stu-id="275c5-126">Next Steps</span></span>  
 <span data-ttu-id="275c5-127">创建 X12 和 AS2 协议之间的两个贸易合作伙伴中, 所述[步骤 10： 配置 X12 和 AS2 贸易合作伙伴协议](../core/step-10-configure-the-x12-and-as2-trading-partner-agreement.md)</span><span class="sxs-lookup"><span data-stu-id="275c5-127">You create an AS2 and X12 agreement between the two trading partners, as described in [Step 10: Configure the X12 and AS2 Trading Partner Agreement](../core/step-10-configure-the-x12-and-as2-trading-partner-agreement.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="275c5-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="275c5-128">See Also</span></span>  
 [<span data-ttu-id="275c5-129">教程 3: AS2 教程</span><span class="sxs-lookup"><span data-stu-id="275c5-129">Tutorial 3: AS2 Tutorial</span></span>](../core/tutorial-3-as2-tutorial.md)