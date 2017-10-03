---
title: "配置回退标识符 (EDIFACT) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2ce56c1-44f1-42dc-94e8-36e5ba664f53
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81ddf25726d7413727fef1f4f41d99916c18c21d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fallback-identifiers-edifact"></a><span data-ttu-id="b5e1e-102">配置回退标识符 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="b5e1e-102">Configuring Fallback Identifiers (EDIFACT)</span></span>
<span data-ttu-id="b5e1e-103">在后备协议中，必须设置收件人引用密码，以确认交换不会被未经授权的收件人接收。</span><span class="sxs-lookup"><span data-stu-id="b5e1e-103">In the fallback agreement, you must set the recipient reference password, in order to verify that the interchange is not being received by unauthorized recipients.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b5e1e-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="b5e1e-104">Prerequisites</span></span>  
 <span data-ttu-id="b5e1e-105">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="b5e1e-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-set-the-sender-recipient-recipient-password"></a><span data-ttu-id="b5e1e-106">设置发件人、收件人、收件人密码</span><span class="sxs-lookup"><span data-stu-id="b5e1e-106">To set the sender, recipient, recipient password</span></span>  
  
1.  <span data-ttu-id="b5e1e-107">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**EDIFACT 回退设置**。</span><span class="sxs-lookup"><span data-stu-id="b5e1e-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **EDIFACT Fallback Settings**.</span></span>  
  
2.  <span data-ttu-id="b5e1e-108">在**EDIFACT 回退设置**对话框中，在**EDIFACT 协议页**选项卡上，在**交换设置**部分中，单击**标识符**.</span><span class="sxs-lookup"><span data-stu-id="b5e1e-108">In the **EDIFACT Fallback Settings** dialog box, in the **EDIFACT Agreement Pages** tab, under the **Interchange Settings** section, click **Identifiers**.</span></span>  
  
3.  <span data-ttu-id="b5e1e-109">在**发件人 (UNB2)**部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b5e1e-109">In the **Sender (UNB2)** section, do the following:</span></span>  
  
    1.  <span data-ttu-id="b5e1e-110">有关**标识 (UNB2.1)**，输入一个最小值和最多 35 个字母数字值。</span><span class="sxs-lookup"><span data-stu-id="b5e1e-110">For **Identification (UNB2.1)**, enter an alphanumeric value with a minimum of one and a maximum of 35.</span></span> <span data-ttu-id="b5e1e-111">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="b5e1e-111">This is a required field.</span></span>  
  
    2.  <span data-ttu-id="b5e1e-112">有关**代码限定符 (UNB2.2)**，从下拉列表中选择一个值。</span><span class="sxs-lookup"><span data-stu-id="b5e1e-112">For **Code qualifier (UNB2.2)**, select a value from the drop-down list.</span></span> <span data-ttu-id="b5e1e-113">此字段为可选字段。</span><span class="sxs-lookup"><span data-stu-id="b5e1e-113">This is an optional field.</span></span>  
  
    3.  <span data-ttu-id="b5e1e-114">有关**反向路由地址 (UNB2.3)**，输入一个字母数字值，该值最少包含一个字符，最多包含 14 个字符。</span><span class="sxs-lookup"><span data-stu-id="b5e1e-114">For **Reverse routing address (UNB2.3)**, enter an alphanumeric value with a minimum of one character and a maximum of 14 characters.</span></span> <span data-ttu-id="b5e1e-115">此字段为可选字段。</span><span class="sxs-lookup"><span data-stu-id="b5e1e-115">This is an optional field.</span></span>  
  
    4.  <span data-ttu-id="b5e1e-116">有关**应用程序引用 ID (UNB7)**，输入一个字母数字值，该值最少包含一个字符，最多六个字符。</span><span class="sxs-lookup"><span data-stu-id="b5e1e-116">For **Application reference ID (UNB7)**, enter an alphanumeric value with a minimum of one character and a maximum of six characters.</span></span> <span data-ttu-id="b5e1e-117">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="b5e1e-117">This is a required field.</span></span>  
  
4.  <span data-ttu-id="b5e1e-118">在**收件人 (UNB3)**部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b5e1e-118">In the **Recipient (UNB3)** section, do the following:</span></span>  
  
    1.  <span data-ttu-id="b5e1e-119">有关**标识 (UNB3.1)**，输入一个最小值和最多 35 个字母数字值。</span><span class="sxs-lookup"><span data-stu-id="b5e1e-119">For **Identification (UNB3.1)**, enter an alphanumeric value with a minimum of one and a maximum of 35.</span></span> <span data-ttu-id="b5e1e-120">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="b5e1e-120">This is a required field.</span></span>  
  
    2.  <span data-ttu-id="b5e1e-121">有关**代码限定符 (UNB3.2)**，从下拉列表中选择一个值。</span><span class="sxs-lookup"><span data-stu-id="b5e1e-121">For **Code qualifier (UNB3.2)**, select a value from the drop-down list.</span></span> <span data-ttu-id="b5e1e-122">此字段为可选字段。</span><span class="sxs-lookup"><span data-stu-id="b5e1e-122">This is an optional field.</span></span>  
  
    3.  <span data-ttu-id="b5e1e-123">有关**反向路由地址 (UNB3.3)**，输入一个字母数字值，该值最少包含一个字符，最多包含 14 个字符。</span><span class="sxs-lookup"><span data-stu-id="b5e1e-123">For **Reverse routing address (UNB3.3)**, enter an alphanumeric value with a minimum of one character and a maximum of 14 characters.</span></span> <span data-ttu-id="b5e1e-124">此字段为可选字段。</span><span class="sxs-lookup"><span data-stu-id="b5e1e-124">This is an optional field.</span></span>  
  
    4.  <span data-ttu-id="b5e1e-125">如果需要，在**收件人引用密码 (UNB6)**部分中，输入收件人引用密码值。</span><span class="sxs-lookup"><span data-stu-id="b5e1e-125">If required, in the **Recipient reference password (UNB6)** section, enter values for the recipient reference password.</span></span> <span data-ttu-id="b5e1e-126">有关**值 (UNB6.1)**，输入一个最小值和最多 14 个字母数字值。</span><span class="sxs-lookup"><span data-stu-id="b5e1e-126">For **Value (UNB6.1)**, enter an alphanumeric value with a minimum of one and a maximum of 14.</span></span> <span data-ttu-id="b5e1e-127">有关**限定符 (UNB6.2)**，输入最少包含一个字符，最多两个字符的一个字母数字值。</span><span class="sxs-lookup"><span data-stu-id="b5e1e-127">For **Qualifier (UNB6.2)**, enter an alphanumeric value with a minimum of one character and a maximum of two characters.</span></span> <span data-ttu-id="b5e1e-128">这些是可选字段。</span><span class="sxs-lookup"><span data-stu-id="b5e1e-128">These are optional fields.</span></span> <span data-ttu-id="b5e1e-129">如果这些值与所接收交换中的 UNB6.1 和 UNB6.2 字段不匹配，BizTalk Server 将挂起该交换。</span><span class="sxs-lookup"><span data-stu-id="b5e1e-129">If these values do not match the UNB6.1 and UNB6.2 fields in a received interchange, BizTalk Server will suspend the interchange.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="b5e1e-130">组合**UNB6.1**和**UNB6.2**必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="b5e1e-130">The combination of **UNB6.1** and **UNB6.2** must be unique.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="b5e1e-131">如果同时为 UNB6.1 和 UNB6.2 输入值，应用更改，然后取消 UNB6.1，则 UNB6.2 中的值也将被删除，而且该字段将被禁用。</span><span class="sxs-lookup"><span data-stu-id="b5e1e-131">If you enter values for both UNB6.1 and UNB6.2, apply the changes and then blank out UNB6.1, the value in UNB6.2 will also be deleted and the field will be disabled.</span></span>  
  
5.  <span data-ttu-id="b5e1e-132">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="b5e1e-132">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5e1e-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b5e1e-133">See Also</span></span>  
 [<span data-ttu-id="b5e1e-134">为交换处理配置 EDIFACT 回退协议属性</span><span class="sxs-lookup"><span data-stu-id="b5e1e-134">Configuring EDIFACT Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)