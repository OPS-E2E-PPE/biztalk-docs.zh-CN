---
title: 配置回退标识符 (EDIFACT) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2ce56c1-44f1-42dc-94e8-36e5ba664f53
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b3e52be4985b1c28c8214b6db558c14f9ffaa7b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355660"
---
# <a name="configuring-fallback-identifiers-edifact"></a><span data-ttu-id="878b1-102">配置回退标识符 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="878b1-102">Configuring Fallback Identifiers (EDIFACT)</span></span>
<span data-ttu-id="878b1-103">在后备协议中，必须设置收件人引用密码，以确认交换不被未经授权的收件人接收。</span><span class="sxs-lookup"><span data-stu-id="878b1-103">In the fallback agreement, you must set the recipient reference password, in order to verify that the interchange is not being received by unauthorized recipients.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="878b1-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="878b1-104">Prerequisites</span></span>  
 <span data-ttu-id="878b1-105">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="878b1-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-set-the-sender-recipient-recipient-password"></a><span data-ttu-id="878b1-106">若要设置发件人、 收件人、 收件人密码</span><span class="sxs-lookup"><span data-stu-id="878b1-106">To set the sender, recipient, recipient password</span></span>  
  
1. <span data-ttu-id="878b1-107">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**EDIFACT 后备设置**。</span><span class="sxs-lookup"><span data-stu-id="878b1-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **EDIFACT Fallback Settings**.</span></span>  
  
2. <span data-ttu-id="878b1-108">在中**EDIFACT 后备设置**对话框中**EDIFACT 协议页**选项卡上，在**交换设置**部分中，单击**标识符**.</span><span class="sxs-lookup"><span data-stu-id="878b1-108">In the **EDIFACT Fallback Settings** dialog box, in the **EDIFACT Agreement Pages** tab, under the **Interchange Settings** section, click **Identifiers**.</span></span>  
  
3. <span data-ttu-id="878b1-109">在中**发件人 (UNB2)** 部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="878b1-109">In the **Sender (UNB2)** section, do the following:</span></span>  
  
   1.  <span data-ttu-id="878b1-110">有关**标识 (UNB2.1)**，输入一个最小值和最多为 35 的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="878b1-110">For **Identification (UNB2.1)**, enter an alphanumeric value with a minimum of one and a maximum of 35.</span></span> <span data-ttu-id="878b1-111">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="878b1-111">This is a required field.</span></span>  
  
   2.  <span data-ttu-id="878b1-112">有关**代码限定符 (UNB2.2)**，从下拉列表中选择一个值。</span><span class="sxs-lookup"><span data-stu-id="878b1-112">For **Code qualifier (UNB2.2)**, select a value from the drop-down list.</span></span> <span data-ttu-id="878b1-113">这是一个可选字段。</span><span class="sxs-lookup"><span data-stu-id="878b1-113">This is an optional field.</span></span>  
  
   3.  <span data-ttu-id="878b1-114">有关**反向路由地址 (UNB2.3)**，输入包含最少一个字符，最多为 14 个字符的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="878b1-114">For **Reverse routing address (UNB2.3)**, enter an alphanumeric value with a minimum of one character and a maximum of 14 characters.</span></span> <span data-ttu-id="878b1-115">这是一个可选字段。</span><span class="sxs-lookup"><span data-stu-id="878b1-115">This is an optional field.</span></span>  
  
   4.  <span data-ttu-id="878b1-116">有关**应用程序引用 ID (UNB7)**，输入包含最少一个字符，最多为 6 个字符的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="878b1-116">For **Application reference ID (UNB7)**, enter an alphanumeric value with a minimum of one character and a maximum of six characters.</span></span> <span data-ttu-id="878b1-117">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="878b1-117">This is a required field.</span></span>  
  
4. <span data-ttu-id="878b1-118">在中**收件人 (UNB3)** 部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="878b1-118">In the **Recipient (UNB3)** section, do the following:</span></span>  
  
   1.  <span data-ttu-id="878b1-119">有关**标识 (UNB3.1)**，输入一个最小值和最多为 35 的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="878b1-119">For **Identification (UNB3.1)**, enter an alphanumeric value with a minimum of one and a maximum of 35.</span></span> <span data-ttu-id="878b1-120">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="878b1-120">This is a required field.</span></span>  
  
   2.  <span data-ttu-id="878b1-121">有关**代码限定符 (UNB3.2)**，从下拉列表中选择一个值。</span><span class="sxs-lookup"><span data-stu-id="878b1-121">For **Code qualifier (UNB3.2)**, select a value from the drop-down list.</span></span> <span data-ttu-id="878b1-122">这是一个可选字段。</span><span class="sxs-lookup"><span data-stu-id="878b1-122">This is an optional field.</span></span>  
  
   3.  <span data-ttu-id="878b1-123">有关**反向路由地址 (UNB3.3)**，输入包含最少一个字符，最多为 14 个字符的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="878b1-123">For **Reverse routing address (UNB3.3)**, enter an alphanumeric value with a minimum of one character and a maximum of 14 characters.</span></span> <span data-ttu-id="878b1-124">这是一个可选字段。</span><span class="sxs-lookup"><span data-stu-id="878b1-124">This is an optional field.</span></span>  
  
   4.  <span data-ttu-id="878b1-125">如果需要，在**收件人引用密码 (UNB6)** 部分中，输入收件人引用密码的值。</span><span class="sxs-lookup"><span data-stu-id="878b1-125">If required, in the **Recipient reference password (UNB6)** section, enter values for the recipient reference password.</span></span> <span data-ttu-id="878b1-126">有关**值 (UNB6.1)**，输入一个最小值和最多 14 个字母数字值。</span><span class="sxs-lookup"><span data-stu-id="878b1-126">For **Value (UNB6.1)**, enter an alphanumeric value with a minimum of one and a maximum of 14.</span></span> <span data-ttu-id="878b1-127">有关**限定符 (UNB6.2)**，输入包含最少一个字符，最多两个字符的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="878b1-127">For **Qualifier (UNB6.2)**, enter an alphanumeric value with a minimum of one character and a maximum of two characters.</span></span> <span data-ttu-id="878b1-128">这些是可选字段。</span><span class="sxs-lookup"><span data-stu-id="878b1-128">These are optional fields.</span></span> <span data-ttu-id="878b1-129">如果这些值与收到的交换中的 UNB6.1 和 UNB6.2 字段不匹配，BizTalk Server 将挂起该交换。</span><span class="sxs-lookup"><span data-stu-id="878b1-129">If these values do not match the UNB6.1 and UNB6.2 fields in a received interchange, BizTalk Server will suspend the interchange.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="878b1-130">组合**UNB6.1**并**UNB6.2**必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="878b1-130">The combination of **UNB6.1** and **UNB6.2** must be unique.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="878b1-131">如果为 UNB6.1 和 UNB6.2 输入值，应用所做的更改，然后取消 unb6.1，UNB6.2 中的值也将被删除和字段将被禁用。</span><span class="sxs-lookup"><span data-stu-id="878b1-131">If you enter values for both UNB6.1 and UNB6.2, apply the changes and then blank out UNB6.1, the value in UNB6.2 will also be deleted and the field will be disabled.</span></span>  
  
5. <span data-ttu-id="878b1-132">单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="878b1-132">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="878b1-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="878b1-133">See Also</span></span>  
 [<span data-ttu-id="878b1-134">为交换处理配置 EDIFACT 后备协议属性</span><span class="sxs-lookup"><span data-stu-id="878b1-134">Configuring EDIFACT Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)