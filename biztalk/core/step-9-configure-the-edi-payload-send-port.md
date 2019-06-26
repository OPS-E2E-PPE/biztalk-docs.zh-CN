---
title: 步骤 9：配置 EDI 有效负载发送端口 |Microsoft Docs
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
ms.openlocfilehash: 77a43ec4402cf2abf86d77e1d6d10512ff9d3694
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244215"
---
# <a name="step-9-configure-the-edi-payload-send-port"></a><span data-ttu-id="67651-102">步骤 9：配置 EDI 有效负载发送端口</span><span class="sxs-lookup"><span data-stu-id="67651-102">Step 9: Configure the EDI Payload Send Port</span></span>
<span data-ttu-id="67651-103">![步骤 9 11](../core/media/tut-step9-of-11.gif "Tut_Step9_of_11")</span><span class="sxs-lookup"><span data-stu-id="67651-103">![Step 9 of 11](../core/media/tut-step9-of-11.gif "Tut_Step9_of_11")</span></span>  
  
 <span data-ttu-id="67651-104">在此步骤中，您将设置发送端口发送到后端 Contoso 应用程序，从 EDI 负载生成的 XML 表示\\_EDIXMLToContoso 文件夹。</span><span class="sxs-lookup"><span data-stu-id="67651-104">In this step, you set up a send port to send the XML generated from the EDI payload to the back-end Contoso application, represented by the \\_EDIXMLToContoso folder.</span></span> <span data-ttu-id="67651-105">此发送端口使用 PassThruTransmit 发送管道。</span><span class="sxs-lookup"><span data-stu-id="67651-105">This send port uses a PassThruTransmit send pipeline.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="67651-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="67651-106">Prerequisites</span></span>  
 <span data-ttu-id="67651-107">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="67651-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-create-the-sendpayloadedixml-send-port"></a><span data-ttu-id="67651-108">创建 Send_Payload_EdiXml 发送端口</span><span class="sxs-lookup"><span data-stu-id="67651-108">To create the Send_Payload_EdiXml send port</span></span>  
  
1. <span data-ttu-id="67651-109">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="67651-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-Way Send Port**.</span></span>  
  
2. <span data-ttu-id="67651-110">在中**发送端口属性**对话框，为发送端口的名称**Send_Payload_EdiXml**。</span><span class="sxs-lookup"><span data-stu-id="67651-110">In the **Send Port Properties** dialog box, name your send port as **Send_Payload_EdiXml**.</span></span> <span data-ttu-id="67651-111">选择**文件**有关**类型**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="67651-111">Select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="67651-112">指定的文件类型，因为发送管道不在有效负载文件执行 AS2 处理。</span><span class="sxs-lookup"><span data-stu-id="67651-112">The FILE type is specified because the send pipeline is not performing AS2 processing on the payload file.</span></span> <span data-ttu-id="67651-113">它是只需将负载文件路由到本地文件夹以便您可以看到 EDI 事务集。</span><span class="sxs-lookup"><span data-stu-id="67651-113">It is just routing the payload file to a local folder so you can see the EDI transaction set.</span></span>  
  
3. <span data-ttu-id="67651-114">在中**FILE 传输属性**对话框中，对于**目标文件夹**，浏览到并选择[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\\_EDIXMLToContoso。</span><span class="sxs-lookup"><span data-stu-id="67651-114">In the **FILE Transport Properties** dialog box, for **Destination folder**, browse to and select [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\\_EDIXMLToContoso.</span></span> <span data-ttu-id="67651-115">将保留**文件名**作为 **%MessageID%.xml**。</span><span class="sxs-lookup"><span data-stu-id="67651-115">Leave **File name** as **%MessageID%.xml**.</span></span> <span data-ttu-id="67651-116">单击“确定”  。</span><span class="sxs-lookup"><span data-stu-id="67651-116">Click **OK**.</span></span>  
  
4. <span data-ttu-id="67651-117">接受默认值为**PassThruTransmit**有关**发送管道**。</span><span class="sxs-lookup"><span data-stu-id="67651-117">Accept the default of **PassThruTransmit** for **Send Pipeline**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="67651-118">由于使用 PassThruTransmit 发送管道，因此管道将不会执行任何 EDI 负载消息处理，但将发送到本地文件夹以 XML 格式生成的 AS2EdiReceive 接收管道。</span><span class="sxs-lookup"><span data-stu-id="67651-118">Because the PassThruTransmit send pipeline is used, the pipeline will not perform any EDI processing on the payload message, but will be sent to the local folder in the XML format produced by the AS2EdiReceive receive pipeline.</span></span>  
  
5. <span data-ttu-id="67651-119">单击**筛选器**在控制台树中。</span><span class="sxs-lookup"><span data-stu-id="67651-119">Click **Filters** in the console tree.</span></span> <span data-ttu-id="67651-120">有关**属性**，输入**BTS。MessageType**。</span><span class="sxs-lookup"><span data-stu-id="67651-120">For **Property**, enter **BTS.MessageType**.</span></span> <span data-ttu-id="67651-121">有关**运算符**，输入 **==** 。</span><span class="sxs-lookup"><span data-stu-id="67651-121">For **Operator**, enter **==**.</span></span> <span data-ttu-id="67651-122">有关**值**，输入`http://schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_864`。</span><span class="sxs-lookup"><span data-stu-id="67651-122">For **Value**, enter `http://schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_864`.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="67651-123">此筛选器可确保，此发送端口将仅提取 X12 864 负载消息从 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="67651-123">This filter ensures that this send port will only pick up X12 864 payload messages from the MessageBox.</span></span>  
  
6. <span data-ttu-id="67651-124">单击“确定”  。</span><span class="sxs-lookup"><span data-stu-id="67651-124">Click **OK**.</span></span>  
  
7. <span data-ttu-id="67651-125">在中**发送端口**窗格[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**Send_Payload_EdiXml**发送端口，然后依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="67651-125">In the **Send Ports** pane of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Send_Payload_EdiXml** send port, and then click **Start**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="67651-126">后续步骤</span><span class="sxs-lookup"><span data-stu-id="67651-126">Next Steps</span></span>  
 <span data-ttu-id="67651-127">创建一个 AS2 和 X12 协议之间两个贸易合作伙伴，如中所述[步骤 10:配置 X12 和 AS2 贸易合作伙伴协议](../core/step-10-configure-the-x12-and-as2-trading-partner-agreement.md)</span><span class="sxs-lookup"><span data-stu-id="67651-127">You create an AS2 and X12 agreement between the two trading partners, as described in [Step 10: Configure the X12 and AS2 Trading Partner Agreement](../core/step-10-configure-the-x12-and-as2-trading-partner-agreement.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67651-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="67651-128">See Also</span></span>  
 [<span data-ttu-id="67651-129">教程 3：AS2 教程</span><span class="sxs-lookup"><span data-stu-id="67651-129">Tutorial 3: AS2 Tutorial</span></span>](../core/tutorial-3-as2-tutorial.md)