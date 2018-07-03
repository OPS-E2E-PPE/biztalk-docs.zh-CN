---
title: 配置确认 (Mdn) (AS2) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb2bf98a-deb4-460f-a1fc-3d2397c39470
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7370b37c7c390e6a837dbf3f700784dbc7fee7e3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017961"
---
# <a name="configuring-acknowledgements-mdns-as2"></a><span data-ttu-id="4a972-102">配置确认 (MDN) (AS2)</span><span class="sxs-lookup"><span data-stu-id="4a972-102">Configuring Acknowledgements (MDNs) (AS2)</span></span>
<span data-ttu-id="4a972-103">在合作伙伴协议中，您可以指定接收 AS2 消息的参与方生成 MDN 响应并将其发回的方式。</span><span class="sxs-lookup"><span data-stu-id="4a972-103">In the partner agreement, you can specify how the party receiving the AS2 message generates an MDN response and sends it to back.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4a972-104">以下属性禁用此页上，如果您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="4a972-104">The following properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
> 
> - <span data-ttu-id="4a972-105">**未收到 MDN 时重新发送 AS2 消息**复选框以及关联的属性</span><span class="sxs-lookup"><span data-stu-id="4a972-105">**Resend AS2 message if MDN not received** check box and associated properties</span></span>  
>   -   <span data-ttu-id="4a972-106">**替代发送端口设置**复选框以及关联的属性</span><span class="sxs-lookup"><span data-stu-id="4a972-106">**Override send port settings** check box and associated properties</span></span>  
> 
>   <span data-ttu-id="4a972-107">仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。</span><span class="sxs-lookup"><span data-stu-id="4a972-107">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="4a972-108">例如，如果创建两个参与方 Party A 和参与方 B，并且对于参与方 A 清除该复选框，上述列表中的属性上禁用**参与方 A-> 参与方 B**单向协议选项卡。</span><span class="sxs-lookup"><span data-stu-id="4a972-108">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4a972-109">必要條件</span><span class="sxs-lookup"><span data-stu-id="4a972-109">Prerequisites</span></span>  
 <span data-ttu-id="4a972-110">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="4a972-110">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-acknowledgements"></a><span data-ttu-id="4a972-111">配置确认</span><span class="sxs-lookup"><span data-stu-id="4a972-111">To configure acknowledgements</span></span>  
  
1. <span data-ttu-id="4a972-112">创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。</span><span class="sxs-lookup"><span data-stu-id="4a972-112">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="4a972-113">若要更新现有 AS2 协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="4a972-113">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2. <span data-ttu-id="4a972-114">在单向协议选项卡上，单击**确认 (Mdn)**。</span><span class="sxs-lookup"><span data-stu-id="4a972-114">On a one-way agreement tab, click **Acknowledgements (MDNs)**.</span></span>  
  
3. <span data-ttu-id="4a972-115">选择**到 MessageBox 中处理入站的 MDN 以进行路由/传递**路由通过 A2 解码器将 MDN 作为直通消息，然后到 MessageBox 中的复选框。</span><span class="sxs-lookup"><span data-stu-id="4a972-115">Select the **Process inbound MDN into MessageBox for routing/delivery options** check box to route the MDN through the A2 Decoder as a passthrough message and then into the MessageBox.</span></span> <span data-ttu-id="4a972-116">当选择此属性时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会提升用于路由的 `IsAS2MdnResponseMessage` 属性。</span><span class="sxs-lookup"><span data-stu-id="4a972-116">When this property is selected, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] promotes the `IsAS2MdnResponseMessage` property for routing purposes.</span></span>  
  
4. <span data-ttu-id="4a972-117">如果您选中**使用的验证和 MSDN 的协议设置而非消息标头**属性中的**验证**页上，选择**请求 MDN**如果复选框贸易合作伙伴必须生成 MDN 以响应 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="4a972-117">If you checked the **Use agreement settings for validation and MSDN instead of message header** property in the **Validations** page, select the **Request MDN** check box if the trading partner must generate an MDN in response to the AS2 message.</span></span>  
  
    <span data-ttu-id="4a972-118">如果**请求 MDN**复选框处于选中状态，还可以设置以下属性：</span><span class="sxs-lookup"><span data-stu-id="4a972-118">If the **Request MDN** check box is selected, you can also set the following properties:</span></span>  
  
   1. <span data-ttu-id="4a972-119">选择**请求经过签名的 MDN**复选框和从**签名算法**下拉列表中选择贸易合作伙伴必须用来对 MDN 签名的 MIC 算法。</span><span class="sxs-lookup"><span data-stu-id="4a972-119">Select the **Request signed MDN** check box and from the **Signing Algorithm** drop-down select the MIC algorithm that the trading partner must use to sign the MDN.</span></span> [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="4a972-120"> 支持 MD5、 SHA1、 和 SHA2 (SHA256 （默认）、 SHA384 和 SHA512)。</span><span class="sxs-lookup"><span data-stu-id="4a972-120"> supports MD5, SHA1, and SHA2 (SHA256 (default), SHA384, and SHA512).</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="4a972-121">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]及更高版本**，则会自动包括 SHA2 支持。</span><span class="sxs-lookup"><span data-stu-id="4a972-121">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] and newer versions**, SHA2 support is automatically included.</span></span> <span data-ttu-id="4a972-122">对于以前[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]版本中，请参阅[KB 3123748](https://support.microsoft.com/kb/3123748)。</span><span class="sxs-lookup"><span data-stu-id="4a972-122">For previous [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] versions, see [KB 3123748](https://support.microsoft.com/kb/3123748).</span></span>
  
   2. <span data-ttu-id="4a972-123">选择**请求异步 MDN**复选框，然后在**回执送达选项 (URL)** 文字框中，输入接收方应接收 MDN 的 URL。</span><span class="sxs-lookup"><span data-stu-id="4a972-123">Select the **Request asynchronous MDN** check box and then in the **Receipt-Delivery-Option (URL)** text box, enter the URL that the receiving party should send the MDN to.</span></span>  
  
       <span data-ttu-id="4a972-124">如果**请求异步 MDN**复选框处于选中状态，还可以设置以下属性：</span><span class="sxs-lookup"><span data-stu-id="4a972-124">If the **Request asynchronous MDN** check box is selected, you can also set the following properties:</span></span>  
  
      1. <span data-ttu-id="4a972-125">选择**MDN 未收到时重新发送 AS2 消息**复选框以启用 AS2 消息的重新传输。</span><span class="sxs-lookup"><span data-stu-id="4a972-125">Select the **Resend AS2 message if MDN not received** check box to enable retransmission of the AS2 message.</span></span> <span data-ttu-id="4a972-126">输入一个值**最小 AS2 消息重新发送间隔**，**数的 AS2 消息重新发送尝试次数**并**停止尝试的 AS2 消息重新发送后**字段，用于指定重试时间间隔，最大尝试次数以及何时停止重新发送消息。</span><span class="sxs-lookup"><span data-stu-id="4a972-126">Enter a value for **Minimum AS2 message resend interval**, **Number of AS2 message resend attempts** and **Stop attempting AS2 message resends after** fields to specify the retry interval, maximum number of attempts and when to stop resending the message.</span></span>  
  
         > [!NOTE]
         >  <span data-ttu-id="4a972-127">必须选择**打开报告**上的复选框**常规属性**页**常规**之前选择的选项卡**重新发送 AS2 消息如果 MDN 不收到**。</span><span class="sxs-lookup"><span data-stu-id="4a972-127">You must select the **Turn ON Reporting** check box on the **General Properties** page of the **General** tab before selecting **Resend AS2 message if MDN not received**.</span></span>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="4a972-128"> 使用跟踪为 AS2 报告以确定何时重新发送 AS2 消息存储的信息。</span><span class="sxs-lookup"><span data-stu-id="4a972-128"> uses tracking information stored for AS2 reporting in order to determine when to resend an AS2 message.</span></span>  
  
      2. <span data-ttu-id="4a972-129">如果**MDN 未收到时重新发送 AS2 消息**选中复选框，选中**替代发送端口设置**若要指定**最小 HTTP 重试间隔**和**HTTP 重试尝试次数**。</span><span class="sxs-lookup"><span data-stu-id="4a972-129">If **Resend AS2 message if MDN not received** check box is selected, check **Override send port settings** to specify the **Minimum HTTP retry interval** and **Number of HTTP retry attempts**.</span></span> <span data-ttu-id="4a972-130">输入一个值**停止尝试 HTTP 重试后**字段来指定最长时间使用 HTTP 适配器进行重试尝试。</span><span class="sxs-lookup"><span data-stu-id="4a972-130">Enter a value for the **Stop attempting HTTP retries after** field to specify the maximum amount of time to attempt retries using the HTTP adapter.</span></span>  
  
   3. <span data-ttu-id="4a972-131">如果所选**请求异步 MDN**复选框并且指定的 URL**回执送达选项 (URL)** 属性，**处置-到通知**文本框中，默认情况下设置为相同的 URL。</span><span class="sxs-lookup"><span data-stu-id="4a972-131">If you selected the **Request asynchronous MDN** check box and specified a URL for **Receipt-Delivery-Option (URL)** property, the **Disposition-Notification-To** text box, is by default set to the same URL.</span></span> <span data-ttu-id="4a972-132">如果未选中**请求异步 MDN**复选框，您必须输入的值**处置-到通知**。</span><span class="sxs-lookup"><span data-stu-id="4a972-132">If you did not select the **Request asynchronous MDN** check box, you must enter a value for **Disposition-Notification-To**.</span></span> <span data-ttu-id="4a972-133">此字段中的值不会在 AS2 处理中使用。</span><span class="sxs-lookup"><span data-stu-id="4a972-133">The value of this field is not used during AS2 processing.</span></span>  
  
5. <span data-ttu-id="4a972-134">单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="4a972-134">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a972-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="4a972-135">See Also</span></span>  
 [<span data-ttu-id="4a972-136">配置 AS2 协议属性</span><span class="sxs-lookup"><span data-stu-id="4a972-136">Configuring AS2 Agreement Properties</span></span>](../core/configuring-as2-agreement-properties.md)