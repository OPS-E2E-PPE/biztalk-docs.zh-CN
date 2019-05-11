---
title: 配置验证 (AS2) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1ff22dc8-a544-46f9-86fb-f6845e2dfe46
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ee93a214730303b4ce510d0da8d4d08e2073990
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390583"
---
# <a name="configuring-validation-as2"></a><span data-ttu-id="5f2d6-102">配置验证 (AS2)</span><span class="sxs-lookup"><span data-stu-id="5f2d6-102">Configuring Validation (AS2)</span></span>
<span data-ttu-id="5f2d6-103">在合作伙伴协议中，必须指定验证设置来验证入站的 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="5f2d6-103">In the partner agreement, you must specify the validation settings to validate the inbound AS2 message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5f2d6-104">没有属性上将禁用**参与方 A-> 参与方 B**单向协议选项卡，如果您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**复选框为参与方 a。但是，以下属性中的相同页上禁用**参与方 B-> 参与方 A**选项卡上，如果您创建参与方 A.时选中复选框</span><span class="sxs-lookup"><span data-stu-id="5f2d6-104">No properties are disabled on **Party A->Party B** one-way agreement tab if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box for Party A. However, the following properties are disabled on the same page in the **Party B->Party A** tab if you selected the check box while creating Party A.</span></span>  
>   
>  -   <span data-ttu-id="5f2d6-105">**使用的验证和 MDN 的协议设置而非消息标头**</span><span class="sxs-lookup"><span data-stu-id="5f2d6-105">**Use agreement settings for validation and MDN instead of message header**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5f2d6-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="5f2d6-106">Prerequisites</span></span>  
 <span data-ttu-id="5f2d6-107">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="5f2d6-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-validation-properties"></a><span data-ttu-id="5f2d6-108">若要配置验证属性</span><span class="sxs-lookup"><span data-stu-id="5f2d6-108">To configure validation properties</span></span>  
  
1. <span data-ttu-id="5f2d6-109">创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。</span><span class="sxs-lookup"><span data-stu-id="5f2d6-109">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="5f2d6-110">若要更新现有 AS2 协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="5f2d6-110">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2. <span data-ttu-id="5f2d6-111">在单向协议选项卡上，单击**验证**。</span><span class="sxs-lookup"><span data-stu-id="5f2d6-111">On a one-way agreement tab, click **Validation**.</span></span>  
  
3. <span data-ttu-id="5f2d6-112">选择**使用的验证和 MDN 的协议设置而非消息标头**复选框，如果你想[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]验证数字签名、 压缩和加密的传入消息，根据中的设置协议。</span><span class="sxs-lookup"><span data-stu-id="5f2d6-112">Select the **Use agreement settings for validation and MDN instead of message header** check box if you want [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] validate the digital signature, compression, and encryption of the incoming message, based upon the settings in the agreement.</span></span> <span data-ttu-id="5f2d6-113">如果清除该复选框，则将根据消息 AS2 标头而不是协议属性来确定此处理过程中的属性来验证消息。</span><span class="sxs-lookup"><span data-stu-id="5f2d6-113">If the check box is cleared, the messages will be validated against the properties in the message AS2 header instead of the agreement properties to determine this processing.</span></span> <span data-ttu-id="5f2d6-114">有关 AS2 标头的列表，请参阅[AS2 消息](../core/as2-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="5f2d6-114">For a list of AS2 headers, see [AS2 Messages](../core/as2-messages.md).</span></span>  
  
4. <span data-ttu-id="5f2d6-115">选择**应对消息进行签名**复选框以确保对入站的消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="5f2d6-115">Select the **Message should be signed** check box to ensure that the inbound message is signed.</span></span>  
  
5. <span data-ttu-id="5f2d6-116">选择**应对消息进行压缩**复选框以确保对入站的消息进行压缩。</span><span class="sxs-lookup"><span data-stu-id="5f2d6-116">Select the **Message should be compressed** check box to ensure that the inbound message is compressed.</span></span>  
  
6. <span data-ttu-id="5f2d6-117">选择**应对消息进行加密**复选框以确保对入站的消息进行加密。</span><span class="sxs-lookup"><span data-stu-id="5f2d6-117">Select the **Message should be encrypted** check box to ensure that the inbound message is encrypted.</span></span> <span data-ttu-id="5f2d6-118">选择中的加密算法**加密算法**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="5f2d6-118">Select the encryption algorithm from the **Encryption Algorithm** drop-down list.</span></span> 

   <span data-ttu-id="5f2d6-119">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]及更高版本**，则会自动包括 AES 支持。</span><span class="sxs-lookup"><span data-stu-id="5f2d6-119">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] and newer versions**, AES support is automatically included.</span></span> <span data-ttu-id="5f2d6-120">选项包括 DES3、 RC2，AES128 （默认）、 AES192 和 AES256。</span><span class="sxs-lookup"><span data-stu-id="5f2d6-120">Options include DES3, RC2, AES128 (default), AES192, and AES256.</span></span>
    
   <span data-ttu-id="5f2d6-121">对于以前[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]版本，选项为 DES3 和 RC2。</span><span class="sxs-lookup"><span data-stu-id="5f2d6-121">For previous [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] versions, the options are DES3 and RC2.</span></span>
  
   > [!NOTE]
   >  <span data-ttu-id="5f2d6-122">只有设置相应属性时，如果 AS2 接收管道验证数字签名、 消息，进行解压缩或解密消息。</span><span class="sxs-lookup"><span data-stu-id="5f2d6-122">Only if the appropriate property is set, the AS2 receive pipeline verifies the digital signature, decompresses the message, or decrypts the message.</span></span> <span data-ttu-id="5f2d6-123">如果**使用的验证和 MDN 的协议设置而非消息标头**选择属性，该消息具有签名、 压缩和加密的协议上选择的不同的传输属性属性，则 AS2 解码器将挂起消息并发布错误。</span><span class="sxs-lookup"><span data-stu-id="5f2d6-123">If the **Use agreement settings for validation and MDN instead of message header** property is selected and the message has different transport properties for signing, compression, and encryption than those selected on the agreement properties, then the AS2 Decoder will suspend the message and post an error.</span></span>  
  
7. <span data-ttu-id="5f2d6-124">选择**检查证书吊销列表**复选框，以确定要用于验证传入消息的证书是否已包含在该值指示是否已被吊销，证书吊销列表或是否已超过到期日期。</span><span class="sxs-lookup"><span data-stu-id="5f2d6-124">Select the **Check Certification Revocation List** check box to determine whether the certificate to be used in validating an incoming message has been included in the Certification Revocation List, indicating that it has been revoked, or whether the expiration date has passed.</span></span> <span data-ttu-id="5f2d6-125">如果是这样，BizTalk Server 不会解密该消息，但将挂起消息。</span><span class="sxs-lookup"><span data-stu-id="5f2d6-125">If so, BizTalk Server will not decrypt the message, but will suspend it.</span></span> <span data-ttu-id="5f2d6-126">如果清除此属性，则 BizTalk Server 将不执行此检查。</span><span class="sxs-lookup"><span data-stu-id="5f2d6-126">If this property is cleared, BizTalk Server will not perform this check.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5f2d6-127">检索和搜索证书吊销列表所涉及的是延迟。</span><span class="sxs-lookup"><span data-stu-id="5f2d6-127">There is a latency involved with retrieving and searching the certificate revocation list.</span></span>  
  
8. <span data-ttu-id="5f2d6-128">选择**检查重复消息**复选框，以确定传入消息是否为重复的以前收到的消息。</span><span class="sxs-lookup"><span data-stu-id="5f2d6-128">Select the **Check for duplicate messages within** check box to determine if the incoming message is a duplicate of previously received messages.</span></span>  
  
    <span data-ttu-id="5f2d6-129">如果您选中**检查重复消息**属性，则设置**天**属性以指示以前接收的消息时检查要使用的跨度复制，检查**挂起重复消息**属性以指示应挂起重复消息。</span><span class="sxs-lookup"><span data-stu-id="5f2d6-129">If you checked the **Check for duplicate messages within** property, set the **days** property to indicate the span of previously received messages to use when checking for duplicates; check the **Suspend duplicate messages** property to indicate that duplicate messages should be suspended.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5f2d6-130">**AS2-从**并**AS2-到**字段用于确定消息是否重复。</span><span class="sxs-lookup"><span data-stu-id="5f2d6-130">The **AS2-From** and **AS2-To** fields are used to determine if a message is a duplicate.</span></span> <span data-ttu-id="5f2d6-131">如果消息包含为这些字段与先前接收的消息相同的值，它将标记为重复这是即使其他标头或负载不同。</span><span class="sxs-lookup"><span data-stu-id="5f2d6-131">If the message contains the same values for these fields as a previously received message, it will be marked as duplicate even if the other headers or the payload is different.</span></span>  
  
9. <span data-ttu-id="5f2d6-132">单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="5f2d6-132">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f2d6-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="5f2d6-133">See Also</span></span>  
 [<span data-ttu-id="5f2d6-134">配置 AS2 协议属性</span><span class="sxs-lookup"><span data-stu-id="5f2d6-134">Configuring AS2 Agreement Properties</span></span>](../core/configuring-as2-agreement-properties.md)