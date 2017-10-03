---
title: "配置验证 (AS2) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1ff22dc8-a544-46f9-86fb-f6845e2dfe46
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e135d048f7dede032803b5830faec4570fa1f4d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-validation-as2"></a><span data-ttu-id="41c7d-102">配置验证（AS2）</span><span class="sxs-lookup"><span data-stu-id="41c7d-102">Configuring Validation (AS2)</span></span>
<span data-ttu-id="41c7d-103">在合作伙伴协议中，您必须指定验证设置来验证入站 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="41c7d-103">In the partner agreement, you must specify the validation settings to validate the inbound AS2 message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="41c7d-104">没有属性上将禁用**A 方-> 方 B**单向协议选项卡，如果你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**复选框当事方 a。但是，将以下属性禁用中相同页面上**B 方-> A 方**选项卡上，如果创建 a 方。 时选中复选框</span><span class="sxs-lookup"><span data-stu-id="41c7d-104">No properties are disabled on **Party A->Party B** one-way agreement tab if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box for Party A. However, the following properties are disabled on the same page in the **Party B->Party A** tab if you selected the check box while creating Party A.</span></span>  
>   
>  -   <span data-ttu-id="41c7d-105">**使用验证和 MDN 的协议设置，而不是消息标头**</span><span class="sxs-lookup"><span data-stu-id="41c7d-105">**Use agreement settings for validation and MDN instead of message header**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="41c7d-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="41c7d-106">Prerequisites</span></span>  
 <span data-ttu-id="41c7d-107">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="41c7d-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-validation-properties"></a><span data-ttu-id="41c7d-108">配置验证属性</span><span class="sxs-lookup"><span data-stu-id="41c7d-108">To configure validation properties</span></span>  
  
1.  <span data-ttu-id="41c7d-109">创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。</span><span class="sxs-lookup"><span data-stu-id="41c7d-109">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="41c7d-110">若要更新现有 AS2 协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="41c7d-110">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="41c7d-111">单向协议选项卡上，单击**验证**。</span><span class="sxs-lookup"><span data-stu-id="41c7d-111">On a one-way agreement tab, click **Validation**.</span></span>  
  
3.  <span data-ttu-id="41c7d-112">选择**使用验证和 MDN 的协议设置，而不是消息标头**复选框，如果你想[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]验证数字签名、 压缩和加密的传入消息，基于中的设置协议。</span><span class="sxs-lookup"><span data-stu-id="41c7d-112">Select the **Use agreement settings for validation and MDN instead of message header** check box if you want [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] validate the digital signature, compression, and encryption of the incoming message, based upon the settings in the agreement.</span></span> <span data-ttu-id="41c7d-113">如果已清空该复选框，则将会根据消息 AS2 标头中的属性来验证消息（而不是根据协议属性）以确定此过程。</span><span class="sxs-lookup"><span data-stu-id="41c7d-113">If the check box is cleared, the messages will be validated against the properties in the message AS2 header instead of the agreement properties to determine this processing.</span></span> <span data-ttu-id="41c7d-114">AS2 标头的列表，请参阅[AS2 消息](../core/as2-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="41c7d-114">For a list of AS2 headers, see [AS2 Messages](../core/as2-messages.md).</span></span>  
  
4.  <span data-ttu-id="41c7d-115">选择**应对消息进行签名**复选框以确保入站的消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="41c7d-115">Select the **Message should be signed** check box to ensure that the inbound message is signed.</span></span>  
  
5.  <span data-ttu-id="41c7d-116">选择**应对消息进行压缩**复选框以确保压缩的入站的消息。</span><span class="sxs-lookup"><span data-stu-id="41c7d-116">Select the **Message should be compressed** check box to ensure that the inbound message is compressed.</span></span>  
  
6.  <span data-ttu-id="41c7d-117">选择**应对消息进行加密**复选框以确保入站的消息进行加密。</span><span class="sxs-lookup"><span data-stu-id="41c7d-117">Select the **Message should be encrypted** check box to ensure that the inbound message is encrypted.</span></span> <span data-ttu-id="41c7d-118">选择从的加密算法**加密算法**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="41c7d-118">Select the encryption algorithm from the **Encryption Algorithm** drop-down list.</span></span> 

    <span data-ttu-id="41c7d-119">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]和更高版本**，AES 支持将自动包含。</span><span class="sxs-lookup"><span data-stu-id="41c7d-119">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] and newer versions**, AES support is automatically included.</span></span> <span data-ttu-id="41c7d-120">选项包括 DES3、 RC2，AES128 （默认值）、 AES192 和 AES256。</span><span class="sxs-lookup"><span data-stu-id="41c7d-120">Options include DES3, RC2, AES128 (default), AES192, and AES256.</span></span>
    
    <span data-ttu-id="41c7d-121">有关以前[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]版本，选项为 DES3 和 RC2。</span><span class="sxs-lookup"><span data-stu-id="41c7d-121">For previous [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] versions, the options are DES3 and RC2.</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="41c7d-122">仅当设置了正确的属性后，AS2 接收管道才会对数字签名进行验证，对消息进行解压缩或解密。</span><span class="sxs-lookup"><span data-stu-id="41c7d-122">Only if the appropriate property is set, the AS2 receive pipeline verifies the digital signature, decompresses the message, or decrypts the message.</span></span> <span data-ttu-id="41c7d-123">如果**使用验证和 MDN 的协议设置，而不是消息标头**选择属性和消息具有用于签名、 压缩和加密比在协议中选择不同的传输属性属性，然后 AS2 解码器将挂起消息，并且会产生错误。</span><span class="sxs-lookup"><span data-stu-id="41c7d-123">If the **Use agreement settings for validation and MDN instead of message header** property is selected and the message has different transport properties for signing, compression, and encryption than those selected on the agreement properties, then the AS2 Decoder will suspend the message and post an error.</span></span>  
  
7.  <span data-ttu-id="41c7d-124">选择**检查证书吊销列表**复选框，以确定要用于验证传入消息的证书是否已包括在证书吊销列表，表示，它已被吊销，或者，是否到期日期已过。</span><span class="sxs-lookup"><span data-stu-id="41c7d-124">Select the **Check Certification Revocation List** check box to determine whether the certificate to be used in validating an incoming message has been included in the Certification Revocation List, indicating that it has been revoked, or whether the expiration date has passed.</span></span> <span data-ttu-id="41c7d-125">如果已吊销，BizTalk Server 将不会对消息解密，但会挂起消息。</span><span class="sxs-lookup"><span data-stu-id="41c7d-125">If so, BizTalk Server will not decrypt the message, but will suspend it.</span></span> <span data-ttu-id="41c7d-126">如果清除此属性，BizTalk Server 将不会执行此项检查。</span><span class="sxs-lookup"><span data-stu-id="41c7d-126">If this property is cleared, BizTalk Server will not perform this check.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="41c7d-127">存在与检索和搜索证书吊销列表有关的延迟时间。</span><span class="sxs-lookup"><span data-stu-id="41c7d-127">There is a latency involved with retrieving and searching the certificate revocation list.</span></span>  
  
8.  <span data-ttu-id="41c7d-128">选择**检查中的重复消息**复选框，以确定传入消息是否为重复的以前接收消息。</span><span class="sxs-lookup"><span data-stu-id="41c7d-128">Select the **Check for duplicate messages within** check box to determine if the incoming message is a duplicate of previously received messages.</span></span>  
  
     <span data-ttu-id="41c7d-129">如果你选中**检查中的重复消息**属性，设置**天**属性以指示以前接收的消息时检查要使用的跨度复制，检查**挂起重复消息**属性以指示应挂起重复消息。</span><span class="sxs-lookup"><span data-stu-id="41c7d-129">If you checked the **Check for duplicate messages within** property, set the **days** property to indicate the span of previously received messages to use when checking for duplicates; check the **Suspend duplicate messages** property to indicate that duplicate messages should be suspended.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="41c7d-130">**AS2-从**和**AS2-到**字段用于确定消息是否为重复。</span><span class="sxs-lookup"><span data-stu-id="41c7d-130">The **AS2-From** and **AS2-To** fields are used to determine if a message is a duplicate.</span></span> <span data-ttu-id="41c7d-131">如果该消息所包含的这些字段的值与先前接收的消息的这些字段值相同，那么，即使其他标头或负载不同，该消息也会被标记为重复消息。</span><span class="sxs-lookup"><span data-stu-id="41c7d-131">If the message contains the same values for these fields as a previously received message, it will be marked as duplicate even if the other headers or the payload is different.</span></span>  
  
9. <span data-ttu-id="41c7d-132">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="41c7d-132">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41c7d-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41c7d-133">See Also</span></span>  
 [<span data-ttu-id="41c7d-134">配置 AS2 协议属性</span><span class="sxs-lookup"><span data-stu-id="41c7d-134">Configuring AS2 Agreement Properties</span></span>](../core/configuring-as2-agreement-properties.md)