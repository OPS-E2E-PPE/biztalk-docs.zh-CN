---
title: 配置标识符 (X12) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 665698d1-c46c-4149-9715-381b4966dd92
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc9b4b5a6b2632c797ff655899b118536dbdde4e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003078"
---
# <a name="configuring-identifiers-x12"></a><span data-ttu-id="8e1ac-102">配置标识符 (X12)</span><span class="sxs-lookup"><span data-stu-id="8e1ac-102">Configuring Identifiers (X12)</span></span>
<span data-ttu-id="8e1ac-103">在合作伙伴协议中，你必须设置 X12 授权和安全属性，以确认交换不被通过接收未经授权的收件人。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-103">In the partner agreement, you must set the X12 authorization and security properties in order to verify that the interchange is not being received by unauthorized recipients.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8e1ac-104">此处所述的交换处理属性也适用于 HIPAA 交换。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-104">The interchange processing properties described here apply also to HIPAA interchanges.</span></span>  
> 
> [!IMPORTANT]
>  <span data-ttu-id="8e1ac-105">以下属性禁用此页上，如果您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-105">The following properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
> 
> - <span data-ttu-id="8e1ac-106">**DestinationPartyName**下**其他协议解析程序**部分。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-106">**DestinationPartyName** under **Additional Agreement Resolvers** section.</span></span>  
> 
>   <span data-ttu-id="8e1ac-107">仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-107">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="8e1ac-108">例如，如果创建两个参与方 Party A 和参与方 B，并且对于参与方 A 清除该复选框，上述列表中的属性上禁用**参与方 A-> 参与方 B**单向协议选项卡。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-108">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8e1ac-109">必要條件</span><span class="sxs-lookup"><span data-stu-id="8e1ac-109">Prerequisites</span></span>  
 <span data-ttu-id="8e1ac-110">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-110">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-set-sender-receiver-and-security-properties"></a><span data-ttu-id="8e1ac-111">设置发送方、接收方和安全属性</span><span class="sxs-lookup"><span data-stu-id="8e1ac-111">To set sender, receiver, and security properties</span></span>  
  
1. <span data-ttu-id="8e1ac-112">创建 X12 编码协议，如中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-112">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="8e1ac-113">若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-113">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2. <span data-ttu-id="8e1ac-114">在单向协议选项卡下**交换设置**部分中，单击**标识符**。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-114">On a one-way agreement tab, under **Interchange Settings** section, click **Identifiers**.</span></span>  
  
3. <span data-ttu-id="8e1ac-115">输入值**ISA1-2 （授权限定符和信息）**。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-115">Enter values for the **ISA1-2 (Authorization qualifier and information)**.</span></span> <span data-ttu-id="8e1ac-116">选择的值**授权限定符 (ISA1)** 从关联的下拉列表。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-116">Select the value for the **Authorization qualifier (ISA1)** from the associated drop-down list.</span></span> <span data-ttu-id="8e1ac-117">如果此值不是**00**，对于**值 (ISA2)** 文字框中，输入一个字母数字字符的最小值和最多 10 个。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-117">If this value is other than **00**, for the **Value (ISA2)** text box, enter a minimum of one alphanumeric character and a maximum of 10.</span></span> <span data-ttu-id="8e1ac-118">此字段为可选字段。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-118">This is an optional field.</span></span> <span data-ttu-id="8e1ac-119">如果您确实要指定这些值，请确保它们与接收的交换中的 ISA1 和 ISA2 字段相匹配，否则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将挂起交换。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-119">If you do specify these values, make sure they match the ISA1 and ISA2 fields in a received interchange otherwise [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will suspend the interchange.</span></span>  
  
4. <span data-ttu-id="8e1ac-120">输入值**ISA3-4 （安全限定符和信息）**。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-120">Enter values for the **ISA3-4 (Security qualifier and information)**.</span></span> <span data-ttu-id="8e1ac-121">选择的值**安全限定符 (ISA3)** 从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-121">Select the value for the **Security qualifier (ISA3)** from the drop-down list.</span></span> <span data-ttu-id="8e1ac-122">如果此值不是**00**，对于**值 (ISA4)** 文字框中，输入一个字母数字值的最小值和最多 10 个。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-122">If this value is other than **00**, for the **Value (ISA4)** text box, enter a minimum of one alphanumeric value and a maximum of 10.</span></span> <span data-ttu-id="8e1ac-123">此字段为可选字段。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-123">This is an optional field.</span></span> <span data-ttu-id="8e1ac-124">如果这些值与所接收交换中的 ISA3 和 ISA4 字段不匹配，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将挂起该交换。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-124">If these values do not match the ISA3 and ISA4 fields in a received interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will suspend the interchange.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="8e1ac-125">值**03 – 密码 （用于向后兼容性）**，是为了向后兼容包含[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]和将在未来版本中删除。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-125">The value **03 – Password (for backward compatibility)**, is included for backward compatibility with [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] and will be removed in future versions.</span></span>  
  
5. <span data-ttu-id="8e1ac-126">输入的值**ISA5-6 （发送方限定符和标识符）**。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-126">Enter the values for **ISA5-6 (Sender qualifier and identifier)**.</span></span> <span data-ttu-id="8e1ac-127">选择从限定符的值**发件人 Id 限定符 (ISA5)** 下拉列表。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-127">Select a value for the qualifier from the **Sender Id Qualifier (ISA5)** drop-down list.</span></span> <span data-ttu-id="8e1ac-128">对于标识符，在**值 (ISA6)** 文字框中，输入最少一个字母数字字符、 最多包含 15 个字符。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-128">For the identifier, in the **Value (ISA6)** text box, enter a minimum of one alphanumeric character and a maximum of 15 characters.</span></span>  
  
6. <span data-ttu-id="8e1ac-129">输入的值**ISA7-8 （接收方限定符和标识符）**。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-129">Enter the values for **ISA7-8 (Receiver qualifier and identifier)**.</span></span> <span data-ttu-id="8e1ac-130">选择从限定符的值**发件人 Id 限定符 (ISA7)** 下拉列表。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-130">Select a value for the qualifier from the **Sender Id Qualifier (ISA7)** drop-down list.</span></span> <span data-ttu-id="8e1ac-131">对于标识符，在**值 (ISA8)** 文字框中，输入最少一个字母数字字符、 最多包含 15 个字符。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-131">For the identifier, in the **Value (ISA8)** text box, enter a minimum of one alphanumeric character and a maximum of 15 characters.</span></span>  
  
7. <span data-ttu-id="8e1ac-132">在中**其他协议解析程序**部分中，对于**DestinationPartyName**属性，为目标参与方指定一个值。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-132">In the **Additional Agreement Resolvers** section, for **DestinationPartyName** property, specify a value for the destination party.</span></span> <span data-ttu-id="8e1ac-133">此值还用于向协议解析出站消息。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-133">This value is also used to resolve outbound messages to an agreement.</span></span> <span data-ttu-id="8e1ac-134">有关详细信息，请参阅[协议解析和架构确定传出 EDI 消息的](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-134">For more information see, [Agreement Resolution and Schema Determination for Outgoing EDI Messages](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="8e1ac-135">通常不需要设置**DestinationPartyName**属性。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-135">You typically do not need to set the **DestinationPartyName** property.</span></span> <span data-ttu-id="8e1ac-136">此属性用作协议属性的一部分，以支持升级方案。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-136">This property is available as part of the agreement properties to support upgrade scenarios.</span></span> <span data-ttu-id="8e1ac-137">从 BizTalk Server 2006 R2 或 BizTalk Server 2009 升级时**DestinationPartyName**属性设置为在 BizTalk Server 2006 R2 或 BizTalk Server 2009 中参与方的名称。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-137">When upgrading from BizTalk Server 2006 R2 or BizTalk Server 2009, the **DestinationPartyName** property is set to the name of the party in BizTalk Server 2006 R2 or BizTalk Server 2009.</span></span>  
  
8. <span data-ttu-id="8e1ac-138">单击**Apply**以接受更改，或单击**确定**以输入和验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-138">Click **Apply** to accept the changes, or click **OK** to enter and validate the changes, and then close the dialog box.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="8e1ac-139">如果单击**确定**或**应用**在此阶段，会收到错误。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-139">If you click **OK** or **Apply** at this stage, you will get an error.</span></span> <span data-ttu-id="8e1ac-140">这是因为你仍需要提供 ISA5 到 ISA8 值上**标识符**其他单向协议选项卡的选项卡。</span><span class="sxs-lookup"><span data-stu-id="8e1ac-140">That is because you still need to provide ISA5 to ISA8 values on the **Identifiers** tab for the other one-way agreement tab.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e1ac-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="8e1ac-141">See Also</span></span>  
 [<span data-ttu-id="8e1ac-142">配置交换设置 (X12)</span><span class="sxs-lookup"><span data-stu-id="8e1ac-142">Configuring Interchange Settings (X12)</span></span>](../core/configuring-interchange-settings-x12.md)