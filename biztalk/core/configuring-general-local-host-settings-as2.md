---
title: "配置常规本地主机设置 (AS2) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 980daac2-8387-44cc-ae55-38639f759668
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de5e5c076e6b245e4a662f8132d027e927df6142
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-general-local-host-settings-as2"></a><span data-ttu-id="c306c-102">配置常规本地主机设置（AS2）</span><span class="sxs-lookup"><span data-stu-id="c306c-102">Configuring General Local Host Settings (AS2)</span></span>
<span data-ttu-id="c306c-103">作为本地主机常规设置的一部分，可以指定 AS2 消息的内容类型以及是否将文件名保留为 AS2 消息标头的一部分。</span><span class="sxs-lookup"><span data-stu-id="c306c-103">As part of the local host general settings, you can specify the content type of the AS2 messages and whether the file name is preserved as part of the AS2 message header.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c306c-104">如果你清除了所有属性会被都禁用此页上**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="c306c-104">All the properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  <span data-ttu-id="c306c-105">仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。</span><span class="sxs-lookup"><span data-stu-id="c306c-105">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="c306c-106">例如，如果创建两个参与方 A 方和方 B 和 A 的当事方，清除复选框，则上面的属性列表会禁用上**A 方-> 方 B**单向协议选项卡。</span><span class="sxs-lookup"><span data-stu-id="c306c-106">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c306c-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="c306c-107">Prerequisites</span></span>  
 <span data-ttu-id="c306c-108">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="c306c-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-the-general-settings"></a><span data-ttu-id="c306c-109">配置常规设置</span><span class="sxs-lookup"><span data-stu-id="c306c-109">To configure the general settings</span></span>  
  
1.  <span data-ttu-id="c306c-110">创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。</span><span class="sxs-lookup"><span data-stu-id="c306c-110">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="c306c-111">若要更新现有 AS2 协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="c306c-111">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="c306c-112">单向协议选项卡上，在**本地主机设置**部分中，单击**常规**。</span><span class="sxs-lookup"><span data-stu-id="c306c-112">On a one-way agreement tab, under **Local Host Settings** section, click **General**.</span></span>  
  
3.  <span data-ttu-id="c306c-113">选择**发送消息之前检查证书吊销列表**复选框，以确定是否已在证书吊销列表中，包含要用于对传出消息进行签名的证书，该值指示它已被吊销，或是否超过到期日期。</span><span class="sxs-lookup"><span data-stu-id="c306c-113">Select the **Check Certification Revocation List before sending the message** check box to determine whether the certificate to be used in signing an outgoing messages has been included in the Certification Revocation List, indicating that it has been revoked, or whether the expiration date has passed.</span></span> <span data-ttu-id="c306c-114">如果是这样，BizTalk 服务器不会加密消息，但它时将挂起。</span><span class="sxs-lookup"><span data-stu-id="c306c-114">If so, BizTalk Server will not encrypt the message, but will suspend it.</span></span> <span data-ttu-id="c306c-115">如果清除此属性，BizTalk Server 将不会执行此项检查。</span><span class="sxs-lookup"><span data-stu-id="c306c-115">If this property is cleared, BizTalk Server will not perform this check.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c306c-116">存在与检索和搜索证书吊销列表有关的延迟时间。</span><span class="sxs-lookup"><span data-stu-id="c306c-116">There is a latency involved with retrieving and searching the certificate revocation list.</span></span>  
  
4.  <span data-ttu-id="c306c-117">有关**默认内容类型**，选择当事方必须使用传出的 AS2 消息的默认内容类型。</span><span class="sxs-lookup"><span data-stu-id="c306c-117">For **Default content type**, select the default content type that the party must use for an outgoing AS2 message.</span></span> <span data-ttu-id="c306c-118">如果`ContentType`属性设置的消息正文部分，设置将用于生成传出的消息; 否则为上下文中的值**默认内容类型**使用属性。</span><span class="sxs-lookup"><span data-stu-id="c306c-118">If the `ContentType` property is set in the context for a message body part, that setting is used to generate the outgoing message; otherwise, the value of this **Default content type** property is used.</span></span>  
  
5.  <span data-ttu-id="c306c-119">选择**MIME 标头中的传输文件名**复选框以将文件名作为出站 AS2 消息的 MIME 标头的一部分发送。</span><span class="sxs-lookup"><span data-stu-id="c306c-119">Select the **Transmit file name in MIME header** check box to send a file name as part of the MIME header for the outbound AS2 message.</span></span> <span data-ttu-id="c306c-120">若要指定的文件名称，选择**指定文件名**或**使系统生成文件名**。</span><span class="sxs-lookup"><span data-stu-id="c306c-120">To specify the file name, select **Specify file name** or **Have system generate file name**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c306c-121">选择**使系统生成文件名**将生成新的 GUID 值作为发送 AS2 消息中每个附件的文件名称。</span><span class="sxs-lookup"><span data-stu-id="c306c-121">Selecting **Have system generate file name** will generate a new GUID value as the file name of each attachment sent in the AS2 message.</span></span>  
  
6.  <span data-ttu-id="c306c-122">如果你选择**指定文件名**，输入中的字符串值或上下文属性**指定文件名**字段。</span><span class="sxs-lookup"><span data-stu-id="c306c-122">If you selected **Specify file name**, enter a string value or context property in the **Specify file name** field.</span></span> <span data-ttu-id="c306c-123">你还可以启用**挂起消息，如果找不到上下文属性 （例如 %属性 %）**挂起消息，如果所选的上下文属性不存在的出站消息。</span><span class="sxs-lookup"><span data-stu-id="c306c-123">You can also enable **Suspend message if context property (e.g. %property%) not found** to suspend the message if the selected context property does not exist for the outbound message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c306c-124">若要指定上下文属性，请将 %字符的属性名称。</span><span class="sxs-lookup"><span data-stu-id="c306c-124">To specify a context-property, enclose the property name with the % character.</span></span> <span data-ttu-id="c306c-125">例如， `%FILE.ReceivedFileName%`。</span><span class="sxs-lookup"><span data-stu-id="c306c-125">For example, `%FILE.ReceivedFileName%`.</span></span>  
  
7.  <span data-ttu-id="c306c-126">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="c306c-126">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c306c-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c306c-127">See Also</span></span>  
 [<span data-ttu-id="c306c-128">配置本地主机设置 (AS2)</span><span class="sxs-lookup"><span data-stu-id="c306c-128">Configuring Local Host Settings (AS2)</span></span>](../core/configuring-local-host-settings-as2.md)