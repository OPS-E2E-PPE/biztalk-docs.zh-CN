---
title: 配置标识符 (EDIFACT) |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 097292f2-1aa5-42e4-aeee-c7d4cbdae17c
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 673501923385c956169670eb1dc61e667e611734
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233845"
---
# <a name="configuring-identifiers-edifact"></a><span data-ttu-id="442a4-102">配置标识符 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="442a4-102">Configuring Identifiers (EDIFACT)</span></span>
<span data-ttu-id="442a4-103">在合作伙伴协议中，必须设置收件人引用密码，以确认交换不会被未经授权的收件人接收。</span><span class="sxs-lookup"><span data-stu-id="442a4-103">In the partner agreement, you must set the recipient reference password, in order to verify that the interchange is not being received by unauthorized recipients.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="442a4-104">以下属性禁用此页上，如果你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="442a4-104">The following properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  -   <span data-ttu-id="442a4-105">**DestinationPartyName**下**其他协议冲突解决程序**部分。</span><span class="sxs-lookup"><span data-stu-id="442a4-105">**DestinationPartyName** under **Additional Agreement Resolvers** section.</span></span>  
>   
>  <span data-ttu-id="442a4-106">仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。</span><span class="sxs-lookup"><span data-stu-id="442a4-106">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="442a4-107">例如，如果创建两个参与方 A 方和方 B 和 A 的当事方，清除复选框，则上面的属性列表会禁用上**A 方-> 方 B**单向协议选项卡。</span><span class="sxs-lookup"><span data-stu-id="442a4-107">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="442a4-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="442a4-108">Prerequisites</span></span>  
 <span data-ttu-id="442a4-109">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="442a4-109">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-set-the-sender-recipient-and-recipient-password"></a><span data-ttu-id="442a4-110">若要设置收件人的密码，发送方和接收方</span><span class="sxs-lookup"><span data-stu-id="442a4-110">To set the sender, recipient, and recipient password</span></span>  
  
1.  <span data-ttu-id="442a4-111">创建 EDIFACT 编码协议中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。</span><span class="sxs-lookup"><span data-stu-id="442a4-111">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="442a4-112">若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="442a4-112">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="442a4-113">单向协议选项卡上，在**交换设置**部分中，单击**标识符**。</span><span class="sxs-lookup"><span data-stu-id="442a4-113">On a one-way agreement tab, under **Interchange Settings** section, click **Identifiers**.</span></span>  
  
3.  <span data-ttu-id="442a4-114">在**发件人 (UNB2)** 部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="442a4-114">In the **Sender (UNB2)** section, do the following:</span></span>  
  
    1.  <span data-ttu-id="442a4-115">有关**标识 (UNB2.1)**，输入一个最小值和最多 35 个字母数字值。</span><span class="sxs-lookup"><span data-stu-id="442a4-115">For **Identification (UNB2.1)**, enter an alphanumeric value with a minimum of one and a maximum of 35.</span></span> <span data-ttu-id="442a4-116">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="442a4-116">This is a required field.</span></span>  
  
    2.  <span data-ttu-id="442a4-117">有关**代码限定符 (UNB2.2)**，从下拉列表中选择一个值。</span><span class="sxs-lookup"><span data-stu-id="442a4-117">For **Code qualifier (UNB2.2)**, select a value from the drop-down list.</span></span> <span data-ttu-id="442a4-118">此字段为可选字段。</span><span class="sxs-lookup"><span data-stu-id="442a4-118">This is an optional field.</span></span>  
  
    3.  <span data-ttu-id="442a4-119">有关**反向路由地址 (UNB2.3)**，输入一个字母数字值，该值最少包含一个字符，最多包含 14 个字符。</span><span class="sxs-lookup"><span data-stu-id="442a4-119">For **Reverse routing address (UNB2.3)**, enter an alphanumeric value with a minimum of one character and a maximum of 14 characters.</span></span> <span data-ttu-id="442a4-120">此字段为可选字段。</span><span class="sxs-lookup"><span data-stu-id="442a4-120">This is an optional field.</span></span>  
  
4.  <span data-ttu-id="442a4-121">在**收件人 (UNB3)** 部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="442a4-121">In the **Recipient (UNB3)** section, do the following:</span></span>  
  
    1.  <span data-ttu-id="442a4-122">有关**标识 (UNB3.1)**，输入一个最小值和最多 35 个字母数字值。</span><span class="sxs-lookup"><span data-stu-id="442a4-122">For **Identification (UNB3.1)**, enter an alphanumeric value with a minimum of one and a maximum of 35.</span></span> <span data-ttu-id="442a4-123">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="442a4-123">This is a required field.</span></span>  
  
    2.  <span data-ttu-id="442a4-124">有关**代码限定符 (UNB3.2)**，从下拉列表中选择一个值。</span><span class="sxs-lookup"><span data-stu-id="442a4-124">For **Code qualifier (UNB3.2)**, select a value from the drop-down list.</span></span> <span data-ttu-id="442a4-125">此字段为可选字段。</span><span class="sxs-lookup"><span data-stu-id="442a4-125">This is an optional field.</span></span>  
  
    3.  <span data-ttu-id="442a4-126">有关**反向路由地址 (UNB3.3)**，输入一个字母数字值，该值最少包含一个字符，最多包含 14 个字符。</span><span class="sxs-lookup"><span data-stu-id="442a4-126">For **Reverse routing address (UNB3.3)**, enter an alphanumeric value with a minimum of one character and a maximum of 14 characters.</span></span> <span data-ttu-id="442a4-127">此字段为可选字段。</span><span class="sxs-lookup"><span data-stu-id="442a4-127">This is an optional field.</span></span>  
  
    4.  <span data-ttu-id="442a4-128">如果需要，在**收件人引用密码 (UNB6)** 部分中，输入收件人引用密码值。</span><span class="sxs-lookup"><span data-stu-id="442a4-128">If required, in the **Recipient reference password (UNB6)** section, enter values for the recipient reference password.</span></span> <span data-ttu-id="442a4-129">有关**值 (UNB6.1)**，输入一个最小值和最多 14 个字母数字值。</span><span class="sxs-lookup"><span data-stu-id="442a4-129">For **Value (UNB6.1)**, enter an alphanumeric value with a minimum of one and a maximum of 14.</span></span> <span data-ttu-id="442a4-130">有关**限定符 (UNB6.2)**，输入最少包含一个字符，最多两个字符的一个字母数字值。</span><span class="sxs-lookup"><span data-stu-id="442a4-130">For **Qualifier (UNB6.2)**, enter an alphanumeric value with a minimum of one character and a maximum of two characters.</span></span> <span data-ttu-id="442a4-131">这些是可选字段。</span><span class="sxs-lookup"><span data-stu-id="442a4-131">These are optional fields.</span></span> <span data-ttu-id="442a4-132">如果这些值与所接收交换中的 UNB6.1 和 UNB6.2 字段不匹配，BizTalk Server 将挂起该交换。</span><span class="sxs-lookup"><span data-stu-id="442a4-132">If these values do not match the UNB6.1 and UNB6.2 fields in a received interchange, BizTalk Server will suspend the interchange.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="442a4-133">组合**UNB6.1**和**UNB6.2**必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="442a4-133">The combination of **UNB6.1** and **UNB6.2** must be unique.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="442a4-134">如果同时为 UNB6.1 和 UNB6.2 输入值，应用更改，然后取消 UNB6.1，则 UNB6.2 中的值也将被删除，而且该字段将被禁用。</span><span class="sxs-lookup"><span data-stu-id="442a4-134">If you enter values for both UNB6.1 and UNB6.2, apply the changes and then blank out UNB6.1, the value in UNB6.2 will also be deleted and the field will be disabled.</span></span>  
  
5.  <span data-ttu-id="442a4-135">在**其他协议冲突解决程序**部分中，为**DestinationPartyName**属性，为目标方指定一个值。</span><span class="sxs-lookup"><span data-stu-id="442a4-135">In the **Additional Agreement Resolvers** section, for **DestinationPartyName** property, specify a value for the destination party.</span></span> <span data-ttu-id="442a4-136">此值还用于向协议解析出站消息。</span><span class="sxs-lookup"><span data-stu-id="442a4-136">This value is also used to resolve outbound messages to an agreement.</span></span> <span data-ttu-id="442a4-137">有关详细信息，请参阅[协议解析和传出的 EDI 消息的架构确定](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="442a4-137">For more information see, [Agreement Resolution and Schema Determination for Outgoing EDI Messages](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="442a4-138">通常不需要设置**DestinationPartyName**属性。</span><span class="sxs-lookup"><span data-stu-id="442a4-138">You typically do not need to set the **DestinationPartyName** property.</span></span> <span data-ttu-id="442a4-139">此属性用作协议属性的一部分，以支持升级方案。</span><span class="sxs-lookup"><span data-stu-id="442a4-139">This property is available as part of the agreement properties to support upgrade scenarios.</span></span> <span data-ttu-id="442a4-140">从 BizTalk Server 2006 R2 或 BizTalk Server 2009 升级时**DestinationPartyName**属性设置为在 BizTalk Server 2006 R2 或 BizTalk Server 2009 方的名称。</span><span class="sxs-lookup"><span data-stu-id="442a4-140">When upgrading from BizTalk Server 2006 R2 or BizTalk Server 2009, the **DestinationPartyName** property is set to the name of the party in BizTalk Server 2006 R2 or BizTalk Server 2009.</span></span>  
  
6.  <span data-ttu-id="442a4-141">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="442a4-141">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="442a4-142">如果你单击**确定**或**应用**在此阶段，你将收到错误。</span><span class="sxs-lookup"><span data-stu-id="442a4-142">If you click **OK** or **Apply** at this stage, you will get an error.</span></span> <span data-ttu-id="442a4-143">这是因为你仍需要提供上 UNB2 和 UNB3 值**标识符**其他单向协议选项卡的选项卡。</span><span class="sxs-lookup"><span data-stu-id="442a4-143">That is because you still need to provide UNB2 and UNB3 values on the **Identifiers** tab for the other one-way agreement tab.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="442a4-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="442a4-144">See Also</span></span>  
 [<span data-ttu-id="442a4-145">配置交换设置 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="442a4-145">Configuring Interchange Settings (EDIFACT)</span></span>](../core/configuring-interchange-settings-edifact.md)