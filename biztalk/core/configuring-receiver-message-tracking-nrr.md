---
title: 配置接收方邮件跟踪 (NRR) |Microsoft 文档
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
ms.openlocfilehash: 942a9c62e69f9f39bf445f0b3028a4e6707f48d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233357"
---
# <a name="configuring-receiver-message-tracking-nrr"></a><span data-ttu-id="a4c92-102">配置接收方消息跟踪（NRR）</span><span class="sxs-lookup"><span data-stu-id="a4c92-102">Configuring Receiver Message Tracking (NRR)</span></span>
<span data-ttu-id="a4c92-103">作为本页设置的一部分，您可以指定是否将入站消息及其确认 (MDN) 存储在不可否认数据库中。</span><span class="sxs-lookup"><span data-stu-id="a4c92-103">As part of the settings on this page, you can specify whether the inbound messages and their acknowledgements (MDNs) are stored in the non-repudiation database.</span></span> <span data-ttu-id="a4c92-104">有关详细信息，请参阅[AS2 处理在 BizTalk Server](../core/as2-processing-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="a4c92-104">For more information, see [AS2 Processing in BizTalk Server](../core/as2-processing-in-biztalk-server.md).</span></span>  
  
 <span data-ttu-id="a4c92-105">若要将消息存储在不可否认数据库中，您必须启用 NRR（接收的不可否认性）作为 AS2 协议属性的一部分。</span><span class="sxs-lookup"><span data-stu-id="a4c92-105">To store messages in the non-repudiation database, the parties must enable NRR (Non-repudiation of receipt) as part of the AS2 agreement properties.</span></span> <span data-ttu-id="a4c92-106">NRR 可确保发送方已验证消息收件人的签名回执。</span><span class="sxs-lookup"><span data-stu-id="a4c92-106">NRR ensures that the sender party has verified the signed receipt from the message recipient.</span></span> <span data-ttu-id="a4c92-107">从理论上讲，NRR 是消息发件人证明消息以未改变的状态到达目的地的不可否认的证据。</span><span class="sxs-lookup"><span data-stu-id="a4c92-107">Conceptually, an NRR is an undeniable proof for the message sender that the message reached the destination unaltered.</span></span> <span data-ttu-id="a4c92-108">仅在数字签名了原始消息和回执时，才能建立 NRR。</span><span class="sxs-lookup"><span data-stu-id="a4c92-108">NRR can be established only when the original message and the receipt are digitally signed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a4c92-109">没有属性上将禁用**A 方-> 方 B**单向协议选项卡，如果你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**复选框当事方 a。但是，将所有属性都禁用中相同页面上**B 方-> A 方**选项卡上，如果创建 a 方。 时选中复选框</span><span class="sxs-lookup"><span data-stu-id="a4c92-109">No properties are disabled on **Party A->Party B** one-way agreement tab if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box for Party A. However, all the properties are disabled on the same page in the **Party B->Party A** tab if you selected the check box while creating Party A.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a4c92-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="a4c92-110">Prerequisites</span></span>  
 <span data-ttu-id="a4c92-111">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="a4c92-111">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-message-tracking-for-inbound-as2-messages-and-outbound-mdn"></a><span data-ttu-id="a4c92-112">配置入站 AS2 消息和出站 MDN 的消息跟踪</span><span class="sxs-lookup"><span data-stu-id="a4c92-112">To configure message tracking for inbound AS2 messages and outbound MDN</span></span>  
  
1.  <span data-ttu-id="a4c92-113">创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。</span><span class="sxs-lookup"><span data-stu-id="a4c92-113">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="a4c92-114">若要更新现有 AS2 协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="a4c92-114">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="a4c92-115">单向协议选项卡上，在**本地主机设置**部分中，单击**接收方消息跟踪 (NRR)**。</span><span class="sxs-lookup"><span data-stu-id="a4c92-115">On a one-way agreement tab, under **Local Host Settings** section, click **Receiver Message Tracking (NRR)**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a4c92-116">要保障接收的不可否认性，必须对消息进行验证和确保消息的完整性。</span><span class="sxs-lookup"><span data-stu-id="a4c92-116">To guarantee non-repudiation of receipt, you must establish the authentication and integrity of the message.</span></span> <span data-ttu-id="a4c92-117">实现此目的的推荐方法是对消息使用数字签名。</span><span class="sxs-lookup"><span data-stu-id="a4c92-117">The recommended way of doing so is by using a digital signature on the message.</span></span> <span data-ttu-id="a4c92-118">因此，如果你选择任何要在不可否认性数据库中存储消息的属性，你应该对消息进行签名通过选择**应对消息进行签名**属性**验证**页。</span><span class="sxs-lookup"><span data-stu-id="a4c92-118">As a result, if you select any of the properties to store messages in the non-repudiation database, you should sign the message by selecting the **Message should be signed** property on the **Validation** page.</span></span>  
  
3.  <span data-ttu-id="a4c92-119">选择**为入站的已编码 AS2 消息启用 NRR**将出站的已编码的 AS2 消息存储在不可否认性数据库。</span><span class="sxs-lookup"><span data-stu-id="a4c92-119">Select **NRR enabled for inbound encoded AS2 messages** to store outbound encoded AS2 messages in the non-repudiation database.</span></span>  
  
4.  <span data-ttu-id="a4c92-120">选择**为入站的已解码 AS2 消息启用 NRR**将出站的已解码的 AS2 消息存储在不可否认性数据库。</span><span class="sxs-lookup"><span data-stu-id="a4c92-120">Select **NRR enabled for inbound decoded AS2 messages** to store outbound decoded AS2 messages in the non-repudiation database.</span></span>  
  
5.  <span data-ttu-id="a4c92-121">选择**为出站的 MDN 启用 NRR**将入站的 MDN 存储在不可否认性数据库。</span><span class="sxs-lookup"><span data-stu-id="a4c92-121">Select **NRR enabled for outbound MDN** to store inbound MDN in the non-repudiation database.</span></span>  
  
6.  <span data-ttu-id="a4c92-122">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="a4c92-122">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4c92-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4c92-123">See Also</span></span>  
 [<span data-ttu-id="a4c92-124">配置本地主机设置 (AS2)</span><span class="sxs-lookup"><span data-stu-id="a4c92-124">Configuring Local Host Settings (AS2)</span></span>](../core/configuring-local-host-settings-as2.md)