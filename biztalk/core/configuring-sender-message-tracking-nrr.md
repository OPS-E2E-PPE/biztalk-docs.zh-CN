---
title: "配置发件人消息跟踪 (NRR) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e6ca2709-ac4b-48c0-82f8-8a43971a86cb
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1785a5502bc1adb9cc8b9aa7f85b6a4473d21c5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-sender-message-tracking-nrr"></a><span data-ttu-id="56f5d-102">配置发送方消息跟踪（NRR）</span><span class="sxs-lookup"><span data-stu-id="56f5d-102">Configuring Sender Message Tracking (NRR)</span></span>
<span data-ttu-id="56f5d-103">作为此页上的一部分设置，您可以指定是否将出站消息及其确认 (MDN) 存储到不可否认数据库中。</span><span class="sxs-lookup"><span data-stu-id="56f5d-103">As part of the settings on this page, you can specify whether the outbound messages and their acknowledgements (MDNs) are stored in the non-repudiation database.</span></span> <span data-ttu-id="56f5d-104">有关详细信息，请参阅[AS2 处理在 BizTalk Server](../core/as2-processing-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="56f5d-104">For more information, see [AS2 Processing in BizTalk Server](../core/as2-processing-in-biztalk-server.md).</span></span>  
  
 <span data-ttu-id="56f5d-105">若要将消息存储在不可否认数据库中，您必须启用 NRR（接收的不可否认性）作为 AS2 协议属性的一部分。</span><span class="sxs-lookup"><span data-stu-id="56f5d-105">To store messages in the non-repudiation database, the parties must enable NRR (Non-repudiation of receipt) as part of the AS2 agreement properties.</span></span> <span data-ttu-id="56f5d-106">NRR 可确保发送方已验证消息收件人的签名回执。</span><span class="sxs-lookup"><span data-stu-id="56f5d-106">NRR ensures that the sender party has verified the signed receipt from the message recipient.</span></span> <span data-ttu-id="56f5d-107">从理论上讲，NRR 是消息发件人证明消息以未改变的状态到达目的地的不可否认的证据。</span><span class="sxs-lookup"><span data-stu-id="56f5d-107">Conceptually, an NRR is an undeniable proof for the message sender that the message reached the destination unaltered.</span></span> <span data-ttu-id="56f5d-108">仅在数字签名了原始消息和回执时，才能建立 NRR。</span><span class="sxs-lookup"><span data-stu-id="56f5d-108">NRR can be established only when the original message and the receipt are digitally signed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="56f5d-109">如果你清除了所有属性会被都禁用此页上**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="56f5d-109">All the properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  <span data-ttu-id="56f5d-110">仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。</span><span class="sxs-lookup"><span data-stu-id="56f5d-110">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="56f5d-111">例如，如果创建两个参与方 A 方和方 B 和 A 的当事方，清除复选框，则上面的属性列表会禁用上**A 方-> 方 B**单向协议选项卡。</span><span class="sxs-lookup"><span data-stu-id="56f5d-111">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="56f5d-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="56f5d-112">Prerequisites</span></span>  
 <span data-ttu-id="56f5d-113">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="56f5d-113">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-message-tracking-for-outbound-as2-messages-and-inbound-mdn"></a><span data-ttu-id="56f5d-114">若要配置的出站 AS2 消息的消息跟踪和入站的 MDN</span><span class="sxs-lookup"><span data-stu-id="56f5d-114">To configure message tracking for outbound AS2 messages and inbound MDN</span></span>  
  
1.  <span data-ttu-id="56f5d-115">创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。</span><span class="sxs-lookup"><span data-stu-id="56f5d-115">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="56f5d-116">若要更新现有 AS2 协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="56f5d-116">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="56f5d-117">单向协议选项卡上，在**本地主机设置**部分中，单击**发件人消息跟踪 (NRR)**。</span><span class="sxs-lookup"><span data-stu-id="56f5d-117">On a one-way agreement tab, under **Local Host Settings** section, click **Sender Message Tracking (NRR)**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="56f5d-118">要保障接收的不可否认性，必须对消息进行验证和确保消息的完整性。</span><span class="sxs-lookup"><span data-stu-id="56f5d-118">To guarantee non-repudiation of receipt, you must establish the authentication and integrity of the message.</span></span> <span data-ttu-id="56f5d-119">实现此目的的推荐方法是对消息使用数字签名。</span><span class="sxs-lookup"><span data-stu-id="56f5d-119">The recommended way of doing so is by using a digital signature on the message.</span></span> <span data-ttu-id="56f5d-120">因此，如果你选择任何要在不可否认性数据库中存储消息的属性，你应该对消息进行签名通过选择**应对消息进行签名**属性**验证**页。</span><span class="sxs-lookup"><span data-stu-id="56f5d-120">As a result, if you select any of the properties to store messages in the non-repudiation database, you should sign the message by selecting the **Message should be signed** property on the **Validation** page.</span></span>  
  
3.  <span data-ttu-id="56f5d-121">选择**为出站的已编码 AS2 消息启用 NRR**将出站的已编码的 AS2 消息存储在不可否认性数据库。</span><span class="sxs-lookup"><span data-stu-id="56f5d-121">Select **NRR enabled for outbound encoded AS2 messages** to store outbound encoded AS2 messages in the non-repudiation database.</span></span>  
  
4.  <span data-ttu-id="56f5d-122">选择**为出站的已解码 AS2 消息启用 NRR**将出站的已解码的 AS2 消息存储在不可否认性数据库。</span><span class="sxs-lookup"><span data-stu-id="56f5d-122">Select **NRR enabled for outbound decoded AS2 messages** to store outbound decoded AS2 messages in the non-repudiation database.</span></span>  
  
5.  <span data-ttu-id="56f5d-123">选择**为入站的 MDN 启用 NRR**将入站的 MDN 存储在不可否认性数据库。</span><span class="sxs-lookup"><span data-stu-id="56f5d-123">Select **NRR enabled for inbound MDN** to store inbound MDN in the non-repudiation database.</span></span>  
  
6.  <span data-ttu-id="56f5d-124">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="56f5d-124">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56f5d-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56f5d-125">See Also</span></span>  
 [<span data-ttu-id="56f5d-126">配置本地主机设置 (AS2)</span><span class="sxs-lookup"><span data-stu-id="56f5d-126">Configuring Local Host Settings (AS2)</span></span>](../core/configuring-local-host-settings-as2.md)