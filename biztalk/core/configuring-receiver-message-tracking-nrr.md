---
title: 配置接收方消息跟踪 (NRR) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce30737a-341b-45be-81a0-a7336219185e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05b57c9b032fb557c23e7ec11a6e6f60fd6692b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355282"
---
# <a name="configuring-receiver-message-tracking-nrr"></a><span data-ttu-id="d0328-102">配置接收方消息跟踪 (NRR)</span><span class="sxs-lookup"><span data-stu-id="d0328-102">Configuring Receiver Message Tracking (NRR)</span></span>
<span data-ttu-id="d0328-103">作为此页上设置的一部分，可以指定是否在不可否认数据库中存储入站的消息和及其确认 (Mdn)。</span><span class="sxs-lookup"><span data-stu-id="d0328-103">As part of the settings on this page, you can specify whether the inbound messages and their acknowledgements (MDNs) are stored in the non-repudiation database.</span></span> <span data-ttu-id="d0328-104">有关详细信息，请参阅[BizTalk Server 中的 AS2 处理](../core/as2-processing-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="d0328-104">For more information, see [AS2 Processing in BizTalk Server](../core/as2-processing-in-biztalk-server.md).</span></span>  
  
 <span data-ttu-id="d0328-105">若要将消息存储在不可否认数据库中，您必须启用 NRR （不可否认接收的） 作为 AS2 协议属性的一部分。</span><span class="sxs-lookup"><span data-stu-id="d0328-105">To store messages in the non-repudiation database, the parties must enable NRR (Non-repudiation of receipt) as part of the AS2 agreement properties.</span></span> <span data-ttu-id="d0328-106">NRR 可确保发送方已验证消息接收方的签名的回执。</span><span class="sxs-lookup"><span data-stu-id="d0328-106">NRR ensures that the sender party has verified the signed receipt from the message recipient.</span></span> <span data-ttu-id="d0328-107">从概念上讲，NRR 是消息发件人消息到达目标不变的确凿无疑的证据。</span><span class="sxs-lookup"><span data-stu-id="d0328-107">Conceptually, an NRR is an undeniable proof for the message sender that the message reached the destination unaltered.</span></span> <span data-ttu-id="d0328-108">仅当原始消息和接收经过数字签名时，才能建立 NRR。</span><span class="sxs-lookup"><span data-stu-id="d0328-108">NRR can be established only when the original message and the receipt are digitally signed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d0328-109">没有属性上将禁用**参与方 A-> 参与方 B**单向协议选项卡，如果您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**复选框为参与方 a。但是，禁用中相同页面上的所有属性**参与方 B-> 参与方 A**选项卡上，如果您创建参与方 A.时选中复选框</span><span class="sxs-lookup"><span data-stu-id="d0328-109">No properties are disabled on **Party A->Party B** one-way agreement tab if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box for Party A. However, all the properties are disabled on the same page in the **Party B->Party A** tab if you selected the check box while creating Party A.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d0328-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="d0328-110">Prerequisites</span></span>  
 <span data-ttu-id="d0328-111">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="d0328-111">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-message-tracking-for-inbound-as2-messages-and-outbound-mdn"></a><span data-ttu-id="d0328-112">若要配置入站的 AS2 消息和出站 MDN 的消息跟踪</span><span class="sxs-lookup"><span data-stu-id="d0328-112">To configure message tracking for inbound AS2 messages and outbound MDN</span></span>  
  
1.  <span data-ttu-id="d0328-113">创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。</span><span class="sxs-lookup"><span data-stu-id="d0328-113">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="d0328-114">若要更新现有 AS2 协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="d0328-114">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="d0328-115">在单向协议选项卡下**本地主机设置**部分中，单击**接收方消息跟踪 (NRR)**。</span><span class="sxs-lookup"><span data-stu-id="d0328-115">On a one-way agreement tab, under **Local Host Settings** section, click **Receiver Message Tracking (NRR)**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d0328-116">若要确保不可否认性的回执，必须建立身份验证和确保消息的完整性。</span><span class="sxs-lookup"><span data-stu-id="d0328-116">To guarantee non-repudiation of receipt, you must establish the authentication and integrity of the message.</span></span> <span data-ttu-id="d0328-117">推荐的方法来这样做因此是对消息使用数字签名。</span><span class="sxs-lookup"><span data-stu-id="d0328-117">The recommended way of doing so is by using a digital signature on the message.</span></span> <span data-ttu-id="d0328-118">因此，如果您选择任何要在不可否认数据库中存储消息的属性，你应登录消息通过选择**应对消息进行签名**上的属性**验证**页。</span><span class="sxs-lookup"><span data-stu-id="d0328-118">As a result, if you select any of the properties to store messages in the non-repudiation database, you should sign the message by selecting the **Message should be signed** property on the **Validation** page.</span></span>  
  
3.  <span data-ttu-id="d0328-119">选择**已为入站编码 AS2 消息启用 NRR**的不可否认数据库中存储出站编码的 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="d0328-119">Select **NRR enabled for inbound encoded AS2 messages** to store outbound encoded AS2 messages in the non-repudiation database.</span></span>  
  
4.  <span data-ttu-id="d0328-120">选择**已为入站解码 AS2 消息启用 NRR**的不可否认数据库中存储解码后的出站 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="d0328-120">Select **NRR enabled for inbound decoded AS2 messages** to store outbound decoded AS2 messages in the non-repudiation database.</span></span>  
  
5.  <span data-ttu-id="d0328-121">选择**对出站 MDN 启用 NRR**来将入站的 MDN 存储在不可否认数据库中。</span><span class="sxs-lookup"><span data-stu-id="d0328-121">Select **NRR enabled for outbound MDN** to store inbound MDN in the non-repudiation database.</span></span>  
  
6.  <span data-ttu-id="d0328-122">单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="d0328-122">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0328-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0328-123">See Also</span></span>  
 [<span data-ttu-id="d0328-124">配置本地主机设置 (AS2)</span><span class="sxs-lookup"><span data-stu-id="d0328-124">Configuring Local Host Settings (AS2)</span></span>](../core/configuring-local-host-settings-as2.md)