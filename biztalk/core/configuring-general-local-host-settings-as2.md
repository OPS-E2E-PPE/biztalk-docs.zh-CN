---
title: 配置常规本地主机设置 (AS2) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 980daac2-8387-44cc-ae55-38639f759668
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b990a44c9599ff725bdd19f7bfdd8286ec11487d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391113"
---
# <a name="configuring-general-local-host-settings-as2"></a><span data-ttu-id="862b9-102">配置常规本地主机设置 (AS2)</span><span class="sxs-lookup"><span data-stu-id="862b9-102">Configuring General Local Host Settings (AS2)</span></span>
<span data-ttu-id="862b9-103">作为本地主机常规设置的一部分，可以指定是否作为 AS2 消息标头的一部分保留的文件的名称和 AS2 消息的内容类型。</span><span class="sxs-lookup"><span data-stu-id="862b9-103">As part of the local host general settings, you can specify the content type of the AS2 messages and whether the file name is preserved as part of the AS2 message header.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="862b9-104">如果你清除了所有属性会都禁用此页上**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="862b9-104">All the properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  <span data-ttu-id="862b9-105">仅在与参与方所发送交换的属性相对应的单向协议选项卡上禁用这些属性。</span><span class="sxs-lookup"><span data-stu-id="862b9-105">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="862b9-106">例如，如果创建两个参与方 Party A 和参与方 B，并且对于参与方 A 清除该复选框，上述列表中的属性上禁用**参与方 A-> 参与方 B**单向协议选项卡。</span><span class="sxs-lookup"><span data-stu-id="862b9-106">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="862b9-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="862b9-107">Prerequisites</span></span>  
 <span data-ttu-id="862b9-108">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="862b9-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-the-general-settings"></a><span data-ttu-id="862b9-109">若要配置常规设置</span><span class="sxs-lookup"><span data-stu-id="862b9-109">To configure the general settings</span></span>  
  
1.  <span data-ttu-id="862b9-110">创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。</span><span class="sxs-lookup"><span data-stu-id="862b9-110">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="862b9-111">若要更新现有 AS2 协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="862b9-111">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="862b9-112">在单向协议选项卡下**本地主机设置**部分中，单击**常规**。</span><span class="sxs-lookup"><span data-stu-id="862b9-112">On a one-way agreement tab, under **Local Host Settings** section, click **General**.</span></span>  
  
3.  <span data-ttu-id="862b9-113">选择**发送消息之前检查证书吊销列表**复选框，以确定是否已在证书吊销列表中，包含要在签名传出消息中使用的证书，该值指示它已被吊销，或是否超过到期日期。</span><span class="sxs-lookup"><span data-stu-id="862b9-113">Select the **Check Certification Revocation List before sending the message** check box to determine whether the certificate to be used in signing an outgoing messages has been included in the Certification Revocation List, indicating that it has been revoked, or whether the expiration date has passed.</span></span> <span data-ttu-id="862b9-114">如果是这样，BizTalk Server 不会加密消息，但将挂起消息。</span><span class="sxs-lookup"><span data-stu-id="862b9-114">If so, BizTalk Server will not encrypt the message, but will suspend it.</span></span> <span data-ttu-id="862b9-115">如果清除此属性，则 BizTalk Server 将不执行此检查。</span><span class="sxs-lookup"><span data-stu-id="862b9-115">If this property is cleared, BizTalk Server will not perform this check.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="862b9-116">检索和搜索证书吊销列表所涉及的是延迟。</span><span class="sxs-lookup"><span data-stu-id="862b9-116">There is a latency involved with retrieving and searching the certificate revocation list.</span></span>  
  
4.  <span data-ttu-id="862b9-117">有关**默认内容类型**，选择参与方必须用于传出 AS2 消息的默认内容类型。</span><span class="sxs-lookup"><span data-stu-id="862b9-117">For **Default content type**, select the default content type that the party must use for an outgoing AS2 message.</span></span> <span data-ttu-id="862b9-118">如果`ContentType`属性设置的上下文中为消息正文部分，设置是用于生成传出消息; 否则为此设置的值**默认内容类型**使用属性。</span><span class="sxs-lookup"><span data-stu-id="862b9-118">If the `ContentType` property is set in the context for a message body part, that setting is used to generate the outgoing message; otherwise, the value of this **Default content type** property is used.</span></span>  
  
5.  <span data-ttu-id="862b9-119">选择**MIME 标头中的传输文件名**复选框以将文件名作为出站 AS2 消息的 MIME 标头的一部分发送。</span><span class="sxs-lookup"><span data-stu-id="862b9-119">Select the **Transmit file name in MIME header** check box to send a file name as part of the MIME header for the outbound AS2 message.</span></span> <span data-ttu-id="862b9-120">若要指定的文件的名称，选择**指定的文件名**或**让系统生成文件名**。</span><span class="sxs-lookup"><span data-stu-id="862b9-120">To specify the file name, select **Specify file name** or **Have system generate file name**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="862b9-121">选择**让系统生成文件名**将作为 AS2 消息中发送每个附件的文件名生成新的 GUID 值。</span><span class="sxs-lookup"><span data-stu-id="862b9-121">Selecting **Have system generate file name** will generate a new GUID value as the file name of each attachment sent in the AS2 message.</span></span>  
  
6.  <span data-ttu-id="862b9-122">如果所选**指定的文件名**，输入中的字符串值或上下文属性**指定文件名**字段。</span><span class="sxs-lookup"><span data-stu-id="862b9-122">If you selected **Specify file name**, enter a string value or context property in the **Specify file name** field.</span></span> <span data-ttu-id="862b9-123">您还可以启用**挂起消息上下文属性 （例如 %property%)找不到**以挂起消息，如果所选的上下文属性不存在对出站消息。</span><span class="sxs-lookup"><span data-stu-id="862b9-123">You can also enable **Suspend message if context property (e.g. %property%) not found** to suspend the message if the selected context property does not exist for the outbound message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="862b9-124">若要指定的上下文属性，请将 %字符的属性名称。</span><span class="sxs-lookup"><span data-stu-id="862b9-124">To specify a context-property, enclose the property name with the % character.</span></span> <span data-ttu-id="862b9-125">例如，`%FILE.ReceivedFileName%`。</span><span class="sxs-lookup"><span data-stu-id="862b9-125">For example, `%FILE.ReceivedFileName%`.</span></span>  
  
7.  <span data-ttu-id="862b9-126">单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="862b9-126">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="862b9-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="862b9-127">See Also</span></span>  
 [<span data-ttu-id="862b9-128">配置本地主机设置 (AS2)</span><span class="sxs-lookup"><span data-stu-id="862b9-128">Configuring Local Host Settings (AS2)</span></span>](../core/configuring-local-host-settings-as2.md)